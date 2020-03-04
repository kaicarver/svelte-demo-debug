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

<main>
  <div class="game">
    <div class="game-board">
      <Board />
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
