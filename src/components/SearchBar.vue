<template>
  <form @submit.prevent=""> 
    <select v-model="strSearch" @change="emitSearch" class="custom-select">
        <option v-for="(options, index) in arrOptions" :key="index" :value="options">{{options}}</option>
    </select>
  </form>
</template>

<script>
export default {
    name: 'SearchBar',
    data () {
        return {
            strSearch: '',
            arrOptions: [],
        }
    },
    methods: {
        emitSearch () {
            this.$emit('search', this.strSearch);
            console.log(this.strSearch);
        }
    },
    props: {
       arrAlbumProp: Array,
    },
    created () {
        this.arrOptions = this.arrAlbumProp;
    }
}
</script>

<style>

</style>