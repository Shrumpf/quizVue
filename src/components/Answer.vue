<template>
  <label>
    <div class="answerBox">
      <input name="answer" v-bind:value="answer.id" type="radio" @change="changeAnswer(answer.id)" :checked="answer.id == selectedAnswer">
      {{ answer.text }}
    </div>
  </label>
</template>

<script>
export default {
  name: "Answer",
  props: {
      answer: {
          Type: Object
      },
      selectedAnswer: Number
  },
  methods: {
      changeAnswer(id) {
          this.$emit('change-answer', id);
      }
  }
};
</script>

<style scoped>
.answerBox {
  padding: 10px;
  border: 1px solid darkgray;
  margin: 4px 0;
  background-color: lightgray;
}
.answerBox:hover {
  background-color: rgb(230, 230, 230);
}
</style>
