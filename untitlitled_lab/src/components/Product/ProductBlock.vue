<template>
  <section class="contentBlock">
    <section class="productPageUp">
      <section class="half1">
        <img :src="image" alt=""/>
      </section>
      <section class="half2">
        <div class="titleCenter">{{title}}</div>
        <section class="description">
          <div class="backCount">Осталось: {{count}} штук</div>
          <div class="backPrice">
            <div class="price">{{price}} руб.</div>
            <button class="buyButton">Купить</button>
          </div>
          <section class="backPrice">
            <div class="titleCenter">Характеристики</div>
            <table>
              <DescrRow v-for="row of characteristics"
              v-bind:row="row"/>
            </table>
          </section>
        </section>
      </section>
    </section>
  </section>
</template>

<script>
import DescrRow from "@/components/Product/DescrRow/DescrRow"
export default {
  name: "ProductBlock",
  components: {
    DescrRow
  },
  props: ['image', 'title', 'count', 'price', 'characteristics']
}
</script>

<style scoped>
  .productPageUp {
    display: flex;
    margin-top: 15px;
    margin-bottom: 15px;
  }

  .productPageUp .half1 {
    width: 40%;
  }

  .productPageUp .half1 img {
    width: 100%;
    border-radius: 5px;
    border: 5px solid #000;
  }

  .productPageUp .half2 {
    width: 60%;
  }

  .productPageUp .half2 .description {
    padding: 1%;
  }

  .backCount {
    padding: 10px;
    font-weight: bold;
    text-align: center;
    border-radius: 5px;
    font-size: xx-large;
    background-color: rgb(176, 173, 173);
  }

  .backPrice {
    padding: 10px;
    margin-top: 2%;
    border-radius: 5px;
    text-shadow: rgb(2 2 2) 0 0 0;
    background-color: rgb(138, 137, 137);
  }

  .backPrice .price {
    font-weight: bold;
    font-size: xx-large;
  }

  table {
    width: 70%;
  }

  .buyButton {
    width: 100%;
    padding: 10px;
    color: #ffffff;
    font-weight: bold;
    border-radius: 5px;
    text-align: center;
    font-size: x-large;
    background-color: rgb(236, 8, 8);
  }
</style>

<style>
  .contentBlock {
    margin: 3%;
    padding: 3%;
    color: ghostwhite;
    border-radius: 10px;
    text-shadow: rgb(2 2 2) 10px 10px 7px;
    background: linear-gradient(rgb(62, 62, 65), rgb(48, 44, 45));
  }

  .titleCenter {
    color: white;
    font-weight: bold;
    text-align: center;
    margin-bottom: 15px;
    font-size: xx-large;
    text-shadow: rgb(2 2 2) 10px 10px 7px;
  }
</style>