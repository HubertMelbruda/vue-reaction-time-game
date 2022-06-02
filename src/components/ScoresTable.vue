<template>
  <div class="score-table">
    <h4>Scores:</h4>
    <p v-for="(score, index) in scores" :key="index">
      {{ index }}. {{ score }} ms
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
</style>
