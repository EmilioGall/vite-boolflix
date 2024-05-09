<script>
import { store } from "../store";

export default {

   props: {

      titleObj: Object,

   },

   data() {
      return {

         store,

      };
   },

   created() {

      // console.log("titleObj", this.titleObj);

   },

   computed: {

      correctLanguage() {

         switch (this.titleObj.original_language) {

            case "en":

               return "gb";

               break;

            case "ja":

               return "jp";

               break;

            case "ko":

               return "kr";

               break;

            case "zh":

               return "cn";

               break;

            case "hi":

               return "in";

               break;

            default:

               return this.titleObj.original_language;

               break;

         };

      },

      correctTitle() {

         if (this.titleObj.original_title) {

            return `${this.titleObj.original_title}`;

         } else {

            return `${this.titleObj.original_name}`;

         };

      },

      correctOriginalTitle() {

         if (this.titleObj.original_title) {

            return `${this.titleObj.title}`;

         } else {

            return `${this.titleObj.name}`;

         };

      },

      correctVote() {

         return Math.ceil(this.titleObj.vote_average / 2);

      },

   },

   methods: {


   },

}
</script>

<template>

   <!-- Card -->
   <div class="card">

      <img :src="`https://image.tmdb.org/t/p/w342${titleObj.poster_path}`" class="card-img-top" alt="...">

      <!-- Card Titles Section -->
      <div class="card-body">

         <h5 class="card-title fs-4"> {{ correctTitle }} </h5>

         <h4 class="card-text fs-5"> {{ correctOriginalTitle }} </h4>

      </div>
      <!-- /Card Titles Section -->

      <!-- Card Info Section -->
      <ul class="list-group list-group-flush">

         <li class="list-group-item">

            <h3 class="my-0 fs-6">
               Language: {{ titleObj.original_language.toUpperCase() }}
            </h3>

            <img :src="`https://flagsapi.com/${correctLanguage.toUpperCase()}/shiny/32.png`" alt="">

         </li>

         <li class="list-group-item">

            <h3 class="my-0 fs-6">
               Vote: {{ correctVote }}
            </h3>

            <div>

               <span class="full-stars" v-for="n in correctVote">

                  <i class="fa-solid fa-star"></i>

               </span>

               <span class="full-stars" v-for="n in (5-correctVote)">

                  <i class="fa-regular fa-star"></i>

               </span>

            </div>

         </li>

      </ul>
      <!-- /Card Info Section -->

   </div>
   <!-- /Cards -->

</template>

<style scoped lang="scss"></style>