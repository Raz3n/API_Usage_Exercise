<template lang="html">
  <div>
    <li v-on:click="handleClick">{{film.title}}
      <label v-on:click="handleFavClick" class="totoro-checkbox" :class="isFavouriteTotoro()"></label>
    </li>
  </div>
</template>

<script>
import FavouriteFilm from './FavouriteFilm.vue'
import {eventBus} from '../main.js'
export default {
  name:'list-component',
  props:['film', 'isChecked'],
  data(){
    return {
      checked: []
    }
  },
  methods: {
    isFavouriteTotoro(){
      if (this.isChecked) {
        return 'favourited'
      }
    },
    handleClick(){
      eventBus.$emit('film-selected', this.film)
    },

    handleFavClick(){
      eventBus.$emit('favourite-films', this.film)
  }
 }
}
</script>

<style lang="css" scoped>
</style>
