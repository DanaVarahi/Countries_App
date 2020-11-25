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
            console.log(this.country) 
        }
    }
}
</script>

<style scoped>

</style>