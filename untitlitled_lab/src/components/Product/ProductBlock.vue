<template>
  <section class="contentBlock">
    <section class="productPageUp">
      <section class="half1">
        <img :src="product.picturl" alt=""/>
      </section>
      <section class="half2">
        <div class="titleCenter">{{product.name}}</div>
        <section class="description">
          <div class="backCount">Осталось: {{product.count}} штук</div>
          <div class="backPrice">
            <div class="price">{{product.price}} руб.</div>
            <button class="buyButton" v-on:click="addToBasket()">
              Купить
            </button>
          </div>
          <section class="backPrice">
            <div class="titleCenter">Характеристики</div>
            <table>
              <DescrRow v-for="row of product.characteristics"
                        v-bind:row="row"/>
            </table>
          </section>
        </section>
      </section>
    </section>
  </section>
</template>

<script>
import router from "@/router";
import VueCookies from "vue-cookie";
import DescrRow from "@/components/Product/DescrRow/DescrRow"
export default {
  name: "ProductBlock",
  components: {
    DescrRow
  },
  data() {
    return {
      product: null,
      api_key: VueCookies.get("api_key")
    }
  },
  async created() {
    const res = await fetch("http://192.168.100.3:8020/api/product/" + VueCookies.get('prod_id'), {
          "method": "GET",
        }
    )
    if (res.status === 200) {
      this.product = await res.json();
    }
  },
  methods: {
    async addToBasket() {
      const res = await fetch("http://192.168.100.3:8020/api/basket/", {
            "method": "POST",
            "headers": {"Content-Type": "application/json"},
            "body": "{\"prod_id\": " + this.product.id + ", \"api_key\": " + JSON.stringify(this.api_key) + "}"
          }
      )
      if (res.status === 200) {
        await router.push({name: 'Login'})
      }
    }
  }
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
}

table {
  width: 100%;
}

.buyButton {
  width: 100%;
  padding: 10px;
  color: #ffffff;
  font-weight: bold;
  border-radius: 5px;
  text-align: center;
  background-color: rgb(236, 8, 8);
}

@media only screen and (min-width: 0px) {
  .backCount {
    font-size: small;
  }
  .backPrice .price {
    font-size: medium;
  }
  .buyButton {
    font-size: medium;
  }
}
@media only screen and (min-width: 770px) {
  .backCount {
    font-size: large;
  }
  .backPrice .price {
    font-size: large;
  }
  .buyButton {
    font-size: large;
  }
}
@media only screen and (min-width: 1200px) {
  .backCount {
    font-size: x-large;
  }
  .backPrice .price {
    font-size: x-large;
  }
  .buyButton {
    font-size: x-large;
  }
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
  text-shadow: rgb(2 2 2) 10px 10px 7px;
}

/*Стиль для простого текста*/
@media only screen and (min-width: 0px) {
  .titleCenter {
    font-size: large;
  }
}
@media only screen and (min-width: 770px) {
  .titleCenter {
    font-size: x-large;
  }
}
@media only screen and (min-width: 1200px) {
  .titleCenter {
    font-size: xx-large;
  }
}
</style>