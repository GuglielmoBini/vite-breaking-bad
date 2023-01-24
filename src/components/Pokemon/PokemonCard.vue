<script>
export default {
    name: 'PokemonCard',
    props: {
        name: String,
        image: String,
        number: Number,
        type1: String,
        type2: String
    }
}
</script>

<template>
    <div class="pokemon-card text-center p-3 col-3">
        <img class="img-fluid" :src="image" :alt="name">
        <div class="mt-2">#{{ number }}</div>
        <h5>{{ name }}</h5>
        <div>{{ type1 }} </div>
        <div>{{ type2 }}</div>
    </div>
</template>

<style lang="scss" scoped>
.pokemon-card {
    background-color: white;
    border-radius: 25px;
    border: 2px solid black;
    margin: 10px;

    img {
        width: 250px;
        height: 250px;
        padding: 10px;
        border-radius: 25px;
        object-fit: contain;
        box-shadow: 0 0 20px 2px black;
    }
}
</style>