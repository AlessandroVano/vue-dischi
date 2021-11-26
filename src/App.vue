<template>
<div id="app">
  <section>
  <Header />
  <CardMusic />

  </section>
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
section {
  background-color: $bg-color-2;
  height: 920px;
}

</style>
