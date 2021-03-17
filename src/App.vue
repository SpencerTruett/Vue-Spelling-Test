<template>
  <div>
    <Speech :word="questions[activeIndex].word" />
    <form @submit.prevent="handleSubmit">
      <input type="text" spellcheck="false" v-model="userInput" />
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import data from "./data";
import Speech from "./components/Speech"

export default {
  components: {
    Speech
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
      console.log(this.userInput, "test")
    }
  }
}
</script>

<style>
</style>