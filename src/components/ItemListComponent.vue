<template lang="pug">
  <li v-on:click="handleClick">{{item.cases}}</li>
</template>

<script>
export default {
  name: 'item-list-components',
  props: ['reports'],
  methods: {
    handleClick(){
      eventBus.$emit('item-selected', this.item)
    }
  }
  
}
</script>

<style>
</style>