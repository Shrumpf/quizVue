<template>
  <div id="app">
    <Quiz
      v-bind:currentQuestion="currentQuestion"
      on:next-question="nextQuestion"
      v-bind:quiz="quiz"
    />
  </div>
</template>

<script>
import Quiz from "./components/Quiz.vue";
export default {
  name: "App",
  components: {
    Quiz
  },
  methods: {
    nextQuestion() {
      console.log("bla");
    }
  },
  data() {
    return {
      currentQuiz: 0,
      quiz: {
        title: "Quiz Title",
        questions: [
          {
            id: 1,
            label: "Question?",
            answers: [
              {
                id: 1,
                text: "One",
              },
              {
                id: 2,
                text: "Two",
              },
              {
                id: 3,
                text: "42",
              }
            ],
            selectedAnswer: null,
            correctAnswer: 3
          },
          {
            id: 2,
            label: "Question 2!?",
            answers: [
              {
                id: 1,
                text: "asd",
              },
              {
                id: 2,
                text: "asd",
              },
              {
                id: 3,
                text: "asd",
              }
            ],
            selectedAnswer: null,
            correctAnswer: 1
          }
        ]
      }
    };
  }
};
</script>

<style>
#app {
  max-width: 80%;
  margin: 5% auto;
  padding: 8px;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
</style>
