<script>
  import Square from "./Square.svelte";

  let status;
  let squares = Array(9).fill(null);
  let nextValue = 'X';
  let winner = null;
  $: squares, console.log('squares has been updated, non-nulls: ' + squares.filter(x => x != null).length);
  $: {
    winner = calculateWinner(squares);
    if (winner) {
      status = "Winner: " + winner;
      nextValue = null;
    } else {
      status = "Next player: " + nextValue;
    }
    // console.log("calculated") // why is this code executed twice for every click?
  }

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
  <div class="status">{status}</div>
  <div class="board-row">
    <!-- I wonder if there's a way to number the squares by the DOM element number?... -->
    <Square bind:value={squares[0]} bind:nextValue/>
    <Square bind:value={squares[1]} bind:nextValue/>
    <Square bind:value={squares[2]} bind:nextValue/>
  </div>
  <div class="board-row">
  {@debug} 
    <Square bind:value={squares[3]} bind:nextValue/>
    <Square bind:value={squares[4]} bind:nextValue/>
    <Square bind:value={squares[5]} bind:nextValue/>
   </div>
  <div class="board-row">
    <Square bind:value={squares[6]} bind:nextValue/>
    <Square bind:value={squares[7]} bind:nextValue/>
    <Square bind:value={squares[8]} bind:nextValue/>
  </div>
</div>
