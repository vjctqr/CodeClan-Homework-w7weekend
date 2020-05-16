<template>
  <div>
      <ul>
          <report-list-component v-for="(item, index) in reportlist" :item="item" :key="index"></report-list-component>
      </ul>
  </div>
</template>

<script>
import ReportListComponent from './ReportListComponent.vue'

export default {
    name: 'reports',
    props: ['report-list'],
    components:{
        "report-list-component": ReportListComponent
    }
}
</script>

<style lang="css" scoped>

</style>