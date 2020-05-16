<template lang="html">
  <div v-if='report'>
    <h3>{{report.name}}</h3>
  </div> 
</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: 'item-list-component',
  props: ['reports']

}
</script>

<style>

</style>