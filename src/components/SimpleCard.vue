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

      toLang() {

         if (this.movieObj.original_language === "en") {

            console.log("language", this.movieObj.original_language);

            return "gb";

         } else if (this.movieObj.original_language === "ja") {

            console.log("language", this.movieObj.original_language);

            return "jp";

         } else if (this.movieObj.original_language === "ko") {

            console.log("language", this.movieObj.original_language);

            return "kr";

         } else {

            console.log("language", this.movieObj.original_language);

            return this.movieObj.original_language;

         };

      },

   },

}
</script>

<template>

   <div class="card">

      <img src="..." class="card-img-top" alt="...">

      <div class="card-body">

         <h5 class="card-title fs-2"> {{ movieObj.title }} </h5>

         <h4 class="card-text fs-5"> {{ movieObj.original_title }} </h4>

      </div>

      <ul class="list-group list-group-flush">

         <li class="list-group-item">

            <p class="my-0">
               Language: {{ movieObj.original_language.toUpperCase() }}
            </p>

            <img :src="`https://flagsapi.com/${toLang().toUpperCase()}/shiny/32.png`" alt="">

         </li>

         <li class="list-group-item">

            {{ movieObj.vote_average }}

         </li>

      </ul>

   </div>

</template>

<style scoped lang="scss"></style>