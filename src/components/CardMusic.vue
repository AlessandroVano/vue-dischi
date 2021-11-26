<template>
<div class="container">
  <div class="boxes">

   <div class="disposition-card mb-3 mx-2 "
    v-for="(cdMusic, index) in CardMusic " 
    :key="`cdMusic-${index}`"
    >
      <Card 
        :image="cdMusic.poster"
        :title="cdMusic.title"
        :subTitle="cdMusic.author"
        :text="cdMusic.genre"
        :subText="cdMusic.year"
      />

   </div>
  </div>
</div>
</template>

<script>
import axios from 'axios';
import Card from '@/components/Card.vue';

export default {
name: 'CardMusic',

components: {
  Card,

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
      }
  }
};
</script>

<style scoped lang="scss">
 .boxes {
     display: flex;  
     flex-wrap: wrap; 
     justify-content: center;
     width: 100%;
     } 

    .disposition-card {
        width: calc(100% / 9);
    }
</style>