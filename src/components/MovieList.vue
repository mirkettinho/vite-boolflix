
<script>

import {store} from "../data/store"
import MovieStructure from "./MovieStructure.vue"

export default {
  components: {
    MovieStructure,
    
  },
  name: "MovieList",
  data(){
    return {
      store
    }
  }
}
</script>

<template>
  <div>
    <h1>FILM</h1>
    <ul>
      <MovieStructure :film="film" v-for="film in store.films" :key="film.id"/>
    </ul>
  </div>

  <div>
    <h1>SERIE TV</h1>
    <ul>
      <MovieStructure :serie="serie" v-for="serie in store.series" :key="serie.id"/> -->
    </ul>
  </div>

</template>

<style lang="scss" scoped>
  h1{
    color: red;
  }
</style>