<template>
  <ProductBlock
      v-bind:characteristics="characteristics" v-bind:image="image"
      v-bind:title="name" v-bind:count="count" v-bind:price="price"/>
</template>

<script>
import ProductBlock from "@/components/Product/ProductBlock"
export default {
  name: "ProductView",
  components: {
    ProductBlock
  },
  props: ['price', 'name', 'image', 'characteristics', 'count']
}
</script>