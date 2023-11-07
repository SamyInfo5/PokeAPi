<template>
    <header>
        <h1>
            Bienvenue sur le pokédex de Kantho
        </h1>
    </header>
    <main>
        <div class="pokemonInPokedex">
                <div class="zo" v-for="(item, i) in pokemonList" key="i">
                    {{ item.pokemon_species.name }}
                </div>
        </div>
    </main>
</template>

<script setup>
const pokemonList = ref([])
  const { data } = await useFetch("https://pokeapi.co/api/v2/pokedex/2/");
  console.log('Data', data.value)
  pokemonList.value = data.value.pokemon_entries
  console.log('pokemonList', pokemonList)
</script>