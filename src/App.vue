<template>
  <div id="app">
    <beer-detail :beer="selectedBeer"></beer-detail>
    <favourites-list :favourites="favouriteBeers"></favourites-list>
    <beers-table :beers="beers"></beers-table>
  </div>
</template>

<script>
import BeersTable from './components/BeersTable'
import BeerDetail from './components/BeerDetail'
import FavouritesList from './components/FavouritesList'
import { eventBus } from './main'

export default {
  name: 'app',
  data() {
    return {
      beers: [],
      selectedBeer: null,
    }
  },
  mounted () {
    fetch('https://api.punkapi.com/v2/beers')
    .then(result => result.json())
    .then(beers => this.beers = beers.map(beer => {
      beer.isFavourite = false
      return beer
    }))
  
    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer
    })
  },
  computed: {
    favouriteBeers: function () {
      return this.beers.filter((beer) => beer.isFavourite === true)
    }
  },
  components: {
    "beers-table": BeersTable,
    "beer-detail": BeerDetail,
    "favourites-list": FavouritesList
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
