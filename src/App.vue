<template>
  <main id="app">
    <Questionnaire msg="Burn's Depression Checklist"
      :questions="questions"
      :answers="answers"
      :legend="legend"
      :results="results" />
  </main>
</template>

<script>
import Questionnaire from './components/Questionnaire.vue'

export default {
  name: 'app',
  components: {
    Questionnaire
  },
  data() {
    return {
      answers: {},
      legend: [
        "Not at all",
        "Somewhat",
        "Moderately",
        "A lot",
        "Extremely"
      ],
      results: [
        {min: 0, max: 5, label: "No depression"},
        {min: 6, max: 10, label: "Normal but unhappy"},
        {min: 11, max: 25, label: "Mild depression"},
        {min: 26, max: 50, label: "Moderate depression"},
        {min: 51, max: 75, label: "Severe depression"},
        {min: 76, max: 100, label: "Extreme depression"}
      ],
      questions: [
        {
          label: "Thoughts and Feelings",
          questions: [
            { id: "q1", label: "Feeling sad or down in the dumps?" },
            { id: "q2", label: "Feeling unhappy or blue?" },
            { id: "q3", label: "Crying spells or tearfulness?" },
            { id: "q4", label: "Feeling discouraged?" },
            { id: "q5", label: "Feeling hopeless?" },
            { id: "q6", label: "Low self-esteem?" },
            { id: "q7", label: "Feeling worthless or inadequate?" },
            { id: "q8", label: "Guilt or shame?" },
            { id: "q9", label: "Critisizing yourself or blaming others?" },
            { id: "q10", label: "Difficulty making decisions?" }
          ]
        },
        {
          label: "Activities and Personal Relationships",
          questions: [
            { id: "q11", label: "Loss of interest in family, friends, or colleagues?" },
            { id: "q12", label: "Loneliness?" },
            { id: "q13", label: "Spending less time with family or friends?" },
            { id: "q14", label: "Loss of motivation?" },
            { id: "q15", label: "Loss of interest in work or other activities?" },
            { id: "q16", label: "Avoiding work or other activities?" },
            { id: "q17", label: "Loss of pleasure or satisfaction in life?" }
          ]
        },
        {
          label: "Physical Symptoms",
          questions: [
            { id: "q18", label: "Feeling tired?" },
            { id: "q19", label: "Difficulty sleeping or sleeping too much?" },
            { id: "q20", label: "Decreased or increased appetite?" },
            { id: "q21", label: "Loss of interest in sex?" },
            { id: "q22", label: "Worrying about your health?" }
          ]
        },
        {
          label: "Suicidal Urges",
          questions: [
            { id: "q23", label: "Do you have any suicidal thoughts?" },
            { id: "q24", label: "Would you like to end your life?" },
            { id: "q25", label: "Do you have to plan for harming yourself?" }
          ]
        }
      ]
    };
  }
}
</script>

<style lang="scss">
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin-top: 60px;
  text-align: left;
}
</style>
