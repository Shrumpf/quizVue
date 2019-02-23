<template>
  <div>
    <div class="questionBox">
      <h1>{{question.label}}</h1>
    </div>
    <div v-for="answer in question.answers" :key="answer.id">
      <Answer
        :answer="answer"
        @change-answer="changeAnswer"
        v-bind:selectedAnswer="question.selectedAnswer"
      />
    </div>
  </div>
</template>

<script>
import Answer from "./Answer.vue";

export default {
  name: "Question",
  components: {
    Answer
  },
  props: {
    question: {
        Type: Object,
        default() {
            return {}
        }
    }
  },

  methods: {
    changeAnswer(id) {
      this.question.selectedAnswer = id;
    }
  }
};
</script>

<style>
.questionBox {
  margin-bottom: 16px;
}
</style>
