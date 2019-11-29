<template lang="html">
  <div id="Film-List">
    <ul>
      <List-component v-for="film in films" :film="film"></List-component>
    </ul>

  </div>

</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
</style>
