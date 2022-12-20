<template>
  <section class="contentBlock">
    <div class="titleCenter">Послесловие</div>
    <div class="justText">
      Пиво - это очень хорошо, но и им слишком увлекаться не стоит. А если Вы выпили настолько много,
      что забыли, кто Вы такой, советуем посмотреть это видео. Автору сайта помогает:
    </div>
    <section class="elementCenter">
      <div class="videoApp">
        <iframe
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

@media only screen and (min-width: 0px) {
  .videoApp iframe {
    width:265px;
    height:200px;
  }
}
@media only screen and (min-width: 770px) {
  .videoApp iframe {
    width:530px;
    height:400px;
  }
}
@media only screen and (min-width: 1200px) {
  .videoApp iframe {
    width:800px;
    height:600px;
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
  .justText {
    font-size: xx-small;
  }
  .titleCenter {
    font-size: large;
  }
}
@media only screen and (min-width: 770px) {
  .justText {
    font-size: small;
  }
  .titleCenter {
    font-size: x-large;
  }
}
@media only screen and (min-width: 1200px) {
  .justText {
    font-size: large;
  }
  .titleCenter {
    font-size: xx-large;
  }
}
.elementCenter {
  text-align: center;
}
</style>