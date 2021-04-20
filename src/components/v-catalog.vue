<template>
  <div class="v-catalog">
      <router-link :to="{name: 'cart', params: {cart_data: CART}}">
        <div class="v-catalog__link_to_cart btn">Cart: {{ CART.length }}</div>
      </router-link>

        <VCatalogItem
            v-for="product in PRODUCTS"
            :key="product.article"
            :product_data="product"
             @addToCart="addToCart"
        />
  </div>
</template>

<script>
import VCatalogItem from './v-catalog-item'
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'v-catalog',
  components: {
    VCatalogItem
  },
  data: () => ({}),
  computed: {
    ...mapGetters([
      'PRODUCTS',
      'CART'
    ]),
  },
  methods: {
    ...mapActions([
      'GET_PRODUCTS_FROM_API',
      'ADD_TO_CART'
    ]),
    addToCart(data) {
      this.ADD_TO_CART(data);
    }
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API()
    .then((response) => {
      if (response.data) {
        console.log('Data arriverd!');
      }
    })
  }
}
</script>

<style lang="scss">
.v-catalog {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.v-catalog__link_to_cart{
  position: absolute;
  top: 28px;
  right: 234px;
  color: #2c3e50;
}
.btn {
  background: #EFEEEE;
  border: 1px solid rgba(255, 255, 255, 0.20);
  border-radius: 12px;
  padding: 10px 20px;
}
</style>