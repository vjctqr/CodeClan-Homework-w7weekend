<template>
  <div>
    <h1>Covid-19 Report</h1>
    <div class="main-container">
      <item-list :allreports='allreports'></item-list>
      <item-detail :item='selectedItem'></item-detail>
    </div>  
  </div>
</template>

<template>
</template>

<script>
  import {eventBus} from './main.js';
  import ReportsComponent from './components/ReportsComponent.vue';
  import ItemListComponent from './components/ItemListComponent';

  export default {
    name: 'app',
      data(){
        return {
        allreports: [],
        };
      },
    mounted(){
      fetch('https://covid19api.io/api/v1/AllReports')
      .then(res => res.json())
      .then(allreports => this.allreports = allreports)

      eventBus.$on('item-selected', (item) => {
        this.selectedItem = item
      })
    },
    components: {
      "item-list": ItemListComponent,
      "item-detail": ItemDetailComponent
    }
  }
</script>

<style>
  .main-container {
  display: flex;
  }
</style>
