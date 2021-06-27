<template>
  <div class="board">
    <div v-for="(n, i) in 9" :key="i">
      <Square @click="handleClick" :value="i" :handlePlay="squares[i]" />
    </div>
    <div v-for="(na, ia) in 9" :key="ia">
      <p>{{ vetor[ia] }}</p>
      <button @click="teste3">Trocar</button>
    </div>
  </div>
</template>

<script>
import Square from "./Square";

export default {
  components: {
    Square,
  },
  data() {
    return {
      turn: true,
      squares: Array(9).fill(null),
      vetor: Array(9).fill("A"),
    };
  },
  methods: {
    handleClick(i) {
      if (this.squares[i] === null) {
        const played = this.turn ? "X" : "O";
        this.turn = !this.turn;
        this.$set(this.squares, i, played);
        this.winner(this.squares);
      }
    },
    winner(squares) {
      const possiveis = [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
      ];

      possiveis.forEach((p) => {
        if (
          squares[p[0]] &&
          squares[p[0]] === squares[p[1]] &&
          squares[p[0]] === squares[p[2]]
        ) {
          console.log("venceu");
        }
      });
    },
    teste3() {
      this.vetor[3] = "B";
    },
  },
};
</script>

<style>
.board {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
</style>