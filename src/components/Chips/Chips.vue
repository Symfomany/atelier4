<template>
	<div class="chip" :class="{cyan: cyan, 'red lighten-1': red}">
		<span v-if="nb > 0">{{ nb }} personnage<span v-if="nb > 1">s</span></span>
		<span v-else>Aucun personnage</span>
	</div>
</template>
<script>
export default {
	name: "chips",
	computed: {
		cyan: function(){
			return this.nb >= 7;
		},
		red: function(){
				return this.nb < 3 ;
		}
	},
	props: {
		nb: {
			type: Number
		}
	}
}

</script>