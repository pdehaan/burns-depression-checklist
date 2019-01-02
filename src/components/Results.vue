<template>
  <table>
    <thead>
      <tr>
        <th>Total Score</th>
        <th>Level of Depression</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(row, idx) of results" :key="idx">
        <td class="range">{{row.min}} &mdash; {{ row.max }}</td>
        <td>{{row.label}}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'Results',
  props: {
    results: Array
  }
}
</script>

<style lang="scss" scoped>
table {
  float: right;
}
thead {
  background-color: gold;
}
td {
  padding: 4px 14px;
  &.range {
    text-align: right;
  }
}
th {
  padding: 10px 20px;
}
</style>

