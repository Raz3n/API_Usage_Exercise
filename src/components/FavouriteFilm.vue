<template lang="html">
  <div>
    <h1>Films yet to see:</h1>
    <ul>
      <li v-for="film in checked">{{film.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-film',
  props: ['films', 'checked']
}
</script>

<style lang="css" scoped>
</style>
