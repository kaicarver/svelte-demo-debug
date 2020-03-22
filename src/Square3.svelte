<script>
  export let value;
  export let nextValue;

  function handleClick() {
    if (nextValue) {
      value = nextValue;
      nextValue = nextValue == "X" ? "Q" : "X";
    }
  }
</script>

<button class="square" on:click={handleClick}>
  {value || ''}
</button>

<style>
  .square {
    float: left;
    padding: 0;
    height: 34px;
    width: 34px;
    line-height: 24px;
  }
</style>