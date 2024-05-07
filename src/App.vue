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
  data() {
    return {
      store,
      cardsArray: [],
      isLoading: false,
    }
  },
  created() {
    this.getStatus();
  },
  methods: {
    getStatus() {
      this.isLoading = true;
      const paramsSt = {};
      if (this.store.selectedStatus !== "All") { 
        paramsSt.status = this.store.selectedStatus;  
      }
      axios.get("https://rickandmortyapi.com/api/character", {
        params: paramsSt  
      }).then((resp) => {
        this.cardsArray = resp.data.results;
        this.isLoading = false;
      })

    }
  }
}
</script>

<template>
  <div class="text-center py-5">
    <h2 class="fw-bolder">Rick and Morty App</h2>
  </div>
  <AppSearch @filter="getStatus" />
  <div v-if="isLoading">Loading...</div>
  <AppListCards :cardsArray="cardsArray" v-else />
</template>

<style></style>