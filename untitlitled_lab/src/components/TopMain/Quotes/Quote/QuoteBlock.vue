<template>
  <section class="quotPlace">
    <div class="quot">„{{ quote }}“
    </div>
    <div class="author">Автор: {{ author }}</div>
  </section>
</template>

<script>
export default {
  name: "QuoteBlock",
  props: {
    quote: String,
    author: String
  }
}
</script>

<style scoped>
.quotPlace {
  margin-top: 10px;
  padding: 1%;
  position: relative;
  border-radius: 10px;
  border: 3px solid white;
}

.quotPlace .quot {
  color: white;
  margin-bottom: 40px;
}

.quotPlace .author {
  bottom: 8px;
  right: 16px;
  color: white;
  font-style: italic;
  position: absolute;
}

@media only screen and (min-width: 0px) {
  .quotPlace .quot {
    font-size: xx-small;
  }
  .quotPlace .author {
    font-size: xx-small;
  }
}
@media only screen and (min-width: 500px) {
  .quotPlace .quot {
    font-size: medium;
  }
  .quotPlace .author {
    font-size: medium;
  }
}
</style>