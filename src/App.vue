<template lang="html">

</template>

<script>
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
