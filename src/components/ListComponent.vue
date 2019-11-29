<template lang="html">
  <div>
    <li v-on:click="handleClick">{{film.title}}</li>
  </div>
</template>

<script>
import FavouriteFilm from './FavouriteFilm.vue'
import {eventBus} from '../main.js'
export default {
  name:'list-component',
  props:['film'],

  methods: {
    handleClick(){
      eventBus.$emit('film-selected', this.film)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
