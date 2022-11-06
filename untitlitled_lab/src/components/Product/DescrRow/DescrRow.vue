<template>
  <tr>
    <td class="characterTitle">
      {{ row.title }}
    </td>
    <td class="characterItem">
      {{ row.item }}
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
    font-size: large;
    font-weight: bold;
  }

  .characterItem {
    font-size: large;
    text-align: right;
  }
</style>