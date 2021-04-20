<template>
  <div class="v-catalog-item">
    <img class="v-catalog-item__image" :src=" require('../assets/images/' +  product_data.image)" alt="img">
    <p class="v-catalog-item__name">{{ product_data.name }}</p>
    <p class="v-catalog-item__price">Price: {{ product_data.price }} грн.</p>
    <button
      class="v-catalog-item__add_to_cart_btn btn"
      @click="addToCart">
      Add to cart
    </button>
  </div>
</template>

<script>


export default {
  name: 'v-catalog-item',
  props: {
    product_data: {
      type: Object,
      default: () => ({})
    }
  },
  methods: {
    addToCart() {
      this.$emit('addToCart' ,this.product_data);
    }
  }
}
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 25%;
  // box-shadow: 0 0 8px #e0e0e0;
  box-shadow: -6px -6px 26px 0 rgba(255, 255, 255,0.83),
               6px 6px 16px 0 rgba(217, 210, 200,0.51);
  background: #EFEEEE;
  border: 1px solid rgba(255, 255, 255, 0.20);
  border-radius: 12px;
  padding: 16px;
  margin: 16px;
}
.v-catalog-item__image {
  width: 100px;
  background: #EFEEEE;
  border: 1px solid rgba(255, 255, 255, 0.20);
  border-radius: 12px;
}
.btn {
  background: #EFEEEE;
  border: 1px solid rgba(255, 255, 255, 0.20);
  border-radius: 12px;
  padding: 10px 20px;

}

</style>