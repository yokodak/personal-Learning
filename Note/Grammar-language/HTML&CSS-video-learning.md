# HTML，CSS学习笔记：

> 📅：2020.09.17
>
> 📍: 学校
>
> 🔗:[尚硅谷新版Web前端HTML5+CSS3全套基础教程完整版(初学者零基础入门)]( https://www.bilibili.com/video/BV1XJ411X7Ud )
>
> 2020.09.17 **13:00**
>
> 2021 8.23 12:12 修改 重构 基于 [HTML教程 - MDN](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML)

Day 01  : 2020.09.18

 12:30 开始

## 1.HTML 基础

超文本标记语言（Hypertext Markup Language) 

### 1.概念引入

- [**HTML**](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML)

  [HTML](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML) (HyperText Markup Language) 不是一门编程语言，而是一种用来告知浏览器如何组织页面的**标记语言**

  HTML（超文本标记语言） 是一种描述语言，用来**定义网页结构**

- **HTML文档**

  HTML 文档是包含多个 [HTML 元素](https://developer.mozilla.org/zh-CN/docs/Glossary/Element) 的**文本文档**。每个元素都用一对开始和结束 [标签](https://developer.mozilla.org/zh-CN/docs/Glossary/Tag) 包裹。每个标签以尖括号（`< >`）开始和结束。也有一部分标签中不需要包含文本，这些标签称为空标签(自结束标签)，如 `<img>`

-  [HTML 元素](https://developer.mozilla.org/zh-CN/docs/Glossary/Element) 

  HTML元素一般构造如下👇

  

  ![](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/anatomy-of-an-html-element.png)

  

  在 HTML 中, 标签用来创建元素

  标签举例: 

  ```html
  - <em>  斜体强调标签 
  - <strong> 加粗强调标签
  - <p> 段落标签
  ```

### 2.块级元素和内联元素,空元素

- 块级元素(块元素)

  在页面中 **独占一行** 的元素称为块元素,在网页中一般使用块元素来对网页进行**布局**

  如

  ```html
  <div>我是块元素的内容</div><h1>我独占页面一行</h1><p>我会换行显示</p>
  ```

  效果如下:

  ![image-20210823144459576](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210823144459576.png)

  

- 内联元素(行内元素)

  不会独占一行,通常用于包裹文字

  如:

  ```html
  <em>第一</em><span>我还是在这行</span><strong>我不会独占一行!</strong><q>我不会换行显示</q>
  ```

  效果如下:

  ![image-20210823144838012](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210823144838012.png)



- 空元素(替换元素)

  不是所有元素都拥有开始标签，内容，结束标签。一些元素只有一个标签，通常用来在此元素所在位置插入/嵌入一些东西

  如  <img> 元素

  ```html
  <p>
      我是块级元素
  </p><img src="https://roy-tian.github.io/learning-area/extras/getting-started-web/beginner-html-site/images/firefox-icon.png"><span>我是行内元素</span>
  ```

  效果如下👇

  

  ![image-20210823145956464](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210823145956464.png)



### 3.元素的属性

属性包含元素的额外信息，这些信息不会出现在实际的内容中。元素的属性有其特定的作用,如标记元素( `id` 属性),指定超链接( `href` 属性 ) 等, 不同的元素之间,属性有所差异,一些属性是所有元素共有的,如 `class` 属性 `id` 属性等

一个属性包含如下内容：

1. 一个空格，在属性和元素名称之间。(如果已经有一个或多个属性，就与前一个属性之间有一个空格。)
2. 属性名称，后面跟着一个等于号。
3. 一个属性值，由一对引号“ ”引起来

如:

```html
<a href = "https://developer.mozilla.org/zhCN/docs/learn/HTML/Introduction_to_HTML/Getting_started"
   title = "MDN" > 开始学习HTML</a>
```

对于没有属性值,只有属性名的属性,我们称之为 **布尔属性** , 如 `disabled ` 属性 

```html
<!-- 使用disabled属性来防止终端用户输入文本到输入框中 -->
<input type="text" disabled>
```

### 4.HTML文档结构

如下的 HTML 文档 (来自 [MDN](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Getting_started#%E5%89%96%E6%9E%90html%E6%96%87%E6%A1%A3))

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>我的测试站点</title>
  </head>
  <body>
    <p>这是我的页面</p>
  </body>
</html>
```

1. `<!DOCTYPE html>`: 声明文档类型(以前的声明类似链接,用于规定HTML 遵守的规则,检测错误等,现在简化了)
2. `<html></html>`: `<html>`元素。这个元素包裹了整个完整的页面，是一个根元素。
3.  `<head>元素`. 这个元素是一个容器，它包含了所有你想包含在HTML页面中但不想在HTML页面中显示的内容。这些内容包括你想在搜索结果中出现的**关键字**和**页面描述**，**CSS样式**，**字符集声明**等等。
4. `<meta charset="utf-8">`: 这个元素设置文档使用utf-8字符集编码
5. `<title></title>`: 设置页面标题，出现在浏览器标签上
6. `<body></body>`: `<body>`元素。 包含了你访问页面时所有显示在页面上的内容，文本，图片，音频，游戏等等。

> 可以通过以下方式查询元素语义，作用
>
> zeal：英文，权威，比较新 
>
> W3Cschool

**14：10** pause

**20：10** start

### 5.实体引用：（转义字符）

在 `HTML` 元素的内容中不管使用多少空格，最后渲染出来还是只有一个空格，如果要显示多个空格，可以使用转义字符 `&nbsp;`*（在vue项目中无效是怎么回事？）*

一些特殊字符如 `<` `>` `'` 是 HTML 语法自身的一部分, 想要在页面上正确地显示它们，也需要使用转义字符

如下：

```html
<p>HTML 中用 <p> 来定义段落元素。</p>

<p>HTML 中用 &lt;p&gt; 来定义段落元素</p>
```

效果如图：

![image-20210823155815158](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210823155815158.png)



下表（[MDN](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Getting_started#%E5%AE%9E%E4%BD%93%E5%BC%95%E7%94%A8%EF%BC%9A_%E5%9C%A8html%E4%B8%AD%E5%8C%85%E5%90%AB%E7%89%B9%E6%AE%8A%E5%AD%97%E7%AC%A6))显示了部分常用的转义字符

| 字符 | 等价字符引用 |
| :--: | :----------: |
| `<`  |    `&lt;`    |
| `>`  |    `&gt`;    |
| `"`  |   `&quot;`   |
| `'`  |   `&apos;`   |
| `&`  |   `&amp;`    |

### 6.HTML注释

<!-- 我是注释 -->

### 7.`<head>`标签里有什么

`<head> ` 元素得内容不会在浏览器中显示，它的作用是保存页面的一些 [元数据](https://developer.mozilla.org/zh-CN/docs/Glossary/Metadata)

- `<title> ` 元素是一项元数据，用于表示整个 HTML 文档的标题（即标签栏看到的标题）

  它的内容也被用在搜索的结果中

- `<meta>` 元素 - 元数据

  元数据就是描述数据的数据，用来构建HTML文档的基本结构，以及就如何处理文档**向浏览器提供信息和指示**，它们本身不是文档内容，但提供了关于后面文档内容的信息 [🔗](https://segmentfault.com/a/1190000010342600)

  如下的`<meta>`元素指定了网页采用的字符集

  ```html
  <meta charset="utf-8"> <!--指定网页字符集为 utf- 8 -->
  ```

  一些常用的 `<meta>` 元素

  - `name` 指定了meta 元素的类型； 说明该元素包含了什么类型的信息。

    ```html
    <meta name="参数" content="具体描述信息">
    ```

  - `content` 指定了实际的元数据内容。s

    如下的两条元数据分别说明了 `网页作者` 和  `页面描述`

    ```html
    <meta name="author" content="Chris Mills">
    <meta name="description" content="The MDN Learning Area aims to provide
    complete beginners to the Web with all they need to know to get
    started with developing web sites and applications.">
    ```

    更多的 `name` 值及其释义见[下表](https://segmentfault.com/a/1190000010342600)

    | 元数据名称       | 说明                                                         |
    | ---------------- | ------------------------------------------------------------ |
    | application name | 当前页所属Web应用系统的名称                                  |
    | ~~keywords~~     | 描述网站内容的关键词,以逗号隔开，用于SEO搜索（已废弃）       |
    | description      | 当前页的说明                                                 |
    | author           | 当前页的作者名                                               |
    | copyright        | 版权信息                                                     |
    | renderer         | renderer是为双核浏览器准备的，用于指定双核浏览器默认以何种方式渲染页面 |
    | viewreport       | 它提供有关视口初始大小的提示，仅供移动设备使用               |

  - `http-equiv` 

    http-equiv属性在HTML4中有很多值，在HTML5中只有`refresh`、`default-style`、`content-type`可用

  - `charset` 

    charset为HTML5中新增的，用来声明字符编码;

- [ ] 关于 `meta` 元素的各种标准元数据，参见 [MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta/name)，这里先占个位，以后再补充

### 8.网页图标

可以通过下面的方式为网页添加图标

```html
<link rel="shortcut icon" href="图标地址，如favicon.ico" type="image/x-icon">
```

> **注**：如果你的网站使用了内容安全策略（Content Security Policy, CSP）来增加安全性，这个策略会应用在图标上。如果你遇到了图标没有被加载的问题，你需要确认认 [Content-Security-Policy](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Content-Security-Policy) header 的 [img-src directive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/img-src) 没有禁止访问图标。([MDN](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#%E5%9C%A8%E4%BD%A0%E7%9A%84%E7%AB%99%E7%82%B9%E5%A2%9E%E5%8A%A0%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9B%BE%E6%A0%87))

- [ ] `<link>` 元素的其他作用 [🔗](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link) 占位 以后补充

### 9.HTML文档书写规范

- [结构化](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)

  使用语义化的元素如 `<header>`、`<nav>`、`<aside>` 等

- 语义化

- 尽量不使用表象元素（ 如 `<b>`  `<i>`和`<u>`)

### 10.链接元素 `<a>`

- `<a>` 的属性

  - `href` =  '地址'  ，用于设置链接指向的网址

    - 链接到文档片段 ：使用 `#` 符号

      将 `href` 属性的值设置为 `#` 则链接到页面顶部 ，设置为元素 `id` 则跳转到对应位置 (如`#bottom`)  当 `href` 的值为`"javascript:;"`时，则点击后不会跳转，可以作为超链接的占位符使用。

      ```html
      <p>请将信件邮寄至 <a href="contacts.html#Mailing_address">我们的地址</a>。</p>
      <!-- 同文档内片段-->
      <p>本页面底部可以找到 <a href="#Mailing_address">公司邮寄地址</a>。</p>
      ```

    - 电子邮件链接

      当 `mailto` 为空时，一个新的发送电子邮件的窗口也会被用户的邮件客户端打开，只是没有收件人的地址信息。

      ```html
      <a href="mailto:nowhere@mozilla.org">向 nowhere 发邮件</a>
      ```

  - `title` =  ' 标题' 设置链接标题，鼠标悬停在元素上会显示标题内容

  - `target` = '值' 设置链接打开的位置，默认为 `_self` 即当前窗口打开，设置为 `_blank`则在新窗口打开

  - `download` = '资源名称'  ，仅适用于同源 URL，下面是一个下载链接到Firefox 的 Windows最新版本的[示例](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks#%E5%9C%A8%E4%B8%8B%E8%BD%BD%E9%93%BE%E6%8E%A5%E6%97%B6%E4%BD%BF%E7%94%A8_download_%E5%B1%9E%E6%80%A7)

    ```html
    <a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=zh-CN"
       download="firefox-latest-64bit-installer.exe">
      下载最新的 Firefox 中文版 - Windows（64位）
    </a>
    ```

- 链接书写规范

  - 说明链接的内容，避免使用 `链接` `点这里` 之类的词作为链接内容
  - 链接到非 `HTML` 资源时，注明资源信息及要求 如 `下载报告 (PDF,10MB)` `进入游戏（需要flash插件）`
  - 保证链接内容尽可能短，不要使用 URL 作为链接内容
  - 链接到同一网站的其他位置，尽量使用相对链接

### 11.HTML高阶文字排版

包括 标记引文、描述列表、计算机代码和其他相关文本、下标和上标、联系信息 等

- [描述列表](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Advanced_text_formatting#%E6%8F%8F%E8%BF%B0%E5%88%97%E8%A1%A8)
- [标记引文](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Advanced_text_formatting#%E5%BC%95%E7%94%A8)
- [计算机代码](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Advanced_text_formatting#%E5%B1%95%E7%A4%BA%E8%AE%A1%E7%AE%97%E6%9C%BA%E4%BB%A3%E7%A0%81)
- [下标和上标](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Advanced_text_formatting#%E4%B8%8A%E6%A0%87%E5%92%8C%E4%B8%8B%E6%A0%87)
- [联系信息，缩略语](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Advanced_text_formatting#%E7%BC%A9%E7%95%A5%E8%AF%AD)
- [时间和日期](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Advanced_text_formatting#%E6%A0%87%E8%AE%B0%E6%97%B6%E9%97%B4%E5%92%8C%E6%97%A5%E6%9C%9F)

### 12.阶段练习

- [信件排版](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Marking_up_a_letter)

  [练习材料](https://github.com/roy-tian/learning-area/tree/master/html/introduction-to-html/marking-up-a-letter-start)

- [构建网页](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/Structuring_a_page_of_content)



## 2.HTML 多媒体

### 1.图片

- 普通图像

  使用 `<img> ` 元素引入

  > - SEO 
  >
  >   将图片放置于 `images`文件夹下有利于  [SEO](https://developer.mozilla.org/zh-CN/docs/Glossary/SEO) ，图像的文件名也会被搜索引擎读取，所以最好是根据图片内容命名，而不是使用随便的字母数字
  >
  > - 路径
  >
  >   同一项目的图片使用相对路径，将图片和 HTML 放在同一服务器上
  >
  > - 注意图片的版权问题，不要随便使用图片，`src` 属性不要指向其他人网站上的图片，可以到一些可商用图片库、无版权图片库搜索图片。如果经过允许可以使用他人图片，要附上说明

  `<img> 、<video>`这样的元素有时被称之为**替换元素**，因为这样的元素的内容和尺寸由外部资源（像是一个图片或视频文件）所定义，而不是元素自身 ( [MDN](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML) )。

  - 备选文本属性 `alt` 

    属性值是对图片的文字描述，用于在图片无法显示或不能被看到的情况，也有利于 SEO , 并在多种情况下发挥作用如 用户有视力障碍，用户关闭图片显示，浏览器不支持图片类型，你把文件名拼错等。
    
    关于 可访问性 的内容 可以参见 [可访问性-MDN](https://developer.mozilla.org/zh-CN/docs/learn/Accessibility)
    
    备选文本的内容在不同情况有不同要求，尽量不要将内容写得冗余繁杂。

    ```html
    <img src="images/dinosaur.jpg"
         alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。">
    ```
    
  - 图片宽高属性

    ```html
    <img src="images/dinosaur.jpg"
         alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
         width="400"
         height="341">
    ```

    > 如果你需要改变图片的尺寸，你应该使用 CSS 而不是 HTML。

  - 图片标题属性

    鼠标悬浮会显现提示信息

    ```html
    <img src="images/dinosaur.jpg"
         alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
         title="A T-Rex on display in the Manchester University Museum">
    ```

  - 内容说明元素 `<figure>` ， `<figcaption>`

    `HTML5` 的元素 用于对页面的元素进行说明，描述（如图片描述，代码说明，方程描述等），通常用于将标题和内容联系起来

    ```html
    <figure>
      <img src="https://raw.githubusercontent.com/mdn/learning-area/master/html/multimedia-and-embedding/images-in-html/dinosaur_small.jpg"
         alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
         width="400"
         height="341">
      <figcaption>曼彻斯特大学博物馆展出的一只霸王龙的化石</figcaption>
    </figure>
    ```

    `<figcaption>` 元素的文字内容描述了 `<figure>`元素

    更多关于  `figure` 和 ` <figcaption>` 见 [figure](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/figure) ，[figcaption](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/figcaption)

  - CSS 背景图

    ```css
    p {
      background-image: url("images/dinosaur.jpg");
    }
    ```

    CSS 背景图片只是为了装饰 , 没有语义上的意义，它们没有任何备选文本，也不能被屏幕阅读器识别。

    如果图像对您的内容里有意义，则应使用 HTML 图像。 如果图像纯粹是装饰，则应使用 [CSS 背景图片](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML#css_%E8%83%8C%E6%99%AF%E5%9B%BE%E7%89%87)。

- 矢量图

  

- 响应式图片

### 2.视频和音频

### 3.嵌入技术



## 3.HTML 表格

## 4.CSS 基础

10.浏览器使用f12检查中的elements窗口内的代码是浏览器内部储存的代码，如果我们写的代码不符合规范，浏览器会自动帮我们修正，但是尽量不要让浏览器帮我们修正代码，这样不仅会影响性能，还有可能得到我们不想要的效果。

11.一些html5新增标签和div，span标签：

 main标签一个网页里只能有一个


![image-20200918210743549](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918210743549.png)



12.列表标签：

ul 无序列表

ol 有序列表

dl 定义列表：一般会用于二级菜单等。

列表间可以相互嵌套；

![image-20200918211232221](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918211232221.png)

![image-20200918211402828](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918211402828.png)



14.相对路径：

./表示当前目录

../表示上一级目录

![image-20200918212259328](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918212259328.png)

15.替换元素：（块元素和行内元素之间）

比如<img>标签

![image-20200918213613060](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918213613060.png)

16.img标签：

img标签的alt属性，用于对图片进行描述，只有当图片无法显示时才会出现，但是它的主要作用是方便浏览器的搜索引擎根据alt里的内容来识别图片，如果不写则不会被搜索引擎所收录。

![image-20200918213929988](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918213929988.png)



17.图片格式：

base64：

![image-20200918222709727](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918222709727.png)

![image-20200918221951419](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918221951419.png)



18.内联框架：

“<iframe> ” 成对的标签

![image-20200918223018636](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918223018636.png)

19.audio标签和video标签：

controls属性：有则运行用户控制，没有则不允许；

loop设置音乐是否循环播放

autoplay设置音频文件是否自动播放；

兼容性问题见下图：（可以使用embed标签但是效果不好）

![image-20200918223946235](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918223946235.png)

video标签：

![image-20200918224607557](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918224607557.png)

## 20.CSS:层叠样式表：

![image-20200918225105474](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918225105474.png)

引入CSS的三种方式：

推荐使用第三种方式：通过链接link标签（自结束）引入外部css文件，这样可以复用，并且由于浏览器的缓存机制，当再次引用该样式文件时，就可以加快网页加载速度，提高用户体验。

![image-20200918225716385](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918225716385.png)

![image-20200918225650379](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918225650379.png)

或者

#### 1.@import和link的区别

1. `@import`是 CSS 提供的语法规则，只有导入样式表的作用；`link`是HTML提供的标签，不仅可以加载 CSS 文件，还可以定义 RSS、rel 连接属性等。 
2.  加载页面时，`link`标签引入的 CSS 被同时加载；`@import`引入的 CSS 将在页面加载完毕后被加载 

### 21.css语法：

选择器 声明块

![image-20200918230329858](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918230329858.png)

### 22.常用选择器：

1. 元素选择器：元素名{} 
2. id选择器：#{}
3. 类选择器：.类名{}
4. 通配选择器：选择页面中所有元素

![image-20200918230941520](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200918230941520.png)

**23：10** 

Day 01 结束 2020.09.18  **23：10**   

# ==Day 02== 开始 2020.09.19  13：20

### 1.复合选择器：

#### 1.交集选择器：

![image-20200919105810490](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919105810490.png)

#### 2.并集选择器：（选择器分组）

![image-20200919105731229](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919105731229.png)



### 2.关系选择器：

1. 子元素选择器：父元素 > 子元素 { }

2. 后代元素选择器：祖先 后代{ } 

3. 兄弟选择器：兄 +后一个 弟（必须是紧挨着的）

   选择下边所有兄弟：上面的不会被选中：兄~弟

![image-20200919110245083](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919110245083.png)

### 3.属性选择器：

选择含有指定属性的元素：

title属性，当鼠标移动到该元素上时，会显示该元素的title属性内的内容；

![image-20200919131801344](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919131801344.png)

### 4.伪类选择器：

==(注意子元素内也有空白文本)==

伪类：用来描述一个元素的特殊状态 比如：hover 表示当鼠标移入时

伪类一般使用 :开头 

##### ：first-child 具体用法见下图；

(注意不是dom结构的子节点！具体参考下面w3c链接)

![image-20200919133139777](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919133139777.png)

https://www.w3school.com.cn/tiy/t.asp?f=eg_css_sel_nth-child_odd_even

```html
<!DOCTYPE html>
<html>
<head>
<style> 
p:nth-child(odd)
{
background:#ff0000;
}
p:nth-child(even)
{
background:#0000ff;
}
</style>
</head>
<body>

<h1>这是标题</h1>
<p>第一个段落。</p>
<p>第二个段落。</p>
<p>第三个段落。</p>
<p>第四个段落。</p>

<p><b>注释：</b>Internet Explorer 不支持 :nth-child() 选择器。</p>

</body>
</html>
```



超链接的伪类：

：link表示没访问过的链接

：visited 表示访问过的链接，只能设置颜色样式，由于隐私原因，一般不使用

![image-20200919133701625](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919133701625.png)

![image-20200919133522271](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919133522271.png)

：hover 鼠标移入 

：active 鼠标点击

![image-20200919134019699](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919134019699.png)

### 5.伪元素选择器：

伪元素：表示页面中一些并不真实存在的位置：（特殊的位置)

伪元素使用::开头

![image-20200919134639418](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919134639418.png)

![image-20200919134608794](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919134608794.png)

::before 

::after

缝隙间

![image-20200919135139214](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919135139214.png)

这两个必须结合content 属性来使用

![image-20200919134909430](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919134909430.png)

![image-20200919135049662](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919135049662.png)

![image-20200919135106240](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919135106240.png)



### ==6.CSS餐厅练习==





### 7.继承：

继承是发生在祖先后代之间的。并不是所有的样式都会被继承，比如背景和布局相关的属性。

![image-20200919140142522](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919140142522.png)

![image-20200919135938844](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919135938844.png)

![image-20200919135857039](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919135857039.png)

![image-20200919135909702](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919135909702.png)

![image-20200919135918729](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919135918729.png)

### 8.选择器的权重：

css的权重优先级表现为：

**`!important > 行内样式 > ID > 类、伪类、属性 > 标签名 > 继承 > 通配符`**

 link和@import这两种引入css的方式并没有权重方面概念，只是单纯的展示出css的层叠行罢了。即写在后边都样式会覆盖前面的样式。 

内联样式>id选择器>类选择器>元素选择器>通配选择器

选择器的权重是累加的，如：div#first的优先级> #first

添加了！important的样式优先级最高，慎用，无法修改

优先级一样的优先使用靠页面下方的

![image-20200919141021267](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919141021267.png)

继承样式没有优先级（最底层）

![image-20200919140944251](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919140944251.png)

![image-20200919140956704](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919140956704.png)

![image-20200919140934297](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919140934297.png)



### 9.长度单位：

#### 1.像素（px）

不同的显示器，（屏幕） 像素大小是不一样的，像素越小的屏幕效果越清晰

所以同样的200px在不同的屏幕显示效果不一样

![image-20200919141858327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919141858327.png)

#### 2.百分比：

相对于其父元素属性的百分比

![image-20200919142056493](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919142056493.png)

#### 3.em：

是相对于元素的字体大小来设置的：会随着字体的大小改变而改变：

1em = 1font像素

如下图，10em=300px；

![image-20200919142456362](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919142456362.png)

#### 4.rem ：

相对于根元素的字体大小

![image-20200919142349188](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919142349188.png)

### 10.颜色单位：

可以通过颜色名来设置颜色 red green blue 等

#### 1.RGB:

(光的三原色：红绿蓝)

0-255之间（0%-100%之间）

rgba a表示不透明度

16进制的颜色

![image-20200919143116992](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919143116992.png)

#### 2.HSL

(Hue Saturation Lightness)

H 色相 （0-360)

S 饱和度 (颜色浓度) 0%-100%

L 亮度  0%-100%

hsla（不透明度）

![image-20200919143514204](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919143514204.png)

*==屏幕取色器==*

直接使用qq截图快捷键  按c复制色号

## 布局 Layout

### 11.文档流:

网页的最底层，网页的基础；

我们所创建的元素都在文档流中

元素两个状态：

  	在文档流中;

​	 不在文档流中（脱离文档流）

元素在文档流中的特点：

块元素

行内元素

![image-20200919144144639](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919144144639.png)



### 12.盒模型：

![image-20200919144657913](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919144657913.png)

![image-20200919150742664](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919150742664.png)

![image-20200919144712975](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919144712975.png)

![image-20200919144733273](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919144733273.png)

**content（内容区）**

width 和 height 设置的是内容区的宽高

**border （边框）**：边框大小也会影响盒子大小

![image-20200919145030981](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919145030981.png)

   	boder-width: 一般默认值是3px,值的设置从左到右依次是：

​	   四个值：上-右-下-左  三个值 ：上 -左右- 下 两个值： 上下-左右  

  	 一个值 ；上下左右

![image-20200919145638089](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919145638089.png)

 边框颜色（border-color）也可以分别设置上下左右的颜色：

![image-20200919145651377](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919145651377.png)

边框样式（border-style）：默认值是没有边框

![image-20200919145743370](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919145743370.png)

![image-20200919145751320](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919145751320.png)

border 简写属性：

![image-20200919150619993](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919150619993.png)



**内边距（padding）**：

![image-20200919151244569](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919151244569.png)



**外边距（margin）**：

会影响元素在网页中占用空间的大小

有正负，可以用来指定移动方向

margin-left 和margin-top 是移动自己

margin-bottom是挤别人

margin-right 目前不会产生任何效果；(因为过度约束的原因，浏览器会自动修改margin-right 的值（当7个值中没有设置auto时，默认的auto是width（如果width没有设置））)

![image-20200919151802428](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919151802428.png)



### 12.盒子模型-水平方向的布局：

一个元素在其父元素中的水平布局必须满足:

以下等式：

左外边距+ 左边框+左内边距+宽度+右内边距+右边框+右外边距 = 其父元素的内容区宽度

如果等式不成立，则称为过度约束

当这七个值中没有设置auto时，浏览器会自动修改margin-right的值（当子元素从父元素中溢出时，会为负值）来满足等式，所以一般我们不会专门设置外右边距。

当有auto时则修改auto的值，三个值可以是auto：margin-left，margin-right,width.

当有一个外边距和宽度被设置为auto时，会修改width的值，外边距会置为0

当三个值都是auto时，修改width 的值，外边距置0

==*当两个外边距同时为auto，则width的值不变，左外边距和右外边距相等，利用此特性，我们常常用来将父元素中的子元素水平居中*==

如：

width：100px;

margin: 0,auto;（0：上下，auto：左右）

![image-20200919153150928](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919153150928.png)

![image-20200919153530703](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919153530703.png)



### 13.盒子模型:垂直方向上的布局

默认情况下，父元素的高度被内容撑开；

设定了高度的话，则是设置的高度；

当子元素从父元素中溢出后，可以使用overflow样式设置超出部分是否显示

也可以使用overflow-x,overflow-y对水平和垂直方向单独设置。

![image-20200919154943288](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919154943288.png)

### 14.垂直外边距的重叠（折叠）

相邻元素垂直方向上的外边距会发生重叠的情况；

如果发生在兄弟元素之间，则取两者间的最大值，兄弟元素的重叠我们不需要处理；

父子元素间相邻外边距，子元素的会传递给父元素（上外边距）则会一起向下移动，会影响布局，所以必须处理==（见24.BFC&27.clearfix)==

![image-20200919160210351](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919160210351.png)

 **16：05**  pause

**20：20**   start

16.行内元素的盒模型：

行内元素不支持宽高，垂直方向上的padding border margin 不会影响页面的布局

![image-20200919202407121](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919202407121.png)

可以通过display属性设置元素显示的类型，来完成行内元素和块元素的互相转换。也可以让元素在页面中不显示。

visibility也可以设置元素是否显示，但是即使隐藏依然会占据页面的位置

![image-20200919202921799](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919202921799.png)



### 16.浏览器的默认样式：

在PC端页面，通常在编写网页时要去除浏览器的默认样式；

可以通过通配选择器来去除;

*{

​		margin：0；

​		padding: 0;

​		list-stlye:none

}

![image-20200919203635450](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919203635450.png)



或者直接引入去除浏览器默认样式的css文件:重置样式表

![image-20200919204230128](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919204230128.png)

文件内容:不全

![image-20200919204015111](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919204015111.png)



### 17.练习：

css从上到下，依次写最外层到最里层（指元素的层级关系，比如该页面中body元素最外层）

要模仿一个网页，可以直接f12查看参数，复制资源。

注意结构设计；

![image-20200919205441229](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919205441229.png)

![image-20200919205617089](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919205617089.png)

![image-20200919205656788](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919205656788.png)

练习2：

![image-20200919210952315](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919210952315.png)

*tips:*

如果要让==文字在其父元素中垂直居中==，只需要将父元素的line-height 设置为和父元素的height一样

![image-20200919210742379](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919210742379.png)



练习3：

![image-20200919212038747](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919212038747.png)

设置“体育”上的红色边框：

![image-20200919212009683](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919212009683.png)

设置新闻列表项目符号：

![image-20200919212518979](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919212518979.png)



### 18.盒子的大小：

content-box:不包括边框，内边距

border-box:包括边框，内边距

![image-20200919212848460](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919212848460.png)



### 19.轮廓、阴影和圆角：

轮廓：outline，不会影响布局

![image-20200919213045339](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919213045339.png)

阴影：box-shadow

```css
/* x偏移量 | y偏移量 | 阴影颜色 */
box-shadow: 60px -16px teal;

/* x偏移量 | y偏移量 | 阴影模糊半径 | 阴影颜色 */
box-shadow: 10px 5px 5px black;

/* x偏移量 | y偏移量 | 阴影模糊半径 | 阴影扩散半径 | 阴影颜色 */
box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);

/* 插页(阴影向内) | x偏移量 | y偏移量 | 阴影颜色 */
box-shadow: inset 5em 1em gold;

/* 任意数量的阴影，以逗号分隔 */
box-shadow: 3px 3px red, -1em 0 0.4em olive;

/* 全局关键字 */
box-shadow: inherit;
box-shadow: initial;
box-shadow: unset;

```





![image-20200919213341991](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919213341991.png)

![image-20200919213350213](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919213350213.png)

圆角：（也可以设置两个值来达到椭圆角）

![image-20200919213714327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919213714327.png)



### 19.浮动：

 浮动的元素会完全脱离文档流；不在占据文档流中的位置，不会浮动超出其父元素，==浮动以后，水平布局的等式便不再需要强制成立；==下面文档流中的元素会自动上移。

浮动元素不会盖住文字，由此可以达成文字环绕图片的效果，这也是浮动发明的原因。

![image-20200919215122067](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919215122067.png)

![image-20200919215130220](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919215130220.png)



### 20.元素脱离文档流的特点：

块元素：块元素不再独占一行；宽度和高度默认被内容撑开；

行内元素：会变成块元素；

脱离文档流以后，便不再需要区别行内元素和块元素了。



### 21.导航条练习：

*tips*：注意，当对元素的大小，宽高不确定什么效果好时，可以通过f12检查元素，进行调试。

![image-20200919220118872](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919220118872.png)

![image-20200919220646186](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919220646186.png)

消除最后的多余像素：

![image-20200919221114508](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919221114508.png)

### 22.页面布局：

善用浮动实现水平布局；

### 23.高度塌陷和BFC:

​	高度塌陷：

![image-20200919222701942](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919222701942.png)

![image-20200919222152828](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919222152828.png)

![image-20200919222201631](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919222201631.png)



BFC(Block Formatting Context):

块级格式化环境

BFC是一个CSS中的隐含属性，开启BFC有很多种方式，但是都会有副作用，我们能一般使用副作用最小的开启方式：将元素的overflow设置为hidden

![image-20200919223343053](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919223343053.png)

开启BFC的元素会变成一个独立的布局环境；它不会被浮动元素所覆盖，开启后子元素和父元素的外边距不会重叠，开启后的父元素可以包含浮动的子元素；

![image-20200919223046740](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919223046740.png)



### 24.clear：

为当前元素清除浮动的影响：原理是浏览器会自动为当前元素添加一个合适的上边距；

![image-20200919224207594](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919224207594.png)



### 25.高度塌陷的比较好的解决方案：

使用::after伪元素解决高度塌陷

为高度塌陷的元素设置一个伪元素after并在其中设置content为空字符串，设置clear为both;

通过该方式我们不用改变html的结构来解决css的问题。



![image-20200919224800716](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919224800716.png)

![image-20200919224810566](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919224810566.png)

![image-20200919224916140](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919224916140.png)



### 26.clearfix

（解决父子元素垂直方向上的外边距重叠问题和高度塌陷）

![image-20200919225516984](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919225516984.png)



## 定位：

### 27.偏移量（offset）：

![image-20200919230406242](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919230406242.png)

### 28.position：（定位）

![image-20200919230717751](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919230717751.png)

static:默认值，元素是静止的，没有开启定位

relative：相对于原来在文档流中的位置

零零点是原来在文档流中的位置

![image-20200919230921020](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919230921020.png)

absolute:

开启绝对定位以后，元素会从文档流中脱离，性质发生改变，行内元素变为块元素。

绝对定位是相对于其包含块（containing block）进行定位的

正常情况下包含块就是离其最近的祖先==块元素==

开启了绝对定位的元素，其包含块是==离其最近的开启了定位的组先元素==（定位原点0，0是包含块的左上角），没有则是根元素。(会随网页滚动而位置发生变化)

![image-20200919231843607](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200919231843607.png)



Day 02 结束 进度：70P结束 **23：20**   2020.09.19

# ==Day 03== 2020.09.20 12：15 start

fixed:

固定定位：也是一种绝对定位，不同的是它永远参照浏览器的视口进行定位，不会随网页的滚动而改变位置。

![image-20200920122454090](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920122454090.png)

sticky:

粘滞定位：定位参考物是其包含块，兼容性不好，使用的不多

![image-20200920123214485](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920123214485.png)



### 1.绝对定位元素的位置：

当一个元素开启绝对定位后，水平和垂直方向上分别 需要满足两个等式(相对于前面的7值等式添加了left和right)

![image-20200920123448717](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920123448717.png)

==question 利用绝对定位使元素在其包含块中垂直水平居中：==

兼容性不错的主流用法是：

```
.element {
    width: 600px; height: 400px;
    position: absolute; left: 50%; top: 50%;
    margin-top: -200px;    /* 高度的一半 */
    margin-left: -300px;    /* 宽度的一半 */
}
```

但，这种方法有一个很明显的不足，就是需要提前知道元素的尺寸。否则`margin`负值的调整无法精确。此时，往往要借助JS获得。

CSS3的兴起，使得有了更好的解决方法，就是使用`transform`代替`margin`. `transform`中`translate`偏移的百分比值是相对于自身大小的，于是，我们可以：

```css
.element {
    width: 600px; height: 400px;
    position: absolute; left: 50%; top: 50%;
    transform: translate(-50%, -50%);    /* 50%为自身尺寸的一半 */
}
```

下图的方法：根据布局等式，将left,right,top,bottom都设置为0，margin设置为auto

![image-20200920124215964](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920124215964.png)

![image-20200920124231692](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920124231692.png)

### 2.元素的层级： 

当元素==开启定位==后，可以通过z-index属性设置元素的层级：一个整数，值越大，层级越高，当层级一样时，越靠后定义的层级越高。祖先元素的层级再高也不会盖住后代元素。

![image-20200920125022242](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920125022242.png)



### 3.轮播图练习

**13：00**  pause

**14:40**     start

### 4.字体族：

![image-20200920145721800](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920145721800.png)

字体分类：

使用以下几个fontfamily浏览器会自动选择各个类别下的任意一个字体。

衬线字体：serif）![image-20200920144204147](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920144204147.png)

非衬线字体：sans-self）![image-20200920144145677](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920144145677.png)

等宽字体：monospace)![image-20200920144220736](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920144220736.png)

浏览器在使用字体时，会按照我们设置的顺序从左到右执行，有则使用，没有则使用下一个；

![image-20200920145457314](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920145457314.png)

==@font-face属性：==

可以将服务器中的字体直接提供给用户使用：（如果是本地字体则需要在文件夹中包含该字体文件，通过font-face引用）

注意版权（用户通过该服务器下载字体，而我们并未获得授权）问题和格式问题，因为可能有些浏览器不兼容字体的格式，所以可能需要添加多个资源链接。

并且由于需要下载字体，第一次打开网页时，字体的加载会比较慢。

![image-20200920144858987](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920144858987.png)



### 5.图标字体：

==图标字体库：font awesome==

![image-20200920150247663](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920150247663.png)

![image-20200920150458407](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920150458407.png)

![image-20200920150509648](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920150509648.png)

通过伪元素来使用图标字体：

![image-20200920151035424](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920151035424.png)

通过实体来使用图标字体：

![image-20200920151058537](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920151058537.png)

阿里云：iconfont

![image-20200920151627901](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920151627901.png)

![image-20200920151636835](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920151636835.png)

### 6.字体的行高和字体框：

行高会在字体框上下平均分配；将行高设置为和高度一样的值可以使单行文字在一个元素中垂直居中。

行间距 = 行高 - 字体大小；

![image-20200920152205040](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920152205040.png)

![image-20200920152004924](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920152004924.png)



### 7.字体的简写属性：

不写不是不设置，而是设置为默认属性，所以注意如果把行高，样式，加粗设置在简写属性前，会被覆盖。

![image-20200920154141929](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920154141929.png)

### 8.文本的布局：

vertical-align 设置元素垂直对其的方式，默认是基线对齐

![image-20200920154915681](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920154915681.png)

设置文本的水平对齐:

![image-20200920155043005](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920155043005.png)



### 8.其他的文本样式：

text-decoration:设置文本修饰

![image-20200920155411984](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920155411984.png)

white-space:设置网页如何处理空白；

设置溢出的文本内容以省略号显示。

![image-20200920155426605](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920155426605.png)

![image-20200920155438009](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920155438009.png)

white-space:pre会保留我们在html中键入的空格和换行

![image-20200920155635211](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920155635211.png)

![image-20200920155701494](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920155701494.png)



## ==9.京东顶部导航条练习==（P84-P86)

练习时对照视频

注意下拉框的设置：

![image-20200920161751223](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920161751223.png)



### 10.背景：

背景颜色，背景图片，背景重复，背景位置

![image-20200920163114116](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920163114116.png)

背景的几个属性：

![image-20200920164408514](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920164408514.png)

![image-20200920164506464](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920164506464.png)

![image-20200920164525810](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920164525810.png)

![image-20200920164542706](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920164542706.png)





### 11.使用背景图片实现渐变效果（结合ps）第90P



### 12.雪碧图

解决网页加载图片资源有延迟问题：（图片切换时会发生闪烁问题）CSS-Sprite我们称为雪碧图

![image-20200920170225935](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920170225935.png)

**==雪碧图：==**

只使用一张图片，通过修改background-position实现多个图片见的切换效果，避免了使用多张图片，这样能避免因为网页加载资源出现的闪烁问题，一次性加载“多个图片”（多张图片集合在了一张雪碧图）降低了浏览器的请求次数和图片资源的大小，加快了访问速度，提高用户体验。

使用广泛

![image-20200920171009291](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920171009291.png)

![image-20200920170946656](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920170946656.png)

![image-20200920170922849](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920170922849.png)



### 13.渐变

具体参数可以参考zeal的css文档

渐变是图片，需要通过background-image来实现

线性渐变：linear-gradient

![image-20200920172044734](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920172044734.png)

径向渐变：radial-gradient：

![image-20200920172656974](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920172656974.png)



**17：30** pause

**19：30** start

### ==**14.电影卡片练习：**==

![image-20200920192700118](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920192700118.png)

![image-20200920193812311](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920193812311.png)



### 15.表格 （table）

colspan横向合并单元格

rowspan纵向合并单元格

thead tbody tfoot

th 头部单元格；

![image-20200920194041555](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920194041555.png)

长表格：

![image-20200920194419872](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920194419872.png)



表格的样式：

border-spacing

border-collapse:设置边框合并；

注意：table不是tr的父元素，tr的父元素是tbody

我们通过设置偶数子元素的背景颜色实现表格的背景色按行切换。

![image-20200920195027746](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920195027746.png)

通过display:table-cell 可以将元素设置为单元格，这样可以使用vertical-align将其中的==元素居中==，用得不多，了解即可。

![image-20200920195137418](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920195137418.png)

![image-20200920195147683](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920195147683.png)



### 16.表单：

![image-20200920200014068](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920200014068.png)

![image-20200920195926334](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920195926334.png)

![image-20200920195959829](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920195959829.png)



表单的补充：

autocomplete = "off" 关闭自动补全

readonly 只读

disabled  禁用

autofocus 自动获取焦点

提交按钮，重置按钮， 普通按钮

color e-mail 一般不会使用 

![image-20200920200728573](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920200728573.png)

![image-20200920200814153](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920200814153.png)



# ==17.项目实战==

*编写代码时善用Emmet编辑工具*

![image-20200920201051568](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920201051568.png)

公共样式表；base.css

![image-20200920201755249](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920201755249.png)

引入外部文件：

![image-20200920201409143](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920201409143.png)

注意的点：

1.用户信息和购物车的浮动，向右浮动（结构上购物车在用户前，float right的效果）

2.超链接设置为块元素

3.解决顶部导航栏的高度塌陷问题

4.注意hover的绑定问题

5.![image-20200920203339137](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920203339137.png)注意这类遮盖边框的处理；

6.利用下边框实现小三角

7.二维码下拉框的位置

8.小三角的hover实现

​	两种方法

![image-20200920205045067](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920205045067.png)

![image-20200920204834985](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920204834985.png)

9.通过将元素的高度设为0px以将元素隐藏,==方便实现过渡效果，使用translation：==

![image-20200920205342208](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920205342208.png)

10.home的hover变化及其过渡效果（160P 20分钟处）

![image-20200920210020066](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920210020066.png)![image-20200920210031841](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920210031841.png)

![image-20200920210149315](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920210149315.png)

隐藏log的alt文字：![image-20200920210258575](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920210258575.png)

11.注意处理商品分类导航和logo间的距离

12.注意处理商品隐藏层的位置以及其hover效果（第一个隐藏的和最后两个不会显示，为显示的其他几个单独设置类）

*tips:按住alt键同时选择多行可以同时进行编辑*

![image-20200920212115924](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920212115924.png)

13.搜索框：

![image-20200920212414462](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920212414462.png)

14.按钮的boxsize是border-box

15.轮播图的切换按钮是一个雪碧图：（也可以用图标字体）

![image-20200920223442935](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920223442935.png)

16.布局等式：

![image-20200920224208147](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920224208147.png)

17.注意工具栏的位置（112P 16分处）

![image-20200920224739754](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920224739754.png)

18.

![image-20200920230143119](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920230143119.png)

![image-20200920230321327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920230321327.png)

19.浏览器标题：

![image-20200920230721346](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920230721346.png)

设置网站的图标：

![image-20200920230902232](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920230902232.png)

20.将代码压缩，减小项目大小，加快访问速度

除了使用下面的工具，以后还有更加强大的工具。

![image-20200920231037105](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200920231037105.png)



Day 03 结束 23：15 进度：114P结束 2020.09.20



# ==Day 04== 开始 12：25 2020.09.21

## 1. animation（动画）

### 1.过渡：

transition：

1. transition-property：指定要过渡的属性，大部分属性都支持（如颜色，外边距等，必须是有效值间的过渡，不能是auto）；

2. transition-duration：过渡的持续时间；

![image-20200921124121459](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921124121459.png)

3. transition-timing-function ：过渡的时序函数，也可以在贝塞尔曲线中指定特定值达到其他过渡效果；也可以使用steps来指定动画几步完成。
4. transition-delay：过渡效果的延迟。

![image-20200921124813579](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921124813579.png)

过渡练习：

![image-20200921125137032](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921125137032.png)

![image-20200921125145948](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921125145948.png)

### 2.动画（animation）：

关键帧：@keyframes

![image-20200921131206626](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921131206626.png)

![image-20200921130249698](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921130249698.png)

![image-20200921130402443](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921130402443.png)

动画练习：可以搜索sprite-animation 下载其他的图片练习

![image-20200921130740582](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921130740582.png)

![image-20200921130748477](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921130748477.png)

### 3.关键帧：小球落下练习

![image-20200921131856134](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921131856134.png)

![image-20200921131936875](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921131936875.png)

![image-20200921131817376](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921131817376.png)



### 4.变形：transform

平移：(可以利用平移使元素居中)

![image-20200921134503970](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921134503970.png)

![image-20200921134524595](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921134524595.png)

![image-20200921134532086](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921134532086.png)

利用平移实现浮出效果：

![image-20200921134333979](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921134333979.png)

![image-20200921134313021](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921134313021.png)

### z轴平移：近大远小

网页的视距：perspective，视角会由于旋转而改变

![image-20200921134923167](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921134923167.png)

![image-20200921135106961](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921135106961.png)

 

==旋转：transform ：rotaze==

可以实现一些好的动画效果：

![image-20200921135641301](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921135641301.png)

![image-20200921135707523](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921135707523.png)

#### ==5.练习：==

利用旋转和动画实现钟表，注意动画时间的设置,这里为了加快效果，把秒设置为10秒转一圈。

![image-20200921140559873](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921140559873.png)



### ==6.练习：立方体旋转==

使用opacity可以为元素设置透明效果；

![image-20200921140937249](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921140937249.png)

```html
1 opacity=0，该元素隐藏起来了，但不会改变页面布局，并且，如果该元素已经绑定一些事件，如click事件，那么点击该区域，也能触发点击事件的
2 visibility=hidden，该元素隐藏起来了，但不会改变页面布局，但是不会触发该元素已经绑定的事件
3 display=none，把元素隐藏起来，并且会改变页面布局，可以理解成在页面中把该元素删除掉一样
```

设置3d变形效果：

transform-style:preserve-3d; 

![image-20200921141446217](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921141446217.png)

![image-20200921141506045](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921141506045.png)

![image-20200921141623261](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921141623261.png)



### 7.缩放：scale

transform-origin：设置变形的原点，默认是center

![image-20200921142225407](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921142225407.png)

## 2.less:

*使用less需要先把less转换为css，所以先在编辑器中安装less转css插件，比如==Easy Less==*

### 1.less介绍：

less是一门css的预处理语言：

css也支持原生变量：通过--声明，设置，通过var引用变量。

css也有一些函数，如calc（）计算函数

但是这些东西兼容性不好，并不是所有浏览器都支持。

![image-20200921143021842](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921143021842.png)

而通过less我们可以实现同样的功能并且兼容性更好。

![image-20200921143901878](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921143901878.png)

less:结构更清晰

![image-20200921143717724](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921143717724.png)

![image-20200921144430271](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921144430271.png)

css:

![image-20200921143746738](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921143746738.png)

![image-20200921144445006](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921144445006.png)

### 2.less语法：

**注释**

![image-20200921144625332](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921144625332.png)

**变量：**

less：@变量名，作为变量时，直接使用即可，作为类名或者一部份值时，必须以@{变量名}的形式使用。变量重名时，优先使用最近的变量，可以在变量声明前就使用变量。

![image-20200921145743928](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921145743928.png)

css：

![image-20200921145812921](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921145812921.png)

**父元素**：  

使用&符

表示的是外层的父元素；

扩展（选择器分组）：extend

![image-20200921151005238](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921151005238.png)

**==混合函数：==**mixins:复制样式,可以在其中直接设置变量，参数可以设置多个，按顺序传递参数，或者在值前指定变量名：

![image-20200921151511247](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921151511247.png)

还可以在定义变量时设置默认值：这样在调用时不传值则使用默认值；

![image-20200921151619748](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921151619748.png)

less:

![image-20200921151243396](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921151243396.png)

css:

![image-20200921151221281](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921151221281.png)

除了以上的函数，还有darken（加深颜色），average（取颜色平均值）等函数。

![image-20200921151922604](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921151922604.png)





**补充：**

在less中所有的数值都可以直接进行运算：

![image-20200921152127669](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921152127669.png)

@import可以将其他的less引入到当前的less中，这样做方便我们将css代码模块化，比如变量单独设置一个less，函数单独设置一个less，再将其引入项目的总的less中，这样也方便维护。

![image-20200921152212485](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921152212485.png)

sourceMap：

体现css和less文件间的对应关系，方便我们修改less代码

我们可以通过修改EasyLess的配置文件实现。通过该配置我们也可以实现压缩代码的功能。

![image-20200921152838811](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921152838811.png)

![image-20200921152946454](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921152946454.png)





**15：30** pause

**15：40** start

## 3.弹性盒

### 1.flex

flex是css中布局的另外一种手段，它主要用来代替float来实现页面的布局，

并且它可以使元素既有弹性，让元素随着页面大小的改变而改变。

通过display:flex将一个元素设置为（块级）弹性容器；

而弹性容器的子元素则是弹性元素（注意是子元素，而不是所有的后代元素）

弹性元素可以同时是弹性元素；

![image-20200921155230210](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921155230210.png)

弹性容器的属性：

![image-20200921155159520](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921155159520.png)

弹性元素的属性：

flex-grow

flex-shrink

默认值是0

![image-20200921155136340](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921155136340.png)

### 2.利用弹性盒实现导航条：

==练习==

![image-20200921160139833](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200921160139833.png)



**16：00**  pause

Day 04  结束 2020.09.21.进度：132p结束

# ==Day 05== 开始 2020.09.22  14：50

### 1.弹性容器中的布局（样式）：

flex的兼容性并不是很好，但是用在移动端没有问题，PC端需要考虑一些老版本的浏览器比如IE8等浏览器。

设置元素在弹性容器内是否自动换行：

![image-20200922145502198](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922145502198.png)

**设置如何分配主轴上的空白空间（可以用来使元素水平居中）**

![image-20200922145544116](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922145544116.png)

设置元素在辅轴上如何对齐：（可以用来使元素垂直居中）

![image-20200922145918372](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922145918372.png)

设置辅轴上空白空间的分布，属性设置和主轴一样

![image-20200922150043280](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922150043280.png)

align-self： 用来覆盖当前弹性元素上的align-items

![image-20200922150137026](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922150137026.png)



### 2.弹性元素上的布局（样式）：

增长系数，缩减系数，基础长度（一般不指定），简写属性

![image-20200922151051380](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922151051380.png)

order:决定弹性元素的排列顺序：

![image-20200922151028989](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922151028989.png)



### 3.==练习:淘宝移动端导航：==

![image-20200922152504186](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922152504186.png)

![image-20200922152516973](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922152516973.png)



### 4.像素：

css和物理像素之间的比值不是固定的，通过改变视口（viewport）的大小，可以改变css像素和物理像素之间的比值。

![image-20200922153511512](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922153511512.png)



### 5.手机的像素

移动端网页的视口是980css像素，不同设备的物理像素不一样，在图中的网站可以查询到一些设备的物理像素（分辨率）

![image-20200922154547463](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922154547463.png)

![image-20200922154722006](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922154722006.png)



### 6.完美视口：

编写移动端网页时，必须确保有一个比较合理的像素比，因此我们需要设置视口的大小，而每一款设备设备的最佳视口大小不一样，所以我们不同的设备需要设置不同的视口，但是这样显然是不现实的。

所以我们其实只需要将视口设置为device-width即可

结论：只要开发移动端网页，就先写上以下代码：

```html
<meta name="viewport" content="width=device-width,initial-scale=1.0">
```

![image-20200922155821989](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922155821989.png)



### 7.vw单位：

因为不同设备的完美视口大小不一，所以同样的css像素在不同的设备下的显示效果不一样，比如375px在iphone6 中是全屏，但是在i6plus中就会缺失一块，所以在移动端的开发中，我们不能再使用px作为长度单位了。

由此引出一个单位vw（viewport width)：

该单位表示的是视口的宽度，1vw=1%视口宽度，即100vw等于一个视口的宽度.

但是设计时不同元素在页面的比列不一样,我们要使用该单位还要对每一个元素的宽度进行计算,显得有些繁琐 (设计图是750px)

![image-20200922161819327](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922161819327.png)



### 8.vw适配:

根据1rem=1html 字体的大小,我们可以将html的字体大小设置为40px css像素(font-size: 5.3333)

~~(或者其他数值),则1rem =  40px ,根据之前计算的 1px = 0.1333333..vw==(当时是依据设计图是750px宽来进行运算的,是否适用于所有设计图?)==~~ 

答:换算公式: 100vw/750 * (设定的网页字体大小,教程中设置的是40px)

需要更改的话根据公式修改750(@total-width:2倍设计图或3倍设计图的宽度(1125)),40px就好,在less中定义变量:

![image-20200922165930856](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922165930856.png)

~~我们可以得到1rem = 5.33333vw~~

此时我们可以使用rem作为单位编写移动端网页:

如需要750px的宽度,则:750/40=18.75rem

此时我们的宽度就是:18.75*5.3333vw约为100vw 即全屏,这样我们在任何设备上看到的都是全屏.

(既然如此为什么不直接使用1px = 0.13333333vw 来进行换算(#🙄,则750px = 750*0.13333333约等于100vw,可能是方便整数乘除? 如果将字体大小设置为100px呢: font-size:13.333333vw ,1rem = 100px, 750px= 750/100 = 7.5rem 这样不是更方便运算么?🙄)



![image-20200922163121670](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922163121670.png)



## ==9.手机端网页练习:==!important

1. 注意中部菜单的布局

![image-20200922171330796](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922171330796.png)

## 响应式布局

通过响应式布局,我们可以使网页适用于不同窗口大小,这主要是使用媒体查询实现的

![image-20200922190434828](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922190434828.png)

**10.媒体查询:**

![image-20200922190334130](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922190334130.png)

**断点:**

![image-20200922191206346](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922191206346.png)



==11.练习:美图响应式导航条练习==

![image-20200922191401132](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922191401132.png)

1. 注意菜单图标的设置:及其动画的实现

   ![image-20200922192413529](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922192413529.png)

![image-20200922192403645](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20200922192403645.png)

2. 注意媒体查询的运用:
3. 注意导航栏最大宽度的设置.

Day 05 结束 2020.09.22 19:50 进度:148P 视频结束

接下来还需要将==练习==完成

还需要学习: JavaScript数据结构 ajax  bootstrap 框架 vue.js  node.js webpack 

![image-20210401203543576](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20210401203543576.png)