<template>
  <li class="cart__item product"
            :key="item.productId">
              <div class="product__pic">
                <img :src="item.product.image" width="120" height="120"
                :alt="item.product.title">
              </div>
              <h3 class="product__title">
                {{item.product.title}}
              </h3>
              <p class="product__info">
                Объем: <span>128GB</span>
              </p>
              <span class="product__code">
                Артикул: {{item.product.id}}
              </span>

              <div class="product__counter form__counter">
                <button type="button" aria-label="Убрать один товар">
                  <svg width="10" height="10" fill="currentColor">
                    <use xlink:href="#icon-minus"></use>
                  </svg>
                </button>

                <input type="text" v-model.number="amount" name="count">

                <button type="button" aria-label="Добавить один товар">
                  <svg width="10" height="10" fill="currentColor">
                    <use xlink:href="#icon-plus"></use>
                  </svg>
                </button>
              </div>

              <b class="product__price">
                {{(item.product.price * item.amount) | numberFormat}}₽
              </b>

              <button class="product__del button-del" type="button"
              aria-label="Удалить товар из корзины" @click.prevent="deleteProduct">
                <svg width="20" height="20" fill="currentColor">
                  <use xlink:href="#icon-close"></use>
                </svg>
              </button>
            </li>
</template>
<script>
import mapMutation from 'vuex';
import numberFormat from '@/helpers/numberFormat';

export default {
  name: 'CartItem',
  props: ['item'],
  filters: { numberFormat },
  computed: {
    amount: {
      get() {
        return this.item.amount;
      },
      set(value) {
        this.$store.commit('updateCartProductAmount', { productId: this.item.productId, amount: value });
      },
    },
  },
  methods: {
    ...mapMutation({
      deleteProduct: 'deleteCartProduct',
    }),
  },
};
</script>
