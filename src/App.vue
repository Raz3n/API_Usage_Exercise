<template>
  <div>
    <h1>Studio Ghibli: Howl's Moving API</h1>
    <film-list :films="films"></film-list>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import FavouriteFilm from './components/FavouriteFilm.vue'
import FilmDetail from './components/FilmDetail.vue'
import FilmList from './components/FilmList.vue'
export default {
  name: 'app',
  data() {
    return {
      films: [],
      people: []
    }
  },
  components: {
    "film-list": FilmList,
    "film-detail": FilmDetail,
    "favourite-film": FavouriteFilm
  },
    mounted() {
      fetch("https://ghibliapi.herokuapp.com/films/")
      .then(res => res.json())
      .then(data => this.films = data),

      fetch("https://ghibliapi.herokuapp.com/people/")
      .then(res => res.json())
      .then(data => this.people = data)

    }


  }

</script>

<style lang="css" scoped>
</style>
