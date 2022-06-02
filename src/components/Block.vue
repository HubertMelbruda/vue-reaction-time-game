<template>
  <div class="block" v-if="isShown" @click="stopTime">
      Click me !!! 
  </div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      isShown: false,
      timer: null,
      reactionTime: 0,
    }
  },
  mounted() {
    setTimeout(() => {
      this.isShown = true
      this.startTime()
    }, this.delay)
  },
  methods: {
    startTime() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    }, 
    stopTime() {
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    },
  }
}
</script>

<style>
  .block {
    width: 400px;
    border-radius: 20px;
    background: #15a267 ;
    color: white;
    text-align: center;
    padding: 100px 10px;
    margin: 40px auto;
  }
</style>