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
    },
    data: function() {
      return {
        settings: {
          cells: []
        }
      }
    },
    created: function() {
      this.initBoard();
    },
    methods: {
      initBoard: function() {
        
        // Initialise the empty cells array
        var cells = new Array(81);
        
        // Add the planets to the cells array
        cells[40] = {cellType: 'planet', cellName: 'Earth'};
        cells[20] = {cellType: 'planet', cellName: 'Mars'};
        cells[24] = {cellType: 'planet', cellName: 'Saturn'};
        cells[60] = {cellType: 'planet', cellName: 'Jupiter'};
        cells[56] = {cellType: 'planet', cellName: 'Pluto'};

        // Add the baubles to the cells array
        cells[4] = {cellType: 'bauble', cellName: 'Skull cove'};
        cells[36] = {cellType: 'bauble', cellName: 'Treasure rock'};
        cells[44] = {cellType: 'bauble', cellName: 'Sparkle sparkle'};
        cells[76] = {cellType: 'bauble', cellName: 'Blackbeards chest'};

        console.log(cells);

        // Fill in any empty cells
        for(var j = 0; j < cells.length; j++) {
          if(typeof cells[j] == 'undefined' || cells[j] == null) {
            cells[j] = {cellType: 'space', cellName: ''};
          }
        }

        // Save the array
        this.settings.cells = cells;
        

      },
    shuffle: function(array) {
        var currentIndex = array.length, temporaryValue, randomIndex;

        // While there remain elements to shuffle...
        while (0 !== currentIndex) {

        // Pick a remaining element...
        randomIndex = Math.floor(Math.random() * currentIndex);
        currentIndex -= 1;

        // And swap it with the current element.
        temporaryValue = array[currentIndex];
        array[currentIndex] = array[randomIndex];
        array[randomIndex] = temporaryValue;
        }

        return array;
      }
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    background: #000;
  }

  #app {
    display: flex;
    flex-direction: column;
    justify-items: center;
    align-items: center;
    color: #fff;
  }
</style>
