<template>
  <div class="home">
    <div class="container m-auto">
      <div class="grid grid-cols-6 gap-4">
        <VtProductCard
          v-for="(product, index) in products"
          :key="index"
          :product="product"
        />
      </div>
    </div>
  </div>
</template>

<script>
import VtProductCard from '@common/VtProductCard'
export default {
  name: 'home',
  components: {
    VtProductCard
  },
  data () {
    return {
      isLoading: true,
      products: []
    }
  },
  methods: {
    async getProducts () {
      await fetch('/data/products.json').then(result => result.json()).then(response => {
        console.log(response)
        if (response.data.length) this.products = response.data
        this.isLoading = false
      })
    }
  },
  mounted () {
    this.getProducts()
  }
}
</script>
