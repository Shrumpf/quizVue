<template>
  <div>
    <div>
      <Question v-bind:question="quiz.questions[currentQuestion]"/>
    </div>

    <div>
      <ButtonPanel
        @last-question="lastQuestion"
        @next-question="nextQuestion"
        @finish-quiz="finishQuiz"
      />
    </div>
  </div>
</template>

<script>
import Question from "./Question.vue";
import ButtonPanel from "./ButtonPanel.vue";

export default {
  name: "Quiz",
  components: {
    Question,
    ButtonPanel
  },
  props: {
    quiz: {
      type: Object,
      default() {
        return {};
      }
    }
  },
  data() {
    return {
      currentQuestion: 0
    };
  },
  methods: {
    lastQuestion() {
      if (this.currentQuestion > 0) this.currentQuestion--;
    },
    nextQuestion() {
      if (this.currentQuestion < this.quiz.questions.length - 1)
        this.currentQuestion++;
    },
    finishQuiz() {
      let i;
      let right = [];
      let wrong = [];
      for (i = 0; i < this.quiz.questions.length; i++) {
        if (
          this.quiz.questions[i].correctAnswer ===
          this.quiz.questions[i].selectedAnswer
        ) {
          right.push(this.quiz.questions[i].selectedAnswer);
        } else {
          wrong.push(this.quiz.questions[i].selectedAnswer);
        }
      }
      console.log({ Right: right, Wrong: wrong });
    }
  }
};
</script>
