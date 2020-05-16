<template>
  <div>
    <h1>Covid-19 Report</h1>
    <div class="main-container">
      <item-list :allreports='allreports'></item-list>
      <item-detail :report='selectedReport'></item-detail>
    </div>  
  </div>
</template>

<template>
</template>

<script>
  import {eventBus} from './main.js';
  import ReportsComponent from './components/ReportsComponent.vue';
  import ItemDetailComponent from './components/ItemDetailComponent';

  export default {
    name: 'app',
      data(){
        return {
        allreports: [],
        selectedReport: null
        };
      },
    mounted(){
      fetch('https://covid19api.io/api/v1/AllReports')
      .then(res => res.json())
      .then(allreports => this.allreports = allreports)

      eventBus.$on('report-selected', (report) => {
        this.selectedReport = report
      })
    },
    components: {
      "reports-component": ReportsComponent,
      "item-detail": ItemDetailComponent
    }
  }
</script>

<style>
  .main-container {
  display: flex;
  }
</style>
