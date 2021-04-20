<template>
  <div class="v-main-wrapper">
     <h1 class="v-catalog-title">Catalog</h1>
     <keep-alive>
        <router-view></router-view>
     </keep-alive>
    <!-- <VCatalog />
    <VCart
      v-if="CART.length"
      :cart_data="CART"
    /> -->
  </div>
</template>

<script>
// import VCatalog from './v-catalog'
// import VCart from './v-cart'
// import { mapGetters } from 'vuex'

export default {
  name: 'v-main-wrapper',
  // components: {
  //   VCatalog,
  //   VCart
  // },
  props: {},
  data: () => ({}),
  // computed: {
  //   ...mapGetters([
  //     'CART'
  //   ])
  // }
}
</script>

<style lang="scss">
.v-main-wrapper {
   max-width: 900px;
   margin: 0 auto;
}
.v-catalog-title h1 {
  font-size: 45px;
}
</style>