<template>
  <section class="contentBlock">
    <div class="titleCenter">АВТОРИЗАЦИЯ</div>
    <div class="littleSubTitle">Логин</div>
    <div>
      <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    </div>
    <div class="littleSubTitle">Пароль</div>
    <div>
      <input type="password" class="form-control" id="exampleInputPassword1">
    </div>
    <button type="submit" class="enterButton">Войти</button>
  </section>
</template>

<script>
export default {
  name: "LoginBlock"
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