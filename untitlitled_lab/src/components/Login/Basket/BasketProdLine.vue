<template>
  <section class="prodLine">
    <div class="pictProd">
      <img :src="item.pict_url" alt="">
    </div>
    <section class="mainInf">
      <div class="subTitleLeft">{{item.name}}</div>
      <div class="subSubTitle">Количество: {{item.count}}</div>
      <div class="subSubTitle">Цена: {{item.price}}₽</div>
      <div class="fullPrice">{{item.price * item.count}}₽</div>
    </section>
    <section class="buttons">
      <button type="submit" class="plusButton" style="background: chartreuse"  v-on:click="plusCountProd()">+</button>
      <button type="submit" class="plusButton" style="background: crimson" v-on:click="minusCountProd()">-</button>
      <button type="submit" class="plusButton" style="background: crimson" v-on:click="delProduct()">×</button>
    </section>
  </section>
</template>

<script>
import VueCookies from "vue-cookie";
export default {
  name: "BasketProdLine",
  props: ['item'],
  methods: {
    async plusCountProd() {
      const newCount = this.item.count + 1
      const res = await fetch("http://192.168.100.3:8020/api/basket/", {
            "method": "PUT",
            "headers": {"Content-Type": "application/json"},
            "body": "{\"prod_id\": " + this.item.id + ",\"api_key\": " + JSON.stringify(VueCookies.get("api_key"))
                + ",\"count\": " + newCount + "}"
          }
      )
      if (res.status === 200) {
        location.reload();
      }
    },
    async minusCountProd() {
      const newCount = this.item.count - 1
      if (newCount !== 0) {
        const res = await fetch("http://192.168.100.3:8020/api/basket/", {
              "method": "PUT",
              "headers": {"Content-Type": "application/json"},
              "body": "{\"prod_id\": " + this.item.id + ",\"api_key\": " + JSON.stringify(VueCookies.get("api_key"))
                  + ",\"count\": " + newCount + "}"
            }
        )
        if (res.status === 200) {
          location.reload();
        }
      }
      else {
        await this.delProduct()
      }
    },
    async delProduct() {
      const res = await fetch("http://192.168.100.3:8020/api/basket/", {
            "method": "DELETE",
            "headers": {"Content-Type": "application/json"},
            "body": "{\"prod_id\": " + this.item.id + ",\"api_key\": " + JSON.stringify(VueCookies.get("api_key")) + "}"
          }
      )
      if (res.status === 200) {
        location.reload();
      }
    }
  },
  data() {
    return {
      item2: {
        "count": 2,
        "name": "Собутыльник (Аянами Рей плюш)",
        "pict_url": "https://sun9-66.userapi.com/impg/kwru8Ld2a0qFvnDlxUMB0zxO7tVfF66N6AqC0A/TY4VtuXpaR0.jpg?size=840x1278&quality=96&sign=5a2271eab47dca66ae5e5bccaa2b8077&type=album",
        "price": 1800.0
      }
    }
  }
}
</script>

<style scoped>
.buttons {
  width: 30%;
}

.plusButton {
  width: 90%;
  height: 30%;
  margin: 3%;
  color: white;
  font-weight: bold;
  text-align: center;
  border-radius: 10px;
  text-shadow: 2px 2px 2px #000;
}

.prodLine {
  width: 85%;
  display: flex;
  margin: 2% 0 2% 0;
  border-radius: 10px;
  border: 4px solid white;
}

.prodLine .pictProd {
  width: 30%;
}

.prodLine .pictProd img {
  width: 100%;
  border-radius: 10px;
  border: 2px solid black;
}

.prodLine .mainInf {
  width: 39%;
  margin-left: 2%;
}

.subSubTitle {
  color: white;
  text-align: left;
  font-weight: bold;
  margin-top: 1%;
  text-shadow: rgb(2 2 2) 2px 2px 2px;
}

.fullPrice {
  border-radius: 5px;
  color: white;
  margin-top: 5%;
  text-align: left;
  font-weight: bold;
  background: forestgreen;
  text-shadow: rgb(2 2 2) 2px 2px 2px;
}

@media only screen and (min-width: 0px) {
  .subTitleLeft {
    font-size: small;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 1;
    line-clamp: 1;
    -webkit-box-orient: vertical;
  }
  .subSubTitle {
    font-size: x-small;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 1;
    line-clamp: 1;
    -webkit-box-orient: vertical;
  }
  .fullPrice {
    padding: 2%;
    line-clamp: 1;
    overflow: hidden;
    font-size: medium;
    display: -webkit-box;
    -webkit-line-clamp: 1;
    text-overflow: ellipsis;
    -webkit-box-orient: vertical;
  }
  .plusButton {
    font-size: large;
  }
}
@media only screen and (min-width: 770px) {
  .subTitleLeft {
    font-size: medium;
  }
  .subSubTitle {
    font-size: small;
  }
  .fullPrice {
    padding: 5%;
    font-size: x-large;
  }
  .plusButton {
    font-size: x-large;
  }
}
@media only screen and (min-width: 992px) {
  .subTitleLeft {
    font-size: large;
  }
  .subSubTitle {
    font-size: medium;
  }
  .fullPrice {
    font-size: xxx-large;
  }
  .plusButton {
    font-size: xxx-large;
  }
}
</style>