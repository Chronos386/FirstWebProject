<template>
  <footer>
    <div class="container">
      <section class="warning">
        <div>Если Тебе ещё нет 18-ти, то Тебе здесь делать нечего.</div>
        <div>
          <img src="https://sun9-55.userapi.com/impg/Du7FslVCFcsTh5YviBz4n-5Z3uAPDZsZdGPF_Q/S-J8uuid3xA.jpg?size=300x300&quality=96&sign=ae8c4c8993b33b7284d21b00f08c1fe1&type=album"
               alt="">
        </div>
        <div>Приходи, когда подрастёшь, пиво Тебя дождётся.</div>
      </section>
      <section class="corpInform">
        <div>
          <img src="@/assets/logo.png" alt="">
        </div>
        <div>
          <div>&copy; LOL Corp, 2022</div>
          <div>+7(800)555-35-35</div>
        </div>
      </section>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style scoped>
footer {
  color: #fff;
  padding: 15px;
  background-color: rgb(121, 24, 24);
}

footer .container {
  display: flex;
  justify-content: space-between;
}

.warning {
  width: 35%;
  padding-top: 5px;
  font-size: medium;
}

.warning img {
  width: 60%;
  display: block;
  padding-top: 10px;
  margin-left: 10px;
  margin-right: auto;
  padding-bottom: 10px;
}

.corpInform {
  width: 35%;
  padding-top: 30px;
  text-align: center;
}

.corpInform img {
  width: 80%;
  padding-top: 10px;
  padding-bottom: 20px;
  align-content: center;
}

@media only screen and (min-width: 0px) {
  .warning {
    font-size: x-small;
  }
  .corpInform {
    font-size: x-small;
  }
}
@media only screen and (min-width: 770px) {
  .warning {
    font-size: small;
  }
  .corpInform {
    font-size: small;
  }
}
@media only screen and (min-width: 1200px) {
  .warning {
    font-size: medium;
  }
  .corpInform {
    font-size: medium;
  }
}
</style>