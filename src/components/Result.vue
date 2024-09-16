<template>
  <div class="block red">
    <h3>Your result is : </h3>
    <p>{{ score }} ms</p>
    <p>{{ rank }}</p>
  </div>
</template>

<script>
export default {
    props : [
        'score'
    ],
    data(){
        return{
            rank : null
        }
    },
    mounted(){
      if(this.score < 250 ) {
        this.rank = 'Ninja Fingers'
      } else if (this.score < 400){
        this.rank = 'Rapid Reflexes'
      } else {
        this.rank = 'Snail pace'
      }
    }
   
}
</script>

<style>
    
</style>