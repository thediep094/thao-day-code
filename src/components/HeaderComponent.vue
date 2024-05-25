<template>
  <header class="header">
    <nav>
      <RouterLink to="/" class="nav-link">Home</RouterLink>
      <RouterLink to="/about" class="nav-link">About</RouterLink>
    </nav>

    <div class="logo">WEB</div>

    <div class="cart-count">{{ total }}</div>
  </header>
</template>

<script>
import { RouterLink } from 'vue-router'

export default {
  modules: [RouterLink],
  data() {
    return {
      total: 0
    }
  },
  methods: {
    sumTotal(price) {
      this.total = this.total + price
    }
  }
}
</script>

<style scoped>
.header {
  position: fixed;
  left: 20px;
  right: 20px;
  top: 20px;
  background-color: #ffffff;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  padding: 0 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 10px;
}

.logo {
  font-size: 30px;
  font-weight: bold;
  color: #ff5722;
}

.nav-link {
  text-decoration: none;
  color: #894722;
  margin-right: 20px;
  font-size: 18px;
}

.cart-count {
  background-color: #ff5722;
  color: #ffffff;
  border-radius: 0;
  font-size: 14px;
  width: 113px;
  height: 47px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
}
</style>
