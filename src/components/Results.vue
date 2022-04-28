<template>
  <p>Reaction time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null,
    }
  },
  mounted() {
    if (this.score < 300) {
      this.rank = "Fast as lightning!"
    } else if (this.score < 450) {
      this.rank ="You did great!"
    } else {
      this.rank = "Drink more coffee and try one more time!"
    }
  }
}
</script>

<style>
  .rank {
    font-size: 1.6em;
    color: #15a267;
    font-weight: bold;
  }
</style>