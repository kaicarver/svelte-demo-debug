<script>
  import Square from "./Square.svelte";

  let status = "Next player: ";
  let squares = Array(9).fill(null);
  let onclick = 'X';

  function calculateWinner(squares) {
    const lines = [
      [0, 1, 2],
      [3, 4, 5],
      [6, 7, 8],
      [0, 3, 6],
      [1, 4, 7],
      [2, 5, 8],
      [0, 4, 8],
      [2, 4, 6],
    ];
    for (let i = 0; i < lines.length; i++) {
      const [a, b, c] = lines[i];
      if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
        return squares[a];
      }
    }
    return null;
  }
</script>

<style>
  .board-row:after {
    clear: both;
    content: "";
    display: table;
  }

  .status {
    margin-bottom: 10px;
  }
</style>

<div>
  <div class="status" on:click={alert(calculateWinner(squares))}>{status} {onclick}</div>
  <div class="board-row">
    <!-- I wonder if there's a way to number the squares by the DOM element number?... -->
    <Square bind:value={squares[0]} bind:onclick/>
    <Square bind:value={squares[1]} bind:onclick/>
    <Square bind:value={squares[2]} bind:onclick/>
  </div>
  <div class="board-row">
    <Square bind:value={squares[3]} bind:onclick/>
    <Square bind:value={squares[4]} bind:onclick/>
    <Square bind:value={squares[5]} bind:onclick/>
   </div>
  <div class="board-row">
    <Square bind:value={squares[6]} bind:onclick/>
    <Square bind:value={squares[7]} bind:onclick/>
    <Square bind:value={squares[8]} bind:onclick/>
  </div>
</div>
