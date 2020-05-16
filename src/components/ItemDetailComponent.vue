<template lang="html">
  <div v-if='reports'>
      <h3>{{reports.cases}}</h3>
      <h3>{{reports.recovered}}</h3>
  </div>
  
</template>

<script>
import {eventBus} from '..main.js';
export default {
    name: 'item-detail',
    props: ['item']
}
</script>

<style>

</style>