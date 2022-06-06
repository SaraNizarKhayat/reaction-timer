<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
      <p> How fast are you!! </p>
    </div>
</template>

<script>
export default {
  props:['delay'],
  data(){
    return {
      showBlock: false,
      timer:null,
      reactionTime: 0
    }
  },
  mounted(){
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods:{
    startTimer(){
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer(){
      clearInterval(this.timer),
      console.log(this.reactionTime)
      this.$emit('end', this.reactionTime)
    }
  } 
}
</script>

<style scoped>
.block{
  width: 400px;
  padding: 70px;
  margin: 100px auto;
  background-color: blueviolet;
  border-radius: 10px; 
}

p{
  color: aliceblue;
  border: none;
  padding: 10px;
}
</style>