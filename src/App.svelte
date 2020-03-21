<script>
  import Board from "./Board.svelte";

  // configuration of the 9 Tic-tac-toe squares in a board, initially empty
  let squares = Array(3).fill(null);
  // all the successive configurations of the board in a game
  let history = [[...squares]];

  let nextValue = 'X';
  let winner = null;
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
      <ol>
        <ul>
          <!-- /* TODO */ -->
        </ul>
      </ol>
    </div>
  </div>
</main>

<style>
  main {
    font: 14px "Century Gothic", Futura, sans-serif;
    margin: 20px;
  }

  ol,
  ul {
    padding-left: 30px;
  }

  .credits {
    font-size: 50%;
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

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

