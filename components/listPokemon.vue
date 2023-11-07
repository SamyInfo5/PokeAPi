<template>
    <div>
        <h1>Liste des Pokémon</h1>
        <ul>
            <li class="pokemonname" v-for="pokemon in pokemonList" :key="pokemon.id">
                <NuxtLink :href="`pokemon/${pokemon.name}`">
                    {{ pokemon.name }}
                </NuxtLink>
            </li>
        </ul>
    </div>
</template>
  
<script setup>
const props = defineProps({
    pokemonList: Array
})
</script>