<template>

<div class="bg ">
  <img class="m-2" src="../assets/logo.png" alt="">

  <select class="m-2" name="" id="">
    <option value="">All genres</option>
    <option value="">rock</option>
    <option value="">pop</option>
    <option value="">jazz</option>
    <option value="">Metal</option>
  </select>

</div>

</template>

<script>

export default {
name: 'Header'
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