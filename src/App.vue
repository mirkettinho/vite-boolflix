
<script>
import {store} from "./data/store.js"
import axios from "axios"
import Header from "./components/Header.vue"
import SearchBar from "./components/SearchBar.vue"
import MovieList from "./components/MovieList.vue"





export default {
  name:"App",
  data(){
    return{
      store
    }
  },
  components:{
    Header,
    SearchBar,
    MovieList
  },
  methods:{
    getApi(){
      store.ricerca = this.store.ricerca.trim();

      if(store.ricerca){
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.apiKey}&language=it-IT&query=${store.ricerca}`) .then(result =>{
          //console.log (result.data.results)
          store.films = result.data.results
          console.log(store.films)
        });

        // axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${store.apiKey}&language=it-IT&query=${store.ricerca}`) .then(result =>{
        //   console.log (result.data.results)
        //   store.series = result.data.results
        // });

        }
      }
    }
}

</script>

<template>
  
  <Header/>

  <SearchBar @search="getApi"/>

  <MovieList/>

</template>

<style lang="scss">

@use "./scss/main.scss";


</style>