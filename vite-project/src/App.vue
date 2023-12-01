<script>
import Birrerie from "./components/Birrerie.vue"
import AppSearch from "./components/AppSearch.vue";
import axios from 'axios';
import { store } from "./store.js";

export default {
	components: {
		Birrerie,
		AppSearch
	},
	data() {
		return {
			store,
		}
	},
	mounted() {
		this.getCharacters();
	},
	methods: {
		getCharacters() {
			let ricerca = this.store.apiUrl;

			if (this.store.searchString.length) {
				ricerca += `?name=${this.store.searchString}`;
			}

			console.log("ho trovato:", ricerca);

			axios.get(ricerca).then(r => {
				this.store.birrerie = r.data.results;
			});
		}
	}

}
</script>

<template>
	<header>
		<AppSearch @search="getCharacters" />
	</header>
	<main>
		<div class="contain">
			<Birrerie v-for="birrerie in store.birrerie" :info="birrerie" />
		</div>
	</main>
</template>

<style scoped>
header {
	text-align: center;
	color: white;
	padding: 3rem;
}

.contain {

	display: flex;
	flex-wrap: wrap;
	background-color: green;
}

main {
	width: 70%;
	margin: 0 auto;

	display: flex;
	flex-wrap: wrap;
}
</style>