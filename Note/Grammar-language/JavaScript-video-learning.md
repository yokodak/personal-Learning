# JavaScript 视频笔记

创建日期：2020.09.03.

视频资源：https://www.bilibili.com/video/BV1YW411T7GX?p=5

尚硅谷最新版JavaScript基础全套教程完整版(140集实战教学,JS从入门到精通)

2020.09.03 

**21:04**

# ==Day 01==   2020.09.03 

1. JavaScript中要严格区分大小写；

2. 引入JavaScript可以采用：3种方式：

   a.直接使用<script></script>  标签；

   b.在<script></script>中引入外部js文件；

   c.在HTML标签中直接使用onclick，href等引入js代码；

```html
<script type="text/javascript">    
    var birthDay = 123;    
    console.log(birthDay);
</script>
```

### 1.JS的标识符命名：

在js中使用var关键字来声明变量：

var birthday = 0701;

![image-20200903213005654](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200903213005654.png)

### 2.转义字符：

在字符串中我们可以使 \ 作为转义字符：当表示一些特殊字符时可以用 \ 进行转义：

\ '' 表示一个双引号''

\ '  表示一个单引号'

\ n 表示换行

\ t 表示制表符 tab

\ \表示 \ 

**![image-20200903215414826](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200903215414826.png)**

### 3.typeOf和JS的数据类型（ES5）

可以使用typeof来检查变量的类型：语法 typeof 变量名

![image-20200903222055885](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200903222055885.png)

#### ==tip:==

如果使用js进行浮点数计算，可能会得到不精确的结果，所以不要使用js进行精确的计算。

![image-20200903221917765](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200903221917765.png)

![image-20200903221945504](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200903221945504.png)

![image-20200903222835954](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200903222835954.png)

Day 01 结束 **22：29** 进度：P10结束

### 4.Day 01 练习：

```html 
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
        <title>ExerciseDay01</title>
        <meta name="description" content="">
        <meta name="keywords" content="">
        <link href="" rel="stylesheet">
    </head>
    <body>
<!--在script标签中编写js代码-->
    <script type="text/javascript">
        var birthDay = 123;
        //转义字符：
        var  str = "我说：\"今天\n天气真不错！\"";
        var str1 = "\\\\\t\\\\";
        //空串
        var str2 = "";
        //js六种数据类型：
        //Number
        var num1 = 123;
        //Null
        var var1 = null;
        //Undefined
        var var2 = undefined;
        //Boolean
        var var3 = true;
        //String
        var  str = "我说：\"今天\n天气真不错！\"";
        //Object（对象）
        var var4 = Object();

        var var5 = NaN;
        var var6 = Number.MAX_VALUE;
        var var7 = Number.MIN_VALUE;
        var var8 = Infinity;
        var var9 = -Infinity;
        console.log("str="+str);
        console.log("str1="+str1);
        console.log("str1="+str1);
        console.log("str2="+str2);
        console.log("birthday="+birthDay);
        console.log("num1:123的数据类型是"+ typeof num1);
        console.log("var1:null的数据类型是"+ typeof var1);
        console.log("var2:undefined的数据类型是"+ typeof var2);
        console.log("var3:true的数据类型是"+ typeof var3);
        console.log("str2空字符串:"+""+"的数据类型是"+ typeof str2);
        console.log("var4：Object()的数据类型是"+ typeof var4);
        console.log("var5:NaN的数据类型是"+ typeof var5);
        console.log("var6:"+var6+"的数据类型是"+ typeof var6);
        console.log("var7:"+var7+"的数据类型是"+ typeof var7);
        console.log("var8:"+var8+"的数据类型是"+ typeof var8);
        console.log("var9:"+var9+"的数据类型是"+ typeof var9);
        console.log("str2 = "+str2);
        //如果使用js进行浮点数计算，可能会得到不精确的结果，
        // 所以不要使用js进行精确的计算。
        var cTest = 0.1 + 0.2;
        console.log("cTest = 0.1 + 0.2="+cTest);
    </script>
    </body>
    </html>


```

![image-20200917200646423](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200917200646423.png)



问题：暂无（忘记了）

# ==Day 02== 开始  2020.09.04

  **10：50-11：10**

### 1.类型转换：

![image-20200904110614503](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904110614503.png)



2020.09.04  **15：04：**

### 2.强制类型转换：

####   a.其他类型转String：

1.调用toString 方法；

 2.调用String()函数；  

####   b.其他类型转Number：

1.调用Number()函数；

 2.调用parseInt()或parseFloat()函数；

![image-20200904154044348](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904154044348.png)

![image-20200904153839427](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904153839427.png)

![image-20200904153905590](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904153905590.png)

![image-20200904153948418](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904153948418.png)

#### c.其他进制的数字：

![image-20200904155956323](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904155956323.png)

![image-20200904155839964](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904155839964.png)

#### d.转换为Boolean：

使用Boolean()函数；

![image-20200904160649501](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904160649501.png)

### 3.JS的运算符：(隐式类型转换)

#### a.算数运算符：

#### b. 和字符串的加法

任何的值和字符串进行加法运算都会先转换为字符串，然后再做拼串操作；

#### c.减法乘法除法运算：

 任何值做- */ （减乘除）运算时都会自动转换为Number,再进行运算；

 ![image-20200904163645453](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904163645453.png)![image-20200904164127277](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904164127277.png)![image-20200904164904857](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904164904857.png)

#### d.自增和自减：

![image-20200904170412386](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904170412386.png)

2020.09.04 **17：10**

2020.09.04 **20：43**

### 4.逻辑运算符：&& || ！

#### a.其他数据类型转换为布尔值

两个！！可以把其他数据类型转换为布尔值

![image-20200904211924204](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904211924204.png)

#### b.赋值运算符 = 

#### c.关系运算符

 ">"  "<"  "="  "<="  ">=" "==" "!="

![image-20200904214328214](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904214328214.png)

![image-20200904214358518](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904214358518.png)

![image-20200904214439421](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904214439421.png)

![image-20200904220921659](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904220921659.png)

![image-20200904220936191](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904220936191.png)

"==="表示全等 不会自动做类型转换，如果两个值的类型不同，直接反回false，

"!=="不全等同理

### 5.条件运算符：

写法：条件表达式？语句1：语句二

![image-20200904222108214](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904222108214.png)

### 6.运算符优先级：

不确定优先级，就记得用括号来提高想要优先计算的表达式

### 7.Unicode编码

在字符串中使用转义字符\u 加上四位编码输入Unicode编码

在网页中使用&# 加上四位编码使用Unicode编码，但是编码要求是10进制，需要转换

![image-20200904215119612](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904215119612.png)

![image-20200904215137544](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200904215137544.png)

2020.09.04 **22：44**

Day 02 结束 进度 P27结束



# ==Day 03==  2020.09.05 学习了前端编辑器sublime Text 3 





# ==Day 04== 2020.09.06 

**10：08-11:30**

### 1.条件判断语句：

1.  if
2. if   else
3. if   else if   else....

### 2.prompt()函数：

![image-20200906110743322](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200906110743322.png)

prompt()函数可以弹出一个提示框，可以在其中的文本框输入内容，该内容会作为该函数的返回值，输入的内容会转换为String类型数据。

eg: var score = prompt("请输入分数：")

![image-20200906112005380](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200906112005380.png)

![image-20200906154608133](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200906154608133.png)

### 3.条件分支语句：

switch ...case 

比较的条件是是否全等；

![image-20200906164725203](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200906164725203.png)

![image-20200906164913455](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200906164913455.png)

### 4.循环语句：

while

do while 

for

Day 04 结束 **20：40** 有效时长2小时左右 进度35p结束





# ==Day05== **14:35**   2020.09.08

### 1.prompt输入判断的改进：  

![image-20200908144630292](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908144630292.png)



### 2.for 循环的死循环：

![image-20200908145004866](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908145004866.png)

### 3.break 和continue：

break关键字可以用来终止离他最近的那个循环语句（或switch语句）（默认情况下）

也可以使用label来指定break哪个循环，具体如下：

eg：hello:  for (..;..;.;)
{

语句...

}

break hello；

![image-20200908160329870](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908160329870.png)

continue关键字则用于跳过当次循环，默认情况下也只作用于离他最近的循环体，也可以使用label来指定跳出

![image-20200908160732444](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908160732444.png)

![image-20200908161015743](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908161015743.png)

**在程序中恰当地使用break，可以提高程序的性能。**

### 4.计算程序的执行时间：

检测一个程序的性能可以使用console.time()和console.timeEnd()来计算程序的执行时间：

![image-20200908161301409](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908161301409.png)

![image-20200908161338241](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908161338241.png)

**16：28** pause

**21：00** start

### 5.Math.sqrt()：

可以用Math.sqrt()对一个数进行开方：

![image-20200908210305757](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908210305757.png)

### **6.重点：==求质数练习==性能改进**

 https://blog.csdn.net/qq_41939020/article/details/99167166 

 因数都是成对出现的。比如，100的因数有：1和100，2和50，4和25，5和20，10和10。看出来没有？成对的因数，其中一个必然小于等于100的开平方，另一个大于等于100的开平方。

所以如果一个数，在2至它的平方根之间都没有因数 ，那么它一定是质数。

当他能被2到他的平方根之间的任意一个数整除，那他就不是质数，就不需要再判断了，直接跳出循环。

**再改进：**而在2到他的平方根之间，能被2整除的数字也不需要进行取余判断了，因为一旦一个数取余2不等于0,那他取余2的倍数也不会等于0，所以只需要判断2到他的平方根之间不是2的倍数的那些数即可，也就是只需要判断能否被这之间的质数整除，能就不是质数。

究极方案（目前）：

**筛选法：**

 利用了筛法，首先，2是公认最小的质数，所以，先把所有2的倍数去掉；然后剩下的那些大于2的数里面，最小的是3，所以3也是质数；然后把所有3的倍数都去掉，剩下的那些大于3的数里面，最小的是5，所以5也是质数……
　　上述过程不断重复，就可以把某个范围内的合数全都除去（就像被筛子筛掉一样），剩下的就是质数了。维基百科上有一张很形象的动画，能直观地体现出筛法的工作过程。 

 ![å¨è¿éæå¥å¾çæè¿°](https://img-blog.csdnimg.cn/20190811101655376.gif) 

### 7.对象（Object):

对象属于一种符复合类型的数据，在对象中可以保存多个不同数据类型的属性。 

![image-20200908211142667](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908211142667.png)

#### 1.对象的分类：

1.内建对象  2. 宿主对象  3. 自定义对象

![image-20200908211401332](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908211401332.png)

#### 2.对象的创建：

使用new关键字调用构造函数(constructor)来创建对象：

var 对象名 =  new Object();

![image-20200908212313439](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908212313439.png)

#### 3.对象的增删改查:

##### a.向对象添加属性：

对象.属性名 = 属性值；

![image-20200908212611570](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908212611570.png)

##### b.读取对象中的属性：

![image-20200908212803346](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908212803346.png)

##### c.修改对象中的属性值：

![image-20200908212905610](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908212905610.png)

##### d.删除对象中的属性：

delete 对象.属性名；

![image-20200908212953295](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908212953295.png)



#### 4.对象的属性名和属性值：

##### a.属性名：

对象的属性名可以是任意字符，但是如果要使用特殊字符，需要用[]取名：对象.[" 属性名"]= 属性值；读取时也要用相同形式:

![image-20200908214011576](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908214011576.png)

![image-20200908214305684](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908214305684.png)

使用[]对对象的属性命名更加灵活，因为[]中的属性名可以由变量来传递，例如 :

var n = " 123"

此时 obj [" 123"] = obj[n]

![image-20200908214706870](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908214706870.png)

##### b.属性值：

JS对象的属性值可以是任意类型的数据，甚至可以是一个对象；

如果把对象比作塑料袋，属性比作商品，那么这就类似于塑料袋里再装塑料袋；要取用属性时，只需要遵循对象.属性名.属性名即可；

![image-20200908214746171](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908214746171.png)

![image-20200908215041224](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908215041224.png)

##### c.==tips== : in运算符

要判断一个对象中是否包含某些属性，可以使用in运算符判断：

语法：" 属性名" in 对象名；

![image-20200908215343018](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200908215343018.png)

Day 05 结束 **22：00** 进度：48p结束

# ==Day 06== 开始 **20：00** 2020.09.09

### 1.基本数据类型和引用数据类型：

#### 1.基本数据类型

基本数据类型保存的是变量的值，在JS中变量是直接保存在栈内存中的，栈内保存的是变量的值：如 var a = 10；值与值之间是独立存在的

![image-20200909210817956](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909210817956.png)

![image-20200909210857442](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909210857442.png)

#### 2.引用数据类型(Object)

而引用数据类型(Object)保存的是对象的地址，当使用new Object创建一个新的对象时，在堆内存中会分配一个单独的空间用于存储对象，而在变量保存的是对象的地址（对象的引用）：如var obj =  new Object()；

变量obj的值是对象obj的地址；

![image-20200909211010580](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909211010580.png)

![image-20200909211031193](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909211031193.png)

![image-20200909211147739](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909211147739.png)

![image-20200909211224581](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909211224581.png)

### 2.对象字面量：

var 对象名 { 

属性名：属性值，

属性名：属性值，

属性名：属性值...

};这样创建对象的方法和使用new关键字创建对象效果是一样的，但是更加简便。

![image-20200909212130665](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909212130665.png)

![image-20200909212417683](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909212417683.png)

![image-20200909212351332](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909212351332.png)

### 3.函数

Function 函数也是一个对象，函数中可以封装一些代码

![image-20200909215541030](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909215541030.png)

![image-20200909220133447](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909220133447.png)

### 4.创建一个函数对象：

##### 1.函数的构造函数

可以将要封装的代码以字符串的形式传递给构造函数，

例如：var fun =  new Function ("代码段")；

##### 2.可以使用函数声明来创建一个函数：

**例如 ：function 函数名 （[形参1，新参2....形参n]）**

**{**

​     **语句...**

**}**

(这是比较常用的创建函数的方式)

![image-20200909220257550](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909220257550.png)

![image-20200909220457877](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909220457877.png)

##### 3.使用函数表达式来创建一个函数：

**![image-20200909220619312](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200909220619312.png)**

Day 06 结束 **22：00**  有效时长一小时 进度 ： 51P结束

# ==Day 07== 开始 **19：30** 

### 1.函数的形参和实参：

#### 1.函数的形参：

形参相当于在函数内定义了一个或多个变量，（多个形参之间使用，隔开）但是变量并未赋值。

如定义以下函数：function sum (a,b)

{

​      console.log (a+b);

}

sum(2,3);

a和b 是形参，并未赋值，当调用函数时，可以在()内传入实际的参数，称为实参。

![image-20200910193528730](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910193528730.png)

#### 2.函数的实参：

调用函数时，解析器不会检查实参的类型，所以函数有可能会接接收到非法的参数，如果有可能的话则需要对参数进行类型的检查。同时，在调用函数时，解析器也不会检查实参的数量，多余的实参不会被赋值，如果实参的数量小于形参的数量，则没有对应实参的形参会是undefined。

![image-20200910193905138](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910193905138.png)

![image-20200910194153737](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910194153737.png)

函数的实参可以是任意类型的数据，也可以是一个对象：

![image-20200910203027422](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910203027422.png)

当函数的参数过多时，我们可以将参数封装到一个对象中，然后通过对象传递参数：

![image-20200910203056557](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910203056557.png)

![image-20200910203117043](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910203117043.png)

![image-20200910203449639](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910203449639.png)

 实参可以是一个对象，故实参也可以是一个函数：

##### ==*疑问：使用函数作为实参有什么好处？*==

在函数中传函数作为实参，记住function()和 function的区别 ，类比于冰淇淋和冰淇淋机器的区别；

### 2.函数的返回值：

一般来说函数承担的大部分功能只是为了返回一个结果，而至于要该结果进行什么操作，由开发人员决定，所以可以使用return 值 将函数的执行结果返回；return后的语句都不会执行；

如果return后不追加任何则函数会返回undefined，函数中不写return也会返回undefined。

![image-20200910195142889](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910195142889.png)

![image-20200910195501498](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910195501498.png)

函数的返回值可以任意类型的数据，也可以是一个对象，一个函数。

![image-20200910205804810](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910205804810.png)

![image-20200910205818424](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910205818424.png)

### 3.偶数判断练习：

![image-20200910200304612](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910200304612.png)     

### 4.立即执行函数：

![image-20200910210221749](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910210221749.png)

![image-20200910210254756](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910210254756.png)

### 5.方法(method)：

对象的属性值可以是任意类型的数据，也可以是一个对象也可以是一个函数，故将一个对象中属性值为函数的属性称为方法（method）

也就是说，当一个函数作为一个对象的属性保存时，我们称这个函数是这个对象的方法。

调用这个函数就是调用该对象的方法。

![image-20200910212236636](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910212236636.png)

![image-20200910212642236](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910212642236.png)

![image-20200910212451207](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910212451207.png)

### 6.枚举对象中的属性：for ...in 

使用for ...in 语句

语法 ：

for (var 变量 in 对象 ){

}

对象中有几个 属性，循环体就会执行几次，每次执行时，会将对象的一个属性名赋值给变量。依据此特性，可以使用下图代码枚举对象中的属性。

![image-20200910212925903](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910212925903.png)

![image-20200910213814779](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910213814779.png)

### 7.JS作用域：

JS中一共有两种作用域：

#### 1.全局作用域：

![image-20200910215709025](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910215709025.png)

直接编写在script标签中的JS代码，都在全局作用域，在页面打开时创建，在页面关闭时销毁。

在全局作用域中有一个全局对象window，该对象由浏览器创建；而在全局作用域中创建的变量都会作为window对象的属性保存，创建的函数都会作为windo对象的方法保存。

#### 2.函数作用域：

函数作用域其实就相当于一个小全局，和全局作用域的关系可以类比学校和教室。

![image-20200910222012981](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910222012981.png)

生命周期短，==调用函数时创建，执行完毕后销毁==

每调用一次就创建一次，每个函数作用域相互独立

函数作用域中可以访问全局变量，全局作用域中无法访问局部变量。

操作变量时，就近原则，逐层向上寻找。

##### ==tips==：函数作用域中也有声明提前的特性

![image-20201031131806207](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201031131806207.png)

下面代码全局作用域里输出的c的值是10；因为不使用var关键字声明的变量都会成为全局变量

![image-20201031131954965](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201031131954965.png)

此时的d相当于window.d

```js
 // console.log(d);//报错，d is not defined
    function fun5(){
      d = 5;//没有用var声明，是全局变量
      console.log(d);//输出5	
    }
    fun5();//调用函数，该函数的函数作用域才会创建

    console.log(d); //输出5
```

![image-20201031132622701](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201031132622701.png)

```javascript

    var d;

    function fun5(){

      console.log(d);//输出undefined，因为该行代码执行时，
        //函数作用域里没有声明变量d,所以会向上一级作用域寻找，上一级的全局作用域 d只是声明了，但是并未赋值
      d = 10; //没有使用var关键字声明，成为全局变量，全局可以访问到
    }
    fun5();//调用函数，该函数的函数作用域才会创建
    console.log(d); //输出10
```

```js
 // var d;

    function fun5(){

      console.log(d);//报错，因为该行代码执行时，函数作用域里没有
      //声明变量d,所以会向上一级作用域寻找，上一级的全局作用域也没有d
      //所以就报错
      d = 10; //只是一个赋值语句，没有定义变量（使用var关键字）
    }
    fun5();//调用函数，该函数的函数作用域才会创建
    console.log(d); //报错，因为d只是被赋值但是未被定义
```

```js

    // d = 0;

    function fun5(){

      console.log(d);//输出undefined，访问的是函数作用域的d

      d = 5;//修改的是函数作用域里的局部变量d
      console.log(d);//输出5
   
      var d = 10; //声明提前
      console.log(d);//输出10
    }
    fun5();//调用函数，该函数的函数作用域才会创建

    console.log(d); //输出undefined 因为全局的d未被赋值

    d = 20;//对声明提前的全局d赋值

    console.log(d); //输出20

    var d = 10;//声明提前

    console.log(d); //输出10
```

定义形参就相当于在函数作用域中声明了变量；

![image-20201031132844692](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201031132844692.png)

![image-20200910220302554](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910220302554.png)



### 8.变量的声明提前：

使用var关键字声明的变量会在所有代码执行前被声明，但是不会被赋值，使用function 函数名(){}会在所有代码执行之前就被创建。

![image-20200910220543137](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200910220543137.png)

![image-20201031131106452](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201031131106452.png)

Day 07 结束 **22：40 ** 有效时长2个半小时 2020.09.10 进度：60P结束

# ==Day 08== 开始 **16：20** 

### 1.上下文对象：this

每次调用函数都会向函数内部传递一个隐含参数this 

当以函数的方式调用时，this就是（指向）window

当以方法形式调用时，this就是该方法的对象。

![image-20200911162446100](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911162446100.png)

![image-20200911171907796](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911171907796.png)

#### 1.this的作用1：灵活

![image-20200911164603610](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911164603610.png)

![image-20200911164627597](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911164627597.png)

![image-20200911164722320](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911164722320.png)

![image-20200911164706456](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911164706456.png)

#### 2.this的作用2：

大批量生成对象：

可以利用函数，在函数中创建对象，将对象作为函数的返回值返回，同时利用形参传递对象的属性值。而使用该方法创建的对象都是通过构造函数Object()创建，所有对象都属于object类型 无法区分多种不同类型的对象，基于此，可以使用构造函数创建对象，将对象细分为某类的对象。

![image-20200911165417780](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911165417780.png)

![image-20200911165644225](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911165644225.png)

![image-20200911165912482](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911165912482.png)

![image-20200911165613840](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911165613840.png)

### 2.构造函数 类：

构造函数就是一个普通的函数，习惯上首字母大写，并且调用时需要使用new 关键字：

function Person {

}

var per =  new Person();

以上代码创建了一个空的构造函数Person();

下图分别创建了一个空的构造函数Dog()和一个构造函数Person()

而使用一个构造函数创建的对象，属于同一类对象，故我们把构造函数称为***类***  ，而由此构造函数创建的对象，我们称之为该类的实例（instance）

![image-20200911171515272](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911171515272.png)

![image-20200911172125441](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911172125441.png)

![image-20200911171110371](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911171110371.png)

##### ==tips:== instanceof 

可以使用instanceof 来检查一个对象是否是某一类的实例

对象 instanceof 构造函数。

![image-20200911172018523](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911172018523.png)

### 3.原型：prototype：

在构造函数中创建一个方法，每调用一次构造函数（创建一个新的对象），该函数（方法）就会创建一次，对于实现相同功能的方法，这样的形式比较浪费空间资源（类比于如果世界上每个人单独使用一个厕所，每诞生一个人，就需要修建一个新的厕所，这样会造成资源的浪费，于是可以多人共享一个厕所，也就是公共厕所）

因此，可以让多个对象共享同一个方法：

下图，将Person内的sayName方法在*全局作用域*中定义，从而实现sayName方法的共享。

![image-20200911173254072](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911173254072.png)

但是在全局作用域中定义此函数会污染命名空间（其他函数不能取名为fun),同时也很不安全（如果又有一个函数名为fun则，之前的fun函数会被覆盖）因此，引出 **原型 **概念。

![image-20200911174914150](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911174914150.png)

每创建一个函数，浏览器的解析器都会向函数中添加一个属性prototype，该属性是一个对象。

![image-20200911175059062](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911175059062.png)

当函数作为普通函数调用时 prototype没有任何作用，

当函数以*构造函数*调用时，该构造函数创建的每一个对象（实例）中都会有一个*隐含的属性*，该属性指向prototype原型对象。（见下图）：

我们可以通过*__(两个下划线)proto__(两个下划线)*来访问该属性

![image-20200911175233603](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911175233603.png)

原型对象prototype相当于该类的公共区域，所有同一类的实例都可以访问该原型对象，定义在该原型对象中的属性和方法都会被所有的实例所“继承”（我觉得类似于c++的继承，实际上相当于委托），故我们可以将实例中的公共属性或者方法，设置在原型对象中，这样节省资源，又安全。

实例本身也可以定义“公共内容”，以自己本身的设置优先。

![image-20200911175328107](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911175328107.png)

![image-20200911180426556](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911180426556.png)

#### 1.向原型中添加属性：

![image-20200911180451330](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911180451330.png)

#### 2.向原型中添加方法:

![image-20200911175734703](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911175734703.png)

**18:05**  pause

**20:30**  continue

### 4.原型的原型：原型链

原型也是对象，所以他也有原型；

可以使用对象.hasOwnProperty（）来检查该对象中是否含有某属性

![image-20200911204413500](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911204413500.png)

![image-20200911204457347](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911204457347.png)

### 5.toString 方法

当我们在控制台打印一个对象时，实际上输出的是该对象的toString方法的返回值，通过修改toString 方法的返回值我们可以让控制台输出我们想要的内容；

![image-20200911205409473](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911205409473.png)

![image-20200911205618548](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911205618548.png)

除此之外，我们还可以对对象的原型的toString方法的返回值进行修改，从而实现让控制台打印这类对象的详细信息：

![image-20200911205830958](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911205830958.png)

### 6.垃圾回收：

当一个对象没有任何的变量或者属性对他进行引用，我们将无法操作该对象，则改对象被称为垃圾。（就像断了线的风筝）

JS中有自动回收这类垃圾的机制，我们也不能对这些垃圾进行清理

我们需要做的，就仅是将不再使用的对象设为null即可。

![image-20200911212833372](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911212833372.png)

### 7.数组：（Array)

数组也是一个对象（内建对象）

读取数组中不存在的索引，不会报错而是会返回undefined；

![image-20200911215055377](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911215055377.png)

![image-20200911214506209](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911214506209.png)

![image-20200911214543496](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911214543496.png)

#### 1.数组的length：

尽量不要创建非连续的数组；

可以使用length查看数组的长度，也可以修改length的值改变数组的长度。

![image-20200911214743892](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911214743892.png)

![image-20200911214840068](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911214840068.png)

#### 2.创建数组：

##### a.使用new关键字，调用构造函数创建数组:

![image-20200911215657754](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911215657754.png)

##### b.使用字面量来创建数组；

![image-20200911215851010](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911215851010.png)

下图注意区分；

![image-20200911215905949](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911215905949.png)

数组里的元素可以是任意的数据类型：

可以是对象，函数，数组

![image-20200911220023053](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911220023053.png)

![image-20200911220113778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911220113778.png)

### 8..数组的方法：

#### 1.push()方法:

可以向数组的末尾添加一个或多个元素，返回值是数组新的长度；

![image-20200911221234331](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911221234331.png)

#### 2.pop()方法：

该方法可以删除数组的最后一个元素，返回值是被删除的元素；

![image-20200911221405935](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911221405935.png)

#### 3.unshift()方法：

向数组开头添加一个或多个元素，返回值是新的数组的长度；

![image-20200911221506869](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911221506869.png)

#### 4.shift()方法：

可以删除数组的第一个元素，返回值是被删除的元素；

![image-20200911221600072](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911221600072.png)

#### 5.slice()方法：

可以从数组的特定位置提取元素，两个参数，第一个参数表示开始的索引（位置），第二个参数截取结束的索引（不包含结束索引），第二个省略不写则会截取开始索引后的所有元素，该方法不会影响到原数组。

(==question:==第二个参数传递arr.length是不是一样的效果？)

![image-20200911230516397](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911230516397.png)

![image-20200911230922277](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911230922277.png)

![image-20200911230542146](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911230542146.png)

#### 6.splice()方法：

该方法会影响到原数组，该方法有三个参数，能将指定的元素从数组里删除，第一个参数表示开始删除的位置（索引），第二个表示删除的数量，第三个及以后表示插入的新元素，这些新元素会插入到开始索引前边。

该方法的返回值是被删除的元素。

使用该方法可以对数组进行删除，替换，添加操作 比较灵活

##### **a.添加：**

![image-20200911231104830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911231104830.png)

![image-20200911231442856](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911231442856.png)

![image-20200911231343864](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911231343864.png)

##### **b.删除**

![image-20200911231530333](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911231530333.png)

##### **c.替换：**

![image-20200911231619561](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911231619561.png)

#### 7.concat()方法：

该方法可以连接两个或多个数组，（包括单个元素）

返回值是连接后的新数组，不会对原数组产生影响

![image-20200912211401243](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912211401243.png)

#### 8.join()方法:

该方法可以将数组转换为一个字符串，不会对原数组产生影响，返回值是转换后的字符串，可以指定一个字符串作为连接各元素之间的参数，默认参数是,

![image-20200912211735462](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912211735462.png)

#### 9.reverse()方法：

该方法用于反转数组，会直接修改原数组；

![image-20200912212321418](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912212321418.png)

#### 10.sort()方法：

sort方法可以用于数组排序，排序规则是按照Unicode编码进行排序，故当该方法用于进行纯数字的数组排序时，可能会得到错误的结果。

但是我们可以自己指定sort排序的规则

在sort()中添加一个回调函数，来指定排序规则，

回调函数有两个参数，如果要从大到小排序，则return a-b 

如果要从小到大排序则返回b-a；

![image-20200912213142458](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912213142458.png)

![image-20200912213114390](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912213114390.png)



### 9.数组的遍历：

#### 1.使用for循环遍历数组：

(变量i其实就是index的首字母，可见for循环常用于数组遍历)

![image-20200911222408213](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911222408213.png)

数组练习：

![image-20200911223605315](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911223605315.png)

![image-20200911223509778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911223509778.png)

数组遍历的另一种方法：

#### 2.使用forEach()方法遍历数组：

![image-20200911225323887](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911225323887.png)

*回调函数*：由我们创建但是不由我们调用的函数:

![image-20200911225402556](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911225402556.png)

![image-20200911225208420](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911225208420.png)

==**问题**==：怎么判断现在需要遍历的是第几个参数？

![image-20200911224927969](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200911224927969.png)

Day 08 结束 23：20 进度 P76 结束 有效时长4小时

# ==Day 09== 开始 **21：00** 

### 1.数组去重练习:

当删除当前的重复元素后，后面的元素会自动补位，当有连续重复的相同元素时，需要再进行一次比较，不然容易漏检，所以删除重复元素后，需要执行j--再在当前比较的索引再比较一遍

![image-20200912210824851](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912210824851.png)

### 2.函数对象的方法：

#### 1.call()和apply():

这两个方法可以指定函数调用时this指向的对象。

![image-20200912214424927](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912214424927.png)

### 3.隐含参数arguments：

arguments是一个类数组对象，在调用函数时，浏览器会传递this和argument这两个隐含参数。我们在调用函数时，传递的实参都会保存到arguments中，所以即使不定义形参也可以通过arguments来使用实参。

他有一个属性callee,该属性对应一个函数对象，就是当前正在执行的函数对象。

![image-20200912214951850](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912214951850.png)

![image-20200912215256274](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912215256274.png)

### 4.Date对象：

在JS中使用Date对象来表示一个时间：

使用构造函数来创建一个Date对象：

var timeNow = new Date();

![image-20200912221038620](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912221038620.png)

#### 1.Date对象的getTime()方法：

该方法可以获取当前时间对象的时间戳

![image-20200912221348467](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912221348467.png)

![image-20200912221500938](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912221500938.png)

利用时间戳来测试代码的性能：

Date.now()方法可以用来返回当前的时间戳；

![image-20200912221732992](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912221732992.png)

#### 2.Date对象的其他方法

以下是一些Date对象的方法，更多方法可以自行查阅。

![image-20200912220253451](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912220253451.png)

### 5.Math对象：

Math和其他对象的不同之处是，它不是一个构造函数。

它属于一个工具类，它里面封装了一些数学运算相关的属性和方法

#### 1.常用的Math方法：

![image-20200912222532886](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912222532886.png)

![image-20200912222907160](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912222907160.png)

![image-20200912223457648](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912223457648.png)

![image-20200912223639176](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912223639176.png)

![image-20200912223740051](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912223740051.png)

#### 2.Math对象属性：

![image-20200912222348779](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912222348779.png)

#### 3.Math对象方法：

![image-20200912222450236](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912222450236.png)

### 6.包装类：

将基本数据类型转换为对象的三个构造函数：一般我们不会使用，这三个包装类是提供给浏览器底层使用的，比如我们使用toString方法对基本数据类型进行转换时：

var s = 123;

s = s.toString() ;

浏览器会将基本数据类型s==临时==转换成String对象s,来调用String对象的toString()方法，从而达到类型转换的目的；调用完方法后，又将其转换为基本数据类型s。

![image-20200912224656093](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912224656093.png)

![image-20200912225034582](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912225034582.png)

![image-20200912225023046](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912225023046.png)

### 7.字符串的相关方法：

（String对象的相关方法）

**字符串在底层是以字符数组的形式储存的**：

![image-20200912225918114](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912225918114.png)

以下是一些常用的字符串方法：

#### 1.charAt()

![image-20200912225851259](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912225851259.png)

#### 2.charCodeAt()

![image-20200912230037026](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912230037026.png)

#### 3.String.fromCharCode();

![image-20200912230256071](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912230256071.png)

#### 4.concat():

![image-20200912230437433](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912230437433.png)

#### 5.indexof():

该方法可以检索一个字符串中是否含有指定内容，有则返回其第一次出现的索引，没有则返回-1，可以传递第二个参数，指定开始查找的位置。

lastIndexof()从后往前找；

![image-20200912230604598](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912230604598.png)

![image-20200912230904677](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912230904677.png)

#### 6.slice()

![image-20200912231029238](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231029238.png)

#### 7.subString():

![image-20200912231150073](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231150073.png)

#### 8.substr():

![image-20200912231255795](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231255795.png)

#### 9.split()

如果传递空串，则会将每个字符都拆分为数组中的一个元素;

![image-20200912231508288](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231508288.png)

![image-20200912231803797](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231803797.png)

![image-20200912231538262](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231538262.png)

#### 10.toUpperCase():

![image-20200912231608052](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231608052.png)

#### 11.toLowerCase():

![image-20200912231714683](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912231714683.png)

其他的字符串方法可以自行查阅：

![image-20200912230151401](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200912230151401.png)

Day 09 结束 2020.09.12 **23：20** 进度：84P结束 有效时长2小时

# ==Day 10== 开始 2020.09.13 **10：00**

### 1.正则表达式：

var 变量 = new RegExp("正则表达式"，"匹配模式")；

第一个参数用于检测一个字符串中是否含有该正则表达式，第二个参数用于指定匹配模式，"i"表示忽略大小写，"g"表示全局匹配模式；

![image-20200913100736338](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913100736338.png)

#### 1.正则语法：

##### a.正则表达式

![image-20200913100910255](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913100910255.png)

在正则表达式中使用或（|）表示或者的意思，有其一则返回true；

![image-20200913102420514](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913102420514.png)

使用（[]）则里面的内容也表示或者；

![image-20200913102608926](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913102608926.png)

![image-20200913103032972](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913103032972.png)

使用^表示除了 即只要字符串中出现除了^之后的正则表达式都返回true；

![image-20200913102808847](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913102808847.png)

![image-20200913102329979](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913102329979.png)

在正则表达式中.代表任意字符，如果要查找.则需要借助转义字符\;

![image-20200913185608355](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913185608355.png)

![image-20200913185539362](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913185539362.png)

##### b.正则的匹配模式

单词边界：\b

![image-20200913190310032](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913190310032.png)

其他特殊字符：

​                  \w（小w) :任何字母、数字、下划线

​					\W（大W）：除了任何字母、数字、下划线

![image-20200913190403729](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913190403729.png)

#### 2.正则表达式的methods：

可以使用正则表达式的test()方法用来检查一个字符串是否符合正则表达式的规则，符合返回true ，不符合返回false；

![image-20200913100821352](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913100821352.png)

#### 3..使用字面量创建正则表达式：

var 变量 = /正则表达式/匹配模式；

![image-20200913101641757](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913101641757.png)

### 2.支持正则表达式的String方法：

#### 1.split(/正则表达式/匹配模式):

会自动全局匹配；

![image-20200913103415698](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913103415698.png)

#### 2.search():

只会查找第一个，设置全局匹配也没用；

![image-20200913103716340](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913103716340.png)

#### 3.match():

根据正则表达式提取符合规则的内容，封装到一个数组中返回，

我们可以为正则表达式设置多个匹配模式，顺序无所谓。

![image-20200913104140265](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913104140265.png)

#### 4.replace():

两个参数，第一个是被替换的内容，可以接收一个正则表达式作为参数，第二个参数是新的内容。

默认只会替换第一个，如果要替换全部，需要在设置匹配模式为g。

该方法不会影响原数组。

![image-20200913104534810](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913104534810.png)

### 3.正则表达式的量词：

通过量词可以设置一个内容出现的次数，但是量词只对它前面的一个内容起作用，所以如果要检查多个连续的字符是否出现需要用括号把要检查的内容包裹起来，如下图：

reg = /b{3}/;表示判断该正则表达式中b是否连续出现3次或3次以上

reg = /ab{3}c/;表示判断该正则表达式中是否正好出现abbbc,如果是abbbbc则会返回false；

![image-20200913105543367](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913105543367.png)

![image-20200913105512906](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913105512906.png)

![image-20200913110346048](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913110346048.png)

![image-20200913110304683](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913110304683.png)

/^a/；表示以a开头；

/a$/；表示以a结尾；

![image-20200913110644002](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913110644002.png)

其他量词可以自行查阅：

![image-20200913105446198](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913105446198.png)

### 4.正则练习：

#### 1.手机号检查：

创建一个正则表达式用来检查一个是字符串是否是手机号：

![image-20200913111043135](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913111043135.png)

![image-20200913111340741](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913111340741.png)

**11：15** pause

**18：50** start

#### **2.去掉字符串中的空格：**

![image-20200913190906545](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913190906545.png)

### 5.邮件正则表达式：

可以上网搜索自己需要的正则表达式，再按需修改；

![image-20200913191733460](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913191733460.png)

### 6.宿主对象DOM,BOM

(Document Object Model ,Browser Object Model):

#### 1.什么是DOM：

![image-20200913192452016](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913192452016.png)

#### **2.节点（Node):**

![image-20200913192703110](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913192703110.png)

#### 3.节点的属性：

![image-20200913192900246](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913192900246.png)

#### 4.文档节点：（document）

浏览器已经给我们提供了文档节点，这个节点是window 的属性

文档节点代表的是整个网页；

通过getElementById()；获取到文档内的对象 

通过innerHTML();可以获取或修改对象内的文字；

但是需要注意该属性对自结束标签没有意义

![image-20200913193422548](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913193422548.png)

![image-20200913203700409](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913203700409.png)

### 7.事件（Event）:

事件就是用户和浏览器之间的交互行为；

![image-20200913194540942](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913194540942.png)

我们可以在时间对应的属性中设置一些js代码，当事件被触发时，这些代码会被执行，但是这样的写法会导致结构和行为耦合，不方便维护，所以不推荐使用。

![image-20200913194529380](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913194529380.png)

因此我们可以在script标签中获取事件对应的对象，编写对应的代码来对事件进行响应；这样能避免耦合。

onclick()这样的为单击事件绑定的函数，我们称之为单机响应函数；

![image-20200913194622726](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913194622726.png)

我们还可以根据需要使用其他的函数：（事件）

![image-20200913194156052](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913194156052.png)

### 8.HTML中js代码的位置：

将js代码写在页面下部：

因为浏览器加载页面时，是自上而下加载的，故如果读取到js代码时页面还未加载，则js代码无法对事件做出反应，所以一般会将js代码编写在页面下部；

![image-20200913201038056](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913201038056.png)

![image-20200913200827696](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913200827696.png)

 如果一定要将js代码写在head标签中，可以使用onload()函数（事件） 为window对象绑定一个onload事件：

![image-20200913201649726](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913201649726.png)

### 9.获取元素节点：

![image-20200913201939149](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913201939149.png)

#### 1.getElementById():

根据id获取到一个节点对象：

![image-20200913202932642](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913202932642.png)

#### 2.getElementsByTagName():

根据标签名获取到一组元素节点对象，该方法会返回一个类数组对象。

![image-20200913203034637](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913203034637.png)

#### 3.getElementsByName():

通过name属性获取一组元素节点对象，该方法会返回一个类数组对象。（NodeList)

![image-20200913203918916](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913203918916.png)

## ==**10.图片切换练习 P 95**==

### 11.获取元素节点的子节点：

![image-20200913211312553](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913211312553.png)

#### 1.getElementsByTagName():

返回 **当前** 节点的指定标签节点

![image-20200913211518550](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913211518550.png)

#### 2.childNodes:

表示当前节点的所有子节点；

需要注意的是除了IE8及以下的浏览器中，DOM标签内的空白文本也会被当成文本节点；

而children属性会获取当前元素的所有子元素

（就不会包括空白节点了，所以浏览器都一样）

![image-20200913212125489](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913212125489.png)

![image-20200913212433041](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913212433041.png)

#### 3.firstChild:

获取到该元素的第一个子节点（包括空白节点）

1. firstElementChild，获取到该元素的第一个子元素（不兼容IE8及以下）
2. lastChild,获取到该元素的最后一个子元素。

![image-20200913212855858](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913212855858.png)

### 12.获取元素节点的父节点和兄弟节点：



![image-20200913213220129](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913213220129.png)

*定义一个函数专门用来为指定元素绑定单击元素：*

![image-20200913214022684](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913214022684.png)

#### 1.parentNode

表示当前节点的父节点；

innerHTML和innerText的区别：

innerText会将html去除,保留纯文本。

![image-20200913213948950](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913213948950.png)

#### 2.previousSibling;

#### 3.nextSibling;

*tips*：文本框的value值就是文本框中填写的内容；

![image-20200913214642034](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913214642034.png)

## ==17.全选反选练习 P100== 

#### 1.全选：

![image-20200913220211874](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913220211874.png)

#### 2.反选：

![image-20200913220101596](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913220101596.png)

#### 3.提交：

![image-20200913220354765](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913220354765.png)

#### 4.全选/全不选框：

##### *==tips==*

* 在事件的响应函数中，响应函数是给谁绑定的，this就是谁

![image-20200913220824600](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913220824600.png)

![image-20200913221718194](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200913221718194.png)

Question：==后面全选/全不选按钮的完善==

Day 10 结束 22：00   进度：100P结束

# ==Day 11== 开始 2020.09.14 10：30

### 1.DOM中的其他一些查询方法及属性：



##### 1.document.body:

获取body标签

##### 2.document.documentElement:

获取HTML标签

##### 3.docunment.all:

all代表的是页面内的所有元素；（类数组）

![image-20200914104341832](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914104341832.png)

##### 4.getElementsByClassName()

根据class属性查询一组元素节点对象，该方法不支持IE8及以下浏览器。

![image-20200914104659519](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914104659519.png)![image-20200914104819199](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914104819199.png)

##### 5.querySelector()

该方法支持IE8及以下浏览器，需要将一个选择器的字符串作为参数来查询一个元素节点对象；如果满足条件的元素有多个，则返回第一个。

##### 6.querySelectorAll()

会返回一组元素节点，封装到类数组对象中

![image-20200914104916827](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914104916827.png)

### 2.DOM对象的增删改查：

（查询在之前已经学过）

![image-20200914105330677](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914105330677.png)

#### 1.读取：

使用innerHTML属性

![image-20200914112150828](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914112150828.png)

#### 2.增加：

##### a.creatElement()用于创建一个元素节点；

##### b.creaTextNode()用于创建一个文本节点

这两个方法的返回值都是创建的新的节点

##### c.appendChild()该方法向一个父节点中添加一个新的子节点

语法：父节点.appendChild(子节点)；

*当我们不不知道父节点是谁时，可以使用 **parentNode*** 属性获取其父节点，这样比较简便*

![image-20200914110508924](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914110508924.png)

![image-20200914110804693](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914110804693.png)

***使用innerHTML也可以完成一些增删改操作：***

一般我们会将其和上面使用的增加方法结合使用，这样更简便；

![image-20200914112633402](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914112633402.png)



##### d.insertBefore():

可以在指定子节点前面插入新的子节点：

语法：**父节点**.insertBefore(新节点，旧节点)；

![image-20200914111237223](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914111237223.png)

#### **3.修改**:

##### a.replaceChild()

可以使用指定的节点替换已有的节点；

语法：父节点.replaceChild(新节点，旧节点)；

![image-20200914111511979](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914111511979.png)

设置标签内的html代码：

![image-20200914112307525](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914112307525.png)

#### 4.删除:

##### a.removeChild():

可以删除一个子节点；

当我们不不知道父节点是谁时，可以使用 **parentNode* ** 属性获取其父节点，这样比较简便

![image-20200914111818479](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914111818479.png)

**11：30**  *pause*

**13：10** *start*

### ==3.添加删除练习 P103-P105==

#### 1.删除：

思路：

1. 获取所有的超链接

2. 遍历超链接，点击超链接后需要删除超链接所在的行，所以需要为每一个超链接设置一个单击响应函数，为了使超链接不跳转，我们可以把响应函数的返回值设置为false或者在href中设置"javascript:;"

3. 通过this上下文对象和parentNode属性获取到超链接所在的行

4. 获取到要删除的员工的名字，通过之前获取到的tr元素，调用children属性或getElementByTag()以及innerHTML属性获取到第一个 ***子元素 ***内的文字

5. 调用confirm()函数使页面在执行删除操作之前弹出一个确认框，再判断该函数的返回值，当用户点击确定时才执行删除操作。

![image-20200914131357048](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914131357048.png)

![image-20200914132500795](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914132500795.png)

![image-20200914132415177](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914132415177.png)

![image-20200914132516698](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914132516698.png)



#### 2.添加：

![image-20200914133923910](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914133923910.png)

思路：

1. 获取员工的信息:获取员工的姓名和员工的邮箱和salary

使用getElementById()方法结合value属性获取。

![image-20200914135101514](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914135101514.png)

2. 将获取到的信息保存到tr中：

根据表格样式：

![image-20200914135640605](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914135640605.png)

使用createElement("tr")创建一个tr；

使用createElement("td")创建4个td；

创建一个a元素

创建文本节点

![image-20200914135420347](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914135420347.png)

然后将获取的信息保存到表格中：

使用appendChild()方法分别为三个td元素添加文本子节点（创建文本子节点时已经获取到文本框的输入值）

再使用同样的方法向a中添加文本

把a元素添加到td元素中，把td元素添加到tr元素中；

![image-20200914135902840](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914135902840.png)

再获取表格：

![image-20200914140318533](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914140318533.png)

将tr添加进table中：

这里需要注意，为了避免隐患，我们一般不将tr添加进table中，这样会导致新添加的tr在tbody之外，所以我们一般将tr添加到tbody中：

![image-20200914140748598](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914140748598.png)

#### 3.设置delete的功能：

先向a中添加href属性；再为新添加的a绑定单击响应函数：

为使代码更加简洁直接在script标签中定义删除的函数：

![image-20200914141035121](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914141035121.png)![image-20200914140431564](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914140431564.png)![image-20200914140906124](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914140906124.png)

#### 4.添加删除操作的改进：

可以利用：innerHTML属性直接设置tr内的内容，再为a元素绑定单击响应函数。

![image-20200914142132312](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914142132312.png)

一个需要注意的点：

在我们为每个超链接绑定单击响应函数时，使用的是this对象来实现，而不是使用allA[i]这样的形式来调用，是因为：

for循环会在页面加载后就立刻执行，而响应函数实在超链接被点击后再执行，所以当for循环执行后i已经变为3，此时响应函数再执行，allA[i]已经是allA[3]了，而allA[]的长度只有2，allA[3]是undefined，所以我们使用this而不是allA[i]。

![image-20200914142646819](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914142646819.png)

### 4.使用DOM来操作css：

#### 1.通过JS修改元素的样式：

语法：元素.style.样式名 = 样式值

在js中css样式名字中的-会被认为是运算符-

所以在js中的css采用驼峰命名法，通过style属性设置的样式都是内联样式，优先级较高。

![image-20200914150719554](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914150719554.png)![image-20200914151032807](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914151032807.png)

#### 2.通过js读取css的样式：

通过style属性读取和设置的都是内联样式。

无法读取样式表中的样式。

![image-20200914151214188](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914151214188.png)

之前的方式无法读取样式表中的样式；

我们需要一个能读取到样式表中的样式的方法：

##### 1.currentStyle

语法：元素.currentStyle.样式名

它可以读取当前元素正在显示的样式，使用的是哪个就返回哪一个（内联样式或者样式表），如果没有设置则返回默认值；

但是属性只支持IE浏览器。

![image-20200914153047333](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914153047333.png)

![image-20200914153402681](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914153402681.png)

##### 2.getComputedStyle()

这个方法可以用来获取当前元素的样式，会返回一个对象，通过对象名可以用来读取样式。如果没有设置，则会返回真实的值，比如width的值不会是auto而是一个长度。

但是该方法不支持IE8及以下浏览器。

![image-20200914153441756](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914153441756.png)

![image-20200914153745010](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914153745010.png)

（以上两种方法都是只读的，不能修改）

这样我们就陷入了两难境地，所以我们想创建一个函数来获取指定元素的样式，能同时兼容IE浏览器和其他主流浏览器。

![image-20200914154110653](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914154110653.png)

##### 3.getStyle() 自己定义的函数

为了解决浏览器的兼容性问题（我们想要找到一个能兼容IE8和其他浏览器的能获取元素的样式的函数）我们创建了一个函数：

getStyle来获取当前元素的样式：

我们只需要判读当前的浏览器是IE8 还是其他浏览器，再根据不同的浏览器选择不同的方式即可。

但是判断浏览器对于我们来说超出知识范围，所以我们可以采用更简单的方法解决这个问题：

我们只需要判断当前浏览器的window对象内是否含有getComputedStyle对象即可（不直接使用getComputedStyle是因为其是一个变量，当浏览器找不到变量时会报错，但是找不到对象不会）

==以后如果要解决浏览器的兼容问题也可以参考此思路==

![image-20200914154746331](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914154746331.png)

==*question：复习[]*==

![image-20200914155445649](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914155445649.png)

### 5..js中操作css的其他属性：

clientWidth

clientHeight

这两个属性返回的只是数值，不带单位，而且其获取的高度和宽度是包括内容区和内边距的（如padding = 10px; width = 100px；则会返回120）

这些属性都是只读的，不能修改。

![image-20200914160224083](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914160224083.png)

offsetHeight和offsetWidth获取的包括内容区、内边距、和边框

按照之前的元素的基础上设置边框为10px则会返回140；

![image-20200914160635376](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914160635376.png)

offsetParent

![image-20200914161104259](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914161104259.png)

offsetLeft

offsetTop

![image-20200914161313059](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914161313059.png)

scrollWidth

scrollHeight

scrollLeft

scrollTop

![image-20200914161636124](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914161636124.png)

![image-20200914161804416](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914161804416.png)

![image-20200914161729113](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914161729113.png)



### 6.滚动条的运用：

![image-20200914162532429](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914162532429.png)

实现一个当用户读完说明书才可以进行注册等下一步操作的功能：

（见下图）：

![image-20200914163220997](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914163220997.png)

思路：

1. 当滚动条滚动到底时，表单可用：

所以先把复选框和提交按钮设置为不可用：

将disabled设置为"disabled"可以使表单项变成不可用状态。

![image-20200914163350735](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914163350735.png)

2. 使用onscroll事件，该事件会在滚动条滚动时触发

   先获取id为info的p元素，为info绑定一个onscroll事件

![image-20200914163547318](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914163547318.png)

3. 检查垂直滚动条是否到底，到底则启用表单项，否则不启用：

   先获取两个表单项，然后判断滚动条是否到底，根据当对象的scrollHeight - scrollTop == 对象的clientHeight时滚动条到底这一条件可以判断。

![image-20200914163901991](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914163901991.png)

4. 当滚动条到底时，设置表单项的disabled属性为false，启用表单项。否则不启用。

**16：40**  pause

**19：40**  start

### 7.一个练习：（event对象）

![image-20200914195219307](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914195219307.png)

![image-20200914195351949](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914195351949.png)

思路：

1. 先获取两个div

![image-20200914195331732](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914195331732.png)

2. onmousemove:该事件会在鼠标在元素中移动时触发

   事件对象（event）：

   当事件的响应函数被触发时，浏览器**每次**都会把一个实参传递进响应函数，该事件对象中封装了当前事件相关的一切信息，比如鼠标的坐标，鼠标的滚轮方向，哪个键盘被按下等。。。

![image-20200914195445227](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914195445227.png)

3. 利用clientX和clientY获取鼠标的坐标，然后在showMsg中显示鼠标的坐标。

![image-20200914200230518](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914200230518.png)

4. 但是在IE8中浏览器不会传递事件对象，在IE及其以下的浏览器中，event事件是作为window的属性保存的，而在火狐中调用window.event会报错；

   为了解决这个兼容性的问题，需要进行一个判断；

![image-20200914200518059](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914200518059.png)

![image-20200914204722227](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914204722227.png)

其他的鼠标键盘属性见下图：

![image-20200914194752111](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914194752111.png)

### 8.练习 ：div跟随鼠标移动：

![image-20200914210736048](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914210736048.png)

思路：

1. 获取div

2. 为整个文档（document）绑定鼠标移动事件onmousemove

3. 解决event的兼容性问题

4. 获取到鼠标的坐标

   cclientX和clientY用于获取鼠标在当前可见窗口的坐标，注意鼠标的坐标是相对于浏览器窗口的；

5. 把鼠标的坐标赋值给div,设置div的偏移量，div的偏移量是相对于页面的。所以鼠标坐标和div偏移量之间会有一段距离差（当页面滚动条滚动时）

   而pageX和pageY则可以获取鼠标相对于页面的坐标，因此此处应该使用pageX，Y而不是clientX,Y

   但是pageX,Y属性在IE8中不支持

   ![image-20200914220351726](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914220351726.png)![image-20200914220630161](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914220630161.png)

   因此，如果要兼容所有浏览器，则需要获取滚动条的长度，将此长度加给div的偏移量。

![IMG_9443(20200914-211345)](C:\Users\yokoda\Desktop\IMG_9443(20200914-211345).JPG)

![image-20200914211051918](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914211051918.png)

![image-20200914212320288](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914212320288.png)

获取滚动条的偏移量：

chrome认为浏览器的滚动条属于body，而火狐等其他的浏览器认为滚动条属于HTML，所以为了解决该兼容性问题，使所有浏览器都能获取到滚动条的长度，需要进行判断，然后再将此长度加给div的偏移量，就能解决（pageX,Y不兼容IE8，而clientX,Y获取的是鼠标相对于浏览器窗口的左边，会与div之间有距离差）的问题，（我们使用的是clientX，Y属性）

![image-20200914221636439](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914221636439.png)![image-20200914221950772](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914221950772.png)

### 9.事件的冒泡：

事件的冒泡（Bubble）

冒泡是指事件的向上传导，当后代元素上的事件被触发时，其祖先元素的相同时间也会被触发，开发中大部分的冒泡都是有益的。

如果想要取消冒泡：

可以将事件对象（event）的cancelBubble属性设置为true。

![image-20200914222922301](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914222922301.png)![image-20200914222725173](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914222725173.png)

### 10.事件的委派：

![image-20200914224634820](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914224634820.png)

事件的委派是利用了冒泡，将事件统一绑定给元素共同的祖先元素，这样后代元素上的事件被触发时，会一直冒泡到祖先元素从而通过祖先元素的响应函数来处理事件，这样可以减少事件绑定的次数，提高程序的性能。

![image-20200914224255901](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914224255901.png)

例如：

（可以使用event对象的target属性判断触发事件的对象是不是我们期望的元素）

![image-20200914224659892](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914224659892.png)

![image-20200914224722370](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914224722370.png)

### 11.事件的绑定：

使用对象.事件  =  函数的形式绑定响应函数只能绑定一个，后面绑定的会覆盖前面的。

![image-20200914225040823](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914225040823.png)

可以使用addEventListener()方法为元素绑定一个或多个响应函数

语法：

元素对象.addEventListener(第一个参数：事件的字符串，不要on 比如"click"，第二个参数，一个回调函数，当事件被触发时，该函数会调用，第三个参数，是否在捕获阶段触发事件，一般是false)

这样当事件被触发时，响应函数会按照函数绑定的顺序执行。

该方法不支持IE8及其以下浏览器

![image-20200914225421670](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914225421670.png)

![image-20200914225905235](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914225905235.png)

IE浏览器支持attachEvent()来绑定事件，不同的是，事件的字符串需要有on，并且后绑定的事件先执行,不需要第三个参数。

但是该方法只支持IE浏览器

![image-20200914230025073](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914230025073.png)

为了解决兼容性问题,我们自己创建一个函数用来绑定事件；

注意 ：attachEvent()中的this是window.

根据以前的思路，判读对象中是否有addEventListener方法，没有则使用attachEvent()

![image-20200914230601971](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914230601971.png)

![image-20200914230952017](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914230952017.png)

![image-20200914231438597](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914231438597.png)

==question：*对this的处理：*==

![image-20200914231413271](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914231413271.png)

### 12.事件的传播：

#### 1.事件流：

三个阶段：

捕获阶段（默认不会触发事件）；

目标阶段；

冒泡阶段；

IE8及其以下浏览器没有捕获阶段；

如果希望在捕获阶段就触发事件，则可以将addEventListener中的false设置为true，但是我们一般不会在捕获阶段触发事件。

![image-20200914232301022](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914232301022.png)

![image-20200914232336380](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200914232336380.png)

Day 11 结束 **23：30** 进度 ：P116结束 有效时长：5个半小时。

# ==Day 12== 2020.09.15 12:50 开始

### 1.练习：拖拽：

![image-20200915125440269](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915125440269.png)

思路：（未考虑滚动条的问题）

1. 首先获取box元素对象。
2. 为box绑定一个鼠标按下事件：onmousedown
3. event的兼容性问问题解决
4. 在onmousemove时间的处理函数中为document绑定一个鼠标移动事件onmousemove；
5. 使用clientX,Y获取到鼠标的位置并修改box的位置
6. 为document绑定一个鼠标松开事件，（注意不是为box绑定，因为这样绑定会受到其他元素的干扰）
7. 当鼠标松开时，取消document的鼠标移动事件和鼠标松开事件（将对应的事件设为null）

![image-20200915130113994](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915130113994.png)

![image-20200915130222824](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915130222824.png)

拖拽的完善：（未考虑滚动条的问题）

我们希望用户在点击box后鼠标就固定在一开始的位置，而不是一直位于box左上角

鼠标的位置是有用户决定的，我们不能改变，所以我们只能改变div的位置。

为了实现之前所说的效果我们需要求出鼠标位置和div之间的偏移量，也就是图中蓝色的那一段，

从图中容易看出，要求此偏移量，只需要用绿色（鼠标.clientX或Y）减去玫红色（元素.offsetTop或Left）。

由此来改变元素的位置。

![image-20200915131321829](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915131321829.png)

![image-20200915131646704](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915131646704.png)

### 2.拖拽的完善：

![image-20200915132618258](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915132618258.png)

![image-20200915132558992](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915132558992.png)

可以使用return false来取消浏览器的这个默认行为；

但是对IE8不起作用

在IE8中，我们可以使用setCapture()方法来捕获==**所有**==鼠标按下的事件，但是该方法只有IE支持，火狐不会报错，但是chrome会报错：

所以需要解决兼容性的问题而进行一个判断：

我们在鼠标按下时就设置box捕获所有的鼠标按下事件：

![image-20200915134258514](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915134258514.png)

或

![image-20200915134316460](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915134316460.png)

在鼠标松开时，取消对事件的捕获

releaseCapture();

松开时取消捕获：

![image-20200915134412186](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915134412186.png)

如果我们希望对页面的多个元素都进行拖拽：

可以将此程序封装为一个函数：

drag(obj);

参数为需要拖拽的对象；

![image-20200915134626331](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915134626331.png)

![image-20200915134720477](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915134720477.png)

**13：47** pause

**19：15**  start

### 3.鼠标的滚轮事件

练习：鼠标滚轮上下滚动，设置一个div随之缩短增长。

![image-20200915194501735](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915194501735.png)

思路：

1. 获取div对象：

2. 为div对象box1绑定一个鼠标滚动事件，onmousewheel；该事件会在鼠标滚动时触发。

但是火狐不支持该属性，在火狐中需要使用DOMMouseScroll来绑定滚动事件且该事件需要通过addEventListener()函数来绑定

##### *==（复习addEventListener)==*

![image-20200915194548891](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915194548891.png)

![image-20200915194957780](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915194957780.png)

3. 判断鼠标滚轮滚动的方向：

使用event对象的wheelDelta属性可以获取鼠标滚轮滚动的方向，

向上滚为正数，向下滚为负数。

在火狐中需要使用event对象的detail属性获取

上滚为负数，下滚为正数

![image-20200915195115408](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915195115408.png)

![image-20200915195355011](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915195355011.png)

4. 修改box1的长度：

![image-20200915195459276](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915195459276.png)

5. 但是当滚轮滚动时，浏览器滚动条也会随之滚动，这是浏览器的默认行为，我们可以通过return false取消浏览器的默认行为。

但是火狐是使用addEventListener()函数绑定鼠标滚动事件的，取消默认行为时不能使用return false，需要使用event对象的preventDefault()方法取消，可是IE却不支持preventDefault,所以需要进行判断。

![image-20200915195539251](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915195539251.png)

![image-20200915195824520](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915195824520.png)



### 4.键盘的事件：

*键盘事件一般都会绑定给一些可以获取到焦点的对象（比如input文本框）或者是document*

onkeydown

按键被按下：一直按着不松手就会一直触发该事件，连续触发时，为了避免误操作，第一次和第二次之间间隔会稍微长一些，其他的很快

onkeyup

按键被松开

![image-20200915201423701](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915201423701.png)

除此之外我们还可以根据event 对象的keyCode属性获取到哪个键被按下：event.keyCode可以获取到被按下键盘的编码

除了keyCode事件对象还提供了几个属性用来判断Alt、Ctrl、Shift键是否被按下。

![image-20200915201910278](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915201910278.png)

判断y和Ctrl是否同时被按下：

![image-20200915202152511](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915202152511.png)

*利用键盘事件让文本输入框中不能输入数字：*

思路：

1. 获取input
2. 数字（0-9）的编码是48-57，借助keyCode判断这几个键是否被按下，如果按下则通过return false来取消onkeydown的默认行为（在文本框中输入内容属于onkeydown的默认行为）则输入的内容便不会出现在文本框中。

![image-20200915202405286](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915202405286.png)



### 5.练习：通过上下左右键盘操纵一个div的移动

![image-20200915202803568](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915202803568.png)

思路：

1. 为document绑定一个键盘按下事件

![image-20200915203417323](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915203417323.png)

2. 获取上下左右键盘的编码

3. 通过条件分支语句判断哪个键被按下

4. 设置一个变量传递移动的量（也就是移动速度）

5. 按住ctrl可以改变（增加或减小）：判断ctrl是否被按下，再来修改speed的值即可；

![image-20200915203333872](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915203333872.png)



### ==6.BOM：==(以及判断浏览器的方法)

Browser Object Model：浏览器对象模型；

Window， Navigator， History， Location， Screen。 

![image-20200915210513115](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915210513115.png)

#### 1.Navigator：

Navigator 代表的是当前浏览器的信息，可以通过该对象的一些属性来判断不同的浏览器，但是由于历史原因，其中的大部分对象已经无法帮助我们识别浏览器了

只有userAgent能帮助我们判断，所以我们可以根据userAgent帮助我们判断浏览器。

![image-20200915212055922](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915212055922.png)

各浏览器的userAgent有所不同：

![image-20200915212437704](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915212437704.png)

##### 判断浏览器：

因此，我们可以根据userAgen内是否含有某些特定字符串来判断浏览器。*==借由此来解决浏览器的兼容性问题.==*

如果根据userAgent还不能判断浏览器，（比如IE11(Edge浏览器)),那么我们可以借助浏览器中特有的属性来判断浏览器，比如IE中的属性ActiveXObject;

![image-20200915212743449](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915212743449.png)

![image-20200915212729927](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915212729927.png)

#### 2.History

属性：length获取当前访问到的链接数量

方法：back() ,forward(), go()

![image-20200915213200705](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915213200705.png)

![image-20200915213657791](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915213657791.png)

![image-20200915213634629](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915213634629.png)

#### 3.Location:

Location可以获取到当前浏览器的地址栏信息

Location的对象和方法：

![image-20200915214153325](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915214153325.png)

assign(),作用和location一样

reload()作用和刷新一样，如果想强制清空缓存（ctrl+f5)，则可以传入参数true。

replace()可以使用一个新页面替换当前页面，调用完后不会生成历史记录，也不能使用回退按钮回退。

![image-20200915214545382](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915214545382.png)

![image-20200915214519751](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915214519751.png)

### 7.定时器：

定时调用：

#### 1.setInterval()

可以将一个函数每隔一段时间执行一次，

两个参数：一个回调函数，该函数每隔一段时间被调用一次，

一个每次调用的间隔时间，单位是毫秒。

该方法的返回值是一个Number类型的数据，作为定时器的唯一标识。

使用clearInterval()可以用来关闭一个定时器，需要上面提到的定时器的唯一标识作为参数，这样将关闭对应的定时器。 

![image-20200915221735246](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915221735246.png)

![image-20200915222051063](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915222051063.png)

![image-20200915222141490](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915222141490.png)

#### 2.延时调用：setTimeout()

延时调用一个函数不会马上执行，而实隔一段时间后再执行，而且只会执行一次，该函数的返回值也是一个Number类型的数字作为该定时器的唯一标识，可以使用clearTimeout()来关闭一个延时调用

![image-20200915231618201](file://C:/Users/yokoda/AppData/Roaming/Typora/typora-user-images/image-20200915231618201.png?lastModify=1604110900)



### 8.切换图片练习：

思路：

1. 获取img标签，并创建一个数组用来保存图片的路径，创建一个变量来保存当前图片的索引。

![image-20200915224818511](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915224818511.png)

2. 开启一个定时器，来自动切换图片：

   在定时调用函数中，使索引自增，并判断索引是否超过最大索引，超  过则将索引设置为0:index = index % imgArr.length;

   然后修改img1的src属性实现自动切换图片。

![image-20200915225029584](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915225029584.png)

3. 添加开始和停止按钮：

   为两个按钮绑定单击响应函数，

   定义一个变量来保存定时器的标识。

   注意clearInterval()可以接受任意参数，不会报错

![image-20200915225446217](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915225446217.png)

![image-20200915225407476](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915225407476.png)

但是每单击一次按钮就会开启一次定时器，我们每次也只能关闭最新开启的那个定时器，这会导致图片切换速度过快*==（question：为什么）==*且无法停止，所以在开启定时器前，要清除当前元素绑定的其他定时器。

![image-20200915225920883](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915225920883.png)

![image-20200915225933095](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915225933095.png)



### 9.移动div练习的改进：

开启一个定时器来控制div的移动，设置时间间隔为30ms

创建一个变量来表示方向

![image-20200915230847884](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915230847884.png)

![image-20200915231114682](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200915231114682.png)

Day 12 结束 2020.09.15.**23：20** 进度：130P结束

# ==Day13:== 2020.09.16  12：50 开始

博客：掘金，思否，开源中国

### 1.定时器的应用：

练习：

点击按钮以后，使box1持续向右移动：

![image-20200916125550660](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916125550660.png)

思路：

1. 获取box1，获取button

![image-20200916125712422](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916125712422.png)

2. 给button绑定一个单击响应函数
3. 开启一个定时器，设置每30毫秒执行一次，用来实现动画效果，然后获取box原来的left值（利用parseInt函数），在样式表中设置left=0px；（避免IE获取到默认值auto）。
4. 在旧值的基础上增加速度，将新值设置给box1

![image-20200916125811526](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916125811526.png)

5. 设置一个终点线，当到达时停止：当到达800时，关闭定时器。但是我们设置的速度值不是总能被800整除，所以当newValue大于800时，我们需要将他赋值为800，这样才能达到刚好到终点线停止的效果。

![image-20200916130408602](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916130408602.png)

![image-20200916130327622](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916130327622.png)

6. 当然，根据之前的练习我们知道，每点击一次按钮，就会开启一个新的定时器，会导致移动速度随着点击次数而变快，所以我们需要在定时器开始前清除该元素的其他定时器。

![image-20200916130904358](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916130904358.png)





### 2.定时器应用二：

练习：

点击按钮以后，使box1持续向左移动：

相对于上一个练习，我们要改的部分并不多，所以我们希望能提取一个函数来控制div的移动：

![image-20200916131958088](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916131958088.png)

思路：（先把timer提取到全局）

![image-20200916132702406](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916132702406.png)

1. 创建一个函数，命名为move，需要传递3个参数：

obj：要执行该动画的对象，target：执行动画的目标位置，speed：移动速度。函数的内容和之前做的练习一样，但是需要修改参数。

![image-20200916132048643](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916132048643.png)

2. 判断speed的值，如果当前元素的位置大于目标位置，则向左移动，如果当前元素的位置小于目标位置，则向右移：先获取元素目前的位置；再判断，如果当前位置大于目标位置，speed应为负值

![image-20200916132413891](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916132413891.png)

![image-20200916132454713](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916132454713.png)

![image-20200916132817555](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916132817555.png)

![image-20200916133007220](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916133007220.png)

![image-20200916132551554](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916132551554.png)





### 3.定时器的应用三：

我们之前把定时器标识变量timer定义到了全局作用域中，这样会导致不同对象的定时器互相干扰，如下图：我们为两个对象都绑定了向右移动函数，当开启一个对象移动时，另一个对象将会被暂停，原因是在一个对象开启时，我们设置的函数中会先清除其他的定时器，所以另一个对象的定时器就被清除了，也就不会执行动画里。

![image-20200916133313313](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916133313313.png)

为了解决这个问题，我们不把timer定义到全局作用域中，而是在move函数中为obj定义一个属性timer来保存定时器的唯一标识，这样当不同对象调用move函数时，会分别拥有自己的定时器：

![image-20200916134241800](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916134241800.png)

![image-20200916134147884](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916134147884.png)

![image-20200916134253159](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916134253159.png)



移动函数的改进：

我们希望可以让动画不只可以向左向右移动，我们还希望动画可以有其他效果，比如改变对象的宽度，高度，让对象向下向上移动，我们还希望能有连续的动画效果，因此，我们需要对该函数进行改进：

1. 新增两个参数，attr表示希望动画执行的样式

![image-20200916135800474](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916135800474.png)

1. callback()一个回调函数，每当动画执行结束时调用

   函数中有函数作为实参则调用，没有则不需要，就不调用，所以使用&&来判断。该函数可以一直嵌套从而实现连续变化的动画效果。

![image-20200916134958506](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916134958506.png)

![image-20200916134828336](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916134828336.png)

![image-20200916135657804](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916135657804.png)



为了方便以后调用，我们可以将该函以及相关的函数封装到一个js文件中，在需要的时候引入：

![image-20200916135917756](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916135917756.png)



### ==4.完成轮播图：==

1. 完成轮播图界面：

   轮播图构成：1个div用来作为显示框：outer，一个ul（无序列表）用来存放图片，几个a(锚)元素来作为切换图片按钮

   div：设置页面居中，位置relative，背景色，padding，设置overflow：hidden

   ul：imgList;开启绝对定位；去除项目符号，设置li浮动

   a:创建一个div：navDiv,来放置这几个按钮，设置绝对定位，背景色百分之50透明，设置鼠标移过改变背景色为黑色，设置各a之间间隔。

![image-20200916142836678](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916142836678.png)

先清除浏览器默认样式：

![image-20200916142921729](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916142921729.png)

outer的样式：

width:520 px；

![image-20200916143019891](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916143019891.png)

imgList:的样式

width:2600px;

![image-20200916143233430](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916143233430.png)

但是在这里吧ul的宽度写死了，不方便删除和添加图片，所以我们使用js来控制ul的宽度：

![image-20200916143611539](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916143611539.png)

ul每向左移动520px,就会显示到下一张图片，所以我们可以通过控制偏移量来控制那张图片显示。但是直接在样式表里写，不方便控制，所以我们借助js来完成：（具体实现见b.轮播图的实现）

![image-20200916143659084](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916143659084.png)![image-20200916145935425](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916145935425.png)



navDiv的a的样式:

![image-20200916144419812](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916144419812.png)![image-20200916144543368](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916144543368.png)



navDiv的样式：

要通过计算使该div位于图片水平居中，直接写计算结果会把值写死，不方便添加删除元素，所以我们使用js来设置该值。

![image-20200916144144176](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916144144176.png)![image-20200916144457565](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916144457565.png)

设置默认显示图片的索引：

![image-20200916144638391](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916144638391.png)



至此页面基本元素完成，下面则要实现轮播功能；



2. 完成点击按钮切换图片功能：

![image-20200916145633536](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916145633536.png)

为所有的超链接都绑定单击相应函数，然后为每一个超链接都添加一个num属性，以此来判断点击的是第几个超链接（因为for循环在响应函数前先执行，all[i]已经是5了不能帮助判断当前是哪个超链接了）。

获取到点击的超链接的索引后根据索引切换图片：

![image-20200916145745199](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916145745199.png)![image-20200916145911915](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916145911915.png)



切换图片完成了，接下来我们需要将当前点击的超链接背景色设置为黑色，而其他的依然是红色：我们专门创建一个函数来解决这个问题：![image-20200916150449165](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916150449165.png)![image-20200916150420976](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916150420976.png)

这样设置后由于内联样式的优先级较高，a的hover效果就失效了，所以我们在内联样式内应该把背景色设置为空串：表示去掉内联样式内的背景色设置，a就会使用样式表中的设置。

![image-20200916150632286](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916150632286.png)



接下来我们还要对切换图片的功能进行完善，因为上面实现的功能不能实现自动切换，所以我们引入我们之前创建的tool.js来实现自动切换：![image-20200916151022595](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916151022595.png)![image-20200916150947245](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916150947245.png)



这样，点击按钮切换图片的功能就完成了；



3. 自动切换图片：

我们创建一个函数用来自动切换图片：

在该函数中，首先开启一个定时器，然后使索引自增，判断索引的值，当索引值大于图片张数时，变为0,也即是第一张。

之后执行move函数切换动画。

![image-20200916152655831](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916152655831.png)

但是这样还是出现了一些问题：

当图片切换到最后一张时，会往回退到第一张，这样就会有一个动画回退的效果，影响体验；

我们的解决思路是：

在ul中再添加一张图片，当最后一张切换完毕后（即新添加的那张）立马跳转到第一张，由于跳转极快，所以人眼难以察觉。

![image-20200916153248591](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916153248591.png)

这样做以后，由于最后一张图片的索引是5超出了我们超链接的索引数，所以我们设置当切换到最后一张时，超链接的索引为0,也就是第一个超链接按钮a变为黑色；

修改setA()函数的内容：

当切换到最后一张图片时，将超链接的索引设为0，并且通过css将最后一张瞬间切换为第一张。

![image-20200916153605577](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916153605577.png)

做完这些之后还有一个bug：点击按钮切换和图片自动切换两个动画都在执行，当我们点击按钮时，不一定能定位到我们想要看到的图片，而点击按钮的操作是用户操作，优先级应该更高，所以，在我们点击按钮后（a）,应该停止自动切换的动画，当点击按钮切换图片的动画完成后，再开启自动切换的动画。![image-20200916154235258](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916154235258.png)![image-20200916154216788](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916154216788.png)

调用move中的回调函数开启自动切换动画：

![image-20200916154426547](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916154426547.png)



至此，轮播图的功能基本完成。





**15:45**  pause 

**20：30** start



### 5.类的操作：对css的类（class的操作）

点击一个按钮，实现改变一个元素的样式，这里修改的是一个div

方法1：获取box1,获取btn01,为btn01绑定单击响应函数，在单击响应函数中修改box的样式：

![image-20200916204827902](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916204827902.png)

该方法的缺点：每修改一个样式，浏览器就需要重新渲染一次界面，这样性能不好，而且当需要修改多个样式时，操作麻烦不方便。

![image-20200916205110720](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916205110720.png)

我们希望一行代码即可修改多个样式：

那我们可以新建一个类：b2：

![image-20200916205335324](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916205335324.png)

当我们点击按钮时，直接令box1.className = b2; 实现对box1的样式的多个样式的修改；这样页面只需要重新渲染一次，表现和行为也进一步分离。

![image-20200916205546029](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916205546029.png)

但是有时候我们并不想修改box1的全部样式，我们只想修改它样式的其中几个，此时我们可以使用+号来为box1添加类，重复的样式会被覆盖，而其他的则不会改变：（注意b2前有一个空格）

![image-20200916205813861](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916205813861.png)

然而当我们每点击一次按钮，就会向该box的样式中添加一个b2，这样的重复没有意义。

因此我们需要判断该元素的样式中是否已经含有对应的类，有则不会添加，没有才添加。

我们定义了一个函数addClass(),来向元素的样式中添加类：

该函数有两个参数，obj表示需要添加class属性的元素，cn表示需要添加的class。

注意加号前的空格（避免拼串操作）

![image-20200916210107839](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916210107839.png)

又定义一个函数hasClass()，借助正则表达式来判断该元素的样式内是否已经含有某类：注意使用转义符\，两个斜杠表示一个斜杠

\b表示单词边界，即该类必须是独立的 ，比如判断是否含有b2,b2则有，b2016则无

![image-20200916210346109](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916210346109.png)

删除样式中的一个类：

用空串代替类；

![image-20200916210825773](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916210825773.png)

toggleClass，有则删除，没有则添加：

![image-20200916210926053](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916210926053.png)

![image-20200916210947578](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916210947578.png)



### ==6.练习：二级菜单：==

![image-20200916211126677](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916211126677.png)

页面基本元素：（部分）

![image-20200916211246653](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916211246653.png)

部分css代码：

![image-20200916211437993](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916211437993.png)

class有collasped则叠起，没有则展开：通过控制元素的高度实现；

![image-20200916211725202](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916211725202.png)

![image-20200916211527952](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916211527952.png)

![image-20200916211539100](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916211539100.png)

![image-20200916211620391](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916211620391.png)

思路：

1. 每个菜单顶部是一个span，通过点击span，对应的div折叠或展开，所以给span绑定单击响应函数：

   先通过querySelectorAll()方法获取所有span

   （使用该方法是为了兼容IE8）

2. 调用之前创建的toggleClass()函数来切换菜单的展开和折叠状态，为了保证只能有一个菜单上=是展开的（如果没有该要求则不需要进行以下操作）

   需要定义一个变量来保存当前打开的菜单，同时为了避免第一个菜单展开再折叠后便无法再打开（因为此时openDiv默认为第一个，而此时的parentDiv也是第一个菜单，那代码就会执行删除collapse又添加collapse，相当于还是将第一个菜单置于关闭状态），所以需要进行判断，只有当openDiv和parentDiv不相同时，才关闭之前打开的菜单。

![image-20200916213026143](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916213026143.png)

为了可以统一处理动画效果，我们将以上代码改为以下代码：

增加了一个判断，当该div中没有collapse时才进入if。

![image-20200916214307410](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916214307410.png)



实现菜单切换的过渡效果：

定义一个函数：用来实现菜单的切换（包含动画效果）

1. 在切换之前，先获取元素的高度，切换后再获取一次元素的高度，我们需要的就是在元素高度的变化间添加动画效果。
2. 切换后将元素的高度重置为begin（一开始的高度，要么是折叠，要么是展开）
3. 然后调用我们之前创建的move函数来实现动画效果，动画执行完毕后，如果不将我们重置元素高度时在内联样式中设置的高度清空则会导致div高度固定（内联样式优先度比样式表也就是类中定义的高），切换状态则不会生效。所以需要在回调函数中将内联样式的height清空，设置为空串。

![image-20200916215411672](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916215411672.png)

此时，我们在切换菜单状态的地方调用toggleMenu函数即可：

（两个地方需要调用）

![image-20200916220310506](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916220310506.png)



### 7.JSON:

JSON  JacaScript Object Notation  JS对象标识符（JS对象表示法）

JSON就是一个特殊格式的字符串，这个字符串可以被任意恶的语言所识别，并且可以转换为任意语言中的对象，JSON主要用于开发中的数据交互。

JSON字符串中的属性名必须加双引号；

JSON中不允许函数对象，只允许普通的对象，数组，字符串，布尔值，数值，null这几种数据。

JSON分类：{},对象

​                      []数组

![image-20200916225753512](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916225753512.png)

以下都是一些JSON格式的数据：

![image-20200916230508112](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916230508112.png)

在js中，为我们提供了一个工具类：JSON。

这个对象可以帮助我们将一个JSON转换为js对象，也可以将一个js对象转换为JSON

JSON转Js对象：

使用JSON.parse()，需要一个JSON字符串作为参数，将该字符串转换为JS对象并作为返回值返回；

![image-20200916230725789](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916230725789.png)

js对象转JSON：

使用JSON.stringify()：

需要一个js对象作为参数，将该对象转换为JSON字符串并将其作为返回值返回；

![image-20200916231116675](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916231116675.png)



但是JSON在IE7及其以下的浏览器并不支持;

![image-20200916231345212](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916231345212.png)



由此引出一个强大的函数：

eval()

该函数可以执行一段字符串形式的js代码，并将执行结果返回，通过该方法也可以将一个JSON字符串转换为一个js对象。

但是该方法性能比较差，且具有安全隐患：用户可能向其传递一个恶意代码块从而影响网页安全（信息泄露，网页崩溃等）

所以一般不推荐使用。

![image-20200916231431208](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916231431208.png)

为了解决IE7对JSON的兼容问题，我们只需要引入一个外部的js文件即可：

json2.js

该文件创建了一个JSON对象

![image-20200916232002726](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916232002726.png)

![image-20200916231855335](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916231855335.png)



至此，该教程学习完毕，还有很多其他的前端知识需要学习：

![image-20200916232114613](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200916232114613.png)



### 8.关于JSON的补充：

json与xml的比较：

![image-20200926200114406](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926200114406.png)

parse也可以有第二个参数，该参数是一个函数，可以按照我们的要求在转换是就完成对数据的一些操作，比如修改数据等。

stringify也可以有第二个参数和第三个参数：第三个参数主要是用于对json排版，提高可读性，第二个参数可以修改数据

![image-20200926201855395](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926201855395.png)



**GeoJSON和TopJSON:**

(geojson.io)

专门用来表示地理信息的JSON

![image-20200926202428953](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926202428953.png)

![image-20200926202650160](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926202650160.png)

从上到下：点，线，面

![image-20200926203117707](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926203117707.png)

![image-20200926203039459](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926203039459.png)

![image-20200926203246935](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926203246935.png)





![image-20200926203359575](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926203359575.png)



工具：

![image-20200926203514202](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926203514202.png)



Day13 结束 2020.09.16 23：20 进度P140结束，整个视频进度结束

























​        

​    















​	