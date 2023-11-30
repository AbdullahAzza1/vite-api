<script>

export default {
    name: "Birrerie",
    props: {
        info: Object
    },


}

</script>

<template>
    <div class="card-wrapper">
        <div class="card">
            <img :src="info.id" />
            <h2> nome della birreria: {{ info.name }}</h2>

        </div>
    </div>
</template>

<style scoped>
.card-wrapper {
    padding: 1rem;
    width: 50%;
}

.card {
    padding: 1rem;
    background: orangered;
    color: white;
}

.card img {
    width: 100%;
}
</style>