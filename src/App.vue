<template>
  <div id="app">
    <beers-table v-bind:beers="beers"></beers-table>
  </div>
</template>

<script>
import BeersTable from './components/BeersTable'

export default {
  name: 'app',
  data() {
    return {
      beers: [],
    }
  },
  mounted () {
    fetch('https://api.punkapi.com/v2/beers')
    .then(result => result.json())
    .then(beers => this.beers = beers)
  },
  components: {
    "beers-table": BeersTable,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
