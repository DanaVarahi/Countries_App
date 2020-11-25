<template>
  <div>
      <ul>
          <li v-for="(country, index) in countries" :country="country" :key="index"></li>
      </ul>
  </div>
</template>

<script>
import Country from './Country.vue';

export default {
    name: 'countires-list',
    props: ['countries'],
    components: {
        "country": Country
    }
}
</script>

<style scoped>

</style>