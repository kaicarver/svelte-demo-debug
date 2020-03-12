<script>
  import Square from "./Square.svelte";

  let status = "Next player: ";
  let squares = Array(9).fill(null);
  let onclick = 'X';
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
  <div class="status">{status} {onclick}</div>
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
