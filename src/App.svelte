<script>
  import Board from "./Board.svelte";
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

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<svelte:head>
	<title>Svelte Tic-tac-toe</title>
</svelte:head>

<main>
  <div class="game">
    <div class="game-board">
      <Board />
      <p class="credits">
        <a href="https://github.com/kaicarver/svelte-demo">Source on Github</a>,
        adapted for
        <a href="https://svelte.dev/">Svelte</a>
        after
        <a href="https://github.com/kaicarver/react-demo">doing</a>
        the excellent
        <a href="https://reactjs.org/tutorial/tutorial.html">React tutorial</a>.
      </p>
    </div>
    <div class="game-info">
      <div>
        <!-- /* status */ -->
      </div>
      <ol>
        <ul>
          <!-- /* TODO */ -->
        </ul>
      </ol>
    </div>
  </div>
</main>
