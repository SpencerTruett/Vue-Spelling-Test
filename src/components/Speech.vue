<template>
  <button @click="sayWord">Say Word</button>
</template>

<script>
export default {
  props: ["word"],
  methods: {
    sayWord() {
      const voices = window.speechSynthesis.getVoices();
      const utterance = new SpeechSynthesisUtterance(this.word);
      utterance.voice = voices[4];
      speechSynthesis.speak(utterance);
    }
  }
}
</script>

<style>
</style>