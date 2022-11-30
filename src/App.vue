<template>
  <div id="app">
    <HeaderComp @search="searchAll" />
    <MainComp :arrayFilm="FilterFilms" :arraySerie="FilterSerie" />
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
  },
  data(){
    return{
      FilterFilms: [],
      FilterSerie: [],
    }
  },
  mounted(){
  },
  methods: {
    searchAll(valoreInput){
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=22fe714c30b0e22065d5943a4abfc6fa&query=' + valoreInput)
        .then((response)=>{
          this.FilterFilms = response.data.results;
        });
        axios.get('https://api.themoviedb.org/3/search/tv?api_key=22fe714c30b0e22065d5943a4abfc6fa&language=it_IT&query=' + valoreInput)
        .then((response) =>{
          this.FilterSerie = response.data.results;
        })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  height: 100vh;
  background-color: #424242;
}
</style>
