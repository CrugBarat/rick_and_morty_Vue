<template lang="html">
  <div>
    <h1>Rick & Morty</h1>
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
</style>
