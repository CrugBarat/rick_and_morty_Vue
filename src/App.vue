<template lang="html">
<character-list></character-list>
</template>

<script>

import CharacterList from './components/CharacterList.vue';
import {eventBus} from './main.js';


export default {
  name: 'app',
  data() {
    return {
      characters: [],
      selectedCharacter: null
    }
  },
  mounted() {
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characters = characters)
  },
  components: {
    "character-list": CharacterList
  }
}
</script>

<style lang="css" scoped>
</style>
