<script>
import axios from "axios";
import AppListCards from "./components/AppListCards.vue"
export default {
  components: {
    AppListCards
  },
  data () {
    return {
      cardsArray: [],
    }
  },
  created () {
    axios.get("https://rickandmortyapi.com/api/character").then((resp) => {      
      this.cardsArray = resp.data.results;
      console.log(this.cardsArray)
    })
  }
}
</script>

<template>
  <AppListCards :cardsArray="cardsArray" />
</template>

<style>
</style>