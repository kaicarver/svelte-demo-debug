<script>
  import Square from "./Square.svelte";

  export let squares;
  export let nextValue;
</script>

<style>
  .board-row:after {
    clear: both;
    content: "";
    display: table;
  }
</style>

<div>
  <div class="board-row">
    <!-- I wonder if there's a way to number the squares by the DOM element number?... -->
    <Square bind:value={squares[0]} bind:nextValue/>
    <Square bind:value={squares[1]} bind:nextValue/>
    <Square bind:value={squares[2]} bind:nextValue/>
  </div>
  <div class="board-row">
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
