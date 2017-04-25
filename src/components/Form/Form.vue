<template>
	<form>
		<label>Nom</label>
		<input type="text" placeholder="Le nom" class="validate">

		<button type="button" class="btn" @click="add">Envoyer</button>
	</form>

</template>

<script>

	export default{
		name: 'form',
		methods: {
			add(){
				this.$emit('addPersonnage', "mon code")
			}
		}

	}

</script>