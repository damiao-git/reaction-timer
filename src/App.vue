<template>
  <h1>Ninja Reaction Timer</h1>
  <button class="botao" @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <!-- <p v-if="showResults">Reaction time: {{ score }} ms</p> -->
  <Result v-if="showResults" :score="score"/>
</template>

<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  name: 'App',
  components: {
    Block, Result
  },
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000,
      this.isPlaying = true,
      this.showResults = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}

.botao{
  width: 100px;
  height: 30px;
  background: #2d30f3;
  color: white;
  border-radius: 5px;
  border: none;
}
.botao:hover{
  background: #4446ee;
  color: white;
  border: 1px white;
  cursor: pointer;
  font-weight: bold;
}
.botao[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
