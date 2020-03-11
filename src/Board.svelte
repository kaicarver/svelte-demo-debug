<script>
  import Square from "./Square.svelte";

  let status = "Next player: X";
  let squares = Array(9).fill(null);
  $: onclick = 'Y';
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
    <Square bind:value={squares[0]} {onclick}/>
    <Square bind:value={squares[1]} {onclick}/>
    <Square bind:value={squares[2]} {onclick}/>
  </div>
  <div class="board-row">
    <Square bind:value={squares[3]} {onclick}/>
    <Square bind:value={squares[4]} {onclick}/>
    <Square bind:value={squares[5]} {onclick}/>
   </div>
  <div class="board-row">
    <Square bind:value={squares[6]} {onclick}/>
    <Square bind:value={squares[7]} {onclick}/>
    <Square bind:value={squares[8]} {onclick}/>
  </div>
</div>
