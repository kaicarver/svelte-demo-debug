<script>
  import Board3 from "./Board3.svelte";

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
    console.log("history3: ", history);
    count = history.length;
  }
  $: status = "Next player: " + nextValue;

  function handleClick(s) {
      alert(s);
  }
</script>

<h2>Game 3, Board composed of Squares, but TODO: use function?</h2>
<Board3 bind:squares bind:nextValue handleClick={handleClick}/>

<div class="status">
  {status}
  <br />
  history size: {count}
</div>
