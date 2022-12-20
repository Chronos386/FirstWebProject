<template>
  <section class="contentBlock">
    <div class="titleCenter">Спасибо, что выбрали Нас!</div>
    <section class="ourThanks">
      <section class="ayanamiImg">
        <img src="https://31.media.tumblr.com/dad390d9ee8b57ddd3edcfbae9059dfe/tumblr_inline_nb4zdqw3HV1sf3h99.gif"
             alt="">
      </section>
      <section class="ayanamiTextImg">
        <div class="text">
          Надеемся, что Вам понравится опыт работы с Нами. Мы всегда рады, как новым клиентам, так
          старым друзьям. Пиво объединяет людей и, как минимум, оно свело Нас с Вами, так давайте же
          и дальше проводить как можно больше времени вместе)
        </div>
        <div class="titleCenter">И помните:</div>
        <section class="elementCenter">
          <img src="https://i.pinimg.com/originals/fd/f4/6b/fdf46b6f290cac86d40988bab22ed419.jpg"
               alt="">
        </section>
      </section>
    </section>
  </section>
</template>

<script>
export default {
  name: "ThanksBlock"
}
</script>

<style scoped>
.ourThanks {
  display: flex;
}

.ourThanks .ayanamiImg {
  width: 40%;
}

.ourThanks .ayanamiImg img {
  width: 100%;
  border-radius: 10px;
  border: 4px solid white;
}

.ourThanks .ayanamiTextImg {
  width: 60%;
}

.ourThanks .ayanamiTextImg .text {
  margin: 20px;
}

@media only screen and (min-width: 0px) {
  .ourThanks .ayanamiTextImg .text {
    font-size: xx-small;
  }
}
@media only screen and (min-width: 770px) {
  .ourThanks .ayanamiTextImg .text {
    font-size: medium;
  }
}
@media only screen and (min-width: 1200px) {
  .ourThanks .ayanamiTextImg .text {
    font-size: large;
  }
}

.ourThanks .ayanamiTextImg img {
  width: 50%;
  margin: 15px;
  border-radius: 10px;
}
</style>