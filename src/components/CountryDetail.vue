<template>
    <div v-if="country">
         <h2>{{ country.name}}</h2>
         <p>{{ country.capital }}</p>
         <p>{{ country.population }}</p>
    </div>
</template>

<script>
export default {
    name: "country-detail",
    props: ['country']
}
</script>

<style scoped>

</style>