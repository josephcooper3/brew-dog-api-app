<template>
  <article v-if="beer">
    <ul>
      <li>{{beer.name}}</li>
      <li>{{beer.tagline}}</li>
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