<template>
  <div>
    <p>Results: {{ correctCount }} / {{ data.length }}</p>
    <p v-if="perfectScore">Perfect Score!</p>
  </div>
</template>

<script>
export default {
  props: ["questions"],
  computed:{
    correctCount(){
        return this.data.filter(q => {
        return q.word.toLowerCase() === q.userInput.toLowerCase();
      }).length;
    },
    perfectScore(){
      return this.correctCount === this.data.length;
    }
  }
}
</script>

<style>
</style>