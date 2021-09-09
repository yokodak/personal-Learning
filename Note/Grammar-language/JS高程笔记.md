# JS高程笔记

>🙎‍♂️：yokodak（1393050651@qq.com）
>
>📅：2021年9月9日
>
>⌚：09点05分

### 1.什么是 JS

#### 1.1背景

- 诞生背景

  代替服务端语言处理客户端输入验证，因为以前表单验证需要和服务端进行通信来验证，而网速非常慢

  网景公司` Navigator` 浏览器中加入 了`JavaScript `来改变这个局面。

- 历史回顾

  - 1995`Brendan Eich`- `mocha(liveScript)` --> 更名 `JS` (1.0) 
  - --> `Netscape Navigator 3` 中发布了 1.1 版本 -- 微软发布 `ie3`- `JScript` 
  - --> 1996 .8 微软进军 `web`浏览器市场 
  - --> 1997 , `javaScript 1.1`提交到 `ecma` - `TC39`委员会 - 数月后 - `ECMA-262`(脚本语言标准) 
  - -->1998，`ISO`，`iCE`将 `ECMAScript `采纳为标准 -- 此后 `ES`成为各家浏览器实现 `JS` 的标准

#### 1.2 JS 实现

完整的 `js`包括以下几个部分

![image-20210909092457986](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210909092457986.png)

- `ECMAScript`

  ECMAScript 只是对实现这个规范描述的所有方面的一门语言的称呼。JavaScript 实现了 ECMAScript，而 Adobe ActionScript 同样也实现了 ECMAScript。
  
- `DOM` （p31)

  dom 是什么

  dom 标准制定背景

  dom 版本迭代历史及版本特点

  其他 语言的 dom （文档对象模型）（svg，数学标记语言）

⌚ stop 2021年9月9日 09点52分

⌚start 2021年9月9日 20点07分

- BOM

  总体来说，BOM 主要针对浏览器窗口和子窗口（frame），不过人们通常会把任何特定于浏览器的 扩展都归在 BOM 的范畴内。

### 2. html 中的 js

- script 标签属性 

  - type  = 'module' -- ES6 否则不能使用 import，export 关键字？
  - 跨域的 crossorigin 属性
  - integrity 确保引入文件的安全性
  - defer 立刻开始下载， 推迟执行 js, 脚本会被延迟到整个页面都**解析**完毕后再运行，只对外部脚本文件才有效
  - async 立刻开始下载 , 异步脚本保证会在页面的 load 事件前执行，告诉浏览器不用等待该脚本，不阻塞文档渲染，各个异步 js 的执行顺序无法保证

  script 阻塞渲染

  代码中不能出现字符串。

  `</script>` x

  `<\/script>` 转义 ok

  src 属性引入外部js 在解释外部 JavaScript 文件时，页 面也会阻塞。（阻塞时间也包含下载文件的时间。）

  引入 外部 js  的script 元素内部的 js 代码会被忽略

  `MIME`类型的作用？

  ![image-20210909202633660](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210909202633660.png)

  

- script 的跨域请求

- script 的位置 -- 头部（会阻塞） -- > body 减少下载时间，页面更快渲染

- 动态加载脚本，默认异步，不过由于浏览器对 async 不是都支持

  让预加载器知道这些 动态请求文件的存在:

  ```html 
  <link rel="preload" href="gibberish.js"> 
  ```

  如果要统一动态脚本的加载行为，可以明确将其设置为同步加载:

  ```js
  let script = document.createElement('script');
  script.src = 'gibberish.js';
  script.async = false;
  document.head.appendChild(script); 
  ```

- CDATA 标记 ,使内联 js 通过 XHTML 验证

- 使用外部 js 的好处

  - 易维护，统一管理，可复用
  - 浏览器，相同文件只下载一次，加快页面加载速度
  - 不必考虑 XHTML 的兼容问题，包含外部 JavaScript 文件的语法在 HTML 和 XHTML 中是一样的。

- 切割 js 文件，HTTP2 ,轻量可缓存

- noscript 元素 用于给不支持 JavaScript 的浏览器提供替代内容。对于禁用 JavaScript 的浏览器来说，这个元素仍然有它的用处

  可以包含任何可以出现在中的 HTML 元素，script 除外

⌚ end of a day 2021年9月9日 20点57分 



