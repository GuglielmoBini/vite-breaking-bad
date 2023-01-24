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
    <div class="pokemon-card text-center p-3 col-3 mb-4">
        <figure>
            <img class="img-fluid" :src="image" :alt="name">
        </figure>
        <figcaption>
            <div>#{{ number }}</div>
            <h5>{{ name }}</h5>
            <div class="d-flex justify-content-center">
                <div class="mx-1">{{ type1 }} </div>
                <div v-if="type2" class="mx-1">{{ type2 }}</div>
            </div>
        </figcaption>
    </div>
</template>

<style lang="scss" scoped>
.pokemon-card {

    img {
        width: 250px;
        height: 250px;
        border-radius: 50%;
        object-fit: cover;
        box-shadow: 0 0 20px 2px black;
    }

    figcaption {
        padding: 10px;
        background-color: white;
        border-radius: 25px;
        box-shadow: 0 0 20px 2px black;

    }
}
</style>