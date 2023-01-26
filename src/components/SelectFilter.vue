<script>
import { store } from '../data/store';
export default {
    name: 'SelectFilter',
    data() {
        return {
            store,
            selectedChoice: '',
        }
    },
    emits: ['change-choice']
};
</script>

<template>
    <section id="select-filter" class="mb-5 d-flex justify-content-center">
        <select class="form-select w-25 text-center" v-model=selectedChoice
            @change="$emit('change-choice', selectedChoice)">
            <option value="" selected>--</option>
            <option v-for="pokemonType in store.pokemonTypes" :key="pokemonType" :value="pokemonType">{{ pokemonType }}
            </option>
        </select>
    </section>
</template>