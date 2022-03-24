<template>
  <div id="app">
    <header-album />
    <main-album />
    <footer-album />
  </div>
</template>

<script>
import HeaderAlbum from './components/HeaderAlbum.vue'
import MainAlbum from './components/MainAlbum.vue'
import FooterAlbum from './components/FooterAlbum.vue'

export default {
  name: 'App',
  components: {
    HeaderAlbum,
    MainAlbum,
    FooterAlbum,
  }
}
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";
@import "../node_modules/bootstrap/scss/functions";
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";

</style>
