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

   <div class="bg-black p-3">

      <div class="container-md ">

         <div class="row justify-content-between align-items-center">

            <div class="col-4">

               <h1 class="fs-1 text-danger">BOOLFLIX</h1>

            </div>

            <div class="col-8 d-flex justify-content-end">

               <input type="text" placeholder="Search" aria-label="Search"
                  class="border border-secondary rounded-start-1 border-end-0">


               <button class="text-white bg-secondary border border-secondary rounded-end-1 border-start-0">
                  <i class="fa-solid fa-magnifying-glass p-2"></i>
               </button>


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