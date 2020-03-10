<script>
  export let value = '?';
</script>

<style>
  .square {
    background: #fff;
    border: 1px solid #999;
    float: left;
    font-size: 24px;
    font-weight: bold;
    line-height: 24px;
    height: 34px;
    margin-right: -1px;
    margin-top: -1px;
    margin-bottom: 0px;
    border-radius: 0px;
    padding: 0;
    padding-bottom: 1px;
    text-align: center;
    width: 34px;
  }

  .square:focus {
    outline: none;
  }

  .square:focus {
    background: #ddd;
  }
</style>

<button class="square" on:click={() => value = value == 'X' ? 'O' : 'X'}>{value || ''}</button>
