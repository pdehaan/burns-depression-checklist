<template>
  <section class="legend">
    <div v-for="(label, idx) in legend" :key="idx">{{ idx }} &ndash; {{ label }}</div>
  </section>
</template>

<script>
export default {
  name: 'Legend',
  props: {
    legend: Array
  }
}
</script>

<style lang="scss" scoped>
section.legend {
  float: right;
  padding: 30px;
}
</style>


