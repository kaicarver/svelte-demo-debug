<script>
  import Board from "./Board.svelte";

  let squares = Array(9).fill(null);
  let nextValue = 'X';
  let winner = null;
  let status;

  $: squares, console.log('squares has been updated, non-nulls: ' + squares.filter(x => x != null).length);
  $: {
    winner = calculateWinner(squares);
    if (winner) {
      status = "Winner: " + winner;
      nextValue = null;
    } else {
      status = "Next player: " + nextValue;
    }
    // console.log("calculated") // why is this code executed twice for every click?
  }

  function calculateWinner(squares) {
    const lines = [
      [0, 1, 2],
      [3, 4, 5],
      [6, 7, 8],
      [0, 3, 6],
      [1, 4, 7],
      [2, 5, 8],
      [0, 4, 8],
      [2, 4, 6],
    ];
    for (let i = 0; i < lines.length; i++) {
      const [a, b, c] = lines[i];
      if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
        return squares[a];
      }
    }
    return null;
  }
</script>

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

<svelte:head>
	<title>Svelte Tic-tac-toexx</title>
</svelte:head>

<main>
  <div class="game">
    <div class="game-board">
      <Board bind:squares bind:nextValue/>
    </div>
    <div class="game-info">
      <div class="status">
        {status}
      </div>
      <ol>
        <ul>
          <!-- /* TODO */ -->
        </ul>
      </ol>
    </div>
  </div>
  <p class="credits">
    <a href="https://github.com/kaicarver/svelte-demo">Source on Github</a>,
    adapted for
    <a href="https://svelte.dev/">Svelte</a>
    after
    <a href="https://github.com/kaicarver/react-demo">doing</a>
    the excellent
    <a href="https://reactjs.org/tutorial/tutorial.html">React tutorial</a>.
  </p>
</main>
