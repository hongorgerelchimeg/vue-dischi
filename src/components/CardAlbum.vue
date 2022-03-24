<template>
  <div class="col-6 col-md-4 col-lg-2 card">
      <img :src="albumPoster" alt="">
      <h1>{{albmTitle}}</h1>
      <p>{{albumAuthor}}</p>
      <p>{{albumYear}}</p>  
  </div>
</template>

<script>
export default {
    name: 'CardAlbum',
    props: {
        albumPoster: String,
        albmTitle:String,
        albumAuthor:String,
        albumYear:String,
    }
};
</script>

<style scoped lang="scss">
    .card {
      height: 30vh;
      h1 {
          color: white;
          font-size: 1em;
      }
      p {
          color: #756D62;
          font-size: .8em;
      }
    }
</style>