<template>
  <header class='bg-primary p-2 d-flex justify-content-between align-items-center'>
      <img :src="require('../assets/img/logo.png')" alt="">
      

  </header>
</template>

<script>


export default {
    
    name: 'HeaderAlbum',
    data () {
        return {
            searchString: '',
        }
    },

};
</script>

<style scoped lang="scss">
    header {
        
        img {
            max-height: 2.5rem;
            margin-left: 1rem;
        }
    }

</style>