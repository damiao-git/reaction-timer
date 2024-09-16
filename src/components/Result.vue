<template>
  <div class="block red">
    <h3>Your result is : </h3>
    <p>{{ score }} ms</p>
    <p v-if="result">{{ result }}</p>
  </div>
</template>

<script>
export default {
    props : [
        'score'
    ],
    data(){
        return{
            result : null
        }
    },
   
}
</script>

<style>
    
</style>