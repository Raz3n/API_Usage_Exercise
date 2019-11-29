<template>
  <div>
    <h1>Studio Ghibli: Howl's Moving API</h1>
    <film-list :films="films"></film-list>
    <film-detail :film ="selectedFilm"></film-detail>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import FavouriteFilm from './components/FavouriteFilm.vue'
import FilmDetail from './components/FilmDetail.vue'
import FilmList from './components/FilmList.vue'

export default {
  name: 'app',
  data(){
    return {
      films: [],
      selectedFilm: null,
      people: []
    }
  },
  components: {
    "film-list": FilmList,
    "film-detail": FilmDetail,
    "favourite-film": FavouriteFilm
  },
    mounted(){
      fetch("https://ghibliapi.herokuapp.com/films/")
      .then(res => res.json())
      .then(films => this.films = films)

      eventBus.$on('film-selected', (film) => {
        this.selectedFilm = film;
      })
    }
  }

</script>

<style lang="css" scoped>
</style>
