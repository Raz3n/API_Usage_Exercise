<template lang="html">
  <div id="film-detail" v-if="beer">
    <h1>{{film.title}}</h1>
    <p>{{film.release_date}}</p>
    <p>{{film.director}}</p>
    <p>{{film.description}}</p>
  </div>

</template>

<script>
export default {
  name: 'film-detail',
  props: ['films']
}
</script>

<style lang="css" scoped>
</style>
