<template>
  <section class="productTitleContentBlock">
    <QuoteBlock quote="Я вообще не пью молоко. Молоко это для младенцев, а когда вырастаешь нужно пить пиво." author="Арнольд Шварценеггер"/>
    <QuoteBlock quote="Пиво — это еще одно доказательство того, что Господь любит нас и хочет, чтобы мы были счастливы." author="Бенджамин Франклин"/>
  </section>
</template>

<script>
import QuoteBlock from "@/components/TopMain/Quotes/Quote/QuoteBlock"
export default {
  name: "QuotesBlock",
  components: {
    QuoteBlock
  }
}
</script>

<style scoped>
  .productTitleContentBlock {
    width: 60%;
    height: min-content;
    padding: 1%;
    color: ghostwhite;
    border-radius: 10px;
    text-shadow: rgb(2 2 2) 10px 10px 7px;
    background: linear-gradient(rgb(62, 62, 65), rgb(48, 44, 45));
    z-index: 0;
  }
</style>