<template>
  <section class="topAyanami">
    <QuotesBlock/>
    <Pict/>
  </section>
</template>

<script>
import Pict from "@/components/TopMain/Pict/Pict";
import QuotesBlock from "@/components/TopMain/Quotes/QuotesBlock";
export default {
  name: "TopMain",
  components: {
    QuotesBlock,
    Pict
  }
}
</script>

<style scoped>
  .topAyanami {
    display: flex;
    padding: 10px;
  }
</style>