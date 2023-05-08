
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
  <ul>
    <MovieStructure :film="film" v-for="film in store.films" :key="film.id"/>
  </ul>
</template>

<style lang="scss" scoped>

</style>