<template>
	<div class="cell" v-bind:class="[activeClass]">
		<span>{{ this.settings.cellName }}</span>
	</div>
</template>

<script>
export default {
	name: 'Cell',
	props: {
		id: String,
		settings: Object
	},
	created: function() {
		
		// Set the style for the cell type
		switch(this.settings.cellType) {
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
	mounted: function() {
		
		// Save the cell screen position
		this.position = {
			vMiddle: (this.$el.offsetTop + ( this.$el.offsetWidth / 2 )),
			hMiddle: (this.$el.offsetLeft + ( this.$el.offsetHeight / 2 ))
		}

	},
	data: function() {
		return {
			activeClass: '',
			position: null
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
		text-align: center;
	}

	.planet {
		background: url('../assets/planet-1.png');
		background-repeat: none;
		background-size: contain;
		background-position: center;
	}

	.bauble {
		background: url('../assets/asteroid-1.png');
		background-repeat: none;
		background-size: contain;
		background-position: center;
	}

	.space {
		background: #000;
	}
</style>