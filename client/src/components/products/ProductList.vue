<template>
  <div>
    <div class="products">
    
        <product-item :products="products" ></product-item>
    </div>
  </div>
</template>
<style>
.product {
  border-bottom: 1px solid black;
}
.product__image {
  width: 100px;
  height: 100px;
}
</style>
<script>
import ProductItem from './ProductItem.vue';
export default {
  name: 'product-list',
  created() {
    if (this.products.length === 0) {
      this.$store.dispatch('allProducts')}},
  computed: {
    products() {
      return this.$store.getters.allProducts;
    }
  },
  components: {
    'product-item': ProductItem
  }
}
</script>