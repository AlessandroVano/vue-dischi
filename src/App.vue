<template>
<div id="app">
  <section>
  <Header />
  <CardMusic :cdMusic="CardMusic"/>

  </section>
</div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue'
import CardMusic from '@/components/CardMusic.vue'

export default {
  name: 'App',
  components: {
    Header,
    CardMusic,
  },
  data() {
    return {
         CardMusic: null,
        };
  },
  created() {
     this.getCreateCardMusic();
  },
  methods: {
      getCreateCardMusic() {
        
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(result =>{
             console.log(result.data); 
            this.CardMusic = result.data.response
        })
        .catch(err => console.log(err));
      },
  },
}
</script>

<style lang="scss">
@import '@/styles/globals';
section {
  background-color: $bg-color-2;
  height: 920px;
}

</style>
