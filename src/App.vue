<template>
  <div>
    <h1>Covid-19 Report</h1>
    <div class="main-container">
      <item-list :reports='reports'></item-list>
      <item-detail :item='selectedItem'></item-detail>
    </div>  
  </div>
</template>

<template>
</template>

<script>
  import {eventBus} from './main.js';
  import ItemListComponent from './components/ItemListComponent.vue';
  import ItemDetailComponent from './components/ItemDetailComponent';

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
      "item-detail": ItemDetail
    }
  }
</script>

<style>
  .main-container {
  display: flex;
  }
</style>
