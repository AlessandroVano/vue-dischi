<template>
<div class="container">
  <div class="row">

   <div class="col-2"
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

</style>