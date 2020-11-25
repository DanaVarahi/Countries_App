<template>
  <div class="container">
    <h1>Countries</h1>
    <countires-list :countries='countries'></countires-list>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import { eventBus } from './main.js';

export default {
  name: 'app',
  data(){  
    return {
      countries: [],
      selectedCountry: null
    };
  },

  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

  },
  components: {
    "countires-list": CountriesList,
  }
}

</script>

<style scoped>

</style>


  
