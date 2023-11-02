<template>
    <div>
        <h1>Liste des Pokémon</h1>
        <ul>
            <li class="pokemonname" v-for="pokemon in pokemonList" :key="pokemon.id">
                {{ pokemon.name }}
            </li>
        </ul>
    </div>
</template>
  
<script setup>
const pokemonList = ref([]);

const fetchPokemonList = async (offset = 0) => {
    const { data } = await useFetch(`https://pokeapi.co/api/v2/pokemon/?offset=${offset}&limit=1290/`);
    pokemonList.value = data._rawValue.results;
    console.log(data)
};

// Appeler la fonction pour récupérer la liste initiale de Pokémon
fetchPokemonList();
</script>