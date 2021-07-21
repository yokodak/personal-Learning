# Ajax学习笔记：

视频：尚硅谷Web前端Ajax教程初学者零基础入门到精通全套完整版（ajax2020最新

视频资源： https://www.bilibili.com/video/BV1WC4y1b78y 

创建日期：2020.09.26  20:40

# ==Day 01== 2020.09.26  20:40 开始

![image-20200926203903658](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926203903658.png)

### 1.AJAX： 

Asynchronous JavaScript And XML (异步的JS和XML)

Ajax可以在浏览器中向服务器发送异步请求，这样无需刷新页面即可获取数据。

![image-20200926204141306](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926204141306.png)

ajax应用特别广泛：比如百度搜索框自动提示，新闻列表下拉刷新，注册页面表单校验等。懒加载，用的时候再加载，不用则不加载。提高网页加载速度和用户体验。

### 2.XML

XML用户来传输和存储数据；

![image-20200926205120937](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926205120937.png)

现在在ajax中我们利用json来取代了XMl

### 3.Ajax特点：

优点：不刷新网页和服务器进行通信，根据用户事件来更新部分页面内容

缺点：没有历史，不能回退，存在跨域问题：比如a.com想通过ajax想b.com发送请求，是不允许的（但是也有其他方法解决），对SEO（搜索引擎优化）不友好，爬虫无法获取到响应体内的内容

![image-20200926205427536](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926205427536.png)



### 4.HTTP协议：

请求报文与响应文本结构：

HTTP：Hypertext Transport Protocol （超文本传输协议）

![image-20200926210211098](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926210211098.png)

请求：请求报文

行： 请求类型（POST ,GET...等等)   URL路径   协议版本

头：注意格式

空行

体：get请求请求体为空，post请求请求体可以不为空。

![image-20200926211432047](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926211432047.png)

响应：响应报文

行：Http协议版本    响应状态码（200：ok ,404:找不到，403：forbidde，401   ：未授权，500：内部错误。303：跳转）响应状态字符串

头

空行

体：返回的内容。

![image-20200926211021612](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926211021612.png)



### 5.Chrome网络控制台查看通信报文：

#### **get**请求

（百度搜索页面刷新）

Request Headers；请求头和请求行（点击viewsource）

Query String Parameters:查询字符串参数，对url里的参数进行解析

Preview：对响应体的预览。

![image-20200926212234011](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926212234011.png)



Response Headers:响应行和响应头

Response ：响应体的内容：

![image-20200926212415857](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926212415857.png)



#### **Post**请求（登录账号）

From Data 

![image-20200926212954118](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926212954118.png)

点击viewsource：原始的请求体内容

![image-20200926213018608](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926213018608.png)

因为登录是一个跳转，所以响应体没有内容

![image-20201120211300441](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201120211300441.png)

### 5.Express框架：

![image-20200926213556298](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926213556298.png)

```js
//1. 引入express
const express = require('express');

//2. 创建应用对象
const app = express();

//3. 创建路由规则
// request 是对请求报文的封装
// response 是对响应报文的封装
app.get('/', (request, response)=>{
    //设置响应
    response.send('HELLO EXPRESS');
});

//4. 监听端口启动服务
app.listen(8000, ()=>{
    console.log("服务已经启动, 8000 端口监听中....");
});
```

![image-20200926220432660](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926220432660.png)

![image-20200926220422176](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926220422176.png)

![image-20200926220401762](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926220401762.png)



### 6.AJAX小案例：

实现点击按钮，在页面中返回请求结果（响应体）

发送get请求

**准备：**

页面准备：

![image-20200926221049965](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926221049965.png)

服务准备：

允许跨域

![image-20200926221359111](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926221359111.png)

![image-20200926221518249](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926221518249.png)

![image-20200926221504342](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926221504342.png)



**Ajax请求的基本操作**：

为button绑定一个点击事件，当点击按钮时，向服务器发送请求

创建一个XMLHttpRequest对象，调用open方法初始化，设置请求方法和URL（代码中是给8000端口发送请求）

调用send方法发送请求

调用onreadystatechange方法，判断服务器是否返回了所有的结果，再判断状态码是否在200-300之间（ok),如果是，则进行响应，我们用console.log输出响应结果。然后设置div#result的html内容为响应体

![image-20200926223021263](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926223021263.png)

![image-20200926223041177](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926223041177.png)



![image-20200926222408254](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926222408254.png)

![image-20200926223753309](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926223753309.png)

![image-20200926223842067](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926223842067.png)

### 7.在Ajax中如何设置请求参数：

在URL的后面跟上  ？参数设置 如下图的？a=100&b=200...

![image-20200926224127837](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926224127837.png)

![image-20200926224056915](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926224056915.png)



### 8.Ajax发送POST请求：

在上面代码的基础上进行修改：

![image-20200926224731747](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926224731747.png)

![image-20200926224718672](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926224718672.png)

Post设置请求体：

3种都可以，还可以通过json发送数据

![image-20200926224933388](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926224933388.png)



### 9.Ajax设置请求头信息：

调用setRequestHeader方法设置请求头，可以自定义但是需要在服务端进行相应处理（见后文）

一般会把身份校验的信息放置在请求头。传递给服务器，服务器进行提取，对用户信息进行校验。

Content-Type是用来是设置请求体内容的类型的，后面那串是固定写法，表示参数查询字符的类型。

![image-20200926225435679](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926225435679.png)

自定义请求头（会报错）

![image-20200926225227024](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926225227024.png)

解决方案：

![image-20200926225331844](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926225331844.png)

![image-20200926225616961](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926225616961.png)



### 10.Ajax服务端响应Json数据：

按下键盘，服务端进行响应，将json数据返回到网页，在指定的div输出该json对应的对象中的某个属性

网页：

![image-20200926230229151](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926230229151.png)

服务端：

send方法只能传递字符串，所以要响应一个对象，需要先调用stringify方法把对象转换为json

![image-20200926230545698](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926230545698.png)

网页：

在接受到json数据后，我们想要的是输出对象中的一个属性，所以我们需要对接收的数据进行一个转换：

两种方式：

手动转换：调用parse方法将响应结果（json)转换为一个对象，设置div的innerHTML为该对象的name属性；

自动转换：设置响应体的数据类型为json，则响应结果会自动转换为一个对象。

![image-20200926231243818](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926231243818.png)

![image-20200926231034582](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200926231034582.png)





Day 01 结束 2020.09.26 23：15 进度：15P结束；



# ==Day 02==  2020.09.27 13：05 

### 1.nodemon工具：

自动重启工具，当我们对文件内容进行修改，会自动重启服务。

![image-20200927131133922](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927131133922.png)

### 2.IE缓存问题解决：

（实际工作中会有工具自动解决该问题，我们不需要专门去设置）

关键：在URL添加ie?t="+Date.now()" 用来获取当前的时间戳

![image-20200927131541760](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927131541760.png)



### 3.Ajax请求超时与网络异常处理：

服务端模拟延时：3s后才响应

![image-20200927132339733](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927132339733.png)

网页端调用timeout方法设置超时设置，当请求超时，则取消发送请求

也可以调用ontimeout方法，添加一个回调函数，输出提示信息

网络异常（断网），可以调用onerror方法，添加一个回调函数，输出提示信息。

![image-20200927132302524](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927132302524.png)

![image-20200927132139733](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927132139733.png)



### 4.Ajax取消请求：

手动取消：注意 x是在不同的函数定义和调用（==函数作用域？==，所以需要在函数外部声明

调用Ajax对象的abort方法取消发送

![image-20200927132929397](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927132929397.png)

a

### 5.Ajax请求重复发送：

用户可能在同一个页面多次请求同样的内容，比如多次点击按钮，每点击一次就会向服务器发送一个请求，如果服务器的响应速度不快，则会造成大量请求堆积，服务器压力大。在用户数量多时，尤为明显。

因此我们可以根据判断用户发送的请求是否是同一个请求来取消重复请求（取消前一个请求，创建一个新的请求），这样服务器始终只接收到一个请求，服务器压力减小，性能提升较大。

首先，创建一个标识符 （变量）isSending用来判断是否正在发送Ajax请求，初始值为false，然后判断请求的响应状态，如果请求已经返回全部结果（readyState==4）

则将标识符设置为false。

当我们再次点击按钮发送请求时，先判断isSending标识符的值，如果正在发送(即isSending==true)则取消该请求，创建一个新的请求。

这样当用户多次请求，而服务器没有即时响应，也始终只有一个请求。

![image-20200927134128661](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927134128661.png)

![image-20200927134105239](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927134105239.png)



### 6.Jquery中发送Ajax请求

1. 先引入Jquery库：

crossorigin = "anonymous" 用来消除警告

![image-20200927135428966](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927135428966.png)

2. 绑定响应函数，按照下面格式，大括号内是参数，第三个参数是一个回调函数，可以对响应体进行一些操作（比如在控制台输出），第四个参数是响应体的数据类型，设置为json，会返回一个对象

![image-20200927135857342](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927135857342.png)

![image-20200927135704479](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927135704479.png)

3. 服务器端：

![image-20200927140023585](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927140023585.png)



通用方法发送Ajax请求:

![image-20200927140721066](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927140721066.png)

![image-20200927140824992](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927140824992.png)

服务端：

![image-20200927140920428](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927140920428.png) 

### 7.Axios发送Ajax请求：

安装：可以使用npm安装，也可以直接在页面中引入。

![image-20200927141053193](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927141053193.png)

使用:

配置baseURL，这样可以不用每次都写baseURL里的内容，在axios中我们可以对url参数，请求头信息做设置。

该方法是一个promise对象

GET：

![image-20200927141454164](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927141454164.png)

输出promise的值：（value），该值是一个对象，他的属性就是响应头响应体等等，我们可以对该对象进行操作获取我们想要的数据。

![image-20200927141753373](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927141753373.png)



POST: 第一个参数是服务器路径，第二个参数是请求体，第三个参数是其他设置

请求体是一个json格式字符串：

![image-20200927142245249](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927142245249.png)

![image-20200927142116460](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927142116460.png)

通用方式：结构清晰，和报文对应密切

![image-20200927142739566](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927142739566.png)

![image-20200927142825049](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927142825049.png)



### 8.使用fetch函数发送Ajax请求：

用得不多

![image-20200927143159996](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927143159996.png)

服务端：

![image-20200927143213231](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927143213231.png)



### 9.跨域：

#### 同源策略：

![image-20200927143447532](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927143447532.png)

#### 如何解决跨域：

![image-20200927143919009](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927143919009.png)

==jsonp：原理：==



原生jsonp实践：

服务端：

![image-20200927145600011](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927145600011.png)

网页端：

![image-20200927145740024](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927145740024.png)

![image-20200927145625767](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927145625767.png)



### 10.Jquery发送Jsonp请求：

网页:

![image-20200927150226012](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927150226012.png)

服务端：

![image-20200927150356799](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927150356799.png)



### 11.设置CORS响应头解决跨域：

CORS（Cross-Origin-Resource-sharing)跨域资源共享；官方跨域解决方案； 

![image-20200927150535786](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927150535786.png)

在服务端设置即可：也可以单独设置对某个网站跨域

![image-20200927151140325](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200927151140325.png)

Day 02 结束 2020.09.27 15：20 进度 ：30P 结束，视频内容结束