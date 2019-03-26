<template>
  <!--只能存在一个根容器-->
  <div class="container">
    新的组件{{title}}
    <input v-model="searchText">
    <button @click="sendMsg" type="button" name="button">传递数据</button>
  </div>
</template>

<script>
  export default {
    name: 'learn',

    props:["title"],
    //所有的初始化状态全部放入data中
    data () {
      return {
        searchText:''
      }
    },
    methods:{
      sendMsg(){
        this.$emit("getMsg",this.searchText)
      }
    },
    computed:{

    },

    //实时监听数据变化，可以在这里做相关判断
    watch:{

    }

  }
</script>

<!--样式-->
<!--
Add "scoped" attribute to limit CSS to this component only
添加scoped属性限制样式只在当前组件中生效
-->
<style lang="css" scoped>


  .container{
    background: red;
  }


</style>
