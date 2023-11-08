<template>
  <header>
    <div class="container">
      <button>
        <NuxtLink href="/"> Home </NuxtLink>
      </button>
      <h1>PokeApi NuxtJs</h1>
    </div>
  </header>
  <main>
    <div class="">
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
              <p>{{ item.location_area.name }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
  <footer>
    <h1>designed by SamyCode</h1>
  </footer>
</template>

<script setup>
const id = ref(1);
const pokemonList = ref([]);

const { data } = await useFetch(`
  https://pokeapi.co/api/v2/pokemon/${id.value}
`);

const { data: localisation } = await useFetch(
  `https://pokeapi.co/api/v2/pokemon/${id.value}/encounters`
);

const fetchPokemonList = async (offset = 0) => {
  const { data } = await useFetch(
    `https://pokeapi.co/api/v2/pokemon/?offset=${offset}&limit=1290/`
  );
  pokemonList.value = data._rawValue.results;
};

fetchPokemonList();
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  overflow: hidden;
}

header {
  background-color: #d88001;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 100px;
  color: white;
}

main {
  background: #6078a1;
  height: 80vh;
  overflow: scroll;
  display: flex;
  flex-direction: column;
}

footer {
  background-color: #d88001;
  height: 9vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 10px;
}

.container {
  width: 90%;
  margin: 0 auto;
}

.pokemonBox {
  display: flex;
  height: 300px;
  padding-top: 40px;
}

.pokemonImage {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.pokemon {
  width: 100%;
  overflow: scroll;
}

.listPokemon {
  display: flex;
  justify-content: center;
  align-items: center;
}

.statOfPokemon {
  font-size: 40px;
  justify-content: space-around;
  padding-top: 20px;
  display: flex;

  & h6 {
    color: white;
  }
}

.caract {
  padding-top: 50px;
  display: flex;
  width: 100%;
  justify-content: space-around;
}

.types {
  & p {
    color: white;
    font-size: 30px;
  }
}

.localisation {
  & p {
    color: white;
    font-size: 30px;
  }
}
</style>
