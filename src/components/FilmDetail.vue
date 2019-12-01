<template lang="html">
  <div id="film-detail" v-if="film">
    <div id="detailWrapper">
    <h1>{{film.title}}</h1>
    <div id="flexWrapper">
    <p><b>Released: </b>{{film.release_date}}</p>
    <p><b>Director: </b> {{film.director}}</p>
    <p><b>Description: </b>{{film.description}}</p>
  </div>
</div>
</div>

</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']
}
</script>

<style lang="css" scoped>
#flexWrapper {
    box-sizing: border-box;
    height: 350px;
    width: 60%;
    background: #eee;
    color: #222;
    padding: 10px;
    border: 1px solid #ccc;
  }

</style>
