<template>
  <ul class="catalog__list" >
    <ProductItem :product="product" v-for="(product) in products" :key="product.id"/>
  </ul>
</template>

<script>
import ProductItem from './ProductItem.vue';

export default {
  name: 'ProfuctList',
  props: ['products'],
  components: { ProductItem },
};
</script>

<style>

</style>
