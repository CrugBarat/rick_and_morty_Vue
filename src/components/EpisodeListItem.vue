<template lang="html">
  <div class="episodes">
    <p>{{episode.name}}</p>
  </div>
</template>

<script>
export default {
  name: 'episode-list-item',
  props: ['episode']
}
</script>

<style lang="css" scoped>
  p {
    padding: 0;
    margin: 0;
  }
</style>
