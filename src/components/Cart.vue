<template>
    <div>
      <h1>Your Cart</h1>
      <div class="products">
        <div v-for="(product, index) in cart" :key="index">
          {{ product.name }}
          <img class="image" :src="product.image" />
          <div>{{ product.cost }}</div>
          <button v-on:click="removeItemFromCart(product)">Revove From Cart</button>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
        props: [
            "cart"
        ],
        methods: {
            removeItemFromCart(product) {
                this.$emit("removeItemFromCart", product)
            }
        }
    };
</script>

<style scoped>

</style>