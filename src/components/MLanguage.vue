<script>
import {store} from "../data/store"

export default {
  name: "Language",
  props: {
    language: String
  },
  data(){
    return{
      store,
      imagePath: "/img/",
      languages: [
        "de",
        "en",
        "es",
        "fr",
        "it",
        "ja",
        "ko",
        "zh",
        "pt",
        "lv",
        "cs"
      ]
    }
  }
}
</script>

<template>
  <div v-if="this.languages.includes(language)">
    <h6>Language:</h6>
    <img :src="imagePath + language + '.png'" alt="">
  </div>

  <div v-else>
    <h6>Language:</h6>
    <span>{{ language}}</span>
  </div>
</template>

<style lang="scss" scoped>

</style>