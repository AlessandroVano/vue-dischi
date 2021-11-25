<template>
  <div class="sist">
        <img :src="image" :alt="title">
     <h3> {{title}} </h3>
     <h4> {{subTitle}} </h4>
     <h5> {{text}} </h5>
    <span>{{subText}} </span>
  </div>
</template>

<script>
export default {
name: 'Card',
props: {
    image: String,
    title: String,
    subTitle: String,
    text: String,
    subText: String,
}
}
</script>

<style  scoped lang="scss">
@import '@/styles/globals';

img {
    width: 199px; 
    display: flex;
    justify-content: space-between;
    padding: 23px;
    margin-top: 202px;
  }
 .sist {
   background: $bg-color;
 }
</style>