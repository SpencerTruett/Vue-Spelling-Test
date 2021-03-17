<template>
  <form @submit.prevent="handleSubmit">
    <input type="text" spellcheck="false" v-model="userInput" />
    <button type="submit">Submit</button>
  </form>
</template>

<script>
import data from "./data";

export default {
  data() {
    return {
      questions: data,
      activeIndex: 0,
      userInput: ""
    };
  }
}
</script>

<style>
</style>