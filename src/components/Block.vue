<template>
  <div class="block" v-if="isShowed">
      Click this block 
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShowed: false,
    }
  },
  mounted() {
    setTimeout(() => {
      this.isShowed = true
    }, 3000)
  },
  methods: {
    
  }
}
</script>

<style>
  .block {
    width: 400px;
    border-radius: 20px;
    background: #0fb570 ;
    color: white;
    text-align: center;
    padding: 100px 10px;
    margin: 40px auto;
  }
</style>