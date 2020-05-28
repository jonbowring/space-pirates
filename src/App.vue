<template>
  <div id="app">
    <Board/>
  </div>
</template>

<script>
  import Board from './components/Board.vue'

  export default {
    name: 'App',
    components: {
      Board
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
