<script>
import Birrerie from "./components/Birrerie.vue"

import axios from 'axios';
import { store } from "./store.js";

export default {
  components: {
    Birrerie
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
      axios.get(this.store.apiUrl).then(risultato => {
        this.store.birrerie = risultato.data.results;
      });
    }
  }

}
</script>

<template>
  <main>
    <Birrerie v-for="birrerie in store.birrerie" :info="birrerie" />
  </main>
</template>

<style scoped>
main {
  width: 80%;
  margin: 0 auto;

  display: flex;
  flex-wrap: wrap;
}
</style>