<template>
	<div class="card s4 col" :class="{amber: amber}">
		<div class="card-image">
			<img :src="perso.photo">
			<span class="card-title">{{ perso.nom }} {{ perso.prenom }}</span>
			<a @click="removePerso" class="btn-floating btn-large waves-effect waves-light red">
				<i class="material-icons">delete</i>
			</a>

		</div>

		<div class="card-content">
			<p>{{ perso.sexe|sexe }}</p>
			<p>{{ perso.biographie }}</p>
		</div>
		<div class="card-action">
			<a href="#">This is a link</a>
		</div>
	</div>
</template>
<script>
export default {
	name: "liste",
	methods: {
		removePerso: function(){
			 // J'emet un evenement parent qui s'appel remove()
				this.$emit('remove');
		},
		baratheon: function(biographie){
			let regex = new RegExp(/Baratheon/,"i");
			return regex.test(biographie);
		}
	},
	computed: {
		amber: function(){
			let regex = new RegExp(/Baratheon/,"i");
			return regex.test(this.perso.biographie);	
		}
	},
	filters: {
		sexe: function(persoSexe){
			if(persoSexe == false){
				return "C'est une femme";
			}else{
				return "C'est un homme";
			}
		}
	},
	props: {
		perso: {
			type: Object,
			default: function(){
				return {}
			}
		}
	}
}
</script>