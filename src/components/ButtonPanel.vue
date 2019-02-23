<template>
  <div>
    <input type="button" value="Zurück" @click="lastQuestion">
    <input type="button" value="Weiter" @click="nextQuestion">
    <input type="button" value="Finish" @click="finishQuiz">
  </div>
</template>

<script>
export default {
  name: "ButtonPanel",
  methods: {
    lastQuestion() {
      this.$emit("last-question");
    },
    nextQuestion() {
      this.$emit("next-question");
    },
    finishQuiz() {
        this.$emit("finish-quiz");
    }
  }
};
</script>

<style scoped>
input[type="button"] {
  background-color: #4caf50; /* Green */
  border: none;
  color: white;
  padding: 10px 23px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-right: 4px;
}
</style>
