<template>
  <tr>
    <td v-on:click="handleClick">
      <img :src="beer.image_url">
    </td>
    <td>{{beer.name}}</td>
    <td>{{beer.tagline}}</td>

    <td>
      <input type="checkbox" v-on:change="handleCheckbox">
    </td>
  </tr>
</template>



<script>
import { eventBus } from '../main'
import { log } from 'util';

export default {
  name: 'table-component',
  props: ['beer'],
  methods: {
    handleClick() {
      eventBus.$emit('beer-selected', this.beer)
    },
    handleCheckbox() {
      this.beer.isFavourite = !this.beer.isFavourite
    }
  }
}
</script>

<style lang="css" scoped>
  img {
    width: 25px;
  }
  img:hover {
    cursor: pointer;
  }
</style>