<template>
  <main class="bg-secondary p-5">
      <div v-if="pageLoaded == false" class="server-delay">
          <page-loader />
      </div>
      <div v-else-if=" networkError == true" class="server-delay">
          <h1>API Address Error, page item not found! Contact support!</h1>
      </div>
      <div v-else class="row row-cols-lg-6 g-3">
        <card-album v-for="(album, index) in arrAlbum" :key="index" 
        :albumPoster="album.poster"
        :albmTitle="album.title"
        :albumAuthor="album.author"
        :albumYear="album.year"
        :albumGenre="`genre-${album.genre}`"
        />
      </div>
      
  </main>
</template>

<script>
import CardAlbum from './CardAlbum.vue'
import PageLoader from './PageLoader.vue'
import axios from 'axios'
export default {
    name: 'MainAlbum',
    components: {
        CardAlbum,
        PageLoader,
    },
    data () {
        return {
            arrAlbum: [],
            networkError: false,
            responseDelay: 3000,
            pageLoaded: false,

        }
    },
    created () {
        setTimeout (() => {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then((ele) => {
                    this.pageLoaded = true;
                    ele.data.response.forEach(ele => {
                        this.arrAlbum.push(ele);
                })
            
                    
            }) .catch(error => {
                    // handle error
                    console.log(error);
                    this.pageLoaded = true;
                    this.networkError = true;
                });
        }, this.responseDelay);
    },
};
</script>

<style scoped lang="scss">
    .row {
        max-width: 1000px;
        margin: 0 auto;
    }
    .server-delay {
        color: white;
        display:flex;
        justify-content:center;
        align-items:center;
        height:80vh;
    }
</style>