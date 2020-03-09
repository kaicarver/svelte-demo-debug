<script>
  import Square from "./Square.svelte";

  let status = "Next player: X";
  let num = 0;
  let init = Array(9).fill('*');
  let squares = init;
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
debug:<br>
init array:<br>
{init}<br>
squares array:<br>
{squares}<br>
<div>
  <div class="status">{status}</div>
  <div class="board-row">
    <Square bind:value={squares[num]}/>{num++}
    <Square bind:value={squares[num]}/>{num++}
    <Square bind:value={squares[num]}/>{num++}
  </div>
  <div class="board-row">
    <Square bind:value={squares[num]}/>{num++}
    <Square bind:value={squares[num]}/>{num++}
    <Square bind:value={squares[num]}/>{num++}
  </div>
  <div class="board-row">
    <Square bind:value={squares[num]}/>{num++}
    <Square bind:value={squares[num]}/>{num++}
    <Square bind:value={squares[num]}/>{num++}
  </div>
</div>
