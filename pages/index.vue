<template>
  <header>
    <div class="container">
      <h1>PokeApi NuxtJs</h1>
    </div>
  </header>
  <main>
    <div>
      <div class="container">
        <div class="pokemonBox">
          <div class="pokemonImage">
            <img :src="data.sprites.front_default" alt="" />
          </div>
          <div class="pokemon">
            <div class="listPokemon">
              <listPokemon :pokemonList="pokemonList" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="detailsPokemon">
      <div class="container">
        <div class="statOfPokemon">
          <div class="stat" v-for="(item, i) in data.stats" key="i">
            <h6>{{ item.stat.name }} : {{ item.base_stat }}</h6>
          </div>
        </div>
        <div class="caract">
          <div>
            <h1>Types</h1>
            <div class="types" v-for="(items, j) in data.types" key="j">
              <p>{{ items.type.name }}</p>
            </div>
          </div>
          <div>
            <h1>localisation</h1>
            <div class="localisation" v-for="(item, k) in localisation" key="k">
              <pre>{{ item.location_area.name }}</pre>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import "~/assets/styles.css";

const id = ref(1);
const pokemonList = ref([])

const { data } = await useFetch(`
  https://pokeapi.co/api/v2/pokemon/${id.value}
`);

const { data: localisation } = await useFetch(
  `https://pokeapi.co/api/v2/pokemon/${id.value}/encounters`
);

const fetchPokemonList = async (offset = 0) => {
  const { data } = await useFetch(`https://pokeapi.co/api/v2/pokemon/?offset=${offset}&limit=1290/`);
  pokemonList.value = data._rawValue.results;
  console.log('pokemonList', pokemonList.value)
};



fetchPokemonList();
</script>
