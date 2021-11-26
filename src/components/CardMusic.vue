<template>
<div class="container">
  <div class="boxes">

   <div class="disposition-card mb-3 mx-2 "
    v-for="(cdMusic, index) in  cdMusic " 
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

import Card from '@/components/Card.vue';

export default {
name: 'CardMusic',

components: {
  Card,

},

props: {
  cdMusic: Array
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