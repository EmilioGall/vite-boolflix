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

   <input type="text" placeholder="Search" aria-label="Search"
      class="border border-secondary rounded-start-1 border-end-0" v-model="store.textImput">


   <button class="text-white bg-secondary border border-secondary rounded-end-1 border-start-0" @click="$emit('searchToHeader')">
      <i class="fa-solid fa-magnifying-glass p-2"></i>
   </button>

</template>

<style scoped lang="scss"></style>