# vb

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


1.安装Vue
  node版本必须大于等于8.9
  vue-cli3.x:npm install -g @vue/cli
  拉取 2.x 模板 (旧版本)####`vue init` 的运行效果将会跟 `vue-cli@2.x` 相同
  vue-cli2.x:npm install -g @vue/cli-init
2.创建项目
  vue init webpack my-project
  注意：安装依赖的时候选择最后一个自己安装
  cd my-project
  npm start/npm run dev
3.工程目录

4.基础指令
  Mustache: {{ 变量 }}   只能存在单行语句(单个表达式)
  v-once: 只能渲染一次
  v-html: 解析html结构
  v-bind: 指令(解析属性中的对象)
  v-bind简写: (:)
  v-if: 条件渲染
  v-show: 条件渲染

5.v-if vs v-show
  v-if 是“真正”的条件渲染，因为它会确保在切换过程中条件块内的事件监听器和子组件适当地被销毁和重建。
  v-if 也是惰性的：如果在初始渲染时条件为假，则什么也不做——直到条件第一次变为真时，才会开始渲染条件块。

  相比之下，v-show 就简单得多——不管初始条件是什么，元素总是会被渲染，并且只是简单地基于 CSS 进行切换。

  一般来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。
  因此，如果需要非常频繁地切换，则使用 v-show 较好；如果在运行时条件很少改变，则使用 v-if 较好。

6.列表渲染
  v-for:

7.事件处理
  1.事件改变data数据，data数据改变会引起视图的变化
  2.事件传递参数
    传参数同时传event，event要用$event
  3.数组更新检测
    push,unshift
    最开始讲数组的时候，老师在讲一个方法的时候会说，返回一个原数组还是新数组
    变异方法：改变原数组则可以引起视图更新，
            不改变原数组，创建新数组，则无法引起数组更新


8.计算属性
  计算属性缓存 vs 方法:
  我们可以将同一函数定义为一个方法而不是一个计算属性。两种方式的最终结果确实是完全相同的。
  然而，不同的是计算属性是基于它们的依赖进行缓存的。只在相关依赖发生改变时它们才会重新求值。
  这就意味着只要 message 还没有发生改变，多次访问 reversedMessage 计算属性会立即返回
  之前的计算结果，而不必再次执行函数。

9.Class和Style的绑定

10.表单输入绑定
  修饰符：
    .lazy
    .number
    .trim

  watch:监听事件

11.组件传递数据props

12.自定义事件向父组件传递数据
  $emit   =>子组件可以通过调用内建的 $emit 方法 并传入事件名称来触发一个事件：
