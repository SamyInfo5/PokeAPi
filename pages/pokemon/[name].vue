<template>
  <header class="headerPokemon">
    <button> <a href="/acceuil">Back To acceuil</a> </button>
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
const route = useRoute();
const { data: pokemon } = await useFetch(
  `https://pokeapi.co/api/v2/pokemon/${route.params.name}`
);
console.log(pokemon);
</script>

<style scoped>
header {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: black;

  & button {
    margin-right: 10px;
    height: 50px;
    width: 125px;
    border-radius: 15px;
  }

  & h1 {
    color: white;
  }
}

main {
  display: flex;
  justify-content: flex-center;
  align-items: flex-start;
  overflow: scroll;
  background-color: red;
  height: 80vh;
}

footer {
  background-color: black;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 10vh;
}

.classPokemon {
  display: flex;

  & h1 {
    color: white;
    margin-right: 20px;
  }

  & .types p {
    color: white;
    font-size: 30px;
    padding-right: 10px;
  }
}

.abilitys {
  display: flex;

  & h1 {
    color: white;
    margin-right: 20px;
  }

  & .abi p {
    color: white;
    font-size: 30px;
    padding-right: 10px;
  }
}

.expBase {
  display: flex;
  justify-content: flex-end;
  align-items: flex-center;

  & h1 {
    color: white;
    margin-right: 20px;
  }

  & .exp {
    color: white;
    font-size: 20px;
  }
}

.allAttack {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  & h1 {
    color: white;
  }

  & .atck button {
    height: 90px;
    width: 120px;
    margin: 9px;
  }
}
</style>
