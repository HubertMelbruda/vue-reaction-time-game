<template>
    <h1>Play a game and check your reflex</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <div v-if="!showResult" class="game-space">Game space</div>
    <Block v-if="isPlaying" :delay="delay" @end="endGame" />
    <Results v-if="showResult" :score="score" />
</template>

<script>
import Block from "./components/Block.vue"
import Results from "./components/Results.vue"

export default {
  name: "App",
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false,
    }
  },
  components: {
    Block,
    Results,
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResult = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResult = true
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin: 60px auto;
  max-width: 900px;
  position: relative;
  box-sizing: border-box;
}

button {
  font-size: 1.4em;
  width: 120px;
  background: #15a267;
  color: #ffffff;
  border: 1px black solid;
  border-radius: 5px;
  padding: 8px 15px;
  cursor: pointer;
}

button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}

.game-space {
  position: absolute;
  left: 260px;
  top: 120px;
  width: 350px;
  border-radius: 20px;
  border: 1px solid black;
  padding: 90px 10px;
  margin: 40px auto;
  z-index: -1;
}
</style>
