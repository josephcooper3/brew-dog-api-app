<template>
  <table>
    <thead>
      <th></th>
      <th>Name</th>
      <th>Tagline</th>
      <th>Add to Faves</th>
    </thead>
      <tbody>
        <table-component v-for="(beer, index) in beers" v-bind:beer="beer" v-bind:key="index"></table-component>
      </tbody>
  </table>
</template>

<script>
import TableComponent from './TableComponent'

export default {
  name: 'beers-table',
  props: ['beers'],
  components: {
    "table-component": TableComponent
  }
}
</script>

<style lang="css" scoped>

</style>