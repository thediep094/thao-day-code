<template>
  <div class="page">
    <header-component ref="headerComponent"></header-component>
    <section-title
      :title="'Our popular products'"
      :description="'Dry food, wet food and dog treats - only natural raw materials made with less pressure and temperature for a higher natural nutritional content.'"
    ></section-title>
    <div class="feature-products">
      <product-card
        v-for="(product, index) in products"
        :product="product"
        :key="index"
        @addToCard="addToCard"
      ></product-card>
    </div>
  </div>
</template>
<script>
import HeaderComponent from '@/components/HeaderComponent.vue'
import ProductCard from '@/components/ProductCard.vue'
import SectionTitle from '@/components/SectionTitle.vue'
export default {
  props: {},
  data() {
    return {
      products: [
        {
          name: 'Caniene Freeze-dried nuggets food',
          tag: 'Dry Food',
          price: 120.0,
          salePrice: 126.25,
          img: '01.png'
        },
        {
          name: 'Caniene Freeze-dried nuggets food',
          tag: 'Dry Food',
          price: 120.0,
          salePrice: 126.25,
          img: '02.png'
        },
        {
          name: 'Caniene Freeze-dried nuggets food',
          tag: 'Dry Food',
          price: 120.0,
          salePrice: 126.25,
          img: '03.png'
        }
      ]
    }
  },
  components: {
    ProductCard,
    HeaderComponent,
    SectionTitle
  },
  methods: {
    addToCard(product) {
      if (this.$refs.headerComponent) {
        this.$refs.headerComponent.sumTotal(product?.price)
      }
    }
  }
}
</script>

<style scoped>
.feature-products {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
}
</style>
