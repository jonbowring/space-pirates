<template>
	<div class="board">
		<Cell v-for="n in 200" v-bind:key="'cell' + n"/>
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
		width: 100%;
		display: grid;
		grid-template-columns: repeat(20, 1fr);
		grid-template-rows: repeat(10, 1fr);
	}
</style>