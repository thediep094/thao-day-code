<template>
  <div class="product-card">
    <!-- <img src="" alt="" /> -->
    <div class="info">
      <div class="tag">{{ product?.tag }}</div>
      <div class="name">{{ product?.name }}</div>
      <div class="price">{{ product?.price }}</div>
      <button @click="buyProduct(product.price)">Buy</button>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    product: {
      type: Object
    }
  },
  methods: {
    buyProduct(price) {
      this.$emit('buyProduct', price)
    }
  }
}
</script>
<style></style>
