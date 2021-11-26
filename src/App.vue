<template>
<div id="app">
  <section>
                 <!--vado a prendere il testo che ho utilizzato dentro al @change nella select dell'header e lo inserisco qui ed eseguo quello che metto nel metodo (in questo caso nel method 'ricercaGenere')   -->
  <Header     @scelta="ricercaGenere" />
          <!-- una volta creato il metodo andare a sostiture il mio CardMusic con filteredGenere -->
  <CardMusic :cdMusic=" filteredGenere"/>

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
         sceltaGenere: '',
        };
  },
computed: {
       filteredGenere() {
         /* scelta genere musicale che mi riporta alla collezione completa dei dischi */
         if(this.sceltaGenere === '') {
           return this.CardMusic;
         }
         /* con item mi prendo l'oggetto attuale dell'iterazione, prendo il genere (genre <- quello dell'array ) con toLowerCase lo converto tutto in minuscolo e infine voglio cercare se dentro c'è uno dei generi che seleziono,
         in pratica quando questa cosa è true mi porta fuori l'elemento (item) e iterazione dopo iterazione mi costruisce un array che porta fuori al mondo esterno*/
         return this.CardMusic.filter(item =>{
         return item.genre.toLowerCase().includes(this.sceltaGenere.toLowerCase())
         });

         
       }
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

      ricercaGenere(genre) {
    /*  console.log(genre); */
     this.sceltaGenere = genre;
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
