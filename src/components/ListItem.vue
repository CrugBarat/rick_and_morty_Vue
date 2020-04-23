<template lang="html">
  <div class="list-items-container">
    <div class="list-items">
      <li v-on:click="handleClick"> <img :src="character.image"> {{character.name}}</li>
    </div>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'list-item',
  props: ['character'],
  methods: {
    handleClick: function () {
      eventBus.$emit('character-selected', this.character)
    }
  }
}
</script>

<style lang="css" scoped>

li {
  list-style-type: none;
}

.list-items-container {
  display: block;
  font-family: 'Bangers', cursive;
  color: white;
  text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
}

.list-items:hover {
  background-color: #97ce4c;
}

.list-items {
  border: dashed 3px;
  width: 350px;
  display: inline-block;
}

img {
  border-radius: 50%;
  height: 40px;
}
</style>
