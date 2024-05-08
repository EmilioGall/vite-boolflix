<script>
import { store } from "../store";

import SearchBar from "./SearchBar.vue";

export default {

   components: {

      SearchBar,

   },

   data() {
      return {

         store,

      };
   },

}
</script>

<template>

   <div class="bg-black p-3">

      <div class="container-md ">

         <div class="row justify-content-between align-items-center">

            <div class="col-4">

               <h1 class="fs-1 text-danger">BOOLFLIX</h1>

            </div>

            <div class="col-8 d-flex justify-content-end">

               <SearchBar @search="$emit('search')"/>

            </div>

         </div>

      </div>

   </div>


</template>

<style scoped lang="scss">
button {
   background: none;
   color: inherit;
   border: none;
   font: inherit;
   cursor: pointer;
   outline: inherit;

}
</style>