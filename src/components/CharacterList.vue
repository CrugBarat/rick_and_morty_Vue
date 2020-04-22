<template lang="html">
  <div>
    <select v-on:change="handleSelect" v-model="selectedCharacter">
      <select-item v-for="(character, index) in characters" :character="character" :key="index"></select-item>
    </select>
  </div>

</template>

<script>
// import ListItem from './ListItem.vue';
import SelectItem from './SelectItem.vue';

import {eventBus} from '../main.js'

export default {
  data () {
    return {
      selectedCharacter: null
    }
  },
  name: 'character-list',
  props: ['characters'],
  components: {
    'select-item': SelectItem
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
