<template>
  <div>
    <div :class="{active:classDemo}">
      css
    </div>
    <div :class="cssObj">
      test
    </div>
    <button @click="changeCss()" type="button" name="button">改变css</button>
    <div :class="[isActive ? activeClass : '', errorClass]">
      test1
    </div>

    <!--Class 与 Style 绑定对象语法中：对象中的key只能是个字符串无论加不加引号如第一个div中的active-->
    <div class="old" :class="[{ helloC:classDemo },isActive ? 'active' : 'noactive']">
      应用的中的样式
    </div>

    <div class="myinput">
      <input v-model.trim="inputmsg" type="text" name="" value="">
      <p>{{inputmsg}}</p>
      <input type="checkbox" id="checkbox" v-model="checked">
      <label for="checkbox">{{ checked }}</label>
    </div>
    <button @click="changeName()" type="button" name="button">改变name</button>
    <p>{{myname}}</p>
  </div>
</template>

<script>
  export default {
    name: 'vuedemo',
    data () {
      return {
        msg: 'hello',
        classDemo: true,
        active:'active1',
        cssObj:{
          'c1':true,
          'c2':true
        },
        activeClass: 'active',
        errorClass: 'text-danger',
        isActive: true,
        inputmsg:'',
        checked:false,
        myname:'zhouyize'
      }
    },
    methods:{
      mMsg(){
        return this.msg.split('').reverse().join('')
      },

      changeName(){
        this.myname+='1'
      }
    },
    computed:{
      //如果数据没有被改变，则不会重新计算
      getMsg(){
        return this.msg.split('').reverse().join('')
      },
      changeCss(){
        this.cssObj = {
          "c1":false,
          "c2":true
        }
      }
    },

    //实时监听数据变化，可以在这里做相关判断
    watch:{
      inputmsg(data){
        console.log(data)
      },

      myname(data){
        console.log(data)
      }
    }


  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .active{
    color:red
  }
</style>
