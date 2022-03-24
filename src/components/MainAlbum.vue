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
export default {
    name: 'MainAlbum',
    components: {
        CardAlbum
    },
    data () {
        return {
            arrAlbum: null,
        }
    }
};
</script>

<style scoped lang="scss">
    .row {
        max-width: 1000px;
        margin: 0 auto;
    }
</style>