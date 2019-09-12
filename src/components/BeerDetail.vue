<template>
  <article v-if="beer">
    <ul>
      <li><h2>{{beer.name}} ({{beer.abv}}%)</h2></li>
      <li><h3>{{beer.tagline}}</h3></li>
      <li>{{beer.description}}</li>
    </ul>
  </article>
</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>

</style>