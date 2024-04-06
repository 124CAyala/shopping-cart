<template>
  <!-- for updating html -->
  <div>

    <header>{{ cart.length }} in cart
      <button v-on:click="navigateTo('cart')"> View Cart </button>
      <button v-on:click="navigateTo('products')"> View Products </button>
    </header>

    <!-- v-if for navigating through app -->
    <div v-if="page === 'cart'">
      <Cart v-on:removeItemFromCart="removeItemFromCart" :cart="cart" />
    </div>
    <!--  -->

    <div v-if="page === 'products'">
      <Products v-on:addItemToCart="addItemToCart" />
    </div>
  </div>
  <!--  -->
</template>

<script>
import Products from './components/Products.vue'
import Cart from './components/Cart.vue'

export default {
  name: "App",
  data: () => {
    return {
      page: "products",
      cart: [],
    }
  },
  methods: {
    addItemToCart(product) {
      this.cart.push(product);
      console.log(this.cart);
    },
    navigateTo(page) {
      this.page = page;
    },
    removeItemFromCart(product) {
      this.cart.splice(this.cart.indexOf(product), 1);
    }
  },
  components: {
    Products,
    Cart
  }
};
</script>


<style>
.products {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.image {
  height: 300px;
  width: 300px;
}
</style>

