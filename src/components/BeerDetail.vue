<template>
  <article v-if="beer">
    <h2>{{beer.name}} ({{beer.abv}}%)</h2>
    <h3>{{beer.tagline}}</h3>
    <p>{{beer.description}}</p>
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