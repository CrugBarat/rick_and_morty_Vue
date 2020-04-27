<template lang="html">
  <div v-if="episodes" class="episode-container">
  <div  class="episode-list">
    <p class="name-font">Episode List</p>
      <episode-list-item v-for="(episode, index) in episodes" :key="index" :episode="episode"></episode-list-item>
  </div>
  </div>
</template>

<script>

import EpisodeListItem from './EpisodeListItem'
export default {
  name: 'episode-list',
  props: ['episodes'],
  components: {
    'episode-list-item': EpisodeListItem
  }
}
</script>

<style lang="css" scoped>

.episode-container {
  display: block;
  text-align: center;
  margin-top: 10px;
}

.episode-list {
  border: dashed 3px #fff;
  width: 500px;
  color: #fff;
  font-size: 20px;
  display: inline-block;
  font-family: 'Montserrat', sans-serif;
  text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
}

.episode-list:hover {
  background-color: #6BA230;
}

p {
  margin: 0;
  padding: 0;
}

.name-font {
  font-family: 'Bangers', cursive;
  font-size: 25px;
  padding-bottom: 5px;
}
</style>
