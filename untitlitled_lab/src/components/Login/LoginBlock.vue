<template>
  <section class="contentBlock">
    <div class="titleCenter">АВТОРИЗАЦИЯ</div>
    <div class="littleSubTitle">Логин</div>
    <div>
      <input type="text" class="form-control" name="login" placeholder="Введите логин" v-model="form.login" aria-describedby="emailHelp">
    </div>
    <div class="littleSubTitle">Пароль</div>
    <div>
      <input type="password" class="form-control" name="password" v-model="form.password" placeholder="Введите пароль" >
    </div>
    <button type="submit" class="enterButton"  v-on:click="signIn()">Войти</button>
  </section>
</template>

<script>
import VueCookies from "vue-cookie";
export default {
  name: "LoginBlock",
  data() {
    return {
      form: {
        "login": '',
        "password": ''
      }
    }
  },
  methods: {
    async signIn() {
      const res = await fetch("http://192.168.100.3:8020/api/login/", {
            "method": "POST",
            "headers": {"Content-Type": "application/json"},
            "body": JSON.stringify(this.form)
          }
      )
      if (res.status === 200) {
        VueCookies.set('login', this.form.login)
        const reqBody = await res.json()
        VueCookies.set('api_key', reqBody.api_key)
      }
      location.reload();
    }
  }
}
</script>

<style scoped>
.littleSubTitle {
  margin-top: 20px;
  font-size: small;
  margin-bottom: 10px;
}

.enterButton {
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