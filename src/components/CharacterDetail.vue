<template lang="html">
  <div class="details-container">
    <div class="char-details">
      <img :src="character.image">
      <p class="name-font">{{character.name}}</p>
      <p>{{character.origin.name}}</p>
      <p>{{character.gender}}</p>
      <p>{{character.species}}</p>
      <p>{{character.location.name}}</p>
      <p>{{character.status}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'character-detail',
  props: ['character']
}
</script>

<style lang="css" scoped>

.details-container {
  display: block;
  text-align: center;
}

.char-details {
  border: dashed 3px #fff;
  border-radius: 20%;
  width: 350px;
  color: #fff;
  font-size: 20px;
  display: inline-block;
  font-family: 'Montserrat', sans-serif;
  text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
}

.char-details:hover {
  background-color: #41B4C7;
}

img {
  border-radius: 50%;
  height: 100px;
}

p {
  margin: 0;
  padding: 0;
}

.name-font {
  font-family: 'Bangers', cursive;
  font-size: 25px;
}
</style>
