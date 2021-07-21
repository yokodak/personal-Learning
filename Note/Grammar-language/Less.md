# Less

> 2021.07.12 🤦‍♂️摘自 👉[学习Less-看这篇就够了](https://juejin.cn/post/6844903520441729037#heading-0)

### 基本语法：

#### 变量：

- **值变量：**

  ```less
  @color:red;
  .box2 {
    color: @color;
  }
  ```

- **选择器变量**

  ```less
  @selector:#box;
  @{selector} { //注意选择器变量名需要用大括号包裹，第一个大括号结束后需要有个空格
    color: #706b6b;
  }
  ```

- **URL变量**

  (其实类似于vue.config.js的别名)

  ```less
  @images: ' ../img'; //需要加引号
  body {
    background: url('@{images}/bg.png');
  }
  ```

- **属性变量**

  ```less
  @bgc: background-color;
  
  \#box1 {
  
   	@{bgc}:red;
  
  }
  ```

- **声明变量**

  ```less
  @config:{
    @{bgc}:red;
    width: 100px;
    height: 100px;
  }
  .box {
    @config()
  }
  ```

- **关于变量的作用域：就近原则**👇

  ```less
  /* Less */
  @var: @a;
  @a: 100%;
  #wrap {
    width: @var;
    @a: 9%;
  }
  
  /* 生成的 CSS */
  #wrap {
    width: 9%;
  }
  
  ```

- **变量定义变量**

  ```less
  /* Less */
  @h:  "helloworld";
  @var:    "h";
  #wrap::after{
    content: @@var; //将@var替换为其值helloworld;
  }
  /* 生成的 CSS */
  #wrap::after{
    content: "helloworld";
  }
  ```

  

#### 变量的运算：

支持像素(px)的运算，16进制颜色的运算等

- 加减法时 以第一个数据的单位为基准

- 乘除法时 注意单位一定要统一

  ```less
  @BoxHeight:100px;
  @BoxColor:#222;
  .box{
    height: @BoxHeight - 20px;
    width: @BoxHeight * 2;
    @bgc: @BoxColor - #111;
    color: @BoxColor * 2
  }
  ```


#### 嵌套

&表示的父级（上一级）选择器

```less
.header { 
  &::after { //&表示父级选择器，即此例中的.header
    content:'helloLess!';
  }
  .title{ //嵌套，表示header的子级
    color: #222;
  }
  &.footer{ //注意和上面👆区分，这里的footer类是和header同级
    color: #706b6b;
  }
  &_body { //不进行嵌套
    margin-top: 20px;
  }
}
/* 生成的 CSS */
.header::after{
  content:"helloLess!";
}
.header .title{ //嵌套了，节点的class依然是title,不过是嵌套在#header内的，如👇图
  font-weight:bold;
}
.header.footer {
  color: #706b6b;
}
.header_body{//没有嵌套
   margin-top: 20px;
}
```

> <img src="https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210712170009538.png" alt="image-20210712170009538" style="zoom:150%;" />

- **媒体查询的嵌套**

  ```less
  //css
  @media screen and (maxwidth:768px){
    body {
        width:100px; 
    }
  }
  @media print and (maxwidth:768px){
    body {
        width:200px; 
    }
  }
  //less
    body {
         @media screen{
          @media (max-width:768px){
            width:100px;
          }
      }
         @media print{
          @media (max-width:768px){
            width:200px;
          }
      }
  }
  ```


#### 混合方法mixin

方便对样式进行复用

```less
/* Less */
.card() {
    background: #f6f6f6;
    box-shadow: 0 1px 2px rgba(151, 151, 151, .58);
}
#wrap{
  .card();
}

/* 生成的 CSS */
#wrap{
  background: #f6f6f6;
  box-shadow: 0 1px 2px rgba(151, 151, 151, .58);
}

```

混合方法可以设置默认参数，在使用时，如果不传入参数，则会使用默认参数

- @arguments 表示全部参数
- 默认参数必须带单位

```less
/* Less */
.border(@a:10px,@b:50px,@c:30px,@color:#000){
    border:solid 1px @color;
    box-shadow: @arguments;//指代的是 全部参数
}
#wrap{
    .border(0px);
}
/*css*/
#wrap{
    border:solid 1px #000;
    box-shadow: 0px 50px 30px #000;
}
```

