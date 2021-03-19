<template>
  <div>
    <div v-if="!testFinished">
      <Speech :word="questions[activeIndex].word" />
      <p>Word {{ activeIndex + 1 }} of {{ questions.length }}</p>
      <form @submit.prevent="handleSubmit">
        <input type="text" spellcheck="false" v-model="userInput" />
        <button type="submit">Submit</button>
      </form>
    </div>
    <div v-else>
      <Score :questions="questions" />
    </div>
  </div>
</template>

<script>
import data from "./data";
import Speech from "./components/Speech"
import Score from "./components/Score"

export default {
  components: {
    Speech,
    Score
  },
  data() {
    return {
      questions: data,
      activeIndex: 0,
      userInput: ""
    };
  },
  methods: {
    handleSubmit() {
      this.questions[this.activeIndex].userInput = this.userInput;
      this.activeIndex += 1;
      this.userInput = "";
    }
  },
  computed: {
    testFinished() {
      return this.questions.every(q => q.userInput);
    }
  }
}
</script>

<style>
</style>