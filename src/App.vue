<template>
  <div>
    <h1>Covid-19 Report</h1>
  </div>
</template>

<template>

</template>

<script>
  import {eventBus} from './main.js';

  export default {
    name: 'app',
      data(){
        return {
        reports: [],
        selectedItem: null
        };
      },
    mounted(){
      fetch('https://covid19api.io/api/v1/AllReports')
      .then(res => rs.json())
      .then(reports => this.reports = reports)

      eventBus.$om('item-selected', (item) => {
        this.selectedItem = item
      })
    },
    components: {
      "item-list": ItemList,
      "item-datail": ItemDetail
    }
  }
</script>

<style>
  .main-container {
  display: flex;
  }
</style>
