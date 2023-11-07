<template>
    <header class="headerPokemon">
        <h1>Voici : {{ $route.params.name }} <img :src="pokemon.sprites.front_default" alt=""></h1>
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

                <h1>Abiliter du Pokemon :</h1>
                <div class="types" v-for="(items, j) in pokemon.abilities" key="j">
                    <p>{{ items.ability.name }}</p>
                </div>

                <h1>Expérience de Base :</h1>
                <div class="exp">
                    {{ pokemon.base_experience }}
                </div>

                <h1>Toutes les attaques que le pokemon peux apprendre</h1>
                <div class="types" v-for="(items, j) in pokemon.moves" key="j">
                    <h3 class="attack">{{ items.move.name }}</h3>
                </div>
            </div>
        </div>
    </main>
    <footer>
        <h1>designed by Samuel</h1>
    </footer>
</template>

<script setup>
import "~/assets/singlepokmn.css";
const route = useRoute()
const { data: pokemon } = await useFetch(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`)
console.log(pokemon)
</script>