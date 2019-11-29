<template lang="html">
  <div>
    <h1>Studio Ghibli: Howl's Moving API</h1>

  </div>

</template>

<script>
import FavouriteFilm from './components/FavouriteFilm.vue'
import FilmDetail from './components/FilmDetail.vue'
import FilmList from './components/FilmList.vue'
export default {
  name: 'app',
  data() {
    return {
      films: []
    }
  },
    mounted() {
      fetch('https://ghibliapi.herokuapp.com/films')
      .then(res => res.json)
      .then(films => this.films = films)
    }
  }

</script>

<style lang="css" scoped>
</style>
