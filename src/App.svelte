<script>
  import Board from "./Board.svelte";

  let squares = Array(3).fill(null);
  let history = [[...squares]];
  let nextValue = 'X';
  let status;
  let count = 0;

  $: squares, console.log('squares has been updated, non-nulls: ' + squares.filter(x => x != null).length);
  $: {
    history.push([...squares]);
    console.log(history)
    status = "Next player: " + nextValue;
    count = history.length;
    console.log("calculated") // why is this code executed twice for every click?
  }

</script>

<svelte:head>
	<title>Svelte DEBUG Tic-tac-toe</title>
</svelte:head>

<main>
  <div class="game">
    <div class="game-board">
      <Board bind:squares bind:nextValue/>
    </div>
    <div class="game-info">
      <div class="status">
        {status}<br>
        history size: {count}
      </div>
    </div>
  </div>
</main>

<style>
  main {
    font: 14px "Century Gothic", Futura, sans-serif;
    margin: 20px;
  }

  .game {
    display: flex;
    flex-direction: row;
  }

  .game-info {
    margin-left: 20px;
  }

  .status {
    margin-bottom: 10px;
  }
</style>

