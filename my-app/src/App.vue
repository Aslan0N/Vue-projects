<template>
  <div id="app">
    <h1>{{ name + " " + surname}}</h1>
    <button class="btn btn-success" @click="increment">(+)</button>
    {{ count }}
    <button class="btn btn-danger" @click="decrement">(-)</button>
   <button class="btn btn-dark" @click="reset">Reset</button>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      name: "Aslan",
      surname:"Nazar",
      count : 0
    }
  },
  methods:{
    increment(){
      this.count++
    },
    decrement(){
      this.count--
    },
    reset(){
      this.count = 0
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #104272;
  margin-top: 60px;
}
</style>
