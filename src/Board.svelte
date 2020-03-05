<script>
  import Square from "./Square.svelte";

  let status = "Next player: X";
  let num = 1;
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
    <Square value={num++} />
    <Square value={num++} />
    <Square value={num++} />
  </div>
  <div class="board-row">
    <Square value={num++} />
    <Square value={num++} />
    <Square value={num++} />
  </div>
  <div class="board-row">
    <Square value={num++} />
    <Square value={num++} />
    <Square value={num++} />
  </div>
</div>
