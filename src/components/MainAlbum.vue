<template>
  <main class="bg-secondary p-5">
      <div v-if="pageLoaded == false" class="server-delay">
          <page-loader />
      </div>
      <div v-else-if=" networkError == true" class="server-delay">
          <h1>API Address Error, page item not found! Contact support!</h1>
      </div>

      <div v-else class="row row-cols-lg-6 g-3">
        <card-album v-for="(album, index) in searchAlbum" :key="index" 
        :albumPoster="album.poster"
        :albmTitle="album.title"
        :albumAuthor="album.author"
        :albumYear="album.year"
        :albumGenre="`genre-${album.genre}`"
        />
      </div>
      <search-bar 
      :arr-album-prop="arrOptions"
      :arr-artist-prop="arrOptionsArtist"
      class="search-bar-absolute" 
      @searchArtist="stringPassArtist" 
      @search="stringPassAgain" />
      
  </main>
</template>

<script>
import CardAlbum from './CardAlbum.vue'
import PageLoader from './PageLoader.vue'
import axios from 'axios'
import SearchBar from './SearchBar.vue';
export default {
    name: 'MainAlbum',
    components: {
        CardAlbum,
        PageLoader,
        SearchBar,
    },
    data () {
        return {
            arrAlbum: [],
            networkError: false,
            responseDelay: 3000,
            pageLoaded: false,
            arrOptions: [''],
            arrOptionsArtist: [''],
            searchString: '',
            strArtist: '',
            combinedFilterArr: [],

        }
    },
    methods: {
        stringPassAgain(strSearch) {
            this.searchString = strSearch;
            console.log(this.searchString);
        },
        stringPassArtist(strArtistPass) {
            this.strArtist = strArtistPass;
            console.log(this.strArtist);
        }
    },
    created () {
        setTimeout (() => {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then((ele) => {
                    this.pageLoaded = true;
                    ele.data.response.forEach(ele => {
                        this.arrAlbum.push(ele);
                        if (!this.arrOptions.includes(ele.genre)) {
                                return this.arrOptions.push(ele.genre);
                        }
                        if (!this.arrOptionsArtist.includes(ele.author)) {
                                return this.arrOptionsArtist.push(ele.author);
                            }
                })
            
                    
            }) .catch(error => {
                    // handle error
                    console.log(error);
                    this.pageLoaded = true;
                    this.networkError = true;
                });
        }, this.responseDelay);

    },
    computed: {
        searchAlbum() {
            if (this.searchString == 'All') {
                return this.arrAlbum;

               
            } else {
                return this.arrAlbum.filter((objCharacter) => objCharacter.genre.includes(this.searchString)).filter((objChar) => objChar.author.includes(this.strArtist));
                }
      
        },
    }
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
        height: 70vh;
    }
    .search-bar-absolute {
        position: absolute;
        top: 1rem;
        right: 30px
    }
</style>