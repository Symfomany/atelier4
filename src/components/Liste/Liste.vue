<template>
	<div>
		<p> Nb: <b>{{ personnages.length }}</b> personnages </p>
		<chips :nb="2"></chips>

		<div class="row">
			<card @remove="removeListe(personnage)" :key="personnage.id" :perso="personnage" v-for="personnage in personnages"></card>
		</div>


		<div>
			<form-create @addPersonnage="addListe($event)"></form-create>
		</div>

		<div v-if="personnages.length === 0" class="progress">
			<div class="indeterminate"></div>
		</div>
	</div>
</template>


<script>

import Card from '@/components/Card/Card'
import Chips from '@/components/Chips/Chips'
import Form from '@/components/Form/Form'

export default {
	name: "liste",
	components: {card: Card, chips: Chips, formCreate: Form},
	data() {
		return {
			personnages: []
		}
	},
	methods: {
		addListe: function(content){
			console.log('coucou tu veux voir...' + content);
		},
		removeListe: function(personnage){
			console.log(personnage);
			this.personnages.splice(this.personnages.indexOf(personnage), 1);
		}
	},
	created: function(){
		this.$http.get('https://raw.githubusercontent.com/Symfomany/angu/master/datas/got.json').then(function(response) {
			this.personnages = JSON.parse(response.body);
		});
	}
}

</script>