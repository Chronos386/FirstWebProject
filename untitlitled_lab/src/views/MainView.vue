<template>
  <section>
    <TopMain/>
    <HelloThereBlock/>
    <WhyOurBeerBlock/>
    <ProductsTitleBlock/>
    <ProductsLine v-bind:products="products"/>
    <ThanksBlock/>
    <VideoBlock url="https://www.youtube.com/embed/y8tkWwwql44?autoplay=0&mute=0"/>
  </section>
</template>

<script>
import TopMain from "@/components/TopMain/TopMain"
import HelloThereBlock from "@/components/ContentBlocks/HelloThereBlock"
import WhyOurBeerBlock from "@/components/ContentBlocks/WhyOurBeerBlock"
import ProductsTitleBlock from "@/components/ContentBlocks/ProductsTitleBlock";
import ProductsLine from "@/components/Product/ProductsLine";
import ThanksBlock from "@/components/ContentBlocks/ThanksBlock";
import VideoBlock from "@/components/ContentBlocks/VideoBlock";
import VueCookies from "vue-cookie";
export default {
  name: "MainView",
  components: {
    TopMain,
    HelloThereBlock,
    WhyOurBeerBlock,
    ProductsTitleBlock,
    ProductsLine,
    ThanksBlock,
    VideoBlock
  },
  data() {
    return {
      products: null
    }
  },
  async created() {
    VueCookies.delete('prod_id')
    const res = await fetch("http://192.168.100.3:8020/api/products/", {
          "method": "GET",
        }
    )
    if (res.status === 200) {
      this.products = await res.json();
    }
  }
}
</script>