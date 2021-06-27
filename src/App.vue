<template>
  <div id="app">
    <h1>Player: {{ player }}</h1>
    <Board />
  </div>
</template>

<script>
import Board from "./components/Board";

export default {
  name: "App",
  data() {
    return {
      player: "X",
    };
  },
  components: {
    Board,
  },
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 500px;
  flex-direction: column;
}
</style>
