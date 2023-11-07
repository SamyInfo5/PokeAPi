<template>
  <header class="headerPokemon">
  <button> <a href="/acceuil/index.vue">Back To acceuil</a> </button>
    <h1>Voici : {{ $route.params.name }}</h1>
    <img :src="pokemon.sprites.front_default" alt="" />
  </header>
  <main>
    <div>
      <div class="container">
        <div class="classPokemon">
          <h1>Pokemon de Types :</h1>
          <div class="types" v-for="(items, j) in pokemon.types" key="j">
            <p>{{ items.type.name }}</p>
          </div>
        </div>
        <div class="abilitys">
          <h1>Abiliter du Pokemon :</h1>
          <div class="abi" v-for="(items, j) in pokemon.abilities" key="j">
            <p>{{ items.ability.name }}</p>
          </div>
        </div>
        <div class="expBase">
          <h1>Expérience de Base :</h1>
          <div class="exp">
            {{ pokemon.base_experience }}
          </div>
        </div>
        <div class="allAttack">
          <h1>Toutes les attaques que le pokemon peux apprendre</h1>
          <div class="atck">
            <button class="attack" v-for="(items, j) in pokemon.moves" key="j">{{ items.move.name }}</button>
          </div>
        </div>
      </div>
    </div>
  </main>
  <footer>
    <h1>designed by Samuel</h1>
  </footer>
</template>

<script setup>
import "~/assets/singlepkmn.css";
const route = useRoute();
const { data: pokemon } = await useFetch(
  `https://pokeapi.co/api/v2/pokemon/${route.params.name}`
);
console.log(pokemon);
</script>
