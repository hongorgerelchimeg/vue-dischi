<template>
  <main class="bg-secondary p-5">
      <div class="row">
        <card-album 
        
        />
      </div>
  </main>
</template>

<script>
import CardAlbum from './CardAlbum.vue'
import axios from 'axios'
export default {
    name: 'MainAlbum',
    components: {
        CardAlbum
    },
    data () {
        return {
            arrAlbum: null,
        }
    },
    created () {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((ele) => {
                ele.data.response.forEach(ele => {
                    this.arrAlbum.push(ele);
                });
                
        })
    },
};
</script>

<style scoped lang="scss">
    .row {
        max-width: 1000px;
        margin: 0 auto;
    }
</style>