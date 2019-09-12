<template>
  <article v-if="favourites.length > 0">
    <h2>Favourite Beer List</h2>
    <ul v-for="(beer, index) in favourites" :key="index">
      <li v-on:click="handleClick(beer, index)">{{beer.name}}</li>
    </ul>
  </article>
</template>

<script>
import { eventBus } from '../main'

export default {
  name: 'favourites-list',
  props: ['favourites'],
  methods: {
    handleClick(beer, index) {
      eventBus.$emit('beer-selected', this.favourites[index])
    }
  }
}
</script>


<style lang="css" scoped>
  article {
    text-align: left;
  }
</style>