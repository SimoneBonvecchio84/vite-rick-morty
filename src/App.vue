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
    // this.isLoading = true;
    // axios.get("https://rickandmortyapi.com/api/character").then((resp) => {
    //   this.cardsArray = resp.data.results;
    //   this.isLoading = false;
    // })
    this.getStatus();
  },
  methods: {
    getStatus() {

      if (this.store.selectedStatus !== "All") {

        console.log("Get Status", this.store.selectedStatus);
        axios.get("https://rickandmortyapi.com/api/character", {
          params: {
            status: this.store.selectedStatus
          }
        }).then((resp) => {
          this.cardsArray = resp.data.results;
        })
      } else {
        axios.get("https://rickandmortyapi.com/api/character").then((resp) => {
          this.cardsArray = resp.data.results;
          this.isLoading = false;
        })
      }
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