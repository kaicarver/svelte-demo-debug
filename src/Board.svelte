<script>
  import Square from "./Square.svelte";

  let status = "Next player: X";
  let num = 0;
  let squares = Array(9).fill('*')
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
debug: squares array: {squares}
<div>
  <div class="status">{status}</div>
  <div class="board-row">
    <Square bind:value={squares[num++]} />
    <Square bind:value={squares[num++]} />
    <Square bind:value={squares[num++]} />
  </div>
  <div class="board-row">
    <Square bind:value={squares[num++]} />
    <Square bind:value={squares[num++]} />
    <Square bind:value={squares[num++]} />
  </div>
  <div class="board-row">
    <Square bind:value={squares[num++]} />
    <Square bind:value={squares[num++]} />
    <Square bind:value={squares[num++]} />
  </div>
</div>
