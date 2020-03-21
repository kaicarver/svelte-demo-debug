<script>
  import Board from "./Board.svelte";

  let squares = Array(3).fill(null);
  let history = [[...squares]];
  console.log("history: ", history);
  let nextValue = "X";
  let status;
  let count = 0;

  $: {
    // why is this code executed twice for every click?
    history.push([...squares]);
    console.log("history: ", history);
    status = "Next player: " + nextValue;
    count = history.length;
  }
</script>

<Board bind:squares bind:nextValue />

<div class="status">
  {status}
  <br />
  history size: {count}
</div>
