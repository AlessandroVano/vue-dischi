<template>
<div id="app">
  <section>
                 <!--vado a prendere il testo che ho utilizzato dentro al @change nella select dell'header e lo inserisco qui ed eseguo quello che metto nel metodo (in questo caso nel metodo 'ricercaGenere')   -->
  <Header     @scelta="ricercaGenere" />
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
      ricercaGenere() {
     console.log('emit evento');
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
