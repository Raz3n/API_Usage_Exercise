<template lang="html">
  <div>
    <h3>Films yet to see:</h3>
    <ul>
      <li v-for="film in checked">{{film.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-film',
  props: ['film', 'checked']
}
</script>

<style lang="css" scoped>
ul {
  font-weight: bold;
}

</style>
