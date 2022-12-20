<template>
  <ProductBlock/>
</template>

<script>
import ProductBlock from "@/components/Product/ProductBlock"
import VueCookies from "vue-cookie";
export default {
  name: "ProductView",
  props: ['prod_id'],
  components: {
    ProductBlock
  },
  async created() {
    if (this.prod_id) {
      VueCookies.set('prod_id', this.prod_id)
    }
  }
}
</script>