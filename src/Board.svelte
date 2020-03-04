<script>
  import Square from "./Square.svelte";

  let status = "Next player: X";
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
    <Square value="1" />
    <Square value="2" />
    <Square value="3" />
  </div>
  <div class="board-row">
    <Square />
    <Square />
    <Square />
  </div>
  <div class="board-row">
    <Square />
    <Square />
    <Square />
  </div>
</div>
