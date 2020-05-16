<template lang="html">

  <li v-on:click="handleClick">{{item.name}}</li>
  
</template>

<script>
import {eventBus} from '../main.js';

export default {
    name: 'report-list-component',
    props: ['item'],
    methods: {
      handleClick(){
        eventBus.$emit('item-selected', this.item)
      }
    }
}
</script>

<style>

</style>