<template>
  <div class=" bg p-3  card h-100 ">
        <img :src="image" :alt="title">
        <div class=" text-card  text-center" >
           <h3> {{title}} </h3>
           <h4> {{subTitle}} </h4>
           <span>{{subText}} </span>
           <h5> {{text}} </h5>
        </div>
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
@import '@/styles/variables';


  img{ 
    width: 100%;
   
}

 h3 {
    font-size: $h3; 
   text-transform: uppercase;
 } 

 h4 {
   font-size: $h4;
    color: $text-color;
 }
 h5 {
   font-size: $h4;
   
 }
 span {
   font-size: $span;
   color: $text-color;
 }

 .card {
   background: $bg-color;
   

 }
 
.text-card {
    text-transform: uppercase;
     margin-top: 0.8rem ;
     margin-bottom: 1.5rem; 
     color: $title-color;
}
</style>