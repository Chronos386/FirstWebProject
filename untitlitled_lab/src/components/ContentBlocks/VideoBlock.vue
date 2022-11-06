<template>
  <section class="contentBlock">
    <div class="titleCenter">Послесловие</div>
    <div class="justText">
      Пиво - это очень хорошо, но и им слишком увлекаться не стоит. А если Вы выпили настолько много,
      что забыли, кто Вы такой, советуем посмотреть это видео. Автору сайта помогает:
    </div>
    <section class="elementCenter">
      <div class="videoApp">
        <iframe width="600" height="450"
                :src="url">
        </iframe>
      </div>
    </section>
  </section>
</template>

<script>
export default {
  name: "ContentBlock",
  props: ['url']
}
</script>

<style scoped>
  .videoApp {
    margin: 20px;
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

  /*Стиль для простого текста*/
  .justText {
    font-size: large;
  }

  .elementCenter {
    text-align: center;
  }
</style>