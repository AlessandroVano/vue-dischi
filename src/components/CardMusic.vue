<template>
<div class="container">
  <div class="row">

  </div>
</div>
</template>

<script>
import axios from 'axios';

export default {
name: 'CardMusic',
data() {
    return {
         CardMusic: [],
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
        })
        .catch(err => console.log(err));
      }
  }
};
</script>

<style scoped lang="scss">

</style>