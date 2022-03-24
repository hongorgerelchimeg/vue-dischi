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
$primary: #2D3A46;
$secondary: #1E2D3B;

@import "~bootstrap/scss/bootstrap";
@import "~bootstrap/scss/functions";
@import "~bootstrap/scss/variables";
@import "~bootstrap/scss/mixins";


</style>
