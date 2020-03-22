<script>
  import Square from "./Square3.svelte";

  export let squares;
  export let nextValue;
  export let handleClick;
</script>

<div on:click={handleClick(squares)}>
  <Square bind:value={squares[0]} bind:nextValue/>
  <Square bind:value={squares[1]} bind:nextValue/>
  <Square bind:value={squares[2]} bind:nextValue/>
</div>
