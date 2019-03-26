<template>
  <div class="hello">
    <p>{{"haha123"}}</p>
    {{123+3}}
    {{"ok"? 'yes' : 'no'}}
    {{ "hello!".split('').reverse().join('') }}
    {{msg}}
    <p v-once>{{msg}}</p>
    <div v-html="hello"></div>
    <a v-bind:href="url">{{url_name}}</a>
    <div :class="divClass">容器</div>
    <div :class="div2Class+'-1'">容器1</div>
    <div v-if="flag">孙悟空</div>
    <div v-else="flag">通臂猿猴</div>
    <div v-show="flag">真· 三国无双</div>
    <ul>
      <li v-for="(item,index) in names" :key="index">{{index}}-{{item.name}}-{{item.age}}</li>
    </ul>
    <ul>
      <li v-for="(value,key,index) in obj" :key="index">{{value}}-{{key}}-{{index}}</li>
    </ul>
    <button @click="clickHandler('哈哈',$event)" type="button" name="button">按钮</button>
    <ul>
      <li v-for="item in helloArr">{{item}}</li>
    </ul>
    <button @click="addHandler()" type="button" name="button">添加</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App!',
      hello: '<h3>Hello</h3>',
      url_name: "百度",
      url:"http://www.baidu.com",
      divClass:'isActive',
      div2Class:"list",
      flag: false,
      names:[
        {name:"Jim",age:20},
        {name:"Tim",age:25},
        {name:"Tom",age:28}
      ],
      obj:{
        name:"Hanmeimei",
        age:20
      },
      helloArr: ['hello1','hello2','hello3'],
    }
  },
  methods:{
      clickHandler(data,event){
        console.log(data)
        console.log(event)
        this.flag = !this.flag;
      },

      addHandler(){
        console.log(this.helloArr.concat(['hello4','hello5']))
        console.log(this.helloArr)
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

  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
