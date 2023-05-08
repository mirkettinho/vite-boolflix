
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
    serie: Object
  },
  data(){
    return{
      store,
      star: Math.ceil(this.film.vote_average/2)
    }
  }
}
</script>

<template>
  <div>
    <li>
      <ul>
        <img :src="'https://image.tmdb.org/t/p/w342' + film.poster_path " alt="">
        <li>{{ film.title }}</li>
        <li>{{ film.original_title }}</li>
        <li><MLanguage :language="film.original_language" /></li>
        <li>
          <i v-for="n in star" class="fa-solid fa-star"></i> 
          <i v-for="n in (5 - star)" class="fa-regular fa-star"></i> 
        </li>
      </ul>
    </li>
  </div> 

  <!-- <div>
    <li>
      <ul>
        <li>{{ serie.name }}</li>
        <li>{{ serie.original_name }}</li>
        <li><MLanguage :language="serie.original_language" /></li>
        <li>{{ serie.vote_average }}</li>
      </ul>
    </li>
  </div> -->
  

</template>

<style lang="scss" scoped>
  li{
    color: white;
  }
  h1{
    color: red;
  }
</style>