<template>
  <section class="row">
    <ProductCard v-for="product of products"
                 v-bind:product="product"/>
  </section>
</template>

<script>
import ProductCard from "@/components/Product/Card/ProductCard"
export default {
  name: "ProductsLine",
  components: {
    ProductCard
  },
  props: ['products']
}
</script>

<style scoped>

</style>