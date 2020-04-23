<template lang="html">
    <div>
      <p class="heading">Rick <span class="heading-and">and</span> Morty</p>
      <character-list :characters="characters" v-model="selectedCharacter"></character-list>
      <character-detail v-if="selectedCharacter" :character="selectedCharacter"></character-detail>
    </div>
</template>

<script>

import CharacterList from './components/CharacterList.vue';
import {eventBus} from './main.js';
import CharacterDetail from './components/CharacterDetail.vue';


export default {
  name: 'app',
  data() {
    return {
      characters: [],
      selectedCharacter: null,
    }
  },
  mounted() {
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characters = characters.results)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character;
    });
  },
  components: {
    "character-list": CharacterList,
    "character-detail": CharacterDetail,
  }
}
</script>

<style lang="css" scoped>

  .heading {
    font-family: 'RickMortyFont';
    color: #41B4C7;
    text-shadow: -1px -1px 0 #6BA230, 1px -1px 0 #6BA230, -1px 1px 0 #6BA230, 1px 1px 0 #6BA230;
    font-size: 120px;
    text-align: center;
    padding: 25px;
    margin: 0;
  }

  .heading-and {
    font-size: 50px;
  }

</style>

<style>
body {
  background-image: url('./assets/background.png');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  width: 100vw;
  height: 100vh;
  display: block;
  cursor: url('./assets/gun.png'), auto;
}

@font-face {
  font-family: 'RickMortyFont';
  src: url('./assets/fonts/font.ttf');
}
</style>
