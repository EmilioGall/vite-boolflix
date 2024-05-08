<script>
import { store } from "../store";


export default {

   components: {


   },

   data() {
      return {

         store,

      };
   },

}
</script>

<template>

   <div class="container text-center">

      <div class="row row-cols-4">

         <div class="col" v-for="movie in store.moviesArray">
         
         {{ movie.title }}

         </div>


      </div>

   </div>

</template>

<style scoped lang="scss"></style>