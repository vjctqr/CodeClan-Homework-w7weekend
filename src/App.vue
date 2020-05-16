<template>
  <div>
    <h1>Covid-19 Report</h1>
    <div class="main-wrapper">  
    <report-list-component :reportlist='reportlist'></report-list-component>
    <item-detail :item='selectedItem'></item-detail>
  </div>
</template>

<template>
</template>

<script>
  import ItemComponent from './components/ItemComponent.vue';
  import {eventBus} from './main.js';
  import ReportListComponent from './components/ReportListComponent.vue';

  export default {
    name: 'app',
      data(){
        return {
        reportlist: {},
        selectedItem: null
        }
      },
    mounted(){
        fetch('https://covid19api.io/api/v1/AllReports')
        .then(res => res.json())
        .then(reportlist => this.reportlist = reportlist)
      
        eventBus.$on("show-report", (reports) => {
        this.selectedItem = item
      })
    },
    components: {
      "report-list-component": ReportListComponent,
      "item-component": ItemComponent
    }
  }
</script>

<style>
  .main-wrapper {
  display: flex;
  }
</style>
