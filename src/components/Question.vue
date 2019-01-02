<template>
  <tr class="question">
    <td class="text"><b>{{ q.replace(/^q/, "") }}.</b> {{ label }}</td>
    <td v-for="input in 5" :key="input"><input type="radio" :name="q" :value="input-1" v-model="answers[q]" /></td>
  </tr>
</template>

<script>
export default {
  name: 'Question',
  props: {
    q: String,
    label: String,
    answers: Object
  }
}
</script>

<style lang="scss" scoped>
  tr:hover {
    background-color: #ddd;
  }
  td.text {
    padding: 4px 24px;
    text-align: left;
  }
</style>
