<template lang="html">
  <div id="film-detail" v-if="film">
    <h1>{{film.title}}</h1>
    <p><b>Released: </b>{{film.release_date}}</p>
    <p><b>Director: </b> {{film.director}}</p>
    <p><b>Description: </b>{{film.description}}</p>
  </div>

</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']
}
</script>

<style lang="css" scoped>
</style>
