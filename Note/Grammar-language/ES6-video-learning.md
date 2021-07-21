# 尚硅谷Web前端ES6教程，涵盖ES6-ES11

资源： https://www.bilibili.com/video/BV1uK411H7on?from=search&seid=13986015627271652015 

创建时间：2020.09.24

# ==Day 01== 2020.09.24 20:50

### 1.版本更新内容：

![image-20200924205049010](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924205049010.png)

### 2.声明变量：

#### **let**

不能重复声明，块级作用域，==？不影响作用域链== ，不存在变量提升（声明提前）

![image-20200924213732831](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924213732831.png)

==let的运用实例：==

![image-20200924214150714](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924214150714.png)

==question：==*对于作用域以及循环还需要了解，为什么使用var和items[i]就没效果还是存在疑问。*



#### const：

一定要赋初始值，一般使用大写，常量的值不能修改，块级作用域，对数组和对象的元素进行修改，不算对常量的修改，除非直接修改其地址。所以使用const声明数组和对象能避免我们误操作修改其地址。

![image-20200924214627695](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924214627695.png)



### 3.解构赋值：

数组的解构：

![image-20200924215146780](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924215146780.png)

对象的解构：（常用于将方法结构）

![image-20200924215119102](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924215119102.png)

==question：==*最后两行代码是解构了第一个属性name还是方法xiaopin呢？*



### 4.模板字符串：

使用反引号 ``  特点：其内容中可以直接出现换行符，（不再需要使用+"/n"的方式），使用${字符串变量}字符串可以直接进行字符串拼接。

![image-20200924215650907](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924215650907.png)



### 5.简化对象写法：

当变量名和属性名相同时，可以简写。

同时在方法的定义上也可以直接写（）{} (下附图片ES5写法)

![image-20200924220117787](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924220117787.png)

ES5写法：

![image-20200924220331345](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924220331345.png)

![image-20200924220347153](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924220347153.png)



### 6.箭头函数：

ES5:

var fn =  function(a,b){

​	return  a + b;

}

ES6:

let fn =  (a,b) => a + b;

![image-20200924221135011](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924221135011.png)

特性：

**this** 箭头函数中的this是静态的， 它始终指向函数声明时作用域下的this的值

如下两个函数，都是在全局作用域中声明的，this指向的是window对象，当调用函数时，会打印window下name的值。

当通过call函数传递块级作用域下的name时，由于getName函数不是箭头函数创建，所以this指向调用school对象，而箭头函数创建的getName2函数的this由于是静态的，所以不会改变，仍然是window。

![image-20200924221339988](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924221339988.png)

箭头函数不能作为构造函数实例化对象：

![image-20200924222013853](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924222013853.png)

不能使用arguments变量：

箭头函数的简写：当形参有且只有一个时，可以省略小括号，当函数代码只有一条语句时，可以省略大括号，此时，return关键字也必须省略。

![image-20200924221037280](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924221037280.png)



### 7.箭头函数的案例：

此时在匿名函数的作用域下this指向的是ad，我们将其赋值给_this，因此可以通过_this改变ad的样式。

而由于箭头函数的this是静态的，它指向起创建时的作用域下的this，也即是ad，所以也可以在箭头函数内直接使用this改变ad的样式。

![image-20200924222622016](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924222622016.png)

2. 

筛选偶数，注释内的是ES5代码

![image-20200924223229063](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924223229063.png)

箭头函数不适合与this有关的回调（比如事件回调）以及事件的方法。



### 8.函数参数默认值：

![image-20200924223825687](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924223825687.png)

配合解构使用：

不使用解构：

![image-20200924223950148](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924223950148.png)

ES6:

==question==

![image-20200924223857767](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924223857767.png)



### 9.rest参数：

rest用来代替arguments获取函数的实参，参数必须放在最后，获取的实参是一个数组。

![image-20200924225549977](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924225549977.png)

![image-20200924225725372](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924225725372.png)



### 10.扩展运算符：...

...能将数组转换为逗号分隔的参数序列

![image-20200924225922285](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924225922285.png)

扩展运算符的运用：

数组的合并：（注释内是ES5的方式）

![image-20200924230128390](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924230128390.png)

数组的克隆：

![image-20200924230239659](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924230239659.png)

将伪数组转换为数组：

![image-20200924230338694](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924230338694.png)



### 11.新的数据类型：symbol

![image-20200924230600729](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924230600729.png)

创建symbol：

s2,s3不全等，s4,s5全等。

![image-20200924230831909](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924230831909.png)

### 12.symbol的使用：

向对象中添加方法：

ES5：需要检查对象中是否已经含有up方法

![image-20200924231538381](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924231538381.png)

ES6:即使已经有up方法也不会影响原结构。

![image-20200924231258829](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924231258829.png)

![image-20200924231314636](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924231314636.png)

![image-20200924231243774](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924231243774.png)



### 13.symbol的方法：

在一些特定的场景下会被调用。

![image-20200924231741937](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924231741937.png)

![image-20200924232042761](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924232042761.png)

![image-20200924232147437](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924232147437.png)

### 14.迭代器：

iterator就是一个属性：

![image-20200924232444214](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924232444214.png)

![image-20200924232227417](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924232227417.png)

for in 

for of

![image-20200924232720607](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924232720607.png)

原理：

*注意next方法的返回值*

![image-20200924232511191](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924232511191.png)

![image-20200924232643461](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200924232643461.png)

Day 01 2020.09.24 23：30 进度 18P结束；

# ==Day 02==  2020.09.25 09：30 开始 

### 15.迭代器的应用：自定义遍历数据

在这里我们的需求是：使用for of 遍历对象里的数组里的每一个值（该数组是对象的属性）通过迭代器 ，我们可以自定义的遍历数据。

*注意this指向的对象*

![image-20200925092516686](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925092516686.png)

![image-20200925092500943](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925092500943.png)



### 16.生成器：

其实就是一个特殊的函数

==question：==*yeild语句是用作什么的？*

![image-20200925092844140](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925092844140.png)

![image-20200925101047744](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925101047744.png)

![image-20200925101056355](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925101056355.png)



参数传递:

next 内的参数将作为其上一个yield语句的执行结果

![image-20200925101723531](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925101723531.png)

![image-20200925101744238](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925101744238.png)

### 17.生成器实例：

1. 解决回调地狱

ES5:

![image-20200925102053106](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925102053106.png)

利用生成器：

![image-20200925102257973](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925102257973.png)

![image-20200925102356189](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925102356189.png)

2. 

下面代码块中的next是第二次调用（第一次调用是生成器函数调用next），它的实参将作为第一个yield语句的返回结果（即console.log(users) 的输出结果）

![image-20200925102937752](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925102937752.png)

![image-20200925103227931](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925103227931.png)

![image-20200925102825821](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925102825821.png)



### 18.promise：

==question：==*什么是异步操作（异步编程）?*

![image-20200925131200185](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925131200185.png)

promise对象有三个状态：初始化，成功，失败。

当调用resolve时，对象的状态是成功，可以调用promise对象中的then方法

![image-20200925103408391](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925103408391.png)

形参resolve和reject可以是其他名字，但是一般我们使用resolve和reject对其命名。

then方法有两个参数，两个参数都是函数，成功的形参一般命名为value，

失败的形参一般命名为reason。

当promise对象状态为成功时（即调用了resolve时）会调用then方法的第一个函数，当对象状态为失败时，则会调用第二个函数。

==question:==*then方法里的函数的参数是怎么传递的？为什么变量err 会传递到function（reason）？*

![image-20200925104729895](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925104729895.png)



promise封装读取文件：

![image-20200925132313093](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925132313093.png)

注释部分是ES5

![image-20200925132236800](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925132236800.png)



promise封装ajax：

不使用promise：

![image-20200925132614492](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925132614492.png)

使用promise：

![image-20200925132849368](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925132849368.png)

![image-20200925132902191](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925132902191.png)

promise的then方法：

![image-20200925133649993](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925133649993.png)



promise实践：读取多个文件

不使用promise：

![image-20200925133936481](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925133936481.png)

使用promise：

![image-20200925134639781](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925134639781.png)

![image-20200925134359573](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925134359573.png)



promise的catch方法：

就是处理当promise对象状态为失败时的方法。

![image-20200925134838852](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925134838852.png)



### 19.集合set：

![image-20200925135315895](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925135315895.png)

![image-20200925135257581](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925135257581.png)

集合的运用：

数组去重：

![image-20200925135428333](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925135428333.png)

求交集：

==question：==*数组的filter方法*

![image-20200925135748127](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925135748127.png)



求并集：

![image-20200925135842106](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925135842106.png)



求差集：

![image-20200925135950267](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925135950267.png)



### 20.map：

和普通对象不同的是map可以将各种类型的值，包括对象作为属性名（键key）

![image-20200925140031224](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925140031224.png)

![image-20200925140301287](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925140301287.png)

![image-20200925140436301](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925140436301.png)



### 21.类（class)

![image-20200925140510334](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925140510334.png)

ES5创建一个“类”（实例化一个对象）

![image-20200925140700959](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925140700959.png)

ES6创建一个类：

![image-20200925140919700](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925140919700.png)

static关键字定义的变量属于类，而不属于实例化对象：

![image-20200925141217425](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925141217425.png)

### 22.类的继承：

父类：

![image-20200925141801624](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925141801624.png)

子类继承：

![image-20200925141833548](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925141833548.png)

子类对父类方法的重写：

子类可以重写父类方法，但是不能调用父类的方法：

![image-20200925142046445](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925142046445.png)

  

**14：20**  pause

**16:40**     start





### 22.get 和 set

类中的constructor不是必须的

get常用于进行一些动态变化的属性进行操作，比如加减运算等

set常用对一些需要判断的属性进行操作。set可以添加更多的设置和判断。

![image-20200925164628406](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925164628406.png)



### 23.ES6里的数值扩展：

Number.EPSILON表示Javascript里的最小精度，如果二值之差小于该值，则认为他们是相等的。

![image-20200925165136853](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925165136853.png)

二进制和八进制：

![image-20200925165330299](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925165330299.png)

Number 的方法：

Number.isFinite():用来检查一个数值是否是有限数；

（100/0是无限数）

Number.isInteger :检查一个数是否为整数

![image-20200925165418546](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925165418546.png)

Math的方法： 

Math.trunc 将数字的小数部分抹掉

Math.sign 判断一个数到底是正数负数还是零 正数返回1 负数返回-1 零返回0 

![image-20200925165737416](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925165737416.png)

![image-20200925165009759](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925165009759.png)



### 24.对象方法的扩展：

![image-20200925170004609](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925170004609.png)

#### Object.is：

判断两个值是否完全相等，和全等不同的是，用它比较两个NaN时 ，返回的是true。

![image-20200925170150766](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925170150766.png)

#### Object.assign：

对象的合并，有相同的属性时，后定义的对象会覆盖之前定义的，没有则不会覆盖。（适合用作配置合并）

![image-20200925170311439](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925170311439.png)

#### 设置原型对象：

如下代码设置了cities这个对象作为school的原型（cities的原型是object)

一般不建议这样设置对象的原型，（一般会在创建对象时就指定）

![image-20200925170654743](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925170654743.png)



### 25.模块化：

![image-20200925170909655](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925170909655.png)

模块化语法：

![image-20200925171111277](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925171111277.png)

**三种暴露方式：**

**export** -分别暴露：

当我们希望那些数据对外暴露，在其前面加上export关键字：

在其他文件引入时，需要在script标签中使用type = module 引入：

语法：import * as 变量名 from "文件路径" ；

这样在文件中暴露的变量会被存入到我们定义的变量中，如图中的m1.

![image-20200925171334498](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925171334498.png)

统一暴露：在export中写入需要暴露的数据，引入的方式和分别暴露一样；

![image-20200925171717220](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925171717220.png)

![image-20200925171812562](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925171812562.png)



默认暴露：export default，在括号中写入要暴露的数据，引入方法和之前一样，不同的是，要使用其中的变量，需要加上default关键字。

![image-20200925171933396](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925171933396.png)

![image-20200925172056875](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925172056875.png)



**引入模块数据方式：**

第一种就是之前使用的，我们称之为通用导入；

![image-20200925171812562](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925171812562.png)

2. 解构赋值形式导入：

   当变量有重名时，可以使用as 设置别名

   对于默认暴露，不能直接使用default，需要为default设置别名

![image-20200925172623847](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925172623847.png)

3. 简便形式：仅针对默认暴露：

![image-20200925172803132](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925172803132.png)

4. 使用入口文件导入：

![image-20200925173039045](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173039045.png)

一般在做项目时不会这样引入，为了考虑兼容性问题，而会使用Babel对模块化代码进行转换。

![image-20200925173014454](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173014454.png)

![image-20200925172949896](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925172949896.png)



### 26.Babel

（视频中的文件目录结构）：

![image-20200925173850297](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173850297.png)

![image-20200925174600121](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925174600121.png)

1. 安装：（局部安装）

![image-20200925173443995](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173443995.png)

![image-20200925173503714](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173503714.png)

2. 

![image-20200925173549913](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173549913.png)

转换前：

![image-20200925173720983](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173720983.png)

转换后：

![image-20200925173646295](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925173646295.png)



3. 打包：

在HTML页面中引入打包后的文件

![image-20200925174104716](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925174104716.png)

![image-20200925174014776](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925174014776.png)



### 27.ES6模块化引入npm包：

1. 安装：

![image-20200925174825483](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925174825483.png)

2. 导入npm包；

![image-20200925175008512](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925175008512.png)



# ES6以后新特性：

## 1.ES7：

![image-20200925192242759](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925192242759.png)

### 数组.includes 

用来判断数组是里是否包含某个元素；

**运算符 用于幂运算

![image-20200925192221127](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925192221127.png)



## 2.ES8：

![image-20200925192412815](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925192412815.png)

### 1.async 和 await：

在函数的声明前加上async关键字，该函数的返回值是一个promise对象，而该promise对象的结果(成功还是失败，值是什么)由async函数执行的返回值决定。

如：在return后跟的的是字符串或者其它非promise类型的对象，返回结果就是成功的promise，即async函数的返回值是一个（以字符串为例）状态为成功的promise对象，其值就是该字符串（如果什么都不写就是undefined）。

而如果抛出错误，则async函数的返回值是一个失败的promise对象。

他的值就是抛出的对象（比如：Error:出错了！）。

如果在return后跟的是一个promise对象：

如果该对象是成功的，则async函数返回的promise对象也是成功的并且它的值就该对象成功的值。

如果该对象是失败的，则async函数返回的promise对象也是失败的并且它的值就该对象失败的值。

![image-20200925192856124](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925192856124.png)

await：

![image-20200925194444373](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925194444373.png)

await表达式必须写在async函数中，它会返回其后面跟着的promise对象成功的值，如果该对象失败，则需要用try catch 捕获。

![image-20200925194729548](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925194729548.png)



async 和 await 结合案例：（读取文件内容）

==question：==*data的实参是什么？promise的成功值是怎么获取到文件"为学.md"的？*

![image-20200925195302960](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925195302960.png)

![image-20200925195239161](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925195239161.png)

async 和 await 结合案例：（发送ajax请求）：

![image-20200925195819765](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925195819765.png)

promise与then实现：

![image-20200925195926057](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925195926057.png)

async 和 await 实现：

![image-20200925200107497](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925200107497.png)

### 2.ES8对象方法扩展：

![image-20200925200159940](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925200159940.png)

Object.values (获取所有的值）和 Object.entries 返回的结果是数组，数组内的每个元素也是数组（获取所有的键和值）

==question== ：*Map是什么？*

![image-20200925200438710](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925200438710.png)

getOwnPropertyDescriptors():返回对象属性的描述对象：

**可以用来深度克隆对象**

注：第一个参数null是是设置原型对象为没有。

![image-20200925200943716](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925200943716.png)

![image-20200925200810415](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925200810415.png)

## 3.ES9：

### 1.Rest 参数（...）和 spread扩展运算符：

rest参数在ES6中已经引入，但是当时只针对于数组，ES9中为对象也提供了rest参数。

![image-20200925201702559](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925201702559.png)

扩展运算符：

![image-20200925202028549](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925202028549.png)

![image-20200925202142156](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925202142156.png)

### 2.正则扩展：命名捕获分组

==question== *正则表达式里的标签是什么*

![image-20200925202403481](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925202403481.png)

![image-20200925202415294](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925202415294.png)

![image-20200925202522875](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925202522875.png)

命名捕获分组：

![image-20200925202716204](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925202716204.png)

![image-20200925202623890](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925202623890.png)

### 3.正则扩展：反向断言：

断言：根据目标内容的前边（反向）和后边（正向）来对目标进行唯一性的识别

![image-20200925203034557](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925203034557.png)



### ==4.正则扩展：dotAll模式==

增加了模式修正符s

![image-20200925203754541](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925203754541.png)

![image-20200925203815325](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925203815325.png)

## ES10：

### 1.对象扩展方法：

fromEntries：将二维数组或者Map转换为对象：

![image-20200925204222811](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204222811.png)

![image-20200925204241241](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204241241.png)

Map：

![image-20200925204321997](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204321997.png)

![image-20200925204336974](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204336974.png)

entries：将对象转换为数组：

![image-20200925204203206](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204203206.png)

![image-20200925204355398](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204355398.png)

### 2.字符串扩展方法：

trimStart 和 trimEnd

用来清除空白字符，trim清除所有 trimStart清除左边（前边）trimEnd清除右边（后边）

![image-20200925204625577](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204625577.png)

![image-20200925204632848](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204632848.png)

### 3.数组方法扩展：

flat与flatMap

flat将数组降维：默认3降2 2降1 也可以在方法内传递参数表示深度，比如传2，则将3维数组降为一维数组。

![image-20200925204839713](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925204839713.png)

flatMap：

![image-20200925205123745](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925205123745.png)

![image-20200925205131296](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925205131296.png)  

 4.symbol的扩展：description属性，可以获取symbol的描述字符串；

![image-20200925205302993](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925205302993.png)

## ES11:

### 1.私有属性：

不能在类外部进行访问，声明前加#

注释内的三条语句会报错，但是方法intro调用不会

![image-20200925205621983](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925205621983.png)

![image-20200925205809533](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925205809533.png)

### 2.promise.allSettled

allSettled 返回的结果总是成功（resolved），能得到每一个promise对象的成功或者失败的状态（成功：fulfilled,失败：rejected)和值（存在一个数组中）

all只要有一个对象是失败的就会返回失败（rejected），其出错的值就是对象中失败的promise的值，都成功则会返回resolved，成功值是promise对象成功的值形成的一个数组:

![image-20200925210700528](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925210700528.png)

![image-20200925210140535](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925210140535.png)

![image-20200925210019924](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925210019924.png)

### ==3.String的matchAll方法：== 

question

用于对数据的批量提取：

![image-20200925211026094](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925211026094.png)

![image-20200925210950671](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925210950671.png)



### 4.可选链操作符：?.

获取db内的host属性值

注释是不使用可选链操作符的方法

使用可选链操作符，可以不用对变量进行层层判断，即使没有获取到结果也不会报错，而是返回undefined。

![image-20200925211522931](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925211522931.png)



### 5.动态import:

动态import可以实现按需引入：

注释是静态引入，不管什么时候调用，我们都先进行引入

而import函数，是动态引入，它的返回结果是一个promise对象，该promise成功的值就是模块中export的对象。

![image-20200925212009882](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925212009882.png)



6.新的数据类型：BigInt 大整型

主要用于大数值运算：

![image-20200925212611974](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925212611974.png)

![image-20200925212627918](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200925212627918.png)

### 7.绝对全局对象：globalThis

始终指向全局对象（浏览器中是window，node.js里是global）

Day 02 结束  21：30 进度：全部视频结束 68P

2020.09.24





