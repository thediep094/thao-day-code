<template>
  <div class="section-title">
    <div class="wrapper">
      <div class="title">{{ title }}</div>
      <div class="description">{{ description }}</div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    description: {
      type: String,
      default: ''
    }
  }
}
</script>
<style scoped>
.section-title {
  max-width: 100%;
  display: flex;
  justify-content: center;
  margin-bottom: 50px;
}

.wrapper {
  display: flex;
  max-width: 600px;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  text-align: center;
}

.title {
  color: #ff5722;
  font-size: 50px;
  font-weight: bold;
}
.description {
  color: #894722;
  font-size: 18px;
}
</style>
