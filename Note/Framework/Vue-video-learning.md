vue学习笔记：

视频：2019年最全最新Vue、Vuejs教程，从入门到精通

视频资源： https://www.bilibili.com/video/BV15741177Eh 

创建日期：2020.09.29  19：30

# ==Day 01==  2020.09.29 19:30开始

### 1.声明式编程和命令式编程：

Vue其实是在vue.js里定义的一个类，里面有各种属性，我们使用vue就是将其实例化，传递参数。

![image-20200929195042443](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929195042443.png)

![image-20200929195314943](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929195314943.png)

### 2.v-for：列表循环



![image-20200929200023583](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929200023583.png)

优点：只需要写一行代码，当数据更新时(比如添加一个列表项），页面实时发生改变（响应式，数据双向绑定）不需要再创建一个新的li，然后将数据传入。

![image-20200929195958548](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929195958548.png)

### 3.v-for案例:计数器

v-on:监听事件，当v-on 后面的事件发生时，我们可以设置函数对其进行响应，使用语法糖@可以代替v-on(on是当某事发生时的意思)

在vue对象中我们还可以将属性设置为函数，利用属性methods我们可以在methods属性中定义多个或一个函数。

这个案例如果使用原生js实现的话要：1.获取button，2.为button添加监听事件onclick，3.通过onclick调用实现计数器加减的函数。

![image-20200929201048399](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929201048399.png)

### 4.vue的MVVM：

MVVM：Model View ViewModel

![image-20200923215235230](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200923215235230.png)

![image-20200929201945298](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929201945298.png)

如下图：obj是model  vue是ViewModel ，Html是 View

![image-20200929202325451](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929202325451.png)

### 5.vue实例中传入的对象options（参数）

目前我们学习的 该对象可以包含 el,data,method 三个选项（属性）

![image-20200929203328885](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929203328885.png)

### 6.vue的生命周期：

我们可以在vue中调用一些函数来知晓其生命周期执行到那一步，如以下两个函数，会被打印在控制台（虽然我们没有调用这两个函数）。在vue的源码中定义有一个回调函数callHook

![image-20200929204706132](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929204706132.png)

![image-20200929204316375](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929204316375.png)

### 7.vue的生命周期函数有哪些：

vue每执行到某一步骤会有一个回调函数来说明当前vue的生命周期，我们可以通过调用这些回调函数，在vue的某一个生命周期对齐进行处理：下图包含了一些回调函数：在数据更新前，数据更新完毕后等等 。

![image-20200929205046910](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929205046910.png)

### 8.定义vue的template：

==在vscode中怎么定义live template?(定义vue的模板）==

### 9.模板语法：插值操作

mustache（胡子）

不仅可以直接写变量，也可以写一些简单的表达式：

{{ }}

![image-20200929211858335](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929211858335.png)

插值的其他操作：

v-once：一次性插入 不再修改

![image-20200929212236767](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929212236767.png)

![image-20200929212210177](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929212210177.png)

v-html：用来插入html内容

![image-20200929212455792](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929212455792.png)

![image-20200929212224265](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929212224265.png)

v-text:

(不常用，如果我们希望该字符串后面还要更新内容，该方法不会显示更新内容，在其后，跟的字符串会覆盖所有内容)

![image-20200929212726908](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929212726908.png)

![image-20200929212628141](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929212628141.png)

v-pre：

将其后的东西原模原样的渲染出来，不做解析

![image-20200929212902054](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929212902054.png)

v-cloak（斗篷）

当vue解析后，该属性会被删除，所以我们借助这属性，在vue被解析之前将元素隐藏，避免在页面中出现{{变量}}导致用户体验不好。但是不常用

![image-20200929213259466](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929213259466.png)



### 10.v-bind:

网页中很多数据都不是写死的，比如图片，图片数据是会更新的。借助v-bind我们可以实现动态的绑定元素的内容（比如超链接，图片链接）

![image-20200929213827683](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929213827683.png)

语法糖写法：直接写：（冒号）

![image-20200929214545564](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929214545564.png)

v-bind 动态绑定class

通过该方法我们可以给元素动态的绑定class，

对象语法：v-bind ：class = " { 类名：Boolean ，类名：Boolean...}"

一般布尔值我们不会直接指定而是通过变量设置，如下图isActive

通过该方法，我可以将时有时无的class按需添加到元素上，而元素始终需要的类，我们可以按照原来的方式写死。不必再通过原生js的方法获取对象后修改。

![image-20200929221254314](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929221254314.png)

![image-20200929220941101](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929220941101.png)

如果觉得上面的绑定导致代码太长，可以使用函数：

![image-20200929223208071](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929223208071.png)

在methods中定义函数，将上面的对象当中返回值返回即可（变量前要加this）

![image-20200929223220058](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929223220058.png)

![image-20200929223331171](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929223331171.png)

数组语法：用的不多

![image-20200929223643892](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929223643892.png)

![image-20200929223552025](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929223552025.png)



### ==11.练习：点击列表中的哪一项，该项就变成红色：==

![image-20200929224008944](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929224008944.png)

待完成

使用v-for遍历movies中的元素及其索引，li绑定一个类，只有当前的的li索引（我们定义的变量currentIndex)等于我们点击的索引时，才绑定该类。

![image-20200930152806969](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930152806969.png)

![image-20200930152712928](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930152712928.png)



### 12.v-bind 绑定style: 组件式开发常用

语法：

![image-20200929225216503](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929225216503.png)

同样的我们也可以使用一个函数来代替语法内容：

![image-20200929225336578](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929225336578.png)

数组语法：每个数组元素是一个对象，对象中是一个键值对。

![image-20200929225544165](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929225544165.png)

### 13.计算属性 computed：

输出一个名字的全名,可选以下四种方式：

![image-20200929230309032](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929230309032.png)

第四种方式使用的是计算属性 computed：

computed是一个对象，我们定义其一个属性fullName来返回全名（实际上也是语法糖）该属性的值是一个函数，该函数返回了全名。

这样我们再使用mustache{{fullName}}在页面输出全名，比较简洁，可读性更高。

![image-20200929230340729](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929230340729.png)

### 14.计算属性的复杂操作：

计算书的总价

![image-20200929231107866](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929231107866.png)

选中部分是ES6语法：for in ，for of

![image-20200929231033123](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200929231033123.png)

### 15.当天回顾：

见学习资料-vue -学习笔记-day01-文本笔记-课堂回顾

Day 01结束 2020.09.29 23：20 

# ==Day 02== 2020.09.30 9：20 开始

### 1.计算属性setter和getter：

计算属性有两个方法：set和get，一般我们不写set方法，所以计算方法可以看作一个只读属性。而当我们调用get方法时一般会简写：直接使用属性名：匿名函数的方式编写代码，（实际上不是匿名函数，是get被我们省略了），所以当我们在mustache里传入fullName属性时，其实是调用了该属性内的get方法来返回全名。

如果要使用set方法，该方法有一个参数，该参数会获取我们设置的修改值。

在本例中，如果我们想修改fullName，可以将我们在控制台传入的修改值拆分为数组，再分别赋值给firstName和lastName。

![image-20200930093138956](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930093138956.png)

### 2.计算属性和methods的对比：

计算属性的缓存：

计算属性computed：

会将计算的结果缓存，只要进行计算的两个变量没有改变，就不会重新计算，

以此来提高性能。

和methods不同，methods没有缓存机制，每次返回结果都会调用一次函数，当函数是一些比较消耗时间的内容时（比如for循环），多次调用会降低程序性能，所以我们尽量使用computed属性。

还要注意的就是在html里不要写一些复杂的逻辑运算，这样可读性差。

### ==3.块级作用域：let== 

==btns里面的i和监听函数里的i为什么不一样？==

answer：for 循环里的实际上是在大括号里定义的，如下图，for中的代码总共会被执行3次，每一次i都会被赋值，第一次i = 0，第二次i  = 1,第三次 i = 2.也就是说btns[i]分别在每次i别赋值时随后便被赋值，所以和循环到第几次的i是一样的。

但是回调函数不会在i被赋值后立马执行，而是在按钮被点击后执行，此时for循环内的3次循环已经执行完毕。因为在for循环中没有块级作用域（后面的循环修改i的值，i就统一被修改，当回调函数要使用变量i时，就只能找到最后被修改的i)，所以当我们点击任意一个按钮时，i已经被赋值为3（最后一次循环i++了），此时我们点击按钮（按钮的索引i在for循环时已经传入）调用回调函数时，打印的i就是3.

![image-20200930105122740](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930105122740.png)

ES5中，for和if是没有块级作用域的，只有函数才有。

![image-20200930100704615](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930100704615.png)

ES5:

![image-20200930101218732](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930101218732.png)

![image-20200930100943173](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930100943173.png)

ES6:使用let

![image-20200930110817321](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930110817321.png)

ES5中使用闭包：

而当我们在ES5中使用闭包解决该问题时，实际上就是相当于立即执行函数执行了多次，每次向其中传递了参数i作为实参。而ES5中函数是有自己的作用域的，所以函数中的i始终是for循环时传入的当次循环的i,不会因为后面整个for的i的改变而改变。

![image-20200930110436434](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930110436434.png)

**11：15** pause

**12：35** start

### 4.const的使用和注意点：

开发中优先使用const，当某一个变量需要改变的时候再用let

![image-20200930124023913](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930124023913.png)

![image-20200930125008499](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930125008499.png)

### 5.对象字面量的增强写法：

在对象字面量中：

键名和值名相同可以简写，函数 函数名 ：function 可以简写为：函数名 （）

还引入了部分typescript的介绍。

![image-20200930130137381](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930130137381.png)

### 6.v-on使用：

语法糖：@事件比如（@click）

@click = 方法 如果该方法不需要额外参数，那么可以不加（）

![image-20200930130857946](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930130857946.png)

如果方法本身有参数，但是我们不传入，则浏览器会自动将event对象传入，该对象包含了鼠标点击的坐标点等信息。

![image-20200930135419455](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930135419455.png)

如果我们在传递参数的同时也需要event对象，则使用$event作为形参。

![image-20200930135212959](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930135212959.png)

13:20  pause

13：40 start



### 7.v-on的修饰符使用：

使用.stop 阻止事件冒泡,

.prevent 阻止默认事件

.键代码 比如.enter 监听enter键帽

.once事件只触发一次。

![image-20200930140022288](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930140022288.png)

![image-20200930140329117](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930140329117.png)

### 8.v-if ，v-else-if，v-else

在逻辑判断简单的时候我们可以在html中使用这几个条件渲染，但是当逻辑稍复杂一点，我们尽量不要使用，而是使用计算属性 ，在属性中进行逻辑判断。

![image-20200930141213174](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930141213174.png)

登录切换小案例：点击按钮切换登录方式，邮箱登录还是账号登录 。

![image-20200930141615327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930141615327.png)

该案例引出一个问题：Vue在进行dom渲染时，会尽可能的复用已经存在的元素来优化性能，这造成我们在用户名输入框输入的内容，在我们切换登录方式之后还残留在邮箱输入框，没有进行清空。

如果我们不希望Vue对元素重复利用，可以使用key进行标识：

![image-20200930142652371](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930142652371.png)

![image-20200930141927397](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930141927397.png)

### 9.v-show和v-if的区别：

v-if如果不满足条件，则元素会直接被删除（第一次则不会渲染），而v-show会把元素的display属性设置为none

只渲染一次使用v-if，需要反复切换的内容就使用v-show

v-if使用较多



### 10.v-for遍历数组和对象：

遍历对象: v-for = "item in 数组名" {{items}} 也可以获取索引值，第二个参数。

![image-20200930143958960](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930143958960.png)

遍历对象，v-for = "item in 对象名"  {{item}}，也可以获取键名，"(value,key) in 对象名"第一个参数是值，第二个参数是键，也可以获取索引，第三个参数是索引。

![image-20200930143648146](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930143648146.png)



### 11.v-for绑定和不绑定key的区别：

绑定key之后，每个item和key之间一一对应，当我们向数组内插入新值的时候，便不会按照vue默认的diff算法插入，而是按照splice方法的模式插入。

所以一般我们使用v-for的时候都加上一个：key。

![image-20200930145405327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930145405327.png)

![image-20200930145055529](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930145055529.png)

![image-20200930145350788](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930145350788.png)



### 12.数组中哪些方法是响应式的：

push.,pop, shift,unshift,splice,reverse,sort

![image-20200930150735577](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930150735577.png)

![image-20200930151915284](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930151915284.png)

注意，通过索引值修改数组元素不是响应式的：

![image-20200930152214306](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930152214306.png)



### 13.==练习==：购物车案例：

界面搭建：

![image-20200930153946928](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930153946928.png)

![image-20200930154009400](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930154009400.png)

过滤器显示价格样式：在vue模块中添加filters属性：该属性值是一个函数。

注：tofixed方法可以将数值转换为小数（参数指定几位小数）

使用过滤器时 在需要过滤的属性后加   | 过滤器名字

这样做方便复用。

![image-20200930154600911](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930154600911.png)

![image-20200930154342556](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930154342556.png)

![image-20200930154324433](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930154324433.png)



为商品加减数目按钮绑定（事件）函数:

还需要动态绑定按钮的disabled属性，当商品数量减少到1，再点击减少按钮，则不会响应。

![image-20200930155115564](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930155115564.png)

![image-20200930155403528](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930155403528.png)

为移除商品按钮绑定函数：

![image-20200930155754734](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930155754734.png)

![image-20200930155650596](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930155650596.png)

当商品清空时显示购物车为空：使用v-if:

![image-20200930155636796](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930155636796.png)

统计商品总价：

使用计算属性：

![image-20200930155923279](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930155923279.png)

![image-20200930160002182](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930160002182.png)

**计算属性中使用高阶函数reduce：**

![image-20200930201407007](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930201407007.png)

**16：00** pause



**19：30 ** start

### 14.for in ，for of ：

使用for in ，for of 来计算总价：

for in 获取的是索引值，for of 获取的是item

![image-20200930193406989](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930193406989.png)

### 15.三个高阶函数：（方法）

15.filter方法：

面向函数编程

filter方法需要一个回调函数作为参数，该回调函数有一个参数并且必须返回一个Boolean值，当返回true时，会自动把这次回调函数里的参数（实参）加入到新的数组中，当返回false时，会自动过滤。

![image-20200930194718019](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930194718019.png)

ES5写法：

![image-20200930195104287](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930195104287.png)  

16.map方法：

map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。

map() 方法按照原始数组元素顺序依次处理元素。

**注意：** map() 不会对空数组进行检测。

**注意：** map() 不会改变原始数组。

![image-20200930195326958](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930195326958.png)

ES5写法：

![image-20200930200107150](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930200107150.png)

17.reduce方法：

两个参数，第一个参数是一个回调函数，第二个参数是我们设置的初始值，回调函数内有两个参数，preValue和n, (n可以是对象）第一个preValue的值是我们设置的初始值，后面每一个preValue都是前一个返回值，比如第一个返回值是20，则第二个preValue就是20.

该方法可以用来对数组内容汇总相加。

![image-20200930200300824](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930200300824.png)

ES5写法：

![image-20200930200127378](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930200127378.png)

*结合以上三个高阶函数，可以轻松完成我们在ES5中需要3个循环才能处理的任务：取出数组内小于100的值，将其乘2后相加计算出总结果：*

![image-20200930200841764](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930200841764.png)

结合箭头函数使用：

![image-20200930201006578](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930201006578.png)



### 16.v-model：实现了数据的双向绑定

表单绑定：

双向绑定和响应式的不同，响应式是指我们在后台，比如控制台，修改了数据后{{}}mustache里的内容会立刻发生改变，页面的渲染立发生改变。但是当我们改变页面上mustache里内容时，数据并不会有改变。

但是双向绑定，比如为表单input输入框绑定v-model后，实现了数据的双向绑定，当我们通过输入框修改其中的内容时，message也会发生改变

![image-20200930201821240](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930201821240.png)

实际上v-model也是一个语法糖：

他其实是基于v-bind和v-on实现的

使用v-bind （：）为value动态绑定message，监听input事件（我们向文本框中输入内容），当我们向文本框输入内容时，通过event对象，将此时文本框的value值赋值给message，以实现数据的双向绑定。

![image-20200930202808356](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930202808356.png)

### 17.v-model结合radio使用

label标签的作用：

Label标签有两个属性，一个是**for**，一个是 **accesskey**。

 **for**功能：表示这个Lable是为哪个控件服务的，Label标签要绑定了for指定HTML元素的ID或name属性*，你点击这个标签的时候，所绑定的元素将获取焦点*，点击label所包裹内容，自动指向for指定的id或name

 **accesskey**则定义了访问这个控件的热键( 所设置的快捷键不能与浏览器的快捷键冲突，否则将优先激活浏览器的快捷键)

 单选钮、复选框都要点击控件才能选中控件，而如果使用标识就可以实现点击文字选取。

<input type="checkbox" id="a" value="haha" name="cn">
 <label for="a" >haha </label>
 <input type="checkbox" id="b" value="hehe" name="cm">
 <label for="b" >hehe </label>

当v-model绑定的是同一个变量时，name可以省略。

![image-20200930203901697](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930203901697.png)

在Vue对象中，我们也可以将指定sex的值，则radio在页面上则表现为我们设置的初始值。

### 18.v-model和checkbox使用：

单选框：

![image-20200930204940649](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930204940649.png)

多选框：

![image-20200930204902063](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930204902063.png)

![image-20200930205001775](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930205001775.png)

![image-20200930204917816](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930204917816.png)

### 19.v-model结合select使用：

![image-20200930205353435](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930205353435.png)

![image-20200930205418783](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930205418783.png)

### 20.值绑定：

![image-20200930210145947](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930210145947.png)

有时候用户的可选项不是写死的，而是从服务器传过来的，这种情况下我们可以使用值绑定v-bind:value 结合 v-for 渲染表单。

![image-20200930205849453](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930205849453.png)

![image-20200930205838785](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930205838785.png)

### 21.v-model中修饰符的使用：

数据的双向绑定刷新频率太高了，有时候我们希望用户敲下回车再绑定，或者当文本框失去焦点时再绑定，这时候我们可以使用lazy修饰符。

![image-20200930210522650](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930210522650.png)

![image-20200930210713112](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930210713112.png)

number修饰符：

默认情况下，在输入框中输入的内容都会被当作字符串类型进行处理，如果我们希望处理的是数字类型，可以使用number修饰符

trim修饰符，用于过滤左右两边的空格。

![image-20200930211029483](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930211029483.png)



### 22.组件化：

什么是组件化：

![image-20200930211357854](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930211357854.png)

![image-20200930211523786](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930211523786.png)

组件的使用分三步：创建组件构造器，注册组件，使用组件。

![image-20200930212100809](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930212100809.png)

![image-20200930212132710](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930212132710.png)

### 23.组件的使用：

1. 使用Vue的extend方法创建组件构造器，该方法有一个参数，该参数是一个对象，在对象中有一个属性template用来定义模板，把我们希望组件化的内容传入该属性中就定义了一个模板。

2. 调用Vue的component方法注册组件，两个参数，第一个是我们自己定义的该组件的名字，第二个是我们之前创建的构造器。

![image-20200930212809109](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930212809109.png)

3. 使用组件。只有在Vue的实例里才能使用该组件。

![image-20200930213156707](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930213156707.png)

优点：可复用，可移植性高。

### 24.全局组件和局部组件：

全局组件可以在多个vue的实例下使用。

**在某个Vue的实例中注册，则会成为局部组件**

如下图注册的组件，只能在app中使用，在app2中使用，无法被解析。

开发中一般使用局部组件

![image-20200930213850431](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930213850431.png)

### 25.组件树:父组件和子组件区分：

  在一个组件内还可以再注册组件：则在一个组件内被注册的组件是该组件的子组件。

先创建一个组件构造器：

![image-20200930214826815](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930214826815.png)

在第二个组件构造器中注册第一个组件：

![image-20200930214906402](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930214906402.png)

在vue实例app中注册第二个组件：实例app也可以看作一个组件（顶层组件root)

![image-20200930215036737](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930215036737.png)

使用组件2（这个时候组件1由于是组件2的子组件，也会一起被渲染）

![image-20200930214712862](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930214712862.png)

组件也是有作用域的，在组件中注册的子组件只能在其父组件中使用，

如果想在实例中使用，则需要在实例中进行注册才可以。

![image-20200930215321070](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930215321070.png)

### 26.注册组件语法糖：（现在一般使用语法糖形式）

注册局部组件语法糖：直接在对应的vue实例中注测（省略了Vue.extend)

在components属性中传递一个对象。

![image-20200930215916352](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930215916352.png)

全局组件语法糖：

![image-20200930220118819](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930220118819.png)

![image-20200930220202726](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930220202726.png)



### 27.组件模板抽离的写法：

1. 使用script标签，注意类型必须是"text/x-template" 然后声明id

在模板中只需要传入我们声明的id即可

![image-20200930220610800](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930220610800.png)

![image-20200930220606439](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930220606439.png)

2. 使用template标签：

![image-20200930220858605](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930220858605.png)



### 28.组件数据的存放：

组件中不能访问Vue实例中的data，组件有自己的数据data,这个data必须是一个函数，且该函数必须返回一个对象。

组件中还可以有自己的methods

![image-20200930221336645](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930221336645.png)

![image-20200930221437755](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930221437755.png)

使用组件数据：

![image-20200930221500006](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930221500006.png)

为什么data属性必须是一个函数呢：

如果组件的data属性是一个对象的话，当我们创建了多个组件实例时，组件实例1如果修改了其中的数据的话，比如使一个计数器加一，那这样其他的组件实例再次使用该组建的数据的话，就会获取到之前的组件1修改后的值。 

而使用函数，每次函数返回的其实是一个新的对象，每个实例会得到属于自己的数据对象，数据之间不会相互干扰。  

![image-20200930222244621](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930222244621.png)



### 29.父子组件间的通信:

通过props向子组件传递数据

通过自定义事件向父组件发送消息

![image-20200930223422120](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930223422120.png)

![image-20200930223558418](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930223558418.png)

![image-20200930223534941](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930223534941.png)



### 30.父组件向子组件传递数据：

​    数据准备及局部组件注册：

![image-20200930225519601](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930225519601.png)

1. 在子组件中使用props属性传递数据，后面跟的是一个数组，数组中的元素必须用单引号包含，这些元素的名字会作为模板中的数据名使用。也可以使用对象传入，优点见下图。
2. 在模板中使用刚才在数组中命名的数据，作为数据展示
3. 使用该组件时，在组件标签内部用v-bind绑定父组件数据和子组件数据。

![image-20200930225903016](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930225903016.png)

![image-20200930225348205](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930225348205.png)



### 31.props驼峰标识：

v-bind不支持驼峰命名法，需要转换（不知道现在支持没有）

![image-20200930230935969](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930230935969.png)



### 32.子组件向父组件通信：(自定义事件)：

1. 数据准备，组件注册

![image-20200930231148164](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930231148164.png)

2. 流程：见图

![image-20200930232200459](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930232200459.png)

![image-20200930232802715](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930232802715.png)

![image-20200930232536188](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930232536188.png)

btnClick方法中定义了自定义的发射事件。

![image-20200930233215636](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200930233215636.png)

### 33.课堂回顾

Day 02 结束 2020.09.30 23：30 进度：60P结束 😵

# ==Day 03==  2020.10.02  16：10 开始

### 1.父子组件通信案例：结合双向绑定；

需求分析：

实现该功能：1. 当我们输入值时，对组件数据和我们的输入数据实现双向绑定，2.并且当组件数据改变时，父组件的数据也要同时发生改变。

3.在改变输入第一个输入框值的过程中，下面一个输入框的值永远是上面一个输入框的100倍。

在改变输入第二个输入框值的过程中，上面一个输入框的值永远是下面一个输入框的1/10

![image-20201002164816275](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002164816275.png)

1. 准备

![image-20201002165725323](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002165725323.png)

2. 数据绑定：

![image-20201002170115980](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002170115980.png)

经过以上两步，实现了父传子数据传送以及数据绑定，但是会报错。Vue官方不建议这样编写程序，因为Vue希望子组件中的数据是随着父组件传送过来的数据的改变为改变。不希望我们直接操作改变子组件的数据。

我们需要将v-model绑定在组件的data属性上：

![image-20201002170741981](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002170741981.png)

![image-20201002170649305](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002170649305.png)

3. 修改父组件内的数据：

![image-20201002172859256](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002172859256.png)

:value 那里是值绑定，其实就是v-model

![image-20201002172553171](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002172553171.png)

子传父，实现数据按比例变化：

![image-20201002171826837](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002171826837.png)

![image-20201002172204410](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002172204410.png)



**17：30** pause

**19：00**  start

通过watch实现：

![image-20201002191814418](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002191814418.png)



### 2.父组件访问子组件：

![image-20201002192121110](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002192121110.png)

两种方式：$children（不太常用）和$refs(比较常用)：

$children是一个数组，里面的每个元素是一个子组件，可以通过数组下标的形式获取到对应的子组件，一般我们需要获取到全部子组件的时候会使用该属性

$refs是一个对象，默认是一个空的对象，当我们需要获取某个组件时，需要先给该组件添加refs，（类似于元素id）然后在获取时，直接使用refs.组件名即可。

![image-20201002193218940](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002193218940.png)

![image-20201002192930604](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002192930604.png)

### 3.子访问父（不常用）：

使用$parent,会直接获取到其父组件，这样会使父子组件之间耦合度更高，所以一般不会使用。

使用$root，会获取到其根组件（一般是Vue实例）

![image-20201002193755125](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002193755125.png)

### 4插槽 Slot:

插槽让我们的组件更具有扩展性，可以让使用组件的人自己决定预留的插槽中展示什么内容，这样同时也提高了组件的复用性。

![image-20201002194446664](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002194446664.png)

![image-20201002194408758](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002194408758.png)

插槽的使用：

直接在模板中预留插槽，还可以设置默认值，当用户不传入元素时，则使用默认插入的元素：

![image-20201002202229871](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002202229871.png)

![image-20201002202117008](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002202117008.png)

具名插槽：

默认情况下我们在组件内插入的元素只会替换掉没有名字的插槽。当我们给插槽取名后，该插槽就变成了具名插槽。在使用时，只有指定该具名插槽，该插槽才会被替换。

这样更方便我们自定义插槽

![image-20201002204045445](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002204045445.png)

### 5.编译作用域：

![image-20201002205218428](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002205218428.png)

组件是有自己的作用域的，不会跨作用域，在哪个模板内定义的，作用域就在那，比如下图的cpn组件是在Vue实例app中注册的，则其作用域就是app。模板（template）cpn的作用域是组件cpn

![image-20201002204905778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002204905778.png)

### 6.作用域插槽：

![image-20201002210028593](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002210028593.png)

由于组件始是有作用域的，父组件不能直接访问到子组件的数据。

但是有时候我们在使用子组件的插槽时，可能子组件中的插槽中包含一些子组件中的数据展示，且有默认的展示形式。（比如列表形式展示，我们需要使用v-for 来获取子组件数据中数组的元素）

而根据需求，该子组件可能会使用多次，每一次都需要将数据以不同形式展示，可能不是以列表形式，可能是水平-分割。这个时候我们要更改数据展示形式就没那么简单了。

于是，vue提供了一种作用域插槽，可以在父组件中获取到子组件数据方便对布局等样式进行修改。

![image-20201002211209910](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002211209910.png)

![image-20201002211047921](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002211047921.png)

![image-20201002210908778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002210908778.png)

### 7.模块化开发：

一开始的模块化思想：将整个js文件内的代码，包含在一个匿名函数内部，在函数内定义一个对象，将想要导出的内容作为该对象的属性存储。

然后将该对象作为此匿名函数的返回值返回，将返回值返回给我们自己定义的一个变量，如moduleA，这样moduleA就成为了函数返回的对象，在其他地方我们想使用刚才js文件内的东西时，直接使用moduleA.属性即可。

解决了复用性低和命名空间污染的问题。

创建一个模板：

![image-20201002213054402](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002213054402.png)

使用该模板：

![image-20201002213134990](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002213134990.png)

![image-20201002213310569](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002213310569.png)

commonjs规范，见node教程；

### 8.ES6的模块化：

==见ES6教程：==

导入类型声明为module：

![image-20201002214353458](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002214353458.png)

导出：

![image-20201002214445878](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002214445878.png)

exportdefault：

![image-20201002215053934](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002215053934.png)

![image-20201002215031235](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002215031235.png)

导入：

![image-20201002214655360](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002214655360.png)

![image-20201002215405432](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002215405432.png)

### **9.webpack**

![image-20201002215714757](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002215714757.png)

![image-20201002220216119](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002220216119.png)

webpack基本使用：

1. 使用模块化思想进行开发

![image-20201002222150218](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002222150218.png)

2. 代码编写完成后，使用webpack的命令将入口文件打包。webpack会自动帮我们处理文件之间的依赖，我们只需要打包入口文件即可：

将src目录下的main.js打包到dist目录下，命名bundle.js

![image-20201002222339982](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002222339982.png)

3. 在html文件中引入打包好的文件即可：

![image-20201002222531225](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002222531225.png)

### 10.webpack配置：

先使用npm init 创建package.json文件对项目包进行描述

npm install 自动下载项目依赖的包。

本地安装webpack

![image-20201002223822682](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002223822682.png)

**webpack.config.js  配置:**

配置后直接使用webpack命令即可，不需要加打包文件路径和文件存放路径（这两个路径我们在该文件中配置了）

![image-20201002224137692](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002224137692.png)

**package.json配置:**

直接使用webpack命令使用的全局的webpack进行打包，有时候我们的项目依赖的webpack版本和全局的不一样，直接使用webpack命令进行打包有可能会出错。

所以我们在包配置文件内将webpack映射为命令build，使用是键入命令

npm run build 即可 该命令会优先执行本地的webpack（项目依赖的版本）

![image-20201002224040565](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002224040565.png)

![image-20201002224102567](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002224102567.png)

### 11.loader：

![image-20201002225027440](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002225027440.png)

![image-20201002225922896](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002225922896.png)

**webpack中的css文件配置：**

1. 安装css的loader：版本2.0.2

![image-20201002225629922](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002225629922.png)

2. 配置css-loader

![image-20201002225747971](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002225747971.png)

3. 安装style-loader 版本：0.23.1

![image-20201002225954245](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002225954245.png)

4. 添加style-loader： 注意使用顺序是从右向左

![image-20201002230313775](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201002230313775.png)

Day 03 结束 进度 78P结束 2020.10.02 23：00



# ==Day 04== 2020.10.03 11：05 开始

### 1.webpack-less文件处理：

安装对应的loader：

less-loader和less

![image-20201003130256746](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003130256746.png)

配置：

![image-20201003130544673](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003130544673.png)

其他也是一样配置：

图片处理：url-loader：

将图片转换为base64编码。

![image-20201003131450567](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003131450567.png)

配置：还有webp图片格式。

配置图片打包后的名字

![image-20201003133549824](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003133549824.png)

当图片大于limit限制大小，则需要使用file-loader:

![image-20201003132016983](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003132016983.png)

webpack.confug.js配置：在url前加上dist配置（暂时的配置，之后不再需要）

![image-20201003132735628](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003132735628.png)

### 2.webpack:ES6 转ES5 --Babel 

![image-20201003134402557](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003134402557.png)

安装babel-loadern :

![image-20201003134332338](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003134332338.png)

配置：

![image-20201003134307301](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003134307301.png)

### 3.webpack配置Vue：

配置后不需要下载Vue，然后在页面中引用了。

安装Vue：

![image-20201003135145338](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003135145338.png)

![image-20201003135220918](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003135220918.png)

配置Vue：

![image-20201003140046936](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003140046936.png)

![image-20201003140350730](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003140350730.png)

使用Vue:

![image-20201003140127055](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003140127055.png)

![image-20201003140251608](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003140251608.png)

### 4.el和template：

template属性中的内容会替换调el里的内容。

开发中不要在html直接写模板，而是只保留Vue实例对应的容器：

div id = app

![image-20201003141526826](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003141526826.png)

将模版定义在Vue实例里，Vue在编译的时候会自动把我们在html里创建的容器替换成模板中的内容。

![image-20201003141351739](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003141351739.png)

![image-20201003141512100](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003141512100.png)

### 5.Vue的终极使用方案：

安装vue-loader：

![image-20201003142236164](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003142236164.png)

![image-20201003142331541](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003142331541.png)

配置vue-loader：

![image-20201003142245542](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003142245542.png)

**抽取组件：**

1. 将模板抽取为一个组件（局部组件），该组件的内容会替代模板内的内容。

![image-20201003143326607](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003143326607.png)



![image-20201003143735065](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003143735065.png)

2. 将main.js中定义的组件抽取到Vue文件夹的app.js中：

![image-20201003144117956](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003144117956.png)

引入App（组件，一个对象，在Vue实例中注册组件时用到，默认导出不需要取名，而是由使用者在使用时自己命名，这里我们命名为App）

![image-20201003143941967](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003143941967.png)

3. 经过以上几步，进行Vue的开发变得更加简洁，但是在app.js中，模块和数据还是没有分离，所以Vue提供了一种文件格式.vue，专门用来存放组件，一个vue文件就是一个组件.

![image-20201003144600859](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003144600859.png)

在该文件中 模板和js文件得到分离，还可以定义样式。

#### ==question== *这样模板怎么导入？模板不是没有包含在默认导出里么，为什么后面导入的时候模板也一起导入了？*

![image-20201003144754761](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003144754761.png)

引入vue：

![image-20201003144845031](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003144845031.png)

运行报错：解决：

指定了版本：

![image-20201003145302342](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003145302342.png)

==还可以安装插件来解决？==

**组件内嵌套组件：**

以.vue文件的形式创建一个组件：

![image-20201003145627064](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003145627064.png)

组件内注册组件：

![image-20201003150009148](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003150009148.png)

使用子组件：

![image-20201003145520392](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003145520392.png)

![image-20201003150112465](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003150112465.png)



**15：40** pause

**19：40** start



### 6.webpack的plugin

横幅（banner）plugin

用来添加版权信息

![image-20201003194501532](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003194501532.png)

![image-20201003194752033](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003194752033.png)

HtmlWebpackPlugin:

![image-20201003195006065](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195006065.png)

![image-20201003195118765](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195118765.png)

安装：

![image-20201003195101521](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195101521.png)

![image-20201003195150321](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195150321.png)

导入：

![image-20201003195714537](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195714537.png)

使用

![image-20201003195558580](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195558580.png)

效果：

![image-20201003195630638](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195630638.png)

js压缩的plugin：uglifyjs

会把注释也删掉 所以会删掉设置的版权信息

![image-20201003195813271](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003195813271.png)

安装：

![image-20201003200007464](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003200007464.png)

导入：

![image-20201003200101088](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003200101088.png)

使用：

![image-20201003200119892](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003200119892.png)

### 7.webpack-dev-server:搭建本地服务器

安装：

![image-20201003200601204](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003200601204.png)

![image-20201003200636967](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003200636967.png)

配置：

![image-20201003201316537](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003201316537.png)

![image-20201003200750482](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003200750482.png)

![image-20201003201141427](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003201141427.png)

运行：直接使用命令npm run dev

### 8.webpack：配置文件分离

开发时依赖的配置和发布时依赖的配置的分离：

![image-20201003201919552](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003201919552.png)

分别抽离：prod.config.js，dev.config.js, base.config.js

![image-20201003201755885](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003201755885.png)

安装：merge

![image-20201003202004430](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202004430.png)

![image-20201003202248708](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202248708.png)

合并配置文件：

![image-20201003202239111](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202239111.png)

![image-20201003202330265](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202330265.png)

使用这两个配置文件：适应于不同场景

![image-20201003202516788](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202516788.png)

配置文件路径：

![image-20201003202728536](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202728536.png)

使用命令：

![image-20201003202600332](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202600332.png)

![image-20201003202914709](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003202914709.png)

### **9.脚手架：Vue Cli(command-Line-Interface)**

![image-20201003205659207](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003205659207.png)

![image-20201003205552889](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003205552889.png)

安装脚手架3:

![image-20201003210900874](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003210900874.png)

![image-20201003210513382](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003210513382.png)

拉取脚手架2模板：

![image-20201003210758117](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003210758117.png)

使用脚手架：

![image-20201003211622962](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003211622962.png)

### 10.脚手架初始化项目过程：

![image-20201003213254883](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003213254883.png)

![image-20201003213136087](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003213136087.png)

### 11.cli2项目结构解析：

![image-20201003213805671](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003213805671.png)

![image-20201003220017944](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003220017944.png)

==以上两个内容忘记了就回放视频==

### 12.课堂回顾





### 13.runtime-compiler和runtime-only的区别

*tips：如果不想使用ESlint规范，在index.js里将是否使用它的选项设置为false即可*

Vue 程序运行过程：

![image-20201003223630855](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003223630855.png)

![image-20201003224333576](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003224333576.png)

两者执行的步骤不一样，runtime-only不需要从template解析到ast这一步，因此实现的代码更小（少6kb)，性能更高。

![image-20201003224042206](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003224042206.png)

### 14.render函数解析：

render属性的值实际上是一个匿名函数，他的参数是一个函数，createElement函数，该函数的用法如下，在该函数内传入的参数会被渲染到虚拟dom，再由虚拟dom渲染到真实的dom。

render的返回值其实就是调用该函数，而该函数内传入的参数会作为vue实例的内容进行渲染

普通用法：

![image-20201003225607043](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003225607043.png)

效果：

![image-20201003230151987](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003230151987.png)

直接替换了div#app

![image-20201003230203753](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003230203753.png)

传入组件对象：该组件会成为Vue实例渲染的内容。

![image-20201003225659166](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003225659166.png)

在App组件对象中，我们也设置有模板内容(template)，该模板内容由vue-template-compiler处理，处理后我们传入的app组件对象中实际上没有template，而是一个render函数。

![image-20201003230618420](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003230618420.png)

![==](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003230342375.png)



**==结论== 我们在开发时，选择runtime-only而不是runtime-compiler**

### 15.VueCli3创建项目及目录结构：

==内容忘记了就回放视频==

创建项目：

![image-20201004115931163](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004115931163.png)

$mount和el区别不是很大。

![image-20201003232859017](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201003232859017.png)

Day 04 结束 2020.10.03 23：30 进度：97P结束

# ==Day 05== 2020.10.04 12:00开始

### 1.vuecli3配置文件的查看和修改：

使用vue ui命令进入以下界面，导入项目，进行配置

![image-20201004122710050](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004122710050.png)

也可以在文件中配置：创建一个文件vue.config.js 在这里面进行配置，会自动和lib里的配置文件进行合并。

![image-20201004124117756](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004124117756.png)

![image-20201004124239797](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004124239797.png)

![image-20201004123840715](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004123840715.png)

### 2.ES6：箭头函数及this指向：==见ES6笔记==

ES5:

var fn =  function(){

​	return  a + b;

}

ES6:

let fn =  (a,b) => {

​	return  a + b;

}

![image-20201004131434187](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004131434187.png)

### 3.什么是路由及其映射：==复习计网==

![image-20201004135536184](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004135536184.png)

![image-20201004140203621](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004140203621.png)

### 4.前端渲染和后端渲染，前端路由和后端路由:

网页发展阶段：

1. **后端路由**阶段：在此阶段，当我们在网页中输入url时，网页会向服务器请求资源，请求的资源会直接通过jsp等技术在后端渲染好（包括数据和html,css静态资源），然后由前端进行展示，而url和页面资源之间的映射关系也是由后端处理，也就是后端路由。

jsp（java server page）将java代码和html代码嵌套在一起，处理数据请求等任务。==可以参见豆渣电影项目复习==

![01-后端路由阶段](C:\Users\yokoda\Desktop\前端学习笔记\学习资料\Vue\vuejs资料和代码\Day 06\上课画图\01-后端路由阶段.png)

2. 前后端分离阶段：随着ajax的出现，后端不再负责渲染和路由，只负责提供数据，当浏览器中输入url时，会向静态资源服务器请求html ,css,js资源。由前端进行渲染，浏览器执行js代码时，如果需要数据，会向服务器请求数据，服务器只用处理数据请求即可，拿到数据后，js代码会创建一些元素，然后再由前端进行渲染。

在该阶段，不同的url请求的是不同的静态资源。此阶段没有前端路由概念

![02-前端后端分离阶段](C:\Users\yokoda\Desktop\前端学习笔记\学习资料\Vue\vuejs资料和代码\Day 06\上课画图\02-前端后端分离阶段.png)

![image-20201004141833861](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004141833861.png)

3. 单页面富应用阶段SPA,整个网页只有一个html

就是在前后端分离阶段的基础上，加了一层前端路由。该阶段的网页只有一个html文件，请求资源时，会下载静态服务器中的所有资源。当我们在页面上进行标签切换（比如从主页切换到about页面），url改变，但是页面不会重新刷新。而是由**前端路由**向下载好的全部资源中抽离当前页面需要的***资源（结合Vue来看，其实就是一个个的组件）***

在Vue中vuerouter会进行资源管理

![image-20201004142852890](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004142852890.png)

![03-SPA页面页面的阶段](C:\Users\yokoda\Desktop\前端学习笔记\学习资料\Vue\vuejs资料和代码\Day 06\上课画图\03-SPA页面页面的阶段.png)

### 5.改变URL但是不让页面刷新的两种手段：

1. 改变URL的hash：

![image-20201004145736102](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004145736102.png)

2. html5的history.pushState(压栈和弹栈)

![image-20201004145958305](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004145958305.png)

html5的history.replaceState

![image-20201004150440417](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004150440417.png)

html5的history的go方法和forward方法：

![image-20201004150724221](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004150724221.png)

![image-20201004150746442](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004150746442.png)

## *Vue-router:*

### 6.vue-router的安装和配置：

![image-20201004150933399](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004150933399.png)

![image-20201004151033333](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004151033333.png)

2.配置路由：（router/index.js）

![image-20201004153613472](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004153613472.png)

挂载：（main.js）

![image-20201004153242772](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004153242772.png)

### 7.使用路由：

![image-20201004153727734](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004153727734.png)

创建路由组件：

![image-20201004154846766](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004154846766.png)

配置路由映射：

![image-20201004154730797](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004154730797.png)

使用路由：

![image-20201004214251790](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004214251790.png)

![image-20201004154457228](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004154457228.png)

### 8.路由的默认值：

![image-20201004155535662](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004155535662.png)

将路由模式修改为html的history模式：

![image-20201004155715800](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004155715800.png)

### 9.router-link的属性补充：

![image-20201004160240142](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004160240142.png)

![image-20201004160627262](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004160627262.png)

统一配置活跃类：

![image-20201004160706610](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004160706610.png)

### 10.通过代码跳转路由：

在方法内调用$router属性（vue-router底层给每一个组件都添加了该属性）的push或replace方法来改变url。

![image-20201004161057749](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004161057749.png)

**16：40**   pause

**19：30**  start



### 11.动态路由的使用：

有时候我们的url不是固定的,比如当不同的用户点击个人中心时，user/用户名（或者用户id）

用户名的不一样会让url也不一样，我们希望url也能随着用户数据的改变而改变，这个时候就需要使用到动态路由：

![image-20201004200205412](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004200205412.png)

![image-20201004195807209](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004195807209.png)

配置动态路由：

![image-20201004195715475](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004195715475.png)

![image-20201004200006427](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004200006427.png)

### 12.打包后的js文件分析：

运行时的支持代码，包括ES6转ES5的支持等。

![image-20201004201732282](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004201732282.png)

### 13.路由懒加载：

一般情况下，我们编写的业务代码会全都打包到一个js文件，随着页面增多，js文件会越来越大，如果我们一次性下载所有资源，可能需要花费一定的时间，甚至造成网页短暂空白。

但是如果我们把不同路由对应的组件分别打包，当路由被访问时才加载，就可以提高网页打开速度。这样的方法叫懒加载。

![image-20201004202010012](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004202010012.png)

![image-20201004202040043](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004202040043.png)

![image-20201004202311283](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004202311283.png)

懒加载的方式：

![image-20201004202844224](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004202844224.png)

![image-20201004203034894](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004203034894.png)

效果：

![image-20201004203219645](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004203219645.png)

### 14.路由的嵌套：

步骤：

创建两个组件：homeNews ，homeMessage:

![image-20201004210421358](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004210421358.png)

动态加载：

![image-20201004210555218](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004210555218.png)

在home的路由配置中对两个嵌套路由进行配置：

![image-20201004210245634](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004210245634.png)

在home组件中嵌套路由组件：

![image-20201004210806845](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004210806845.png)

效果：

![image-20201004205947760](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004205947760.png)

### 15.vuerouter：路由参数传递：

第一种方式就是我们在动态路由中传递用户id的方式；

![image-20201004211239926](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004211239926.png)

第二种方式：

正常配置路由：

![image-20201004212154957](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004212154957.png)

传递方式：

![image-20201004212403373](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004212403373.png)

取出参数：

![image-20201004212523570](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004212523570.png)

*URL的构成*：

![image-20201004211909442](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004211909442.png)

结果：

![image-20201004212058218](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004212058218.png)

不使用router-link组件传递参数：

![image-20201004212839327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004212839327.png)

![image-20201004212931628](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004212931628.png)

效果：路由组件（默认a标签）由button代替了。

![image-20201004213005692](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004213005692.png)

### 16.区分：$router 和 $route

router是VueRouter类的一个实例，VueRouter内部有back，forward等方法，所以我们才能通过该实例调用back方法实现回退。

![image-20201004215048744](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004215048744.png)

![image-20201004213730395](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004213730395.png)

route是当前活跃的路由对象：

![image-20201004213806269](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004213806269.png)

![image-20201004213543950](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004213543950.png)

**所有的组件都继承自Vue类的原型**

![image-20201004215135815](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004215135815.png)

vue源码内为每一个组件（在Vue的原型内）都添加了$router（然后将我们定义的router作为参数传入）和$route属性（谁处于活跃就是谁）

![image-20201004214811644](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004214811644.png)

![image-20201004214837655](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004214837655.png)

### 17.导航守卫：

需求：在SPA中，我们想要在切换路由的同时改变网页的标题：

![image-20201004220227226](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004220227226.png)

解决方案1：借 助组件的生命周期函数created（）在组件被创建时，通过js改变 网页标题：

![image-20201004222207005](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004222207005.png)

但是当组件过多时，这样的方法效率不高。

所以我们可以借助全局导航守卫来完成此需求：使用beforeEach来监听跳转

该方法必须调用其第三个参数next函数

![image-20201004222536733](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004222536733.png)

在路由配置中配置meta元数据：

![image-20201004222753273](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004222753273.png)

![image-20201004222507859](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004222507859.png)

![image-20201004222654583](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004222654583.png)

补充：

![image-20201004223309732](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004223309732.png)

后置钩子不会接收next函数

![image-20201004223808832](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004223808832.png)

![image-20201004223520663](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004223520663.png)

![image-20201004223654529](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004223654529.png)

### 18.路由：keep-alive:

每次切换组件，vue都会重新创建一次组件。

而keep-alive包裹的组件不会频繁地被创建和销毁，只会创建一次。

如果我们希望组件被创建和销毁多次，可以在exclude中指定：

![image-20201004230751961](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004230751961.png)

![image-20201004230821406](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004230821406.png)

![image-20201004224507860](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004224507860.png)

通过这两个函数，离开后再回来就会将之前保存的路由路径push到当前的路由路径，==实现切换页面后再次返回还是保持页面原样==。这两个函数，只有该组件使用了keep-alive组件保持了状态后才有效。

![image-20201004225858909](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004225858909.png)

![image-20201004230248519](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004230248519.png)

![image-20201004225518972](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201004225518972.png)

Day  05 结束 2020.10.04 23：20 进度：118P结束

# ==Day 06==  2020.10.05 14：00开始

### ==1.实现TabBar== 

vuecli2实现

1.思路：组件化 ，定义插槽，flex布局水平对齐tabbar

![image-20201005134552293](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005134552293.png)

组件抽取分析：

![image-20201005150544459](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005150544459.png)

补充：图片插槽应该安排两个：一个正常显示，一个用来显示活跃状态时的样式。

### 2.组件活跃状态时的样式切换：

![image-20201005151935263](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005151935263.png)

![image-20201005152306004](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005152306004.png)

### 3.实现路由：

路由准备：安装插件，创建路由，导出路由对象。

![image-20201005152533882](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005152533882.png)

导入及挂载：

![image-20201005153631628](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005153631628.png)

配置路由映射：

![image-20201005153136830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005153136830.png)

监听tab-bar-item的点击事件：

![image-20201005153531758](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005153531758.png)

![image-20201005153833546](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005153833546.png)

![image-20201005153922390](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005153922390.png)

点击事件的响应函数：

![image-20201005154204054](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005154204054.png)

![image-20201005154250860](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005154250860.png)

配置路由模式为history：

![image-20201005154355635](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005154355635.png)

效果：

![image-20201005154509071](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005154509071.png)



注意文件存放路径的规划：

![image-20201005152929019](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005152929019.png)

### 4.tab-bar-item组件活跃状态时的样式切换：

利用计算属性：

不等于-1说明当前路由组件处于活跃状态。则isActive为true，会切换活跃时的图片显示。

![image-20201005155825087](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005155825087.png)

实现开发人员动态决定活跃路由组件字体颜色：

参数传递+动态绑定+计算属性

![image-20201005160145724](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005160145724.png)

![image-20201005155409639](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005155409639.png)

![image-20201005160537648](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005160537648.png)

动态绑定：

![image-20201005160734383](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005160734383.png)

TabBar组件搭建完毕，**可复用**

补充：将App里的模块代码抽离，单独放到一个组件，这样App里的代码就比较简洁。

形成组件树。

![image-20201005195212076](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005195212076.png)

![image-20201005193419982](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005193419982.png)

给文件路径取别名：

![image-20201005195407969](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005195407969.png)

但是图片等资源文件要使用路径别名的话，要在别名前加~

![image-20201005195510547](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005195510547.png)



**16：10** pause

**19：30**  start 



### 5.Promise：

![image-20201005195636196](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005195636196.png)

链式编程，优雅地处理异步请求

![image-20201005203735708](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005203735708.png)

也可以这样写：

![image-20201005204356160](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005204356160.png)

### 6.Promise的链式调用:

需求：

![image-20201005205859295](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005205859295.png)

![image-20201005205819208](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005205819208.png)

**上面的简写：**

![image-20201005210059898](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005210059898.png)

**再次简写：** js会自动封装promise

![image-20201005210141851](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005210141851.png)

请求失败的简写：（抛出错误）

![image-20201005210344739](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005210344739.png)

简写：

![image-20201005210425787](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005210425787.png)

或者：

![image-20201005210452915](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005210452915.png)

### 7.Promise的All方法:

当需要两个请求都完成才能进行下一步操作的时候，可以使用该方法。

![image-20201005211504889](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005211504889.png)

![image-20201005211330801](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005211330801.png)

## 8.VueX:状态管理模式

![image-20201005211654227](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005211654227.png)

![image-20201005212152168](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005212152168.png)

![image-20201005212636577](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005212636577.png)

### 9.Vuex使用：

安装：版本@3.0.1

![image-20201005213555138](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005213555138.png)

创建一个文件夹来存放Vuex相关文件：

![image-20201005213817567](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005213817567.png)

vuex准备：

![image-20201005214020513](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005214020513.png)

挂载：

![image-20201005214129563](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005214129563.png)

### 10.如何修改vuex里的状态：（如变量的值）vuex的使用

多页面（多个页面需要使用的变量）状态管理：

![image-20201005215038998](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005215038998.png)

vuex-devtools（chrome浏览器插件）和mutations：

通过mutations修改状态：

![image-20201005220810225](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005220810225.png)

在App组件中使用store中的变量counter：通过事件监听来调用方法使用变量

![image-20201005221434354](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005221434354.png)

使用$store.commit方法获取到mutations里定义的方法，从而实现在App组件 中修改couter的值（counter由vuex托管）

![image-20201005220728889](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005220728889.png)

状态跟踪：

![image-20201005220504400](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005220504400.png)

### 11.state的单一状态树：

单一数据源，只创建一个store

![image-20201005221949968](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005221949968.png)

### 12.vuex-getters：

在getters里定义方法，（类似计算属性）在其他地方通过$store.getters调用

方法内可以传入的参数如图：

![image-20201005230309524](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005230309524.png)

![image-20201005230518614](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005230518614.png)

**22：30** pause

**23：00**  start

### 13.mutations的携带参数：

![image-20201005230739301](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005230739301.png)

![image-20201005230826310](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005230826310.png)

传递参数：Payload

![image-20201005231246610](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005231246610.png)

![image-20201005231255972](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005231255972.png)

![image-20201005231530455](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005231530455.png)

![image-20201005231726749](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005231726749.png)

使用方法：

![image-20201005231846285](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005231846285.png)

mutation提交风格：

![image-20201005231942913](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005231942913.png)

![image-20201005232236595](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201005232236595.png)

Day 06 结束 2020.10.05  23：25 进度 135P结束

# ==Day 07== 2020.10.06 12：50 开始

### 1.state数据的响应式原理：

放入state里的属性都会被加入到vue的响应式系统中，没有加入的属性不具有响应式特性。

开发中可以使用vue.set,vue.delete方法实现未声明属性的响应式。

![image-20201006130531466](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006130531466.png)

![image-20201006125129492](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006125129492.png)

![image-20201006130303836](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006130303836.png)

### 2.mutations的类型（type)常量：

官方推荐写法，避免写错type名字

定义常量

![image-20201006131102401](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006131102401.png)

导入：

![image-20201006131321105](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006131321105.png)

mutations里的方法使用常量命名

![image-20201006131143469](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006131143469.png)

在提交时也使用常量，让和mutations统一。

![image-20201006131157134](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006131157134.png)

### 3.vuex-actions:

异步操作不能被devtools捕捉快照。

![image-20201006131706418](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006131706418.png)

如果要让异步操作也能被devtools捕捉，可以通过actions：

![image-20201006134136788](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006134136788.png)

app内的方法：点击按钮修改信息：

![image-20201006133103657](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006133103657.png)

![image-20201006132946851](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006132946851.png)

![image-20201006133959382](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006133959382.png)

最终修改数据的操作还是由mutations里定义的updateInfo完成的：

![image-20201006134146433](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006134146433.png)

需求：

当信息修改完毕后，需要通知信息已经修改完成：

![image-20201006134807019](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006134807019.png)

![image-20201006134719412](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006134719412.png)

结合promise使用：通过dispatch实现promise的中转。

![image-20201006135326758](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006135326758.png)

![image-20201006135208833](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006135208833.png)

### 4.vuex-modules:

![image-20201006135604736](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006135604736.png)

使用方法：

定义模板对象：

![image-20201006141814104](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006141814104.png)

这里的context.commit提交是的当前模板的mutations：

context是一个对象，通过它还可以获取到一些其他数据。

![image-20201006141956796](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006141956796.png)

在store里声明该模板：

![image-20201006140825553](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006140825553.png)

在模板内使用定义getter时的注意事项：

![image-20201006141619695](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006141619695.png)

使用模板里的属性，getters，mutations，actions:

![image-20201006141152656](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006141152656.png)

![image-20201006141253399](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006141253399.png)

### 5.vuex-store文件夹的目录结构组织：

补充：ES6对象的解构：

![image-20201006142447017](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006142447017.png)

当我们把所有要管理的状态及相关的getters，actions都放在一个文件时，该文件会显得臃肿且不便于管理，因此官方推荐我们将其中的内容抽离：形成以下目录结构

![image-20201006143119783](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006143119783.png)

![image-20201006143332830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006143332830.png)

![image-20201006143305949](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006143305949.png)

这样，index文件就干净利索许多。

![image-20201006143521568](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006143521568.png)

**15：20** pause

 

## axios:

### 6.网络模块封装：

axios的基本使用：

安装：

![image-20201006150011316](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006150011316.png)

![image-20201006150028649](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006150028649.png)

导入：

![image-20201006185002282](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006185002282.png)

直接使用：

![image-20201006184931845](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006184931845.png)

![image-20201006184916425](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006184916425.png)

![image-20201006185104425](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006185104425.png)

### 7.axios发送并发请求：

![image-20201006185913443](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006185913443.png)

![image-20201006190007007](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006190007007.png)

### 8.axios的配置：

全局配置：

![image-20201006190323581](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006190323581.png)

常见的配置选项：

![image-20201006190408401](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006190408401.png)

### 9.axios实例和模块封装：

实例：

![image-20201006192039607](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006192039607.png)

![image-20201006191932680](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006191932680.png)

模块封装：

我们在开发中要尽量减少对第三方框架的依赖，因为这些框架有可能会不在使用，我们需要更换其他框架。如果我们在每一份代码中都对第三方框架依赖太重的话，修改代码时每一个文件都要改，十分麻烦。  

所以我们将第三方框架抽取出来，进行封装，当需要更换时，只需要修改封装的文件即可。

axios的封装：

![image-20201006193523899](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006193523899.png)

使用封装：

![image-20201006194246682](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006194246682.png)

### 10.axios拦截器的使用：

应用场景见图：

![image-20201006194854082](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006194854082.png)

![image-20201006195738923](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006195738923.png)

![image-20201006195823788](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006195823788.png)

### ==11.git的基本指令使用：==

本地项目链接远程仓库；

![image-20201006201123349](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006201123349.png)

# 项目开发：

### 1.目录结构安排：

![image-20201006203444650](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006203444650.png)

### 2.引入normalize.css,创建base.css

![image-20201006203831974](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006203831974.png)

### 3.路径别名配置和editconfig:

![image-20201006204607994](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006204607994.png)

![image-20201006204759479](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006204759479.png)

### 4.项目的模块划分：

根据tab-bar划分模块；

### 5.请求首页数据：

不要在首页组件内直接请求，而是新建一个js文件来专门存放对应的请求。

![image-20201006215152477](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006215152477.png)

### 6.首页轮播图的实现：

1.引入组件：

![image-20201006220437191](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006220437191.png)

2.插入数据：

请求数据：

![image-20201006220948079](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006220948079.png)

插入数据:之后会做抽离操作

![image-20201006221317594](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006221317594.png)

3.抽取组件：

上面的写法会让home组件变得非常繁杂，因此对首页的轮播图单独进行抽取：

![image-20201006221722153](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006221722153.png)

![image-20201006222019759](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006222019759.png)

效果：

![image-20201006222043869](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201006222043869.png)

Day 07 结束 2020.10.06 22：30 进度 155P结束

# ==Day 08==  2020.10.07 12：50 开始

### 1.项目开发：

tips:

1. 注意导航条要绝对定位，层级较高

2. 首页的内容不能被导航栏遮盖，所以要设置padding。
3. tab-control注意点：移动端使用sticky定位实现滚动固定，该组件在各个地方使用时，只是文字不一样，没有必要预留插槽，实现该组件的思路和实现Tab-bar的很像。
4. 在开发中，根据导入的文件的性质不同，在导入的地方进行分组，用空格或者注释隔开，比如子组件和公共组件。 在注册组件时，也尽量保持导入顺序一致。

![image-20201007131449362](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007131449362.png)

### 2.首页保存商品的数据结构设计：

请求数据时，请求的数据是一个对象，包含了3个分类下的商品数据，在对象中我们在根据商品分类进行分组，每个属性对应一个商品类型，每个属性也是一个对象，对象中保存了两个属性，一个是当前加载的页码，一个是目前数据总共多少条。

属性里的数据是动态变化的。（用户会上拉请求新的数据）

![image-20201007132534424](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007132534424.png)

![image-20201007132923917](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007132923917.png)

### 3.首页数据的请求和保存：

将组件创建时执行的函数，抽取到methods里，这样created只负责调用相应的函数，而函数内部的代码我们放在methods里编写

![image-20201007134550290](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007134550290.png)

![image-20201007134453178](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007134453178.png)

数据的请求和保存：

编写网络请求的代码：

![image-20201007135546778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007135546778.png)

导入请求数据的方法：（网络相关）

![image-20201007135249398](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007135249398.png)

保存数据：

注意：一般不写重名，下图黄色的getHomeGoods函数是methods内定义的函数，白色的是网络请求相关的函数。

![image-20201007135205474](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007135205474.png)

### 4.首页商品数据的展示:==注意父子组件间的通信和flex布局==

创建两个组件来展示数据：

![image-20201007140647580](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007140647580.png)

![image-20201007140803029](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007140803029.png)

组件goodsList::

![image-20201007141813001](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007141813001.png)

子组件goodsListItems:

![image-20201007141145675](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007141145675.png)

### 5.点击tab-control切换商品展示：

父子通信，子传父：

![image-20201007142517557](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007142517557.png)

![image-20201007142723248](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007142723248.png)

监听事件处理函数：

![image-20201007143336619](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007143336619.png)

==index==  来自于哪？（见下图）tab-control

![image-20201007223825308](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007223825308.png)

![image-20201007143310339](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007143310339.png)

![image-20201007143045487](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007143045487.png)

![image-20201007143159046](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007143159046.png)

### 6.better-scroll:

解决移动端（网页端）的原生滚动的卡顿问题，还能实现弹簧效果。

安装：

![image-20201007145401504](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007145401504.png)

![image-20201007145418679](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007145418679.png)

tips:原生实现局部滚动：

![image-20201007145720919](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007145720919.png)

基本使用：

![image-20201007201233204](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007201233204.png)

一些其他属性：

![image-20201007204751370](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007204751370.png)

**15：00**  pause

**20：00**   start

### 7.将better-scroll运用到项目中：

基本使用：

![image-20201007205027475](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007205027475.png)

![image-20201007205915247](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007205915247.png)

### 8.better-scroll封装：

tips：refs的运用，明确地拿到某一个组件。

![image-20201007225045893](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007225045893.png)

![image-20201007211723466](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007211723466.png)

封装：

![image-20201007212149830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007212149830.png)

使用：导入，并注册

![image-20201007211843416](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007211843416.png)

![image-20201007211612959](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007211612959.png)

![image-20201007211657752](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007211657752.png)

也可以使用下面的方法：

![image-20201007214943813](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007214943813.png)

### 9.backToTop组件封装：

tips: .native修饰符：监听一个组件的原生事件。

![image-20201007213115473](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007213115473.png)

![image-20201007213058765](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007213058765.png)

封装的组件：

![image-20201007214600137](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007214600137.png)

**该组件的功能实现：**

使用：导入及注册：

![image-20201007214058838](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007214058838.png)

![image-20201007214024642](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007214024642.png)

![image-20201007214205659](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007214205659.png)

![image-20201007214352901](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007214352901.png)

![image-20201007213639327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007213639327.png)

### 10.backTop的显示和隐藏：

![image-20201007220356211](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007220356211.png)

![image-20201007215815072](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007215815072.png)

在首页内使用scroll组件：

![image-20201007220637673](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007220637673.png)

决定backTop组件显示还是隐藏：

![image-20201007220929977](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007220929977.png)

![image-20201007220739283](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007220739283.png)

![image-20201007220128152](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007220128152.png)

### 11.上拉加载更多的功能实现：

![image-20201007221608376](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007221608376.png)

监听上拉事件：注意pull-up-load属性要为true，表示我们在首页需要用到上拉加载更多的功能，在scroll组件我们定义的默认为fasle

![image-20201008141401449](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008141401449.png)

![image-20201007221454654](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007221454654.png)

处理上拉事件：获取新数据，展示。

![image-20201007222745389](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007222745389.png)

![image-20201007222502182](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007222502182.png)

![image-20201007223125281](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201007223125281.png)

### 12.内容回顾

Day 08 结束 2020.10.07 23：00 进度 171P结束。

# ==Day 09== 2020.10.08 12:30开始



### 1.解决better-scroll的滚动bug：

![image-20201008123720119](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008123720119.png)

![image-20201008123440070](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008123440070.png)

解决思路：监听每一张图片的加载事件，只要加载完成就执行一次refresh刷新BScroll里的滚动区域高度。

![image-20201008124747904](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008124747904.png)

解决步骤：

监听图片加载事件：

![image-20201008124645780](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008124645780.png)

监听事件对应的函数：

我们监听到图片加载完成后，要在scroll组件内刷新（refresh）滚动区域的高度，但是图片所在的组件 和scroll组件关系太远，无法直接通信。

因此我们借助**==事件总线==** 里的$bus属性来发射及监听自定义事件：

![image-20201008125303492](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008125303492.png)

但是vue中其实并没有$bus这个属性，所以我们利用原型将其添加至vue，令其等于一个vue实例，vue实例可以作为事件总线。

![image-20201008125436711](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008125436711.png)

首页组件监听图片加载完成事件：

scroll组件内定义的refresh函数：

![image-20201008125753211](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008125753211.png)

不要在created里调用refresh：在mounted里调用，这样才能获取到元素。所以将下图的监听代码移到mounted

![image-20201008125649487](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008125649487.png)

![image-20201008131939926](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008131939926.png)

补充，要为scroll函数的调用加一层判断：

![image-20201008132136535](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008132136535.png)

### ==2.频繁刷新的防抖函数处理：== 

关于timer的疑问，timer的值是什么（相当于1个flag用来判断是否清空）

关于clearTimeOut的疑问，为什么clearTimeOut后面不会调用refresh 函数了？

刷新太快，会让服务器压力增大，性能变低。

![image-20201008135319984](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008135319984.png)

![image-20201008135925457](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008135925457.png)

将防抖函数抽取到utils：

![image-20201008141037287](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008141037287.png)

### 3.tab-control吸顶效果实现：

tips:所有的组件都有一个属性$el，用于获取组件中的元素.

先使用@load监听图片的加载。然后做相应处理：

![image-20201008143621209](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008143621209.png)

![image-20201008143418627](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008143418627.png)

![image-20201008143044231](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008143044231.png)

通过复制完成吸顶操作：

将tab-control组件复制一份：

![image-20201008145613758](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008145613758.png)

取消导航栏脱离文档流：让tab-control1不被遮盖：

![image-20201008145450393](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008145450393.png)

为上面一个tab-control1添加一个类，使其层级盖住轮播图

![image-20201008145742722](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008145742722.png)

拿到偏移量：（注意是第二个tab-control)

![image-20201008145934327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008145934327.png)

根据偏移量判断tab-control1是否显示: 

![image-20201008145145051](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008145145051.png)

![image-20201008145115573](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008145115573.png)

![image-20201008150639704](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008150639704.png)

![image-20201008150203424](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008150203424.png)

![image-20201008145008925](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008145008925.png)

### 4.保持home首页离开时的状态：

![image-20201008152327723](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008152327723.png)

1.离开时不要让home销毁：

![image-20201008152147682](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008152147682.png)

2.设置一个变量用来保存离开时的滚动值。

![image-20201008152031084](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008152031084.png)

![image-20201008151949444](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008151949444.png)

## 详情页开发：

### 5.跳转详情页并携带id：

点击商品（goodsitems）跳转到详情页；

先创建详情页组件，为详情页配置路由，监听商品点击事件，在响应函数中进行路由跳转并传递参数：

id:

![image-20201008153002123](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008153002123.png)

![image-20201008153413343](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008153413343.png)

路由配置和参数传递：

![image-20201008153233835](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008153233835.png)

![image-20201008153129962](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008153129962.png)

### 6.详情页导航栏：

实现详情页导航栏组件后，在详情页组件中注册并引用即可：

导航实现如下：

![image-20201008153936717](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008153936717.png)

![image-20201008154248329](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008154248329.png)

![image-20201008154351515](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008154351515.png)

![image-20201008154144935](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008154144935.png)

### 7.详情页数据请求和轮播图：

网络请求函数的封装：

![image-20201008154637029](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008154637029.png)

导入网络请求函数后，请求数据：

![image-20201008154747645](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008154747645.png)

数据展示：轮播图

获取轮播图图片：

![image-20201008160149285](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008160149285.png)

创建轮播图组件并传递数据：

![image-20201008160402208](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008160402208.png)

详情页轮播图组件：

![image-20201008161409414](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008161409414.png)

注意：==因为我们之前将整个组件keepAlive导致从首页点击进详情页时组件不会重新被创建，所以数据也不会更新==

因此我们在keepAlive时要将Detail组件排除在外。

![image-20201008161523553](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008161523553.png)

**16：20 **  pause

**19:20**      start

### ==8.详情页数据展示：（学习数据整合的思想）==

![image-20201008194950338](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008194950338.png)

要获取的数据很多很杂，我们可以将要使用的数据全部请求后保存到一个对象里面，当我们需要使用数据时，直接到我们定义的对象里取用即可。

![image-20201008193627832](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008193627832.png)

![image-20201008194348202](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008194348202.png)

展示商品信息，商品服务等数据的组件：

![image-20201008193400226](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008193400226.png)

![image-20201008193737667](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008193737667.png)

使用：

![image-20201008194500158](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008194500158.png)

![image-20201008194552365](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008194552365.png)

### 9.店铺信息展示：

![image-20201008195247028](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008195247028.png)

思路和展示商品信息一样，也是需要先将复杂的数据抽取到一个组件中，让后创建对应的组件进行数据展示。

![image-20201008195539036](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008195539036.png)

![image-20201008195730897](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008195730897.png)

### 10.为详情页添加滚动：

将tab-bar盖住

![image-20201008200018444](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008200018444.png)

保持nav层级在上：

![image-20201008200237814](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008200237814.png)

导入及注册scroll，给其设置高度，然后将要滚动的内容包裹起来即可。

![image-20201008200530805](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008200530805.png)

![image-20201008200342381](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008200342381.png)

### 11.商品的详细信息展示：

数据不多，一个图片数组，还有一个商品描述信息

分别取出，封装一个组件进行展示即可。

同时还要注意图片加载导致better-scroll有时候不可滚动的问题。

![image-20201008200959848](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008200959848.png)

![image-20201008201212629](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008201212629.png)

解决图片加载导致better-scroll有时候不可滚动的问题:

先监听图片的加载事件，然后发射自定义事件，再由外部对其进行监听后做相应处理。

![image-20201008201559783](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008201559783.png)

![image-20201008201910985](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008201910985.png)

对自定义事件的处理函数：

![image-20201008202207594](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202207594.png)

![image-20201008202225060](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202225060.png)

### 12.商品参数的数据展示：

![image-20201008202621001](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202621001.png)

也是先将复杂的数据保存到一个对象，导入后保存数据，再创建组件进行展示。

![image-20201008202504099](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202504099.png)

![image-20201008202727555](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202727555.png)

数据展示：

![image-20201008202817896](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202817896.png)

在详情页导入及注册后使用（使用时传递参数）：

![image-20201008202921643](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202921643.png)

![image-20201008202945300](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008202945300.png)

### 13.商品评论信息的展示：199P（188P-198P大部分内容是重复的）:

也是一样的思路，但是这里只取一条评论数据：

对评论数据我们需要进行判断，因为有些商品的评论可能没有。

![image-20201008211102621](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008211102621.png)

先获取数据，创建一个组件来展示数据，在详情页使用该组件（同时导入和注册组件）时传入数据，然后再组件中创建模板对传入的数据进行展示：

![image-20201008210745242](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008210745242.png)

### ==14.== 如何将时间戳转换为格式化的字符串（如：2020/10/08）

服务器返回时间都是以Unix时间元年为起点，返回对应的时间戳

![image-20201008211850799](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008211850799.png)

创建一个Date对象，将对应时间戳*1000得到毫秒数据，调用对应的方法方法，传入参数进行格式化：

![image-20201008212215357](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008212215357.png)

js中格式化时间的方法：

![image-20201008212628932](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008212628932.png)

### 15.用户评论的时间数据的处理：

我们从服务器获取到的是时间戳，但是我们希望用户看到的是格式化的时间，

所以需要进行转换：

使用过滤器：

![image-20201008213448775](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008213448775.png)

时间转换：

![image-20201008212748655](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008212748655.png)

### 16.推荐页面的完成：

请求到数据后保存，交由相应组件处理：

因为推荐组件其实和首页的商品展示组件（goodsList）一样，所以我们可以复用组件。

![image-20201008213805794](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008213805794.png)

获取数据：

![image-20201008213738221](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008213738221.png)

复用组件：

![image-20201008214020256](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008214020256.png)

使用时传入数据：

![image-20201008214112530](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008214112530.png)

注意传入的数据不一样，所以可能对图片资源属性的命名也不一样，所以要用或运算来灵活选择：

![image-20201008214433663](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008214433663.png)

### 17.取消全局监听：

因为我们是将goodList组件复用，而在该组件中，监听了一个图片加载事件，以向首页组件发射自定义事件，这就导致我们在详情页使用该组件时，图片加载后也会向首页发送自定义事件。

为了避免上述情况，我们可以采用录用来分别判断当前在哪个页面，然后分别做不同的处理。

![image-20201008214747485](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008214747485.png)

也可以采用取消全局事件监听的方法：

传入两个参数，要取消的事件哎，及其在的函数。

![image-20201008220002818](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008220002818.png)

![image-20201008215448760](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008215448760.png)

### 18.==mixin混入：==

通常用该方法对代码进行复用

![image-20201008220717308](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008220717308.png)

导入混入mixi文件，在组件内声明：

![image-20201008220954895](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008220954895.png)

![image-20201008220922706](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008220922706.png)

mixin内的代码就会被执行。

### 19.==联动效果==：点击标题定位到对应内容。

思路：在tab-control组件内监听点击事件，然后在响应函数中将自定义事件发射到details组件，details组件监听自定义函数，做出相应处理：

处理函数的思路：

![image-20201008225401474](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008225401474.png)

在哪才能获取到正确的偏移量呢？

![image-20201008230253207](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008230253207.png)

![image-20201008225201421](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008225201421.png)

上面的位置不能获取到正确的值，而在每次图片加载完后，可以获取到正确的值，但是会多次获取到偏移量。

为了只获取一次正确的偏移量，我们对获取偏移量的代码添加了防抖操作：

![image-20201008225903261](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201008225903261.png)

Day 09 结束：2020.10.08 23：00 进度：205P结束

# ==Day 10== 2020.10.09 12:30 开始

### 1.滑动到对应内容时，定位到对应标题

在scroll里有监听滚动事件，并发出了一个自定义事件：

![image-20201009124222818](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009124222818.png)

我们在详情页监听该事件，并做相应处理：要传入参数probe-type，否则无法获取位置信息。

![image-20201009124440948](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009124440948.png)

在处理监听事件的函数中实现功能：

首先获取到当前滚动的y值，判断y和每个组件位置的关系，然后将此处的index传入导航的index以实现样式随滚动的位置而改变。

分两组判断，因为导航位置数组（themeTopYs）的长度是4，当循环到最后一次i=3时（第四次循环）判断当前滚动的位置（positionY)和导航中组件的位置themeTopYs[i+1]=themeTopsY[4]并不存在（undefined）就会导致数组越界获取不到值从而不能进入if代码块。

所以需要分组判断，

当i<length-1时，也就是前三种情况，判断位置间的关系，

当i===length（4） -1 时，也就是最后一次循环时，进行位置判断

![image-20201009131052776](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009131052776.png)

然后将当前的i值赋值给导航组件，实现功能。

![image-20201009124129650](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009124129650.png)

tips:使用for in获取的i是字符串类型：若要使用的是数字类型，需要进行类型转换。或者为了避免次问题直接使用比较原始的for循环方式（上图）

![image-20201009125028464](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009125028464.png)

hack做法：

条件判断简化：为数组添加一个最大值作为第5个元素，判断时就不需要分组了（因为数组多了一个元素，当最后一次判断时，和数组的最后一个元素[(i=3)+1]做比较，该值不会是undefined，而是我们添加进去的max值）

同时循环的次数也要相应的减一，因为我们只需要判断4次即可（而length=5）

![image-20201009131353852](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009131353852.png)

![image-20201009131734442](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009131734442.png)

### 2.底部工具栏的封装：

创建一个组件，然后在组件进行导入和注册，并且将其放在滚动组件外。设置其位置。（fixed，或者relative）

注意因为加入了底部工具栏，所以滚动区域的高度也要减去工具栏的高度。

bottom-bar组件：

![image-20201009134303208](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009134303208.png)

### 3.回到顶部按钮的混入封装：

封装：

![image-20201009135521451](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009135521451.png)

导入及注册：

![image-20201009135134856](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009135134856.png)

要在其他组件内使用也很简单：导入，注册，使用，即可

![image-20201009135701459](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009135701459.png)

### 4.将商品加入购物车的实现：

在底部工具栏组件中监听购物车按钮的点击，向外发射自定义事件，在详情页组件对自定义事件进行监听，然后编写对应的函数进行处理：

![image-20201009155054007](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009155054007.png)

使用vuex:

创建vuex对象，导入及挂载。

![image-20201009154903045](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009154903045.png)

![image-20201009141141963](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009141141963.png)

**14：20** pause

**15：40** start

保存商品的代码：

![image-20201009160354693](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009160354693.png)

![image-20201009160746462](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009160746462.png)

优化代码结构：

mutations尽量执行简单的逻辑任务：复杂的逻辑处理交由actions处理

![image-20201009161934764](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009161934764.png)

actions:

![image-20201009162300236](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009162300236.png)

![image-20201009162119058](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009162119058.png)

type:

![image-20201009162144126](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009162144126.png)

优化目录结构：将mutations，actions,type名字都单独抽取到一个js中导出，在vuex中引入并使用就可以

![image-20201009161719570](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009161719570.png)

### 5.购物车的数据展示：导航栏==mapGetters的用法==

复用之前创建的导航栏组件，更换插槽内容后：

![image-20201009163654866](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009163654866.png)

将购物车内的商品数量显示在括号中：

![image-20201009163805171](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009163805171.png)

为了简单的传入商品数量，利用计算属性：

![image-20201009163909038](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009163909038.png)

为了在多个地方也能使用该变量，将其封装到getter：

![image-20201009164044948](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009164044948.png)

![image-20201009164021419](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009164021419.png)

为了让计算属性中的代码减少，利用==mapGetters==方法对getters里的属性做映射：

![image-20201009163332329](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009163332329.png)

![image-20201009164208866](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009164208866.png)

### 6.购物车商品列表的展示：

![image-20201009170930223](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009170930223.png)

创建一个组件来展示商品列表，再针对每一个商品创建一个组件来展示具体的商品数据，然后在购物车组件中引入，注册，使用商品列表组件即可：

数据使用mapGetters来获取。

![image-20201009165942322](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009165942322.png)

![image-20201009170206617](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009170206617.png)

商品信息组件：

![image-20201009170125599](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009170125599.png)

解决better-scroll不能滚动的问题：

原因，向购物车添加商品后，better-scroll并不知道我们的数据更新了，所以可滚动高度依然是0 ，因此我们要在每次进入购物车时，对better-scroll进行一次刷新。

![image-20201009170514608](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009170514608.png)

### 7.购物车列表，每个商品的单独展示：

组件模板：

![image-20201009170755210](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009170755210.png)

封装勾选按钮：

![image-20201009171539543](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009171539543.png)

![image-20201009171433045](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009171433045.png)

### 8.更改商是否被选中：

![image-20201009171858841](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009171858841.png)

![image-20201009172329474](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009172329474.png)

![image-20201009172222798](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009172222798.png)



**17：30**  pause

**19：00**  start

### 9.购物车底部汇总组件：

在购物车页面导入，注册，并使用。

![image-20201009191716658](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009191716658.png)

组件模板：

![image-20201009191818709](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009191818709.png)

![image-20201009192102790](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009192102790.png)

### 10.全选框的设置：

动态绑定选中状态：

![image-20201009193812197](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009193812197.png)

设置选中状态：

![image-20201009193729511](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009193729511.png)

监听全选框的点击：

监听对应的处理函数：

![image-20201009194744735](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009194744735.png)

### 11.商品已添加到购物车的弹窗Toast：

在监听购物车点击事件对应的响应函数中返回一个promise对象

然后回到详情页调用响应函数的then方法进行处理

![image-20201009195643119](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009195643119.png)

![image-20201009195512641](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009195512641.png)

### 12.actions里封装的函数也可以映射，使用mapActions：

![image-20201009195923513](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009195923513.png)

![image-20201009195909503](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009195909503.png)

![image-20201009195512641](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009195512641.png)

### 13.Toast的封装：普通封装

![image-20201009200417221](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009200417221.png)

![image-20201009200727916](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009200727916.png)

![image-20201009200825752](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009200825752.png)

### 14.Toast的封装：==插件封装==

首先在toast文件夹下创建一个index.js文件

入口文件main.js里导入并安装插件，use方法会自动执行安装（install ）函数。

![image-20201009202508076](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009202508076.png)

插件封装：

![image-20201009203209460](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009203209460.png)

在toast组件中国设置默认参数值。

![image-20201009202813300](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009202813300.png)

封装好后，只需要一句代码即可调用：

![image-20201009203341327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009203341327.png)

### ==15.解决移动端300ms延迟：fastClick==

现在似乎大部分浏览器已经解决了该问题

300ms原因：

![image-20201009205106795](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009205106795.png)

安装

![image-20201009203958540](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009203958540.png)

使用：

![image-20201009204105085](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009204105085.png)

### 16.图片懒加载：vue-lazyLoad框架：

![image-20201009205904715](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009205904715.png)

![image-20201009210227302](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009210227302.png)

![image-20201009210252558](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009210252558.png)

![image-20201009210327606](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009210327606.png)

### 17.px2vw-css单位转换插件：

还有其他的插件，px转rem等。

![image-20201009210823052](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009210823052.png)

插件中的配置：

![image-20201009211337218](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009211337218.png)

### 18.nginx:项目部署：这里只说了本地部署。（将自己的电脑作为服务器，外部不能进行访问）

### 19.nginx:项目的远程部署：

首先要买一台远程服务器（阿里云或者腾讯云），然后将项目拷贝到主机的根目录（通过一些软件）

![image-20201009214419574](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009214419574.png)

![image-20201009214241457](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009214241457.png)



### 20.Vue的响应式原理：

![image-20201009214615498](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009214615498.png)

![image-20201009215802297](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009215802297.png)

set中可以监听数据改变(obj.name = kobe)，get中可以监听数据获取（obj.name)

![image-20201009220433021](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009220433021.png)

![image-20201009220800394](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009220800394.png)

![image-20201009220959498](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009220959498.png)

![image-20201009221146875](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009221146875.png)

![image-20201009221459912](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009221459912.png)

![image-20201009221337439](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009221337439.png)

![image-20201009221958794](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009221958794.png)

![image-20201009222544786](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009222544786.png)

![image-20201009222619242](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201009222619242.png)

完整代码：

![image-20201225155038621](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225155038621.png)

![image-20201225155221742](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225155221742.png)

![image-20201225155255011](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225155255011.png)

![image-20201225155333181](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225155333181.png)

![image-20201225155357043](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225155357043.png)

![image-20201225155413466](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225155413466.png)

![image-20201225155457860](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225155457860.png)

![image-20201225160015682](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201225160015682.png)

2020.10.09 22:40 结束 进度231P结束 视频结束

### 虚拟DOM

![image-20201226150249858](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201226150249858.png)

真实dom对应虚拟dom：

![image-20201226165453042](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201226165453042.png)

创建虚拟节点：

![image-20201226210447325](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201226210447325.png)

![image-20201226163930593](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201226163930593.png)

对vue的响应式原理还是不太了解 接下来需要多复习，多练，才能记得清楚。****