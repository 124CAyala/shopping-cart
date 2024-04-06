<template>
    <div>
      <h1>Catalog</h1>
      <div class="products">
        <div v-for="(product, index) in products" :key="index">
          {{ product.name }}
          <img class="image" :src="product.image" />
          <div>{{ product.cost }}</div>
          <button v-on:click="addItemToCart(product)">Add To Cart</button>
        </div>
      </div>
    </div>
</template>
    
<script>
export default {
   data: () => {
    return {
        products: [
        {
          name: "Yellow",
          cost: "19.99",
          image: 'https://www.americasfinestlabels.com/includes/work/image_cache/0632063c82ed12d8efe8a6e381dee829.thumb.jpg'
        },
        {
          name: "Red",
          cost: "9.99",
          image: 'https://www.americasfinestlabels.com/includes/work/image_cache/4b4f4b63cc837b5f01ce2d718b0f9be2.thumb.jpg'
        },
      ]
    }
   },
   methods: {
    addItemToCart(product) {
        this.$emit('addItemToCart', product)
    }
   } 
}
    
</script>
    
<style>
    
</style>