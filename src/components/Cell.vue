<template>
	<div class="cell" v-bind:class="[activeClass]">
		<span>{{ type }}</span>
	</div>
</template>

<script>
export default {
	name: 'Cell',
	props: ['id','type'],
	created: function() {
		
		// Set the style for the cell type
		switch(this.type) {
			case 'planet':
				this.activeClass = 'planet';
				break;
			case 'space':
				this.activeClass = 'space';
				break;
			case 'bauble':
				this.activeClass = 'bauble';
				break;
			default:
				break;
		}
	},
	data: function() {
		return {
			activeClass: ''
		}
	}
}
</script>

<style scoped>
	.cell {
		border: solid 1px #fff;
		height: 10vh;
		width: 10vh;
		display: grid;
		grid-template-columns: 1fr;
		grid-template-rows: 1fr;
		justify-items: center;
		align-items: center;
	}

	.planet {
		background: #0000FF;
	}

	.bauble {
		background: #FF0000;
	}

	.space {
		background: #000;
	}
</style>