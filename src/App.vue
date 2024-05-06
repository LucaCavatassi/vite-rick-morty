<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import AppCards from "./components/AppCards.vue";
import SpinnerComponent from "./components/SpinnerComponent.vue"

export default {
  components: {
    AppHeader,
    AppCards,
    SpinnerComponent,

  },
  
  data () {
    return {
      charactersArray: [],
      isReady: false,
    };
  },

  created() {
    axios.get("https://rickandmortyapi.com/api/character").then((resp)=> {
      this.charactersArray = resp.data.results,
      this.isReady = true
      // console.log(this.charactersArray);
    });
  },

}

</script>

<template>
  <AppHeader /> 
  <div class="container">
    <div class="row">
        <AppCards v-if="isReady" :charactersArray ="charactersArray"/>
        <SpinnerComponent v-if="!isReady" />
    </div>
  </div>

</template>

<style>
  
</style>
