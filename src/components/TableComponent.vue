<template>
  <tr v-on:click="handleClick">
    <td>{{beer.name}}</td>
    <td>{{beer.tagline}}</td>
    <td>
      <img :src="beer.image_url">
    </td>
    <td>
      <input type="checkbox" v-on:click="handleCheckbox">
    </td>
  </tr>
</template>



<script>
import { eventBus } from '../main'

export default {
  name: 'table-component',
  props: ['beer'],
  methods: {
    handleClick() {
      eventBus.$emit('beer-selected', this.beer)
    },
    handleCheckbox() {
      
    }
  }
}
</script>

<style lang="css" scoped>
  img {
    width: 25px;
  }
</style>