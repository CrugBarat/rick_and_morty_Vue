<template lang="html">
  <div class="search-container">
    <div class="search-characters-list">
      <input type="text" placeholder="Get Schwearchy......" v-model="searchCharacters">
      <list-item v-if="searchCharacters" v-for="(character, index) in filteredCharacters" :character="character" :key="index"></list-item>
    </div>
  </div>

</template>

<script>
import ListItem from './ListItem.vue';

import {eventBus} from '../main.js'

export default {
  data () {
    return {
      selectedCharacter: null,
      searchCharacters: ""
    }
  },
  name: 'character-list',
  props: ['characters'],
  components: {
    'list-item': ListItem
  },
  computed: {
    filteredCharacters(){
      return this.characters.filter((character) => {
        return character.name.toLowerCase().includes(this.searchCharacters.toLowerCase())
      });
    }
  },
  methods: {
    handleSelect: function () {
      eventBus.$emit('character-selected', this.selectedCharacter)
    }
  }
}
</script>



<style lang="css" scoped>

.search-container {
  display: inline-block;
  text-align: center;
  width: 100vw;
}

.search-characters-list {
  font-size: 30px;
  padding: 30px;
}

input[type=text] {
  width: 350px;
  background-color: transparent;
  height: 30px;
  color: #41B4C7;
  font-size: 30px;
  font-family: 'Bangers', cursive;
}

::placeholder {
  color: #41B4C7;
}

input[type=text] {
  cursor: url('../assets/gun.png'), auto;
}

input:focus {
  outline: none;
}
</style>
