
<script>
import {store} from "../data/store"
import MLanguage from "../components/MLanguage.vue"

export default {
  components: {
    MLanguage
  },
  name: "MovieStructure",
  props: {
    film: Object,
  },
  data(){
    return{
      store
    }
  }
}
</script>

<template>
  <li>
    <ul>
      <li>{{ film.title }}</li>
      <li>{{ film.original_title }}</li>
      <li><MLanguage :language="film.original_language" /></li>
      <li>{{ film.vote_average }}</li>
    </ul>
  </li>
</template>

<style lang="scss" scoped>
  li{
    color: white;
  }
</style>