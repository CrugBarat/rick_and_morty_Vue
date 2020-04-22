<template lang="html">
  <div>
   <img :src="character.image">
   <p>Name: {{character.name}}</p>
   <p>Origin Name: {{character.origin.name}}</p>
   <p>Gender: {{character.gender}}</p>
   <p>Species: {{character.species}}</p>
   <p>Location: {{character.location.name}}</p>
   <p>Status: {{character.status}}</p>
 </div>
</template>

<script>
export default {
  name: 'character-detail',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
