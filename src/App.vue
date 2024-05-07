<script>
import { store } from "./store";
import axios from "axios";
import AppListCards from "./components/AppListCards.vue";
import AppSearch from "./components/AppSearch.vue"
export default {
  components: {
    AppListCards,
    AppSearch
  },
  data () {
    return {
      store,
      cardsArray: [],
      isLoading: false,  
    }
  },
  created () { 
      this.isLoading = true;
      axios.get("https://rickandmortyapi.com/api/character").then((resp) => {      
        this.cardsArray = resp.data.results; 
        this.isLoading = false;     
      }) 
    } 
}
</script>

<template>  
  <AppSearch />
  <div v-if="isLoading">Loading...</div>
  <AppListCards :cardsArray="cardsArray" v-else />
</template>

<style>
</style>