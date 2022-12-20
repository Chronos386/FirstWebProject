<template>
  <section class="contentBlock">
    <div class="titleCenter">Почему именно Мы?</div>
    <div class="justText">
      Мы сотрудничаем с брендами мирового масштаба, пиво, которое Мы продаём, знают по всему миру, да
      и оно просто вкусное! (Мы сами проверяли)
    </div>
    <div class="justText">
      А так же, Мы проводили независимое исследование в высшей академии пива (получить документы,
      подтверждающие подлинность исследования, Вы можете, отправив запрос в техподдержку, написав Нам на
      почту или позвонив) и пришли к таким выводам:
    </div>
    <section class="ourBeer">
      <div class="beer">
        <div>
          <img src="https://i.pinimg.com/originals/9a/63/13/9a631397a10486da24c57b674958066a.gif"
               alt="">
        </div>
        <div class="subTitleCenter">Наше пиво</div>
      </div>
      <div class="beer">
        <div>
          <img src="https://c.tenor.com/mWPWSIV22sUAAAAM/evangelion-rei-ayanami.gif" alt="">
        </div>
        <div class="subTitleCenter">Не наше пиво</div>
      </div>
    </section>
  </section>
</template>

<script>
export default {
  name: "WhyOurBeerBlock"
}
</script>

<style scoped>
.ourBeer {
  display: flex;
  margin-bottom: 10px;
}

.ourBeer .beer {
  width: 50%;
  margin: 15px;
}

.ourBeer .beer img {
  width: 100%;
}

.subTitleCenter {
  text-align: center;
}

@media only screen and (min-width: 0px) {
  .subTitleCenter {
    font-size: medium;
  }
}
@media only screen and (min-width: 770px) {
  .subTitleCenter {
    font-size: large;
  }
}
@media only screen and (min-width: 1200px) {
  .subTitleCenter {
    font-size: x-large;
  }
}
</style>