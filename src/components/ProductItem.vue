<template>
  <li class="catalog__item" >
      <router-link class="catalog__pic" href="#" :to="{name: 'product', params: {id: product.id}}">
        <img :src="product.image" :alt="product.title">
      </router-link>

      <h3 class="catalog__title">
        <a href="#">
          {{product.title}}
        </a>
      </h3>

      <span class="catalog__price">
        {{product.price | numberFormat}}
      </span>
      <ul class="colors colors--black">
              <li class="colors__item" v-for="color in colors" :key="color.id" >
                <label class="colors__label">
                  <input class="colors__radio sr-only" type="radio"
                  value="color.colorCode" v-model="color.colorCode" >
                  <span class="colors__value"
                  :style="{'background-color': color.colorCode}">
                  </span>
                </label>
              </li>
            </ul>
    </li>
</template>

<script>
import colors from '../data/colors';
import goToPage from '@/helpers/goToPage';
import numberFormat from '@/helpers/numberFormat';

export default {
  name: 'ProdictItem',
  props: ['product'],
  data() {
    return {
      color: '#73B6EA',
    };
  },
  filters: {
    numberFormat,
  },
  computed: {
    // filteredColors() {
    //   return colors.filter((color) => this.product.colorId === color.id);
    // },
    colors() {
      return colors;
    },
  },
  methods: {
    goToPage,
  },
};
</script>
