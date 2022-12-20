<template>
  <section class="contentBlock">
    <div class="titleCenter">{{ login_acc }}</div>
    <div class="subTitleLeft">Корзина:</div>
    <BasketLines style="margin-left: 1%" v-bind:products="basket"/>
    <button type="submit" class="logoutButton"  v-on:click="logOut()">Выйти из аккаунта</button>
  </section>
</template>

<script>
import VueCookies from "vue-cookie";
import BasketLines from "@/components/Login/Basket/BasketLines";
export default {
  name: "AccBlock",
  components: {
    BasketLines
  },
  data() {
    return {
      login_acc: VueCookies.get("login"),
      api_key: VueCookies.get("api_key"),
      basket: null
    }
  },
  methods: {
    async logOut() {
      const res = await fetch("http://192.168.100.3:8020/api/login/", {
            "method": "DELETE",
            "headers": {"Content-Type": "application/json"},
            "body": "{\"api_key\": " + JSON.stringify(this.api_key) + "}"
          }
      )
      if (res.status === 200) {
        VueCookies.delete('login')
        VueCookies.delete('api_key')
      }
      location.reload();
    }
  },
  async created() {
    const res = await fetch("http://192.168.100.3:8020/api/my/basket/", {
          "method": "POST",
          "headers": {"Content-Type": "application/json"},
          "body": "{\"api_key\": " + JSON.stringify(VueCookies.get("api_key")) + "}"
        }
    )
    if (res.status === 200) {
      this.basket = await res.json();
    }
  }
}
</script>

<style scoped>
.logoutButton {
  padding: 5px;
  width: 100%;
  color: white;
  margin-top: 30px;
  font-weight: bold;
  font-size: x-large;
  text-align: center;
  border-radius: 10px;
  background: darkgoldenrod;
}
</style>

<style>
.subTitleLeft {
  color: white;
  text-align: left;
  font-weight: bold;
  margin-top: 3%;
  margin-bottom: 3%;
  text-shadow: rgb(2 2 2) 10px 10px 7px;
}
@media only screen and (min-width: 0px) {
  .subTitleLeft {
    font-size: medium;
  }
}
@media only screen and (min-width: 770px) {
  .subTitleLeft {
    font-size: large;
  }
}
@media only screen and (min-width: 1200px) {
  .subTitleLeft {
    font-size: x-large;
  }
}
</style>