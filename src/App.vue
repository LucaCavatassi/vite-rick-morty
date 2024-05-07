<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import AppCards from "./components/AppCards.vue";
import SpinnerComponent from "./components/SpinnerComponent.vue"
import AppSearch from "./components/AppSearch.vue"

export default {
  components: {
    AppHeader,
    AppCards,
    SpinnerComponent,
    AppSearch,
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

  methods: {
    log () {
      console.log("Cliccato");
    }
  }

}

</script>

<template>
  <AppHeader /> 
  <div class="container">
    <div class="row">
        <SpinnerComponent v-if="!isReady" />
        <AppSearch @filter="log" />
        <AppCards v-if="isReady" :charactersArray ="charactersArray"/>
    </div>
  </div>

</template>

<style>
  
</style>
