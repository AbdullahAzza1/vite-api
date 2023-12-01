<script>
import { store } from "../store.js"

export default {
    name: "AppSearch",
    data() {
        return {
            store
        }
    },
    methods: {
        search() {
            console.log("Cerca: ", this.store.searchString);
            this.$emit("search");
        }
    },
}
</script>

<template>
    <div>
        <h1>the 10 best breweries in Austria</h1>
        <input type="text" placeholder="search..." v-model="store.searchString" @keyup.enter="$emit('search')">
        <button @click="search">search</button>
    </div>
</template>

<style scoped></style>