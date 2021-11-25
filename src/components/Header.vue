<template>

<div class="bg">
  <img class="m-2" src="../assets/logo.png" alt="">
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
}
img {
    width: 50px;
}
</style>