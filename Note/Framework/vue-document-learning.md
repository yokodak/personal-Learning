# vue 学习笔记

随记

### 1. vue 如何将.vue 文件渲染成 dom 挂载到 html中的？

- 在 `html` 中使用 `vue` 
  - 引入 `vue.js` 
  - 创建 `Vue` 实例，传入参数(一个对象），其中 `el` 属性指定挂载的 `dom` 元素（选择器语法）
  - `html` 中创建对应元素，如果要进行数据渲染，可以使用 `{{ }}` （ Mustache语法 ）。
  - 传入 `Vue` 构造函数的对象的 `data` 中的属性还可以用于 `Vue` 的其他语法（指令），如  `v-bind`,`v-if` 等，相当于一个变量
  - `Vue`  实例会完全控制其挂载的 `dom` ，我们不再和 `HTML` 直接交互了, 所有的 `dom` 操作都由 `vue` 来处理，我们只需关注代码逻辑
  - `Vue` 实现了**响应式**，数据的更新会实时表现在视图上

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<body>
  <div class="app">
    <div id="hello">
      {{ message }}
    </div>
  </div>
</body>
<script>
var app = new Vue({
  el: '.app #hello',
  data: {
    message: 'Hello Vue!'
  }
})
</script>
</html>
```

- 常用的 `Vue` 指令

  - `v-bind`(`:`)
  - `v-if` , `v-else`
  - `v-show`
  - `v-for`
  - `v-on`(`@`)
  - `v-model` 双向绑定，常用于表单控件，接收用户输入

- 指令的修饰符

  用于指出一个指令应该以特殊方式绑定

  - `.native`
  - `.prevent`
  - [事件修饰符](https://cn.vuejs.org/v2/guide/events.html#%E4%BA%8B%E4%BB%B6%E4%BF%AE%E9%A5%B0%E7%AC%A6)

- `vue` 如何将 `Vue` 实例挂载到 `dom`？

### 2.vue 是怎么做到响应式的？

https://cn.vuejs.org/v2/guide/reactivity.html

### 3.vue 的组件系统

- 注册组件`Vue.component`(全局注册)

  组件是可复用的 Vue 实例，每用一次组件，就会有一个它的新**实例**被创建。所以它们与 `new Vue` 接收相同的选项，例如 `data`、`computed`、`watch`、`methods` 以及生命周期钩子等。仅有的例外是像 `el` 这样根实例特有的选项。

- 组件的 data 属性必须是一个函数的原因：

  当重复使用同一组件时，每个组件能享有独立的数据对象（函数返回的），数据之间不会相互干扰。  如果data属性是普通对象，那么这个普通对象被所有组件共享（指向同一引用），数据会互相干扰

- `vue` 的 `template` 如何转换为 `dom `？

  Vue 将模板编译成虚拟 DOM 渲染函数。结合响应系统，Vue 能够智能地计算出最少需要重新渲染多少组件（ diff 算法），并把 DOM 操作次数减到最少。

- 组件之间的通信

  - 父传子：父：（v-bind）（动态）调用子组件时 赋值 如 propName = 'hello' ，子 ：props 定义 propName
  - 子传父：子：$emit (eventName,arg) , 父 ： v-on:eventName = handleEvent, arg 将作为实参传入事件的处理函数

- `vue` 组件与 `WebComponents`规范

- 动态组件

  通过 Vue 的 `<component>` 元素加一个特殊的 `is` attribute 来实现

### Vue 的生命周期

![image-20211105162016120](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20211105162016120.png)

### Vue 开发者工具的使用

### vue-transition Vue 的过渡效果

### vue 的类组件写法

vue-class-components

### 其他

- v-html 的安全问题:请只对可信内容使用 HTML 插值，**绝不要**对用户提供的内容使用插值。

- 只有当实例被创建时就已经存在于 `data` 中的 property 才是**响应式**的

- 计算属性 对比 方法 ： 计算属性会缓存，（计算属性是基于它们的**响应式依赖**进行缓存的。也就是说计算属性依赖的 property 只有是响应式的才会进行更新或缓存），而方法每次都会调用都会重新执行一遍

- 计算属性对比侦听器（watch）：当需要在数据变化时执行异步或开销较大的操作时，watch方式是最有用的。所以 watch 一定是**支持异步**的，watch 没有缓存机制

- 在将 `v-bind` 用于 `class` 和 `style` 时，Vue.js 做了专门的增强。表达式结果的类型除了字符串之外，还可以是**对象或数组**。

- 当 `v-bind:style` 使用需要添加[浏览器引擎前缀](https://developer.mozilla.org/zh-CN/docs/Glossary/Vendor_Prefix)的 CSS property 时，如 `transform`，Vue.js 会自动侦测并添加相应的前缀。

- key 属性，vue 会尽可能地复用已存在地元素，如果不希望复用，添加 key 属性即可，元素会被重新渲染

- v-show , v-if  带有 `v-show` 的元素始终会被渲染并保留在 DOM 中。`v-show` 只是简单地切换元素的 CSS property `display`, 注意，`v-show` 不支持 `<template>` 元素，也不支持 `v-else`。`v-if` 有更高的切换开销，而 `v-show` 有更高的初始渲染开销。因此，如果需要非常频繁地切换，则使用 `v-show` 较好；如果在运行时条件很少改变，则使用 `v-if` 较好

- v-for (value（值）, name（键名）, index（索引）) ...in ，  v-for ... of

- **v-for 为什么要与 key 关联 --**  渲染效率相关？

- 需要在内联语句处理器中访问原始的 DOM 事件。可以用特殊变量 `$event`

  ```html
  <button v-on:click="warn('Form cannot be submitted yet.', $event)">
    Submit
  </button>
  ```

- v-model 的修饰符

  - .lazy
  - .number
  - .trim

- 解析dom 模板时的注意事项

  ![image-20211108153247082](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20211108153247082.png)

  

  有些 HTML 元素，诸如 `<ul>`、`<ol>`、`<table>` 和 `<select>`，对于哪些元素可以出现在其内部是有严格限制的, 当要在这些元素中使用自定义组件时，会导致渲染结果出错

  `is` attribute 给了我们一个变通的办法：

  ```html
  <table>
    <tr is="blog-post-row"></tr>
  </table>
  ```

- 将原生事件绑定到组件

  - .native 修饰符
  - `$listeners` property ，里面包含了作用在这个组件上的所有监听器

- 依赖注入

  provide : `provide` 选项允许我们指定我们想要**提供**给后代组件的数据/方法。(所提供的 property 是非响应式的)

  inject: 在**任何后代**组件里，我们都可以使用 `inject` 选项来接收指定的我们想要添加在这个实例上的 property

- 防抖节流

