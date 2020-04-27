<template lang="html">
    <p @mouseover="mouseOver" @mouseleave="mouseLeave">{{initialEpisode}}</p>
</template>

<script>
export default {
  name: 'episode-list-item',
  props: ['episode'],
  data() {
    return {
      initialEpisode: this.episode.name
    }
  },
  methods: {
    mouseOver(){
      this.initialEpisode = this.episode.episode
    },
    mouseLeave(){
      this.initialEpisode = this.episode.name
    }
  }
}
</script>

<style lang="css" scoped>
  p {
    padding: 0;
    margin: 0;
  }

  p:hover {
    color: #41B4C7;
  }
</style>
