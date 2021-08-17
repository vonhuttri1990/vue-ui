<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld v-bind:msg="message"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import axios from "axios"

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return {
      message: null
    }
  }, 
  methods: {
     getData() {
      axios.get('http://localhost:3000').then(res => {
        this.message = res.data
      })
      
    }
  },
  created: function() {
    this.getData()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
