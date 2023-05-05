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
    <ul>
      <li v-for="(film,index) in store.films" :key="index" > name: {{ film.title }} --- original name: {{ film.original_title }} --- language: {{ film.original_language }} --- vote: {{ film.vote_average }} </li>
      
    </ul>
  </div>
<hr>
  <div>
    <ul>
      <li v-for="(serie,index) in store.series" :key="index"> name: {{ serie.name }} --- original name: {{ serie.original_name }} --- language: {{ serie.original_language }} --- vote: {{ serie.vote_average }} </li>
    </ul>
  </div>

</template>

<style lang="scss" scoped>
li{
  color: white;
}
</style>