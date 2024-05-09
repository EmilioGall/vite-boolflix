<script>
import { store } from "../store";

export default {

   props: {

      movieObj: Object,

   },

   data() {
      return {

         store,

      };
   },

   computed: {



   },

   methods: {

      toLanguage() {

         switch (this.movieObj.original_language) {

            case "en":

               console.log("language", this.movieObj.original_language);

               return "gb";

               break;

            case "ja":

               console.log("language", this.movieObj.original_language);

               return "jp";

               break;

            case "ko":

               console.log("language", this.movieObj.original_language);

               return "kr";

               break;

            default:

               console.log("language", this.movieObj.original_language);

               return this.movieObj.original_language;

               break;

         };

      },

   },

}
</script>

<template>

   <div class="card">

      <img src="..." class="card-img-top" alt="...">

      <div class="card-body">

         <h5 class="card-title fs-4"> {{ movieObj.title }} </h5>

         <h4 class="card-text fs-5"> {{ movieObj.original_title }} </h4>

      </div>

      <ul class="list-group list-group-flush">

         <li class="list-group-item">

            <p class="my-0 fs-6">
               Language: {{ movieObj.original_language.toUpperCase() }}
            </p>

            <img :src="`https://flagsapi.com/${toLanguage().toUpperCase()}/shiny/32.png`" alt="">

         </li>

         <li class="list-group-item">

            {{ movieObj.vote_average }}

         </li>

      </ul>

   </div>

</template>

<style scoped lang="scss"></style>