<template lang="html">
  <li v-on:click="handleClick">{{report.name}}</li>
  
</template>

<script>
import {eventBus} from '../main.js';

export default {
    name: 'report-list-component',
    props: ['report'],
    methods: {
      handleClick(){
        eventBus.$emit('report-selected', this.report)
      }
    }
}
</script>

<style>

</style>