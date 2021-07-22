# TypeScript视频学习笔记：

> 📺视频资源：TypeScript从入门到精通视频教程-2020年新版
>
> 🔗链接： https://www.bilibili.com/video/BV1qV41167VD 
>
> 📅创建时间：2020.10.15 15：00
>
> ⌚ 2021年7月21日 15点37分 重写
>
> 📍学校寝室 ——> 公司

Day 01  2020.10.15 15：00开始

> 📌先看官方文档的介绍
>
> - TypeScript offers **all** of JavaScript’s features, and an **additional layer** on top of these: TypeScript’s **type system.**
>
> - The main benefit of TypeScript is that it can highlight unexpected behavior in your code, **lowering the chance of bugs.**
>
> - Typescript支持Javascript的所有特性, 并进行了一层扩展: Typescript的类型系统.
> - 使用Typescript的主要好处是它能突出代码中的意外表现 , 降低代码出现的几率.

因为JS是一门弱类型的编程语言,各种数据类型之间往往会进行类型转换,这会带来一些问题,比如现在写了一个方法,期望参数是数字类型,但是调用该方法的人并不知情,于是传入了一个数组,虽然参数类型出错,但是JS在编译时并不会报错, 当程序运行时发现结果出错, 再次检查时才发现是类型错误

使用TS就能很好的避免这样的情况,根据TS的类型注解, 在声明一个函数的参数(或定义一个变量,属性)时,可以为其指明数据类型, 当传入的实参类型不符合指定类型时,TS就会提示参数错误,如👇

```typescript
function sum(a:number,b:number) {  //将参数a,b都注解为number类型
  return a + b;
}
sum(1,'hello') 
```

此时TS会报错

![image-20210722101638384](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210722101638384.png)

这样就能将运行时才发现的错误,提前到编译前就暴露,提高了代码的健壮性,减少了bug🐛出现的概率

除此之外,TS还对JS有其他的扩展,比如接口、泛型、枚举类型等，我们可以再一点点了解😃

### 1.环境搭建：

##### 安装TypeScript：

使用`npm install typescript -g ` 全局安装 

然后写一段`TS`代码👇

```typescript
const saying:string = 'hello TS';
console.log(saying);
```

调用 `tsc` 命令将 `ts` 文件转换为 `js`

```powershell
PS D:\Typescript> tsc exercise.ts 
```

转换后的`js` 如下

```javascript
var saying = 'hello TS';
console.log(saying);
```

然后使用`node`运行程序

```powershell
PS D:\Typescript> node exercise.js
hello TS
```

可以看到我们写的程序完美地执行啦👍

不过如果每次都要编译后再执就过于繁琐了，为此可以通过安装`ts-node`来执行ts文件

使用命令 `npm install ts-node -g`安装即可

> 📍 一般在项目开发时会引用打包工具如webpack来解析ts文件，不过我们只是为了学习，没必要专门创建一个工程，所以借助 `ts-node`来编译执行ts文件就可以了

然后就能用 `ts-node`命令执行ts文件啦👇

```powershell
PS D:\Typescript> ts-node exercise.ts
hello TS
```



### 2.基础语法

##### 基础类型：

JS中的数据类型 `number`,`string`,`boolean`,`symbol`,`undefined`,`null`以及`object`在TS中都有相对应的数据类型

> 📍注意,TS区分大小写字符,这里的string是小写的，和String是有区别的,根据官方手册的说法👇
>
> The type names `String`, `Number`, and `Boolean` (starting with capital letters) are legal, but refer to some special built-in types that will very rarely appear in your code，*Always* use `string`, `number`, or `boolean` for types.  [🔗](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#the-primitives-string-number-and-boolean)
>
> 这些大写开头的类型虽然是合法的，但是指的是一些特殊的内置类型，我们很少用到，所以在注解类型时，都使用**小写字母开头**的单词

除了这些数据类型，TS还提供了以下几种类型

- any

  如果一个值的类型为any时，则表示它可以是任意类型，不论对它赋什么值，TS都不会报错，如果你没有声明一个值的类型，TS也无法对它进行推断的话，编译器会将其默认为any类型.

  ```typescript
  let d : any = 4;
  d = 'four';
  d = {forth:'four'};
  //不会报错
  ```

- void

   用于标识方法返回值的类型，表示该方法没有返回值。[🔗菜鸟教程](https://www.runoob.com/typescript/ts-type.html)

- never

  表示永远不会出现的值

- enum

  枚举类型于声明**一组**命名的**常数**，当一个变量有几种可能的取值时，可以将它定义为枚举类型 [🔗百度百科](https://baike.baidu.com/item/%E6%9E%9A%E4%B8%BE%E7%B1%BB%E5%9E%8B/2978296?fr=aladdin)

  使用枚举类型可以增强程序的可读性

  ```typescript
  enum Day {Monday,Tuesday,Wednesday}
  console.log(Day.Monday,Day.Tuesday,Day.Wednesday)
  //输出0 1 2 
  ```

  枚举成员的值默认从 `0`开始，在定义时可以指定枚举成员的值，（允许枚举值相同）通过枚举的值，也能访问枚举名

  ```typescript
  enum Day {Monday = 1,Tuesday,Wednesday}
  console.log(Day[2])
  //输出Tuesday
  ```

类：

![image-20201015161120305](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015161120305.png)



##### 类型注解

type annotation 

在声明一个变量时，可以为该变量添加一个注解 ，格式为`变量 : 类型`（如：`let count : number`；）

类型注解是可选的，TS会根据你对变量的赋值自动推断变量的类型（type inference ，类型推断），所以不是总需要写类型注解，不过对于一些复杂情况，还是尽量写上类型注解吧😗

- `普通变量`

  ```typescript
  const num : number = 1;
  const sayHi: string = 'hello';
  let result: boolean = false;
  let god : any;
  let what : undefined;
  let none : null;
  let moon : symbol = Symbol("moon");
  ```

- `普通对象`

  ```typescript
  const dog: {
    name:string;
    age:number
  } = { //初始化的对象，属性名只能为name或age，属性不能缺失
    name:"buddy", //name的类型必须为string
    age:2 //age的类型必须为number
  }
  ```

- `数组`

  ```typescript
  let cats : string [] =['dora','kitty'] //数组内的元素只能为string类型
  ```

- `参数注解`

  TS也支持为方法的参数及其返回值添加类型注解

  ```typescript
  // Parameter type annotation
  function greet(name: string) {
    console.log("Hello, " + name.toUpperCase());
  }
  //当传入非string类型的参数时，TS会提示参数类型错误
  ```

  并且，TS还会自动检查传入参数的个数是否正确，当参数个数不符合时，也会报错。

- `返回值注解`

  ```typescript
  function getFavoriteNumber(): number {
    return 88;
  }
  ```

**16：30**  pause

**18：30**  start







死循环的函数注解：

![image-20201015185003343](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015185003343.png)

![image-20201015185018872](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015185018872.png)

如果函数的参数是一个对象，而我们需要对象的属性是某个特定的类型时：不能直接在属性后进行注解，而是要将对象复制一份，然后在复制的对象里的属性后进行注解。这样TS也能进行类型推断：

![image-20201015185344127](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015185344127.png)

![image-20201015185425118](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015185425118.png)

### 5.数组类型的注解：

单一类型的数组注解：

![image-20201015185936341](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015185936341.png)

多种数据类型的数组注解：

![image-20201015190527654](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015190527654.png)

![image-20201015190834044](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015190834044.png)

数组元素是对象的注解：

![image-20201015190620834](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015190620834.png)

### 6.元组的使用和类型约束：

 一般只在数据源是`CVS`这种文件的时候，会使用元组。可以把元组看成数组的一个加强，它可以更好的控制或者说规范里边的类型。 

当我们要求数组里的元素安装顺序依次是某些类型时，对数组的注解就难以做到。（即使顺序调换，TS也不会报错）

![image-20201015191702548](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015191702548.png)

这个时候我们可以使用元组，下面的代码是一个元组，对它的注解要求他的第一个和第二个元素必须是string类型，第三个元素是number类型，如果在对应的位置没有传入相同类型的值，那么TS编译器会报错。

```js
const xiaojiejie: [string, string, number] = ["dajiao", "teacher", 28];
```

数组里是元组的注解：

![image-20201015191538642](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015191538642.png)

**19:30**  pause

### 7.接口：Interface

**定义一个接口**：

![image-20201015203103114](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015203103114.png)

 如果我们有一个对象是该接口类型，那么必须包含对应的属性和方法：（ 可选值除外）

一个对象：

![image-20201015203132162](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015203132162.png)

![image-20201015203254536](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015203254536.png)

**接口的可选值：**

![image-20201015203413706](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015203413706.png)

![image-20201015203514988](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015203514988.png)

### 8.（续）接口：Interface

接口内还可以定义方法和一个可选的属性

![image-20201015204525395](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015204525395.png)

![image-20201015205104775](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015205104775.png)

接口不仅能限制对象，也能限制类：

下面代码表示XiaoJieJie这个类，受到Girl这个接口的约束，它必须实现接口内的必选属性。否则会报错。

![image-20201015204835606](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015204835606.png)

接口的继承：

Teacher继承了Girl所拥有的所有属性，且也有自己定义的方法。

![image-20201015204640236](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015204640236.png)

### 9.类的概念和使用：

定义一个类：

![image-20201015205756097](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015205756097.png)

类的继承：

使用super关键字可以对父类的方法进行扩展：

![image-20201015205939521](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015205939521.png)

![image-20201015210041800](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015210041800.png)

### 10.类的访问类型：

public  公有属性 ：类外和类内部都可以访问

private 私有属性：只能在类的内部进行访问，继承的子类也不能访问，类的实例也不能进行访问。

![image-20201015210545226](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015210545226.png)

![image-20201015210626528](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015210626528.png)

![image-20201015213935596](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015213935596.png)

protected：受保护的属性：

![image-20201015210939216](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015210939216.png)

### 11.类的构造函数：

方便传递参数为类的实例的属性赋值

![image-20201015211445602](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015211445602.png)

上面的代码可以简化为：

![image-20201015211543012](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015211543012.png)

子类的构造函数：

子类必须使用super关键字才能使用构造函数，即使父类不写构造函数（不是没有，不写时默认构造函数为空Constructor（））也必须使用，当父类有构造函数时必须向super内传递参数。

![image-20201015211919703](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015211919703.png)

![image-20201015211942827](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015211942827.png)

测试：

![image-20201015212034505](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015212034505.png)

![image-20201015212053592](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015212053592.png)

### 12.类的setter和getter：

private虽然让数据得到了很好的保护，但是当我们将其设置为私有时，即使是该类的实例也不能访问到该属性。

![image-20201015213935596](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015213935596.png)

为了让类的实例也能访问到私有属性，TS提供了get和set方法，使我能够通过操作这两个方法实现对私有属性的访问：

除此之外我们还能在get和set方法中对属性进行修改等操作

![image-20201015214407373](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015214407373.png)

当我们对实例的属性进行赋值时，调用的是set方法，当我们直接

使用对象.属性进行访问时调用的是get方法

![image-20201015215338057](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015215338057.png)

![image-20201015215419600](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015215419600.png)

这样我们既可以访问到私有属性，数据的安全性也提高了。

### 13.static关键字，静态属性：

不用实例化一个对象也能直接通过类调用该方法（访问该属性）

![image-20201015215750373](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015215750373.png)

### 14.只读属性和抽象类：

只读属性：在属性名前添加read-only关键字，设置该属性是只读属性，不允许修改

![image-20201015220038129](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015220038129.png)

抽象类：

可以让每一个类中都包含一个相同的函数，但是每一个函数的实现又有所不同

![image-20201015220847272](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015220847272.png)

继承了抽象类的子类必须实现抽象方法：

![image-20201015221022185](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015221022185.png)

### 15.TS的配置文件：tsconfig.json

设置TS如何编译JS文件：

webpack配置：https://mp.weixin.qq.com/s/wnL1l-ERjTDykWM76l4Ajw

具体配置解释：

https://www.tslang.cn/docs/handbook/compiler-options.html

![image-20201015222317079](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015222317079.png)

#### ==NullCheck配置项不是很清楚==

![image-20201015222339346](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015222339346.png)

![image-20201015222940478](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015222940478.png)

![image-20201015223123993](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015223123993.png)

![image-20201015222840207](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015222840207.png)

### 16.联合类型和类型保护（守护）：

创建两个接口：

![image-20201015223916605](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015223916605.png)

#### 联合类型：

一个属性可能是多个类型的数据：

![image-20201015224030254](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015224030254.png)

因为不知道animal是什么类型，所以如果直接调用animal.say（）会报错，因为animal不一定是waiter类型，这个是时候就需要类型保护来判断类型，再进行不同的处理。

#### 类型保护：

根据不同的类型选择不同的处理方式：

###### 类型断言：

![image-20201015224305052](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015224305052.png)

###### 使用in判断：

![image-20201015224350517](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015224350517.png)

###### 使用typeof判断：

![image-20201015224944747](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015224944747.png)

###### 使用instance of判断：

![image-20201015225129037](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015225129037.png)

Day 01 结束：2020.10.15 22：50 进度：18P结束

# ==Day 02==  2020.10.16 12：30 开始：

### 1.Enum枚举类型：



### 2.在Typescript中使用泛型：

#### 函数中使用泛型：

用于解决无法决定参数的具体类型，但是又对参数传入有一定要求。

当我们有封装了一个函数，参数要求传进相同类型的值时，比如都要传入字符串，或者都要传入数字类型。

第一种方法是我们对函数的参数都注解为字符串。但是这样就把函数的参数写死了，只能是字符串。当我们需要传入两个数字时，该函数就不能进行复用。

因此还有一种方法就是我们可以使用联合类型，见下图：

![image-20201016125030235](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016125030235.png)

但是这样却不能保证传入的值都是字符串或者都是数字，即使传入一个数字和一个字符串也不会报错。

为了解决这类问题，TS提供了泛型：

语法<泛型名字> 尖括号里的泛型名字可以是任意的，一般会命名为T，然后我们将该泛型用作指定类型为参数添加注解。

在调用该函数时，函数名后面也要跟一个<具体类型>，这个具体类型指定了函泛型是何种类型，下图表示两个参数都必须是字符串类型，否则编译器会报错。

###### 单一类型泛型：

![image-20201016125701269](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016125701269.png)

这样当我们像让该函数的两个参数都必须是数字时，只需要将函数名后的<string> 改为 <number>即可，不需要再定义一个函数。

![image-20201016130206770](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016130206770.png)

这样函数的复用性就得到了很大的提高。

###### 要求参数是数组：

要求传入的参数是一个数组，并且数组元素必须是string类型

下面两种写法都可以：

![image-20201016130650587](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016130650587.png)

![image-20201016130550273](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016130550273.png)

###### 多个泛型：

也可以对不同的参数进行指定，用法见下图：

![image-20201016130925865](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016130925865.png)

TS也支持类型推断：

下面代码根据我们传入参数的类型进行泛型的类型推断，并且该推断了返回值的类型。

![image-20201016131124210](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016131124210.png)

#### 类中使用泛型：

###### 指定单一泛型：

![image-20201016132115883](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016132115883.png)

![image-20201016132619634](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016132619634.png)

###### 泛型中类的继承:

![image-20201016134856017](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016134856017.png)

![image-20201016135057973](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016135057973.png)

![image-20201016135244273](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016135244273.png)

###### 泛型的约束：指定多个泛型

下图表示T必须是string类型或者number类型。

![image-20201016135419986](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016135419986.png)

### 3.TS命名空间：NameSpace：

相当于提供了一种模块化的方法：

不使用命名空间编写的TS代码：

![image-20201016140413187](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016140413187.png)

编译后的JS代码：

![image-20201016140345970](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016140345970.png)

使用命名空间：

将所有的类都存放在命名空间Home下，只暴露一个要在入口文件使用到的类：page

![image-20201016140638116](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016140638116.png)

![image-20201016140712123](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016140712123.png)

编译后的JS代码：只有page被暴露，其他的都是的函数里的变量。

![image-20201016141113211](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016141113211.png)

![image-20201016140809638](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016140809638.png)

![image-20201016140305552](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016140305552.png)

![image-20201016140936426](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016140936426.png)

### 4.(续)TS命名空间：

一种模块化的思想：

![image-20201016142314389](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016142314389.png)

![image-20201016142146781](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016142146781.png)

![image-20201016141500468](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016141500468.png)

引用该文件:

![image-20201016141941366](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016141941366.png)

命名空间可以嵌套：

在子命名空间内暴露一个类：

![image-20201016141706219](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016141706219.png)

对该类进行访问：

![image-20201016141732656](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016141732656.png)

### 5.TS中使用import导入模块：

在上面我们利用命名空间实现了模块化

TS中也可以使用import，export这样ES6的模块化方式对代码模块化：

导出：

![image-20201016143008244](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016143008244.png)

导入：

![image-20201016142935791](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016143258429.png)

但是这样做会存在一个问题：

编译后的JS文件出现了define关键字，这是AMD模块化的语法，这样的代码在node上可以运行，但是不能在浏览器运行。

![image-20201016143116874](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016143116874.png)

要运行的话必须借助require.js

![image-20201016143408338](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201016143408338.png)

==以上这些方法太麻烦，我们开发时使用webpack，parcel等打包工具打包TS代码不需要那么多引入==

2020.10.16 14:50 结束 进度 ：26P结束 视频结束，后期可能会更新。