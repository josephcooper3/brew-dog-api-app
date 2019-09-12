<template>
  <tr>
    <td>{{beer.name}}</td>
    <td>{{beer.tagline}}</td>
    <td>image goes here</td>
    <td>fave btn goes here</td>
  </tr>
</template>



<script>
export default {
  name: 'table-component',
  props: ['beer']
}
</script>

<style lang="css" scoped>

</style>