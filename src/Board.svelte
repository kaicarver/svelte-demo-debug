<script>
  import Square from "./Square.svelte";

  export let squares;
  export let nextValue;
</script>

<style>

</style>

<div>
  <div class="board-row">
    <!-- I wonder if there's a way to number the squares by the DOM element number?... -->
    <Square bind:value={squares[0]} bind:nextValue/>
    <Square bind:value={squares[1]} bind:nextValue/>
    <Square bind:value={squares[2]} bind:nextValue/>
  </div>
</div>
