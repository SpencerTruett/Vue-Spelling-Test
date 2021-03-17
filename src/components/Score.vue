<template>
  <p>Results: {{ correctCount }} / {{ data.length }}</p>
</template>

<script>
export default {
  props: ["questions"],
  computed:{
    correctCount(){
        return this.data.filter(q => {
        return q.word.toLowerCase() === q.userInput.toLowerCase();
      }).length;
    }
  }
}
</script>

<style>
</style>