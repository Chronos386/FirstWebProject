<template>
  <div class="pict">
    <div>
      <img src="https://64.media.tumblr.com/e9a01cfe9d16d3099e506711c339f7e6/tumblr_n6x5yjcY531s20ivko1_500.gif"
           alt="">
    </div>
    <div class="text">Она уже преисполнилась и бежит за пивом. А Ты?</div>
  </div>
</template>

<script>
export default {
  name: "Pict"
}
</script>

<style scoped>
.pict {
  width: 40%;
  margin-left: 1%;
  color: #000000;
  text-align: center;
}

.pict .text {
  padding: 5px;
  color: #ffffff;
  font-size: large;
  background: black;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
}

@media only screen and (min-width: 0px) {
  .pict .text {
    font-size: xx-small;
  }
}
@media only screen and (min-width: 500px) {
  .pict .text {
    font-size: large;
  }
}

.pict img{
  width: 100%;
  border-top: 5px solid #000;
  border-left: 5px solid #000;
  border-top-left-radius: 5px;
  border-right: 5px solid #000;
  border-top-right-radius: 5px;
}
</style>