<template>
    <header>
        <div class="container">
            <h1>PokeApi NuxtJs</h1>
        </div>
    </header>
    <main>
        <div>
            <div class="container">
                <div v-if="pokemon" class="pokemonBox">
                    <div class="pokemonImage">
                        <img :src="pokemon.sprites.front_default" alt="Pokemon Image" />
                    </div>
                    <div class="pokemon">
                        <div class="listPokemon">
                            <h1>{{ pokemon.name }}</h1>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="detailsPokemon">
            <div class="container">
                <div class="statOfPokemon">
                    <h1>coucou</h1>
                </div>
            </div>
        </div>
    </main>
    <footer>
        <div class="container">
            <div class="containeFooter">
            </div>
        </div>
    </footer>
</template>

<script setup>
</script>