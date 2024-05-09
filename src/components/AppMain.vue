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

         <div class="col row g-2" v-if="!store.isShowedList">

            <h2>NO TITLE SELECTED</h2>

         </div>

         <div class="col row g-2" v-else>

            <!-- Movies Cards -->
            <div class="col row g-2">

               <h2 class="fs-2">Movies Selected</h2>

               <div class="col-3" v-for="movie in store.moviesArray">

                  <SimpleCard :movieObj="movie" />

               </div>

            </div>
            <!-- /Movies Cards -->

         </div>

      </div>

   </div>

</template>

<style scoped lang="scss"></style>