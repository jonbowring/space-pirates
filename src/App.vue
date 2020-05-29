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
          cellTypes: []
        },
        hello: 'world'
      }
    },
    created: function() {
      this.initBoard();
    },
    methods: {
      initBoard: function() {
        
        // Add the planets to the cellTypes array
        for(var i = 0; i < 10; i++) {
          this.settings.cellTypes.push('planet');
        }

        // Add the baubles to the cellTypes array
        for(var k = 0; k < 5; k++) {
          this.settings.cellTypes.push('bauble');
        }

        // Add the space to the cellTypes array
        for(var j = 0; j < 85; j++) {
          this.settings.cellTypes.push('space');
        }

        // Shuffle the cellTypes
        this.shuffle(this.settings.cellTypes);

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

  #app {
    display: flex;
    flex-direction: column;
    justify-items: center;
    align-items: center;
    background: #000;
    color: #fff;
  }
</style>
