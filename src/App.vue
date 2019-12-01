<template>
  <div id="app">
    <h1>Studio Ghibli: Howl's Moving API</h1>
    <film-list :films="films" :checked="checked"></film-list>
    <film-detail :film ="selectedFilm"></film-detail>
    <favourite-film :checked="checked"></favourite-film>
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
      checked: []
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

      fetch("https://ghibliapi.herokuapp.com/people")
      .then(res => res.json())
      .then(people => this.people = people)

      eventBus.$on('film-selected', (film) => {
        this.selectedFilm = film;
      })
// below is now films yet to see but I am in too deep currently
      eventBus.$on('favourite-films', (film) => {
        if(!this.checked.includes(film)){
          this.checked.push(film)}
          else {
            const foundFilm = this.checked.indexOf(film)
            this.checked.splice(foundFilm, 1)
          }
        })
       }
      }

</script>

<style lang="css" scoped>

</style>
