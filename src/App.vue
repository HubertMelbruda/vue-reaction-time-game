<template>
  <h1>Play a game and check your reflex </h1>
  <button @click="start">Play</button>
  <div v-if="isPlaying">
    <Block />
  </div>
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null, 
    }
  }, 
  components: {
    Block,
  }, 
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
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

button {
  font-size: 1.4em;
  background: #0fb570;
  color: #ffffff;
  border: 1px black solid;
  border-radius: 5px;
  padding: 8px 15px;
  cursor: pointer;
}

</style>
