<template>
  <div class="product-card">
    <img :src="`/${product.img}`" alt="" />
    <div class="info">
      <div class="tag">{{ product?.tag }}</div>
      <div class="name">{{ product?.name }}</div>
      <div class="wrapper">
        <div class="sale-price">{{ product?.salePrice }}$</div>
        <div class="price">{{ product?.price }}$</div>
      </div>
      <button class="button" @click="buyProduct(product)">Buy</button>
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
  computed: {},
  methods: {
    buyProduct(product) {
      this.$emit('addToCard', product)
    }
  }
}
</script>

<style scoped>
.product-card {
  width: 30%;
  margin: 20px;
  background: #fff;
  border-radius: 20px;
  overflow: hidden;
  text-align: center;
}

.wrapper {
  display: flex;
  justify-content: center;
}

img {
  width: 100%;
  object-fit: cover;
}

.info {
  padding: 20px;
}

.tag {
  color: #bf8d77;
}

.name {
  color: #894722;
  font-size: 18px;
}

.sale-price {
  margin-right: 10px;
  color: #bf8d77;
  text-decoration: line-through;
  font-size: 14px;
  margin-top: 5px;
}

.price {
  color: #f0510d;
  font-size: 18px;
  font-weight: bold;
}

.button {
  background-color: #ff5722;
  color: #ffffff;
  border-radius: 20px;
  margin-top: 20px;
  width: 100%;
  height: 50px;
  border: none;
  font-size: 18px;
  transition: 0.3s;
  cursor: pointer;
}

.button:hover {
  opacity: 0.7;
}
</style>
