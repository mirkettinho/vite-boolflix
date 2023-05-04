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
  <input type="text" name="searchBar" v-model="store.ricerca" placeholder="inserisci il nome del film/serieTv" >
  <button value="Search" @click="$emit('search')">cerca</button>

  <div>
    <ul>
      <li v-for="(film,index) in store.films" :key="index"> name: {{ film.name }} --- original name: {{ film.original_name }} --- language: {{ film.original_language }} --- vote: {{ film.vote_average }}</li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
li{
  color: white;
}
</style>