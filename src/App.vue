<template>
  <h1>Ninja Reaction Timer</h1>
  <button class="btn" @click="start()" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Result v-if="showResults" :score="score"/>
</template>
<!--learning vue-->

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  data(){
    return {
      isPlaying: false,
      delay:null,
      score:null,
      showResults: false

    }

  },
  components: { Block,Result },
  methods:{
    start(){
      this.delay=2000+Math.random() * 5000
      this.isPlaying=true
      this.showResults=false
      
    },
    endGame(reactionTime){
      this.score=reactionTime
      this.isPlaying=false
      this.showResults=true



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
.btn{
  background: #0faf07;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin:10px;

}
.btn[disabled]{
  opacity: 0.2;
  cursor: not-allowed;

}
</style>
