<template>
  <div class="hello">
    <p>{{"haha123"}}</p>
    {{123+3}}
    {{"ok"? 'yes' : 'no'}}
    {{ "hello!".split('').reverse().join('') }}
    <!--{{ if(true){'对的'}else{'错误的'} }}-->
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
