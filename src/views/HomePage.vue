<template>
  <div class="feature-products">
    <product-card
      v-for="(product, index) in products"
      :product="product"
      :key="index"
      @buyProduct="buyProduct"
    ></product-card>

    <div class="count" @click="increaseCount">{{ count }}</div>
    <button @click="decreaseCount">Minus</button>
    <div>
      {{ sumPlusEight }}
    </div>

    <input type="text" @change="changeSomething" />
  </div>
</template>
<script>
import ProductCard from '@/components/ProductCard.vue'
export default {
  props: {},
  data() {
    return {
      products: [
        {
          name: 'Caniene Freeze-dried nuggets food',
          tag: 'Dry Food',
          price: 120.0,
          salePrice: 126.25
        },
        {
          name: 'Caniene Freeze-dried nuggets food',
          tag: 'Dry Food',
          price: 120.0,
          salePrice: 126.25
        },
        {
          name: 'Caniene Freeze-dried nuggets food',
          tag: 'Dry Food',
          price: 120.0,
          salePrice: 126.25
        }
      ],
      message: 'THAO ABC, MAI PHUONGW XYX, TRNAGT CXXXX',
      count: 0
    }
  },
  components: {
    ProductCard
  },
  methods: {
    increaseCount() {
      this.count = this.count + 1
    },

    decreaseCount() {
      this.count = this.count - 1
    },

    buyProduct(price) {
      this.count = this.count + price
    },
    changeSomething(e) {
      this.count = Number(e.target.value)
    }
  },
  watch: {
    count() {
      console.log('Thay doi')
    }
  },
  computed: {
    sumPlusEight() {
      return this.count + 8
    }
  },
  beforeCreate() {
    console.log('tao truoc')
    console.log('count data', this.count)
  },

  created() {
    console.log('Vua tao xong')
    console.log('count data', this.count)
  },

  beforeMount() {
    console.log('Chua mount')
    console.log('count data', this.count)
  },

  mounted() {
    console.log('Da mount roi')
    console.log('count data', this.count)
  },

  beforeUpdate() {
    console.log('Chua update')
    console.log('count data', this.count)
  },
  updated() {
    console.log('Update roi')
    console.log('count data', this.count)
  },

  unmounted() {
    console.log('Bo di')
    console.log('count data', this.count)
  }
}
</script>
<style>
.count {
  font-size: 50px;
}
</style>
