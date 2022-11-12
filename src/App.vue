<script>
import axios from "axios";

import AppHeader from './components/AppHeader.vue';
import { store } from ".//store";
export default {
  components: {
      AppHeader,
      data(){
        return{
          store,
        }
      }

  }
}
</script>

<template>
  
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
