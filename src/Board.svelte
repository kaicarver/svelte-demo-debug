<script>
  import Square from "./Square.svelte";

  let status = "Next player: X";
  let num = 0;
  let squares = Array(9).fill(null)
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
    <Square value={squares[num++]} />
    <Square value={squares[num++]} />
    <Square value={squares[num++]} />
  </div>
  <div class="board-row">
    <Square value={squares[num++]} />
    <Square value={squares[num++]} />
    <Square value={squares[num++]} />
  </div>
  <div class="board-row">
    <Square value={squares[num++]} />
    <Square value={squares[num++]} />
    <Square value={squares[num++]} />
  </div>
</div>
