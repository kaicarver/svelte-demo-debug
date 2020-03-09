<script>
  import Square from "./Square.svelte";

  let status = "Next player: X";
  let squares = Array(9).fill(null);
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
    <Square bind:value={squares[0]}/>
    <Square bind:value={squares[1]}/>
    <Square bind:value={squares[2]}/>
  </div>
  <div class="board-row">
    <Square bind:value={squares[3]}/>
    <Square bind:value={squares[4]}/>
    <Square bind:value={squares[5]}/>
   </div>
  <div class="board-row">
    <Square bind:value={squares[6]}/>
    <Square bind:value={squares[7]}/>
    <Square bind:value={squares[8]}/>
  </div>
</div>
