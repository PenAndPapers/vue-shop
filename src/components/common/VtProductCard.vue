<template>
  <article class="product-card">
    <img class="block m-auto" :src="product.image_url" alt="">
    <h4 class="text-center">{{ product.name }}</h4>
    <p class="text-center">${{ product.price }}</p>
  </article>
</template>

<script>
export default {
  name: 'VtProductCard',
  props: {
    product: {
      type: Object,
      default: () => {},
      required: true
    }
  }
}
</script>
