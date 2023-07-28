<template>
  <div>
    <h1 @click="currnetColor = 'green'" :class="{ active : isActive}" :style="{ 'background-color': currnetColor}">{{ name }}</h1>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      count:0,
      name:"Aslan",
      currnetColor:"gold",
      isActive:true,
    }
  }
}
</script>

<style>
  h1{
    text-align: center;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  }
  .active{
    border: 2px solid green;
    border-radius: 4px;
    /* background-color: #000; */
    color: red;
    font-size: 40px;
  }
</style>
