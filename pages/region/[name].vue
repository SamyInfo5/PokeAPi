<template>
  <header>
    <h1 class="title">Bienvenue sur le pokédex de {{ route.params.name }}</h1>
  </header>
  <main>
    <div class="container">
      <ol class="pokemonInPokedex">
        <li class="pkdx" v-for="(item, i) in pokemon" key="i">
          <NuxtLink :href="`/pokemon/${item.pokemon_species.name}`">
            {{ item.pokemon_species.name }}
          </NuxtLink>
        </li>
        <div>
      
        </div>
      </ol>
    </div>
  </main>
</template>

<script setup>
const route = useRoute();
const { data } = await useFetch(`https://pokeapi.co/api/v2/region/${route.params.name}`);
const recuppokedex = data.value;
const url = recuppokedex.pokedexes[0].url;
const { data: regionPokedex } = await useFetch(url);
const pokemon = regionPokedex.value.pokemon_entries;


</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  text-decoration: none;
}

.container {
  overflow: scroll;
}

body {
  background: url("/public/assets/bg.jpg");
  background-position: center center;
  background-repeat: no-repeat;
}

.scroll {
  overflow: scroll;
}

header {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #000;
  color: white;
  height: 100px;
}

.title {
  color: white;
}

main {
  display: flex;
  justify-content: flex-end;
  height: 89vh;
  overflow: scroll;
}

.pokemonInPokedex {
  margin-top: 50px;
  margin-bottom: 50px;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  flex-direction: column;
  overflow: scroll;
}

li {
  background: rgb(141, 237, 225);
  list-style: inside url("/assets/pokeball.png");
  width: 200px;
  height: 50px;
}

a {
  font-size: 25px;
}

footer {
  background: black;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
