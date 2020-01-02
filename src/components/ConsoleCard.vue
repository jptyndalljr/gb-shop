<template>
  <div class="console-card">
    <div class="console-text">
      <h1 v-if="name">{{ name }}</h1>
      <h1 v-else>Console Name</h1>
    </div>
    <div class="console-image">
      <g-image v-if="image" :src="require('~/assets/images/' + image)"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ConsoleCard',
  props: [
    'name',
    'image'
  ]
}
</script>

<style lang="scss" scoped>
</style>
