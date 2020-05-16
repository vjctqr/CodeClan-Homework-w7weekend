<template lang="html">
  <div v-if='item'>
      <h3>{{item.cases}}</h3>
  </div>
  
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'item-component',
    props: ['item']

}
</script>

<style>

</style>