<template lang="html">
    <option :value="character">{{character.name}}</option>
</template>

<script>

export default {
  name: 'select-item',
  props: ['character'],
}
</script>

<style lang="css" scoped>
</style>
