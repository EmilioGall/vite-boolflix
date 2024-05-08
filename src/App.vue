<script>
import { store } from "./store";

import axios from "axios";

import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {

  components: {

    AppHeader,
    AppMain,

  },

  data() {
    return {

      store,

    };
  },

  created() {

    // this.getMovies();

  },

  methods: {

    getMovies() {

      let params = {

        api_key: this.store.apikey,

      };

      if (this.store.textImput !== "") {

        params.query = this.store.textImput

        this.store.isShowedList = true;

        console.log("Inserted text", this.store.textImput);

        console.log("isShowedList", this.store.isShowedList);

        axios
          .get("https://api.themoviedb.org/3/search/movie", {
            params,
          })
          .then((resp) => {

            console.log(resp);

            this.store.moviesArray = resp.results;

            console.log("moviesArray", this.store.charactersArray);

          });

      } else {

        this.store.isShowedList = false;

      };

    },
  },

}
</script>

<template>


  <AppHeader @search="getMovies" />

  <AppMain />



</template>

<style scoped lang="scss"></style>
