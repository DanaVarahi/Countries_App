<template>
  <div>
    <h1>Countries</h1>
    <div class="container">
      <countires-list :countries='countries'></countires-list>
      <country-detail :country="selectedCountry"></country-detail>
     </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import { eventBus } from './main.js';
import CountryDetail from './components/CountryDetail.vue'

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

    eventBus.$on('selected-country', (country) => {
      console.log(country)
      this.selectedCountry = country;
    })

  },
  components: {
    "countires-list": CountriesList,
    "country-detail": CountryDetail
  }
}

</script>

<style scoped>
  .container {
    display: flex;
    justify-content: space-between;
  }
</style>


  
