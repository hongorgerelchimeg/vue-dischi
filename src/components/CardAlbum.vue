<template>
  <div class="col-6 col-md-4 col-lg ms-lg-2 me-lg-2 pt-3 text-center card bg-primary">
      <img class="img-fluid" :src="albumPoster" :alt="albmTitle" :data="albumGenre">
      <h1 class="mt-3">{{albmTitle}}</h1>
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
        albumGenre:String,
    }
};
</script>

<style scoped lang="scss">
    .card {
      min-height: 30vh;
      h1 {
          color: white;
          font-size: 1em;
      }
      p {
          color: #8d8e87;
          font-size: .8em;
      }
    }
</style>