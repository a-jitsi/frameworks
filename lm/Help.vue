<template>
  <q-page class="flex">
    <div class="float-left vertical-middle q-pa-sm" style="width:80%">
    <div class="column">
    <q-banner>Help Page for {{ person.first }}</q-banner>
    <input v-model="person.first"/>
      <div class="q-pa-md">
    <q-table
      class="my-sticky-column-table"
      title="Treats"
      :data="treatdata"
      :columns="columns"
      row-key="name"
    />
  </div>
  </div>
    </div>
  </q-page>
</template>

<script>
import { person, treatData, columns } from 'boot/axios'
export default {
  name: 'PageHelp',
  data () {
    return {
      person,
      treatdata: treatData,
      columns
    }
  }
}
console.log(treatData)

</script>
<style lang="sass" scopedSlots>
.my-sticky-column-table
  /* specifying max-width so the example can
    highlight the sticky column on any browser window */
  max-width: 100%

  thead tr:first-child th:first-child
    /* bg color is important for th; just specify one */
    background-color: #fff

  td:first-child
    background-color: #CCF1FF

  th:first-child,
  td:first-child
    position: sticky
    left: 0
    z-index: 1
</style>
