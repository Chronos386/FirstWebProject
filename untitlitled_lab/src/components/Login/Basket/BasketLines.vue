<template>
  <section class="row">
    <BasketProdLine v-for="prod of products"
                         v-bind:item="prod"/>
  </section>
</template>

<script>
import BasketProdLine from "@/components/Login/Basket/BasketProdLine";
export default {
  name: "BasketLines",
  props: ['products'],
  components: {
    BasketProdLine
  }
}
</script>

<style scoped>

</style>