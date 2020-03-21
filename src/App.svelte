<script>
  import Game1 from "./Game1.svelte";
  import Game2 from "./Game2.svelte";
</script>

<h1>
Mini-tic-tac-toe to illustrate a problem I had with Svelte:
</h1>

<Game1/>
<Game2/>

<p>In Game 1, history works as expected. 
In Game 2, history gets erroneously updated twice for every click in a square.</p>
<p>Game 1 and 2 both use a squares array to store the game's state, 
and add a copy of the state to the history at every move.</p>
<p>The difference is that Game 1 doesn't use a Board component, 
it directly uses Squares components. 
Game 2 uses a Board component, which references the squares, 
so the squares array is used on two levels of components.</p>