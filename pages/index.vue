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
              <listPokemon/>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="detailsPokemon">
      <div class="container">
        <div class="statOfPokemon">
          <div class="stat" v-for="(item, i) in data.stats" key="i">
            {{ item.stat.name }} : {{ item.base_stat }}
          </div>
        </div>
      </div>
    </div>
  </main>
  <footer>
    <div class="container">
      <div class="containeFooter"></div>
    </div>
  </footer>
</template>

<script setup>
import "~/assets/styles.css";
const id = ref(1);
const { data } = await useFetch(`https://pokeapi.co/api/v2/pokemon/${id.value}`);

</script>
