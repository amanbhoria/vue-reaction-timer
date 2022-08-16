<template>
<div>
  <h1>Reaction Timer</h1>
  <button class="btn btn-dark" @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResult" :score="score"/>
</div>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue';
export default {
  data() {
    return {
      isPlaying : false,
      delay : null,
      score : null,
      showResult : false,
      dummyShowResult : false
    }
  },
  name: 'App',
  components: {
    Block,
    Results
},
  methods: {
    start() {
      this.delay = 500 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true
    }
  },
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

</style>
