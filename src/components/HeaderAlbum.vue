<template>
  <header>
      <img :src="require('../assets/img/logo.png')" alt="">
  </header>
</template>

<script>
export default {
    name: 'HeaderAlbum'
};
</script>

<style scoped lang="scss">
    header {
        img {
            max-height: 2.5rem;
        }
    }

</style>