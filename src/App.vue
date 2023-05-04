
<script>
import {store} from "./data/store.js"
import axios from "axios"
import Header from "./components/Header.vue"
import Container from "./components/Container.vue"
import SearchBar from "./components/SearchBar.vue"



export default {
  name:"App",
  data(){
    return{
      store
    }
  },
  components:{
    Header,
    Container,
    SearchBar
  },
  methods:{
    getApi(){
      store.ricerca = this.store.ricerca.trim();

      if(store.ricerca){
        axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${store.apiKey}&query=${store.ricerca}`) .then(result =>{
          console.log (result.data.results)
          store.films = result.data.results
        })
        }
      }
    }
}

</script>

<template>
  
  <Header/>

  <SearchBar @search="getApi"/>

  <Container/>

</template>

<style lang="scss">

@use "./scss/main.scss";


</style>