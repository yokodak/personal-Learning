# chrome开发者工具视频教程

> 📅：2021年7月25日
>
> ⌚：20点42分
>
> 📍 ：豪方花园
>
> 📝：之前看的章节包括快捷键，独立窗口，调整窗口位置等
>
> 📌

### 1.访问节点

![image-20210725204024288](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725204024288.png)

### 2.DOM调试

![image-20210725204807925](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725204807925.png)

需要结合访问dom使用，要自己写删除节点的代码（如将节点赋值给一个变量，然后再调用其父节点的removeChild方法执行删除）

### 3.css代码调试

注意盒模型，还有在浏览器本地修改CSS文件（之后会讲）

![image-20210725210746604](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725210746604.png)

### 4.快速面板可视化调试css

![image-20210725211630422](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725211630422.png)

![image-20210725211535992](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725211535992.png)

![image-20210725211752644](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725211752644.png)

![image-20210725211904205](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725211904205.png)

![image-20210725212156094](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725212156094.png)

> 👇一个生成css动画网站（animation.css)(似乎只能看效果 )

![image-20210725212238738](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725212238738.png)

### 5.console面板简介

`ctrl + shift + J` 直接呼出

![image-20210725212617512](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725212617512.png)

![image-20210725213241584](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725213241584.png)

### 6.console常用方法

#### 1.log,warn,error

（s%,字符串占位符）

![image-20210725213655798](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725213655798.png)

![image-20210725214036251](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725214036251.png)

#### 2.table

![image-20210725213941918](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725213941918.png)

#### 3.group

![image-20210725214154354](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725214154354.png)

#### 4.控制台输出样式（c%占位符）

![image-20210725214316809](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725214316809.png)

#### 5.计算代码执行时间

![image-20210725214806644](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725214806644.png)

#### 6，生成网络错误，断言

> 具体代码？

![image-20210725214945561](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725214945561.png)

console.assert

![image-20210725215036756](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725215036756.png)

### 7.调试JS代码

三种方式

![image-20210725223412296](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725223412296.png)

借助chrome开发者工具进行断点调试

![image-20210725223843837](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725223843837.png)

![image-20210725224834379](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725224834379.png)

### 8.使用snippets辅助调试

可以在snippets中导入一些方法库，工具库等，保存到浏览器中，这样方便我们调试时调用（可以直接在console控制台使用）

![image-20210725225616867](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725225616867.png)

### 9.使用devtools编辑本地源文件

将代码导入到工作区后，修改代码相当于在本地IDE直接修改源代码

![image-20210725230313547](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725230313547.png)

### 10.网络面板简介

![image-20210725230647578](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725230647578.png)

#### 1.过滤文件

![image-20210725231300214](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725231300214.png)

![image-20210725232033583](C:/Users/yokoda/AppData/Roaming/Typora/typora-user-images/image-20210725232033583.png)

#### 2.根据时间段过滤请求

![image-20210725231537904](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725231537904.png)

#### 3.查看请求（响应）的具体内容

![image-20210725232235323](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725232235323.png)

#### 4.设置要显示的信息

![image-20210725232347396](C:/Users/yokoda/AppData/Roaming/Typora/typora-user-images/image-20210725232347396.png)

### 11.使用waterfall分析性能

![image-20210725232744940](https://gitee.com/yaorunhua/runbed/raw/master/img/yokoda/image-20210725232744940.png)

⌚ 23点28分 2021年7月25日暂停 进度 第五章 网络面板结束