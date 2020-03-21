<script>
  import Square from "./Square.svelte";

  export let squares;
  export let nextValue;
</script>

<div>
  <Square bind:value={squares[0]} bind:nextValue/>
  <Square bind:value={squares[1]} bind:nextValue/>
  <Square bind:value={squares[2]} bind:nextValue/>
</div>
