<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import AppGrid from './components/AppGrid.vue';

import { store } from "./store";

export default {
  components: {
      AppHeader,
      AppGrid,
    },
    data(){
      return{
        store,
      }
    },
    created () {
      console.log("ciao")


      axios.get("https://rickandmortyapi.com/api/character").then((resp) => {
        this.store.characters = resp.data.results;
        console.log("ciao")
        });
    },
  }

    
</script>

<template>
  <body>
      <AppHeader />  
      <AppGrid />
  </body>

</template>

<style lang="scss">
@use "./styles/general.scss" as *;

body{
    width: 100%;
    background-image: url(./assets/11cdb158-8c35-4fbb-92df-d6cc133f849a.webp);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: bottom;
    overflow-y: scroll;
}

</style>
