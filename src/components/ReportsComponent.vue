<template lang="html">
<div>
  <ul>
    <report-list-component v-for="(report, index) in allreports" :report="report" :key="index"><report-list-component>
  </ul>
</div>

</template>

<script>
import ReportListComponent from './ReportListComponent.vue'

export default {
  name: 'reports-components',
  props: ['allreports'],
  components: {
    "report-list-components": ReportListComponent
    }
}
</script>

<style>
</style>