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

<style scoped>
.pokemonname {
  background: #FDF9C7;
  color: #515251;
  margin-top: 10px;
  font-size: 40px;
  list-style: inside url("/assets/pokeball.png");
  border-top-left-radius: 50px;
  border-bottom-left-radius: 50px;
}
</style>