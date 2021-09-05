# CSS 入门:基础知识梳理

🙎‍♂️：润华 

🙎‍♂️:   一帆

### 1.基础概念

- 什么是 **CSS**

  `CSS  ` 即 层叠样式表 ( **C**ascading **S**tyle **S**heets )

  

  ![CSS-shade](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/CSS-shade.svg)

  ​															    

  <center>( 维基百科<a href = 'https://zh.wikipedia.org/wiki/%E5%B1%82%E5%8F%A0%E6%A0%B7%E5%BC%8F%E8%A1%A8'><i> 层叠样式表</i>，</a> 图片作者：<a href = 'https://en.wikipedia.org/wiki/User:Fenring'><i>Fenring</i></a> )</center>

  `HTML` 用于定义内容的结构和语义，`CSS `用于设计风格和布局。

  比如，您可以使用 `CSS` 来更改内容的字体、颜色、大小、间距，将内容分为多列，或者添加动画及其他的装饰效果。( [MDN](https://developer.mozilla.org/zh-CN/docs/Learn/CSS) )

  

- **CSS** 主要目标

  除了对网页进行 装饰， `CSS` 还有一个主要目标就是 **将内容与显示分离**。

   CSS 出现之前，如果需要为 `HTML `元素添加样式样式，那么往往需要用到其他的样式元素如 `<font>`，`<i>` 等。

  比如下面这个[例子](https://zh.wikipedia.org/wiki/%E5%B1%82%E5%8F%A0%E6%A0%B7%E5%BC%8F%E8%A1%A8#%E6%A6%82%E8%BF%B0)，我们想要将 **二级标题** `h2` 的字体变为  ***斜体*** ， <span style = 'color:green'>**绿色**</span>，仅一个 `<h2>`元素是不能实现的，因为它只定义了结构上的信息。

  那么通过 `HTML` 提供的 `<font>` 和 `<i>` 元素，我们可以这样实现：

  ```html
  <h2><font color="green"><i>不使用CSS</i></font></h2>
  ```

  <h2><font color="green"><i>不使用CSS</i></font></h2>

  这样做虽然能达到我们想要的效果，但是有些缺点：

  - 使 `HTML` 元素变得复杂，如果要实现复杂的样式，需要在单一元素上添加大量用于显示的元素
  - 不利于维护，修改样式需要找到具体的元素才能修改，结构和表现耦合在一起
  - 样式无法复用，实现相同的显示效果需要编写大量重复的代码

  使用就能 `CSS` 能很好地解决这些问题，让 `HTML`只表达文档的 **结构**，而 `CSS`表达文档的 **样式**。

  同样是上面的例子，我们使用 `CSS` 来实现:

```html
<h2>
    使用CSS
</h2>
```


  ```css
  h2 {
      color:green;
      font-style:italic;
  }
  ```

  效果如下：

  ![image-20210902153043558](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210902153043558.png)

  

  [▶ 在线演示](https://jsbin.com/vamavubono/1/edit?html,css,output)

  这样显示就和内容分开了，维护起来更加容易，文档的结构也清晰许多，并且样式代码能多次复用

- **CSS** 语法

  了解 `CSS` 的强大易用以后，现在我们可以自己写一个 `CSS` 文件了。

  `CSS` 的语法规则非常简单，不用担心写错，即使在编写 `CSS` 的过程中出现语法错误，也不会导致文档无法显示，对于不符合规则的 `CSS` 语句，浏览器会选择忽略，继续渲染下一条样式。

  `CSS` 由多组 **规则** 组成，一条常见的规则如下：

  

  ![image-20210902160924081](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210902160924081.png)

  

  

  - 一条 规则 由 **选择器（Selector）** ，大括号，和 **声明** 组成。

  - 一个规则可以包含多个声明；每条声明都应该包裹在 选择器 后的 大括号内。声明之间用 `;` 相隔。

  - 一条声明内包括 **属性** 和 **属性值** ，属性和属性值用 `:` 分隔。一些属性可能有多个属性值。
  - `CSS`的注释用 `/* */`包裹。
  - 如果要为多个选择器设置相同的样式，那么选择器之间用逗号`,`相隔， 见[下例](https://jsbin.com/rubakoyuti/1/edit?html,css,output)

  下面这条规则表示 将文档中的 **所有** `p` 元素 和  `div` 元素的 ：

  宽度设为：`80px`;

  高度设为：`80px`;

  **文字颜色** 设为 ：<span style = 'color:green'>绿色</span>;

  背景色 设置为 ： <span style = 'background-color:black;color:white;width:40px;'>白色</span> ;

  **边框**设置为 ： `1px` , 实线，<span style = 'color:green'>绿色</span>;

  可以看出 `CSS` 的属性还是比较容易理解的，比较直白，遇到生疏的属性查阅后记下来就好了。

  ```css
  p,div {
      width: 80px;
      height: 80px;
      color: green;
      background-color: white;
      border: 1px solid green;
    }
  ```

  效果如下：

  ![image-20210902162511122](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210902162511122.png)

  

  [▶在线演示](https://jsbin.com/rubakoyuti/1/edit?html,css,output)

  `CSS` 的 属性非常多，需要大家在学习的过程中不断积累，目前掌握一些常用的属性即可。

- **CSS** 的层叠概念

  **层叠**（ Cascading  *[kæsˈkeɪdɪŋ]* ） 是什么意思呢 ?

  根据 [知乎问答](https://www.zhihu.com/question/20077745) 答主 [华南虎](https://www.zhihu.com/people/xander-young) 摘抄的 [论文 ](https://www.wiumlie.no/2006/phd/#ch-introduction)片段（[Cascading Style Sheets](https://www.wiumlie.no/2006/phd/#ch-introduction) - Håkon Wium Lie）：

  > [Håkon Wium Lie](https://zh.wikipedia.org/wiki/%E5%93%88%E8%82%AF%C2%B7%E7%BB%B4%E5%A7%86%C2%B7%E8%8E%B1)  - 哈肯·维姆·莱 ，CSS 开发者之一，以于1994年提出的 CSS 概念而闻名 ( [维基百科](https://zh.wikipedia.org/wiki/%E5%93%88%E8%82%AF%C2%B7%E7%BB%B4%E5%A7%86%C2%B7%E8%8E%B1) )

  >  The process of combining several style sheets – and resolving conflicts if they occur – is known as cascading.  
  >
  > 组合多个样式表的过程 —— 如果发生冲突，解决冲突 ——被称为层叠。

  样式引入的顺序 , **选择器权重**，都会决定**样式的优先级**，优先级高的样式会覆盖优先级低的样式，`CSS` 根据样式的优先层级，对多个样式进行组合，最后应用样式，这样的处理方式就是**层叠**。

  关于 **选择器** 和 **样式的优先级** 会在之后讲解。如果想要先了解,可以参见  [MDN-CSS选择器](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Selectors) ,  [MDN-优先级是如何计算的](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Specificity#%E4%BC%98%E5%85%88%E7%BA%A7%E6%98%AF%E5%A6%82%E4%BD%95%E8%AE%A1%E7%AE%97%E7%9A%84%EF%BC%9F)

### 2.如何使用 CSS 

写完 `CSS` ，需要将其应用到文档才能生效，引入`CSS` 的方式有很多种，可以将`CSS`以文件形式引入，也可以在`HTML`中使用 `<style>` 标签引入，还可以直接将其 **内联** 到 `HTML` 元素中。下面将介绍引入 `CSS` 的几种方式。

#### 1.引入 `CSS` 的几种方式

1. 通过`<link>` 元素在 `HTML` 的 `head` 内引入**外部** `CSS` 文件

   ```html
   <link rel="stylesheet" href="https://www.w3school.com.cn/html/csstest1.css"/ >
   ```

   > `csstest1.css`的 [文件](https://www.w3school.com.cn/html/csstest1.css) 中，定义了 一条规则，将页面的 `div`元素背景色都设置为 黑色

2. 在`HTML `的`<style>` 标签中书写 **内部样式**，只对当前页面生效

   ```html
   <style>
   div {
       width: 80px;
       height: 80px;
       background-color: red;
     }
   </style>
   ```

3. 在 `HTML` 元素的 `style` 属性中编写 **内联样式**，只对当前元素生效, **权重高,**仅次于`!important`修饰符

   ```html
   <div style="background-color: green;"></div>
   ```

这三种方式 **内联样式** 的优先级最高, 所谓 *近水楼台先得月*

当对元素应用样式产生冲突(对同一个元素由多个声明)时，优先级高的样式会将优先级低的样式覆盖。不过,样式的优先级由选择器的 **权重 **决定, 选择器 权重 相同的情况下,才会考虑 样式 在文档中的 顺序 

下面先对 **选择器** 作介绍

#### 2.CSS 选择器

- 选择器种类

  - 通配符

  - 元素选择器
  - 类选择器
  - id 选择器
  - 伪类选择器
  - 伪元素选择器
  - 标签属性选择器
  - 关系选择器

- 样式的继承

- 选择器权重

#### 3.浏览器的默认样式

通过[上面](#1.引入 的几种方式) 所提到几种方式引入的样式都称为`用户样式`，除了 用户样式，浏览器内置了一种默认样式，称为`用户代理样式（user agent stylesheet）` ，以下都称为 **默认样式**（浏览器也被称为 `用户代理`）

- 默认样式的作用：

  默认样式样式保证了网页的基本排版，当元素没有指定的样式时，浏览器会按照默认样式来渲染元素。

  比如，一级标题通常是大号加粗字体且独占一行，二级标题也独占一行但字号会小一点，还比如列表的样式，在每项前添加圆点，以表示这些文字不是独立存在的。

  

  ![image-20210903112901867](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210903112901867.png)

  

  <center><i>chrome浏览器一级标题的默认样式(可以在开发者工具中查看)</i></center

  

  ![image-20210903112939736](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210903112939736.png)

  ![image-20210903113036569](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210903113036569.png)

  

  <center><i>chrome浏览器列表的默认样式</i></center>

  [▶在线演示](https://jsbin.com/lupihahadu/1/edit?html,css,output)

  浏览器的默认样式对这些都有预设，如果用户不满意，可以自己写样式覆盖掉。

  [👉查看 webkit 内核浏览器默认样式](http://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css)

- 默认样式带来的问题：

  不同的浏览器的默认样式不一样,甚至同一个浏览器,版本不同,默认样式也会有区别,所以同一个网页在不同的浏览器中会呈现出不同的效果

  > ( 并且每个浏览器对 [CSS规范](https://www.w3.org/Style/CSS/current-work.en.html) 的实现有差异, 也会导致网页的表现不一样, 通常需要解决浏览器的 兼容性问题  [MDN-常见的跨浏览器问题](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/HTML_and_CSS#%E5%B8%B8%E8%A7%81%E7%9A%84%E8%B7%A8%E6%B5%8F%E8%A7%88%E5%99%A8%E9%97%AE%E9%A2%98)  对这方面有一些说明,可参考 )

  并且,有时候浏览器的默认样式,我们不满意,比如 `chrome` 的默认样式会给`body` 元素添加 `8px` 的外边距:

  

  ![image-20210903115432884](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210903115432884.png)

  

- 消除默认样式：

  可以针对某一个样式,自己写一条规则覆盖掉默认样式

  引入 [normalize.css](https://github.com/necolas/normalize.css/blob/master/normalize.css) 对样式进行统一

#### 4.项目中对 ` CSS` 的处理

- 预处理器 如 [less](https://less.bootcss.com/)  

  对 CSS 进行了一些扩展, 使用 [嵌套](https://less.bootcss.com/#%E5%B5%8C%E5%A5%97%EF%BC%88nesting%EF%BC%89) 的方式书写代码,让代码更加简洁,还提供了 **变量** 和 **函数** 等其他功能

### 3. CSS 基础内容

#### 1.盒模型

在 `CSS` 中，所有的元素都被一个个的“盒子（box）”包围着 ( [MDN-盒模型](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/The_box_model) )

`CSS` 中将盒子分为 `块级盒子`和`内联盒子`,他们在页面上的表现不一样

- 块级盒子( `display:block` ) 有以下特点

  - 默认宽度撑满父元素  [▶在线演示](https://jsbin.com/resupowehi/1/edit?html,css,output)
  - 独占一行显示 [▶在线演示](https://jsbin.com/yijekuhito/1/edit?html,css,output)
  - 设置宽(`width`) 高(`height `)有效
  - 内边距（`padding`）, 外边距（`margin`） 和 边框（`border`） 会将其他元素从当前盒子周围“推开”

- 内联盒子( `display:inline` ) 有以下特点

  - 不会独占一行
  - 设置宽(`width`) 高(`height `)**无效**
  - 垂直方向的内边距、外边距以及边框 会被应用但是不会推开其他盒子 [▶在线演示](https://jsbin.com/rulonefate/1/edit?html,css,output)
  - 水平方向的内边距、外边距以及边框会被应用且会把其他盒子推开。

  通过 `CSS ` 的 `display` 属性, 可以改变盒子的**外部**显示类型( 在其他盒子中怎样显示  )

  将  `display` 设置为 `inline-block` 可以让盒子不独占一行, 同时宽高的设置也有效,相当于结合了块级盒子和内联盒子的特点.

- 盒模型

  **标准盒模型**,盒子的宽和高 **不包括** 外边距, 边框, 内边距

  页面上渲染的盒子的大小包括 :内容大小(也就是宽高属性设置的大小), 内边距,边框,外边距

  以一个块级盒子为例  [▶在线演示](https://jsbin.com/rutowavida/1/edit?html,css,output)

  ```css
  div {
    display:block;
    height:100px;
    width:100px;
    background-color: black;
    color:white;
    border: 2px solid red;
    margin:20px;
    padding:20px;
  }
  ```

  ![image-20210903175447626](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210903175447626.png)

  

  <center><i>标准盒模型</i></center>

  

  **替代(IE)盒模型** 盒子的宽和高 **包括** 外边距, 边框, 内边距,实际**盒子内容**的宽高还要减去外边距, 边框, 内边距

  目前绝大多数浏览器默认采用的是 **标准盒模型** (`box-sizing : content-box;`)

  IE浏览器 默认使用替代盒模型，没有可用的机制来切换。（IE8+ 支持使用`box-sizing` 进行切换 -  [MDN](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/The_box_model)) 

  将 `box-sizing` 属性设置为 `border-box`可以将盒子模型变为 替代盒模型

   [▶在线演示](https://jsbin.com/rutowavida/1/edit?html,css,output)

  ![image-20210903180837691](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210903180837691.png)

  <center><i>替代盒模型</i></center>

  

#### 2.文档流

- 正常布局流

  浏览器默认的布局方式，页面上的元素按照 `HTML` 文档中的先后顺序出现

  [▶在线演示](https://jsbin.com/jadagubecu/1/edit?html,css,output)

  当正常流布局不能满足我们的要求时，我们可以通过一些 **布局技术**  来实现想要的效果，比如：

  - 设置 `display` 属性为 `block`, `inline`或`inline-block`来改变布局
  - 开启浮动 `float`
  - `flex` 布局
  - `grid` 布局 （见 [MDN-网格](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Grids) ）
  - 定位

  其中 开启浮动 和 绝对定位 会使元素 脱离文档流，也就是说它所占用的空间会被忽略，其他元素在布局时不会考虑它，关于脱离文档流，可以参考 [知乎问答-脱离文档流](https://www.zhihu.com/question/24529373)  

  `float ` 浮动及清除浮动可以参见 [MDN-float](https://developer.mozilla.org/zh-CN/docs/Web/CSS/float), 下面主要对 `flex`布局 和 `定位`作介绍。

#### 3.flex 弹性布局

弹性盒子布局：一维页面布局，弹性布局使得页面布局变得更加容易，如居中子元素，等量分配子项空间等。

- 弹性容器(盒子)

  通过将（块级）盒子的 `display ` 属性设置为 `flex` , 可以将盒子变为弹性容器。

  > 假如你想设置行内元素为 flexible box，也可以置 [`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display) 属性的值为 `inline-flex` (--[MDN](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox#%E6%8C%87%E5%AE%9A%E5%85%83%E7%B4%A0%E7%9A%84%E5%B8%83%E5%B1%80%E4%B8%BA_flexible))

  弹性容器具有以下几个特点：

  - 子元素自动成为弹性项（`flex item` ） 
  - 容器存在两根轴，主轴 ( `main axis`) 和 交叉轴 （`cross axis` ), 两轴相互垂直。
  - 弹性项默认沿主轴排列，主轴默认为水平方向。

  [▶在线演示](https://jsbin.com/qeyuhakoqa/1/edit?html,css,output)

  通过设置弹性容器的属性，可以决定弹性容器中弹性项的排列方式

  1. 弹性项排列的方向（即主轴的方向）`flex-direction`

     - `row`（默认值）：主轴为水平方向，从左至右
     - `row-reverse`：主轴为水平方向，从右至左。
     - `column`：主轴为垂直方向，从上到下。
     - `column-reverse`：主轴为垂直方向，从下至上。

     [▶在线演示](https://jsbin.com/jitanovoro/1/edit?html,css,output)

  2. 弹性项是否换行展示

     默认情况下，项目都排列在一条轴线上，如果一条轴线放不下，那么通过`flex-wrap`属性来决定是否换行显示。

     - `nowrap`（默认）：不换行。弹性项的大小会被压缩，根据项目原本的大小，按比例分配空间  [▶在线演示](https://jsbin.com/ripugobewo/1/edit?html,css,output)
     - `wrap`：换行，从上到下排列。
     - `wrap-reverse`：换行，从下至上排列。

  3. 弹性项对齐方式 & 空间分布  （ [阮一峰-Flex布局教程：语法篇](https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?__cf_chl_managed_tk__=pmd_q9NITzCo6yNMydZpx3XMFEP9z7KTI._WNgpTZ6.S8Pc-1630834607-0-gqNtZGzNAtCjcnBszQkl) ）

     `justify-content`属性定义了项目在**主轴**上的对齐方式。

     - `flex-start`（默认值）：左对齐
     - `flex-end`：右对齐
     - `center`： 居中 
     - `space-between`：两端对齐，项目之间的间隔都相等。
     - `space-around`：每个项目两侧的间隔相等。

     [▶ 在线演示](https://jsbin.com/weruduqepe/1/edit?html,css,output)

     `align-items`属性定义项目在**交叉轴**（与主轴垂直）上如何对齐。

     - `stretch`（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。

     - `flex-start`：交叉轴的起点对齐。

     - `flex-end`：交叉轴的终点对齐。

     - `center`：交叉轴的中点对齐。[▶ 在线演示](https://jsbin.com/bovapocipu/1/edit?html,css,output)

     - `baseline`: 项目的第一行文字的基线对齐。

       

     ![bg2015071011](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/bg2015071011.png)

     <center><i>交叉轴对齐方式 - <a href ='https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?__cf_chl_managed_tk__=pmd_q9NITzCo6yNMydZpx3XMFEP9z7KTI._WNgpTZ6.S8Pc-1630834607-0-gqNtZGzNAtCjcnBszQkl'>阮一峰-Flex布局教程：语法篇</a></i></center>


- 弹性项

  



#### 4.定位

#### 5.响应式

#### 6.视口

#### 7.单位

### 4.CSS如何运作



![render-1](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/render-1.png)





![render-5](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/render-5.png)



### 5.CSS3 新特性

- 动画
- 3D
- 阴影
- 计算,css变量

