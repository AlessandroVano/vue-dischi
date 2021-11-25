<template>
<div id="app">
  <Header />

   <CardMusic />
</div>
</template>

<script>
import Header from '@/components/Header.vue'
import CardMusic from '@/components/CardMusic.vue'

export default {
  name: 'App',
  components: {
    Header,
    CardMusic,
  }
}
</script>

<style lang="scss">
@import '@/styles/globals';
</style>
