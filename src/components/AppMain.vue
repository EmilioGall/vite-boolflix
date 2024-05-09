<script>
import { store } from "../store";

import SimpleCard from "./SimpleCard.vue";

export default {

   components: {

      SimpleCard,

   },

   data() {
      return {

         store,

      };
   },

}
</script>

<template>

   <div class="container-md text-center">

      <div class="row">

         <!-- No Titles Section -->
         <section class="col row g-2" v-if="!store.isShowedList">

            <h2>NO TITLES SELECTED</h2>

         </section>
         <!-- /No Titles Section -->

         <!-- Cards Section -->
         <section class="col row g-2" v-else>

            <!-- Movies Cards -->
            <div class="col-12 row g-2">

               <h2 class="fs-2">Movies Selected</h2>

               <div class="col-3" v-for="curMovie, curMovieIndex in store.moviesArray">

                  <SimpleCard :titleObj="curMovie" :titleIndex="curMovieIndex"/>

               </div>

            </div>
            <!-- /Movies Cards -->

            <!-- TvSeries Cards -->
            <div class="col-12 row g-2">

               <h2 class="fs-2">TV Series Selected</h2>

               <div class="col-3" v-for="curTvSeries, curTvSeriesIndex in store.tvSeriesArray">

                  <SimpleCard :titleObj="curTvSeries" :titleIndex="curTvSeriesIndex" />

               </div>

            </div>
            <!-- /TvSeries Cards -->

         </section>
         <!-- /Cards Section -->

      </div>

   </div>

</template>

<style scoped lang="scss"></style>