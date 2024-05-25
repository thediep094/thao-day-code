<script>
import { RouterView } from 'vue-router'

export default {
  modules: [RouterView]
}
console.log('abc')
</script>

<template>
  <RouterView />
</template>

<style>
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Roboto';
  background: #fffbef;
}

#app {
  width: 100vw;
  min-height: 100vh;
}

.page {
  margin-top: 100px;
}
</style>
