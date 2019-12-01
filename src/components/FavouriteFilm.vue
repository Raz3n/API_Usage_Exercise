<!-- favourite film should be "Yet to be seen", need to plan better. -->
<template lang="html">
  <div class="topcorner">
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
.topcorner {
  position:absolute;
   top: 80px;
   right: 40px;
   border-style:outset;
   padding-top: 10px;
   padding-right: 20px;
   padding-bottom: 10px;
   padding-left: 20px;
   font-weight: bold;
   
}


</style>
