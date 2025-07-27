<template>
  <p class="react"> Reaction time {{ score }} ms </p>
  <p class="rank"> {{ rank }} </p>
</template>

<script>
export default {
props:['score'],
data(){
  return{
  rank: null
  }
},
  mounted(){
    if(this.score < 250){
      this.rank = 'Ninja fingers'
    } else if(this.score < 400){
      this.rank = 'Rapid Reflexes'
    } else {
      this.rank = 'Snail pace ...'
    }
  }
}
</script>

<style>
.rank{
  font-size: 30px;
  color: blueviolet;
  font-weight: 900;
}
.react{
  margin-top: 40px;
  margin-bottom: -25px;
  font-size: 15px;
}
</style>
