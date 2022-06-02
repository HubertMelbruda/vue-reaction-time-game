<template>
  <div class="score-table">
    <h4>Scores:</h4>
    <p v-for="(score, index) in scores" :key="index" :class="{ bestScore: getTheBestScore(score)}">
      {{ index + 1 }}. {{ score }} ms
    </p>
  </div>
</template>

<script>
export default {
  props: ["scores"],
  data() {
    return {
      scoresToDisplay: [],
    }
  },
  methods: {
    getTheBestScore(score) {
      return score === Math.min(...this.scores) ? 'bestScore' : ''
    }
  },
}
</script>

<style>
.score-table {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 20px;
  width: 200px;
  min-height: 400px;
  border: 1px solid black;
  border-radius: 10px;
}

.bestScore {
  color: #f40d0d;
}
</style>
