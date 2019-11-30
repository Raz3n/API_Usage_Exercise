<template lang="html">
  <div>
    <li v-on:click="handleClick">{{film.title}}
      <label for="checkbox"></label>
      <input v-on:change="handleChange" type="checkbox" :value="checked">

    </li>
  </div>
</template>

<script>
import FavouriteFilm from './FavouriteFilm.vue'
import {eventBus} from '../main.js'
export default {
  name:'list-component',
  props:['film'],
  data(){
    return {
      checked: [],
    }
  },
  methods: {
    handleClick(){
      eventBus.$emit('film-selected', this.film)
    },

    handleChange(){
      eventBus.$emit('favourite-films', this.film)
  }
 }
}
</script>

<style lang="css" scoped>
.totoro-checkbox {
  cursor: pointer;
}

</style>
