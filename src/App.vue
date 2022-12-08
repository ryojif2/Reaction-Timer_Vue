<template>
  <h1>Reaction Timer</h1>
  <button @click="handleStart" :disabled="startGame">Play</button>
  <BlockTest v-if="startGame" :delay="delay" @stopped="endGame" />
  <ResultsTest v-if="showScore" :score="score" />
</template>

<script>
import BlockTest from "./components/BlockTest.vue";
import ResultsTest from "./components/ResultsTest.vue";
export default {
  name: "App",
  components: { BlockTest, ResultsTest },
  data() {
    return {
      startGame: false,
      delay: null,
      score: 0,
      showScore: false,
    };
  },
  methods: {
    handleStart() {
      this.delay = 2000 + Math.random() * 5000;
      this.startGame = true;
      this.showScore = false;
    },
    endGame(resultTime) {
      this.score = resultTime;
      this.startGame = false;
      this.showScore = true;
    },
  },
};
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
