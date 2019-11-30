<template lang="html">
  <div id="film-list">
    <ul>
      <list-component v-for="film in films" :film="film" :isChecked="checked.includes(film)"></list-component>
    </ul>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue';
export default {
  name: 'film-list',
  props: ['films', 'checked'],
  components: {
    "list-component": ListComponent
  }
}
</script>

<style lang="css" scoped>
</style>
