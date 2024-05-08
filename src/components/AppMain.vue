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

      <div class="row g-3 row-cols-4">

         <div class="col" v-for="movie in store.moviesArray">
         
            <SimpleCard :movieObj="movie"/>

         </div>


      </div>

   </div>

</template>

<style scoped lang="scss"></style>