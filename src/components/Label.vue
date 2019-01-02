<template>
  <tr class="label">
    <th width="100%">{{ text }}</th>
    <th v-for="(n, idx) in 5" v-text="idx" :key="idx"></th>
  </tr>
</template>

<script>
export default {
  name: "Label",
  props: {
    text: String
  }
}
</script>

<style lang="scss" scoped>
tr.label {
  background-color: #aaa;

  th {
    padding: 10px;
  }
}
</style>
