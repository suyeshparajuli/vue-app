<template>
  <h1>reaction timer</h1> 
  

  <button @click="start" :disabled="isPlaying">click me</button>
   <Block v-if="isPlaying"  :delay="delay" @end="endGame" />
   <Result v-if="playing" :score="score"/>
  
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'
export default {
  name: 'App',
  components: { Block, Result },
  data(){
    return{
    isPlaying: false,
    delay: null,
    score:null,
    playing:false
  }
},
  methods:{
    start() {
      this.delay = 2000 + Math.random()*6000,
      this.isPlaying = true,
      this.playing = false,


      console.log(this.delay)
    },
    endGame(stopCounter){
      this.score = stopCounter
      this.isPlaying = false
      console.log("yeash")
      this.playing= true
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
