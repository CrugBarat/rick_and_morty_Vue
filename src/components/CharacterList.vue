<template lang="html">
  <div>
    <input type="text" placeholder="Search" v-model="searchCharacters">
    <list-item v-if="searchCharacters" v-for="(character, index) in filteredCharacters" :character="character" :key="index"></list-item>
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
</style>
