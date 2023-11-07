<template>
    <header>
    <h1>
        Bienvenue sur le pokédex de Kantho
    </h1>
    </header>
</template>

<script>
const getAllPokemon = () => {
    const { data } = useFetch('https://pokeapi.co/api/v2/pokedex/2/')
    console.log(data)
}

getAllPokemon()
</script>