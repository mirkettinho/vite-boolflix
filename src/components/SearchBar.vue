<script>
import {store} from "../data/store";



export default {
  name: "SearchBar",
  data(){
    return{
      store
    }
  }
}

</script>

<template>
  <input type="text" name="searchBar" v-model="store.ricerca" placeholder="inserisci il nome del film/serieTv"  @keyup.enter="$emit('search')">
  <button value="Search" @click="$emit('search')">cerca</button>

  <div>
    <h1>films</h1>
    <ul>
      <li v-for="(film,index) in store.films" :key="index" >
        <div>
          <img :src="'https://image.tmdb.org/t/p/w342' + film.poster_path " alt="">
        </div>
         name: {{ film.title }} --- original name: {{ film.original_title }} --- language: {{ film.original_language }} --- vote: {{ film.vote_average }} 
        </li>
      
    </ul>
  </div>

  <div>
    <h1>tv series</h1>
    <ul>
      <li v-for="(serie,index) in store.series" :key="index">
        <div>
          <img :src="'https://image.tmdb.org/t/p/w342' + serie.poster_path " alt="">
        </div>
         name: {{ serie.name }} --- original name: {{ serie.original_name }} --- language: {{ serie.original_language }} --- vote: {{ serie.vote_average }} </li>
      <!-- <img src="src/assets/img/en.png" alt=""> -->
    </ul>
  </div>

</template>

<style lang="scss" scoped>
h1{
  font-size: 40px;
  color: red;
}
li{
  color: white;
}
</style>cccprova
