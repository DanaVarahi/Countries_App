<template>
  <li @click="handleClick">{{ country.name }}</li>
</template>

<script>
import { eventBus } from '../main.js';

export default {
    name: 'country-item',
    props: ['country'],
    methods: {
        handleClick(){
            eventBus.$emit('selected-country', this.country)
        }
    }
}
</script>

<style scoped>

</style>