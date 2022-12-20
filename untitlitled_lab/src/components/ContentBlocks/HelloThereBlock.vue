<template>
  <section class="contentBlock">
    <div class="titleCenter">Здравствуй, дорогой покупатель!</div>
    <section class="helloThere">
      <section class="text">
        <div class="justText">
          Все Мы, время от времени, чувствуем себя не совсем в своей тарелке. На протяжении рабочей
          недели, из-за работы и постоянного стресса, неимоверно начинает копиться усталость.
        </div>
        <div class="justText">
          По Нашему скромному мнению, один из самых простых и приятных способов расслабления - выпить
          немного холодного пива. Пивоварни во всем мире работают для того, чтобы порадовать своих
          ценителей вкусным пивом. Каждый день появляются новые сорта: темные, светлые, с фруктовыми и
          пряными нотами во вкусе.
        </div>
      </section>
      <div class="gif">
        <img src="https://c.tenor.com/fS2VWhhKhU4AAAAC/rei-ayanami-rei.gif" alt="">
      </div>
    </section>
    <div class="justText">
      Но выходные, большинство людей, проводит лёжа в кровати. Периодически, в свой выходной,
      человек
      предпочтёт походу в магазин, вращение на стуле или ещё миллион других занятий. Специально
      для
      всех любителей посидеть дома, и существует Наш интернет магазин! Попробовать самые разные
      виды
      пива Вы можете заказав что-нибудь именно у Нас! Здесь Вы найдете множество сортов пенного из
      самых разных уголков нашей планеты.
    </div>
  </section>
</template>

<script>
export default {
  name: "HelloThereBlock"
}
</script>

<style scoped>
.helloThere {
  display: flex;
  margin-bottom: 10px;
}

.helloThere .text {
  width: 60%;
}

.helloThere .gif {
  width: 40%;
  margin-left: 1%;
}

.helloThere .gif img {
  width: 100%;
}
</style>