<template>
  <section class="q">
    <header>
      <h1>{{ msg }}</h1>
      <p style="text-align: left;"><b>Instructions:</b> Put a check to indicate how much you have experienced each symtom during the past week, including today.<br/>Please answer all 25 questions.</p>
      <p>via <a href="https://www.jaxhealth.com/app/files/public/10161/burns-depression.pdf" target="_blank" rel="noreferrer">https://www.jaxhealth.com/app/files/public/10161/burns-depression.pdf</a></p>

      <Legend :legend="legend" />
    </header>

    <table v-for="(group, idx) in questions" width="100%" :key="idx">
      <Label :text="group.label" />
      <Question v-for="question in group.questions"
        :key="question.id"
        :q="question.id"
        :label="question.label"
        :answers="answers" />
    </table>

    <footer>
      <hr />
      <h2>TOTAL: {{ this.sum(answers) }} ({{ this.level(answers) }})</h2>

      <Results :results="results" />
    </footer>
  </section>
</template>

<script>
import Label from "./Label.vue";
import Legend from "./Legend.vue";
import Results from "./Results.vue";
import Question from "./Question.vue";

export default {
  name: 'Questionnaire',
  components: {
    Label,
    Legend,
    Results,
    Question
  },
  methods: {
    level(obj) {
      const sum = this.sum(obj);
      for (const {max, label} of this.results) {
        if (sum <= max) return label;
      }
    },
    sum(obj) {
      return Object.values(obj).reduce((sum, curr) => sum + curr, 0);
    }
  },
  props: {
    msg: String,
    questions: Array,
    answers: Object,
    legend: Array,
    results: Array
  }
}
</script>

<style scoped lang="scss">
footer h2 {
  text-align: right;
}

header h1 {
  font-size: 2em;
}

.legend {
  text-align: left;
}

.checklist table {
  text-align: left;

  tbody th {
    background-color: #aaa;
    padding: 10px;
  }
}
</style>
