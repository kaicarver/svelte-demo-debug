<script>
  import Board from "./Board.svelte";

  let squares = Array(3).fill(null);
  let history;
  let nextValue = "X";
  let status;
  let count = 0;

  $: {
    if (history)
      history.push([...squares]);
    else
      history = [];
    console.log("history2: ", history);
    count = history.length;
  }
  $: status = "Next player: " + nextValue;
</script>

<h2>Game 2, composed of a Board, itself composed of 3 Squares:</h2>
<Board bind:squares bind:nextValue/>

<div class="status">
  {status}
  <br />
  history size: {count}
</div>
