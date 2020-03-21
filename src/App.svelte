<script>
  import Square from "./Square.svelte";

  let squares = Array(3).fill(null);
  let history;
  console.log("history: ", history);
  let nextValue = "X";
  let status;
  let count = 0;

  $: {
    if (history)
      history.push([...squares]);
    else
      history = [];
    console.log("history: ", history);
    status = "Next player: " + nextValue;
    count = history.length;
  }
</script>

<div>
  <Square bind:value={squares[0]} bind:nextValue/>
  <Square bind:value={squares[1]} bind:nextValue/>
  <Square bind:value={squares[2]} bind:nextValue/>
</div>

<div class="status">
  {status}
  <br />
  history size: {count}
</div>
