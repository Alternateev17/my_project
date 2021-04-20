<template>
  <div class="v-cart-item">
     <img class="v-cart-item__image" :src=" require('../assets/images/' +  cart_item_data.image)" alt="">
     <div class="v-cart-item-data__info">
       <p>{{ cart_item_data.name }}</p>
       <p>{{ cart_item_data.price }}</p>
       <p>{{ cart_item_data.article }}</p>
     </div>
     <div class="v-cart-item__quantity">
       <p>Qty:</p>
       {{ cart_item_data.quantity }}
       </div>
     <button class="btn" @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'v-cart-item',
  props: {
    cart_item_data: {
        type: Object,
        default: () => ({})
    }
  },
  data: () => ({}),
  computed: {},
  methods: {
    deleteFromCart() {
      this.$emit('deleteFromCart')
    }
  },
  mounted() {
    this.$set(this.cart_item_data, 'quantity', 1)
  }

}
</script>

<style lang="scss">
  .v-cart-item {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
    box-shadow: -6px -6px 26px 0 rgba(255, 255, 255,0.83),
                 6px 6px 16px 0 rgba(217, 210, 200,0.51);
    background: #EFEEEE;
    border: 1px solid rgba(255, 255, 255, 0.20);
    border-radius: 12px;
    margin: 5px 0;
  }
  .v-cart-item__image {
    max-width: 50px;
    margin-left: 20px;
    border-radius: 12px;
  }
  .btn {
    box-shadow: -6px -6px 26px 0 rgba(255, 255, 255,0.83),
                 6px 6px 16px 0 rgba(217, 210, 200,0.51);
    background: #EFEEEE;
    border: 1px solid rgba(255, 255, 255, 0.20);
    border-radius: 12px;
    padding: 10px 20px;
    border-radius: 12px;
    margin-right: 20px;

  }

</style>