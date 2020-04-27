<template lang="html">
  <li>{{episode.name}}</li>
</template>

<script>
export default {
  name: 'episode-list-item',
  props: ['episode']
}
</script>

<style lang="css" scoped>

li {
  list-style: none;
  color: white;
}
</style>
