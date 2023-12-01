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
            <h2> name of the brewery: {{ info.name }}</h2>
            <p>adress: {{ info.address_1 }}</p>
            <p>city: {{ info.city }}</p>
            <p>phone: {{ info.phone }}</p>
        </div>
    </div>
</template>

<style scoped>
.card-wrapper {
    padding: 5px;
    width: calc(100%/4);
}

.card {
    padding: 1rem;
    background: maroon;
    color: rgb(255, 255, 255);
}

.card img {
    width: 100%;
}
</style>