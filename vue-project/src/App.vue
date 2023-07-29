<template>
  <div>
    <h1 @click="currnetColor = 'green'" :class="{ active : isActive}" :style="{ 'background-color': currnetColor}">{{ name }}</h1>

    <button class="btn btn-dark m-2" @click="isLoggedIn = !isLoggedIn">Click Me!</button>
    <div v-if=isLoggedIn>
      <p>Successfully logged in</p>
    </div>
    <div v-else>
      <p>Unable to login</p>
    </div>
    <!-- <div v-for="value in 10" :key="value-1">
      {{ value }}
    </div> -->
    <div v-for="(person,index) in user " :key="index">
      <span>{{person.name + " "+ person.age}}</span>
    </div>
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
      isLoggedIn : false,
      user:[
      { "name":"Aslan",
        "surName":"Nazarov",
        "age":19
      },
      { "name":"Nihad",
        "surName":"Aliyev",
        "age":19
      },
      { "name":"Yusif",
        "surName":"Mansimov",
        "age":19
      }
      ]

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
