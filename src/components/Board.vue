<template>
	<div class="board">
		<Cell v-for="n in 100" v-bind:key="'cell' + n" v-bind:id="'cell' + n" v-bind:settings="$parent.settings.cells[(n - 1)]"/>
	</div>
</template>

<script>
import Cell from './Cell.vue'

export default {
	name: 'Board',
    components: {
      Cell
    }
}
</script>

<style scoped>
	.board {
		width: 81vh;
		display: grid;
		grid-template-columns: repeat(9, 1fr);
		grid-template-rows: repeat(9, 1fr);
		grid-gap: 0;
		justify-items: center;
		align-items: center;
	}
</style>