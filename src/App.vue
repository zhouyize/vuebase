<template>
  <div id="app">
    <img src="./assets/logo.png">
    {{demo}}
    <input v-model="ParentText">
    <Learn @getMsg="getSonMsg" :title="ParentText"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import VueDemo from './components/VueDemo'
import Learn from './components/Learn'

export default {
  name: 'App',
  data(){
    return{
      demo:"",
      title:{
        name:'Tim',
      },
      ParentText:''
    }
  },

  methods:{
    getSonMsg(data){
      this.demo=data
    }
  },

  components: {
    HelloWorld,
    VueDemo,
    Learn, //注入
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
