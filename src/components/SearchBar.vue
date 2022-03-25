<template>
  <form @submit.prevent=""> 
    <select v-model="strSearchAutor" @change="emitSearchArtist" class="custom-select">
        <option value="">--Choose by an Artist--</option>
        <option v-for="(options, index) in arrArtistOptions" :key="index" :value="options">{{options}}</option>
    </select>
     <select v-model="strSearch" @change="emitSearch" class="custom-select">
        <option value="">--Choose an genre--</option>
        <option v-for="(options, index) in arrOptions" :key="index" :value="options">{{options}}</option>
    </select>
  </form>
</template>

<script>
export default {
    name: 'SearchBar',
    data () {
        return {
            strSearchAutor: '',
            strSearch: '',
            arrOptions: [],
            arrArtistOptions: [],
        }
    },
    methods: {
        emitSearch () {
            this.$emit('search', this.strSearch);
            
        },
        emitSearchArtist () {
            this.$emit('searchArtist', this.strSearchAutor);
            
        }

    },
    props: {
       arrAlbumProp: Array,
       arrArtistProp: Array,
    },
    created () {
        this.arrOptions = this.arrAlbumProp;
        this.arrArtistOptions = this.arrArtistProp;
    }
}
</script>

<style>

</style>