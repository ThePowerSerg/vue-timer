<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block-Delay v-if="isPlaying" :delay="delay"/>
</template>

<script>
import BlockDelay from './Block-Delay.vue'
export default {
  components: { BlockDelay },
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: { 
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
