<template lang="html">
  <div>
    <h1>Favourite Films:</h1>
    <ul>
      <li v-for="film in checked">{{film.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-film',
  props: ['films']
}
</script>

<style lang="css" scoped>
</style>
