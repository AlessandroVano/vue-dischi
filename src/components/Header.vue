<template>

<div class="bg ">
  <img class="m-2" src="../assets/logo.png" alt="">

  <select 
     class="m-2"
     v-model="sceltaGenere"
     @change="$emit('scelta', sceltaGenere)">


    <option value="">All genres</option>
    <option value="rock">rock</option>
    <option value="pop">pop</option>
    <option value="jazz">jazz</option>
    <option value="metal">Metal</option>
  </select>

</div>

</template>

<script>

export default {
name: 'Header',

data() {
  return {
        sceltaGenere: '',
    }
  }
}

</script>

<style scoped lang="scss">
@import '@/styles/variables.scss';


.bg {
     background-color: $bg-color;
     margin-bottom: 80px; 
     display: flex;
     justify-content: space-between;
}
 
  

img {
    width: 50px;
}
</style>