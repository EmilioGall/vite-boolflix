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

}
</script>

<template>

   <div class="card">

      <img src="..." class="card-img-top" alt="...">

      <div class="card-body">

         <h5 class="card-title fs-2"> {{ movieObj.title }} </h5>

         <h4 class="card-text fs-5">Original title</h4>

      </div>

      <ul class="list-group list-group-flush">

         <li class="list-group-item">An item</li>

      </ul>

   </div>

</template>

<style scoped lang="scss"></style>