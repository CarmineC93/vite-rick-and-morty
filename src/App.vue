<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import AppGrid from './components/AppGrid.vue';
import ChangePage from './components/ChangePage.vue';

import { store } from "./store";

export default {
  components: {
      AppHeader,
      AppGrid,
      ChangePage
    },
    data(){
      return{
        store,
        urlPage: "https://rickandmortyapi.com/api/character",
        actualPage : 1,
        prevPage : this.actualPage - 1,
        nextPage : this.actualPage + 1,
      }
    },
    created () {

      axios.get(this.urlPage).then((resp) => {
        this.store.characters = resp.data.results;
        console.log(resp.data.info.pages)
        });
    },
      methods : {

      changePrevPage(){
        this.actualPage --

        let apiBase = `https://rickandmortyapi.com/api/character?page=${this.actualPage}`

        axios.get(apiBase).then((resp) => {
            this.urlPage = apiBase
            console.log(this.actualPage + " actual");
            console.log(resp.data.info.pages)
            console.log(resp.data.info.next)
          })
      },

      changeNextPage(){
        this.actualPage ++

        let apiBase = `https://rickandmortyapi.com/api/character?page=${this.actualPage}`

        axios.get(apiBase).then((resp) => {
        this.urlPage = apiBase
        console.log(this.actualPage + " actual");
        console.log(resp.data.info.pages)
        console.log(resp.data.info.next)
        })
      },
    }
  }

    
</script>

<template>
  <body>
      <AppHeader /> 
      <ChangePage @changeRight="changeNextPage" 
                  @changeLeft="changePrevPage" /> 
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
