<template>
  <tr>
    <td class="characterTitle">
      {{ row.title }}
    </td>
    <td class="characterItem">
      {{ row.body }}
    </td>
  </tr>
</template>

<script>
export default {
  name: "DescrRow",
  props: {
    row: {
      type: Object
    }
  }
}
</script>

<style scoped>
.characterTitle {
  text-align: left;
  font-weight: bold;
}

.characterItem {
  text-align: right;
}

@media only screen and (min-width: 0px) {
  .characterTitle {
    font-size: x-small;
  }

  .characterItem {
    font-size: x-small;
  }
}

@media only screen and (min-width: 770px) {
  .characterTitle {
    font-size: large;
  }

  .characterItem {
    font-size: large;
  }
}

@media only screen and (min-width: 1200px) {
  .characterTitle {
    font-size: x-large;
  }

  .characterItem {
    font-size: x-large;
  }
}
</style>