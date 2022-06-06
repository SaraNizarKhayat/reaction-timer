<template>
  <h1> Let's play together </h1>
  <button @click="start" :disabled="isPlaying" class="play"> PLAY </button>
    <block v-if="isPlaying" :delay="delay" @end ="endGame"/>
    <results v-if="showResult" :score="score"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components:{ Block , Results},
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },
  methods:{
    start(){
        this.isPlaying = true
        this.delay = 1000 + Math.random() * 3000
        this.showResult = false
      },
      endGame(reactime){
        this.score = reactime
        this.isPlaying = false
        this.showResult = true
      }
  }
}
</script>

<style>
body{
  text-align: center;
}
#app{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
button{
  padding: 15px;
  border: none;
  background-color: blueviolet;
  color: aliceblue;
  font-weight: bold;
  border-radius: 5px;
}
</style>
