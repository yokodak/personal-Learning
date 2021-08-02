# TypeScript学习笔记：

> 📺视频资源：TypeScript从入门到精通视频教程-2020年新版
>
> 🔗链接： https://www.bilibili.com/video/BV1qV41167VD 
>
> 📅创建时间：2020.10.15 15：00
>
> ⌚ 2021年7月21日 15点37分 重写
>
> 📍学校寝室 ——> 公司

## 简介

先看了视频，后来再根据官网教程对笔记进行更新修改

大部分是自己对TS官网 **[handbook](https://www.typescriptlang.org/docs/handbook/intro.html)** 的归纳，官方网站的handbook写的比较清晰易懂且详细，建议可以直接看handbook，如果对我的笔记感兴趣也可以继续往下看😉

Day 01  2020.10.15 15：00开始

📌先看官方文档的介绍

> - TypeScript offers **all** of JavaScript’s features, and an **additional layer** on top of these: TypeScript’s **type system.**
>
> - The main benefit of TypeScript is that it can highlight unexpected behavior in your code, **lowering the chance of bugs.**
>
>   译：Typescript支持Javascript的所有特性, 并进行了一层扩展: Typescript的类型系统.
>
>    		使用Typescript的主要好处是它能突出代码中的意外表现 , 降低代码出现的几率.
> 

因为JS是一门弱类型的编程语言,各种数据类型之间往往会进行类型转换,这会带来一些问题,比如现在写了一个方法,期望参数是数字类型,但是调用该方法的人并不知情,于是传入了一个数组,虽然参数类型出错,但是JS在编译时并不会报错, 当程序运行时发现结果出错, 再次检查时才发现是类型错误

使用TS就能很好的避免这样的情况,根据TS的类型注解, 在声明一个函数的参数(或定义一个变量,属性)时,可以为其指明数据类型, 当传入的实参类型不符合指定类型时,TS就会提示参数错误,如👇

```typescript
function sum(a:number,b:number) {  //将参数a,b都注解为number类型
  return a + b;
}
sum(1,'hello') 
```

此时TS会报错

<img src = "https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210722101638384.png">

这样就能将运行时才发现的错误,提前到编译前就暴露,提高了代码的健壮性,减少了bug🐛出现的概率

除此之外,TS还对JS有其他的扩展,比如接口、泛型、枚举类型等，我们可以再一点点了解😃

## 1.环境搭建

编辑器：VSCode

安装TypeScript：

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



## 2.基础语法

### 1.基础类型

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

### 2.类型注解

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
  function greet(name: string){
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

📅 2021年7月26日 12 ：11 start  

​									   12 ：30 pause

​										14：05 start

### 3.匿名函数类型推断

TS会根据代码的上下文对匿名函数的参数类型进行推断（contextual typing）

如下👇

```typescript
const names = ['tony','jonny','kenny'];
names.forEach(function(name) {
  console.log(name.toUppercase()) //注意这里方法名写错
})
```

此时，TS会报错



![image-20210726143651719](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210726143651719.png)



这说明即使我们没有对匿名函数的参数`name`进行类型注解，TS依然能够根据我们的代码上下文推断出`name`应该是`string`类型，因为我们定义的**数组** `names`的元素都是string类型，所以当调用names数组的`forEach`方法时，TS推断匿名函数的参数是string类型。

### 4.对象类型注解

在[类型注解](#2.类型注解) 中，我们给出了一个普通对象类型注解的例子。

定义一个对象类型，只需要列出它的属性及属性对应的数据类型（可选）即可，如下官网给出的一个[例子](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#object-types)，将打印坐标的方法` printCoord` 的参数`pt`注解为一个对象类型，其属性`x`,`y` 都是number类型

```typescript
// The parameter's type annotation is an object type
function printCoord(pt: { x: number; y: number }) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}
printCoord({ x: 3, y: 7 }); //参数必须是一个对象，且对象的属性必须是number类型
```

> 📍 注解时，对象的每个属性的类型注解是可选的，如果不进行注解，TS会默认其类型为any

- 可选的属性

  对象类型也可以指明它的**属性**是否**可选**，也就是该属性不是必须拥有的属性，在想要设置为可选的属性名后加上一个`?`即可，如下

  ```typescript
  function printName(obj: { first: string; last?: string }) {
    // ...
  }
  // Both OK
  printName({ first: "Bob" }); //参数注解为对象类型，有两个属性，first必选，last是可选的
  printName({ first: "Alice", last: "Alisson" });
  ```

  需要注意的是，可选的属性不存在时，访问该属性，则值为`undefined`，所以需要注意在用到该属性的地方进行判断，如下

  ```typescript
  function printName(obj: { first: string; last?: string }) {
    // Error - might crash if 'obj.last' wasn't provided!
    console.log(obj.last.toUpperCase());
  }
  printName({first:'Alice'})
  ```

  此时编译器并不会报错，但是当运行程序时，由于没有传入第二个属性，访问时会报错:

  <p style = "color:red; font-family:'Fira Code'">error TS2532: Object is possibly 'undefined'.</p>

  所以，正确的做法是加上一层判断, 或使用JS新语法（？）代替

  ```typescript
  function printName(obj: { first: string; last?: string }) {
    if (obj.last !== undefined) {
      // OK
      console.log(obj.last.toUpperCase());
    }
    // A safe alternative using modern JavaScript syntax:
    console.log(obj.last?.toUpperCase());
  }
  ```

### 5.联合类型

在TS中，不仅可以将一个变量注解为某种单一数据类型，还可以将其注解为多种数据类型，表示该变量的值可以是这些类型中的任意一种，这样的类型称为联合类型（Union type）

如下的方法`printId`的参数注解为 `number | string `，表示传入的参数可以是数字或字符串

```typescript
function printId(id: number | string) {
  console.log("Your ID is: " + id);
}
// OK
printId(101);
// OK
printId("202");
```

不过，相应的，将一个变量注解为联合类型后，则该变量将不再具有某种数据类型特有的方法，比如将参数`id`注解为联合类型 `number | string `后，就不能再对参数`id`调用 `string`类型特有的方法 `toUpperCase`

```typescript
function printId(id: number | string) {
  console.log(id.toUpperCase()); //TS报错
```

所以，如果要根据传入的不同类型的数据做不同的操作的话，通常需要添加一层判断👇

```typescript
function welcomePeople(x: string[] | string) {
  if (Array.isArray(x)) {
    // Here: 'x' is 'string[]'
    console.log("Hello, " + x.join(" and "));
  } else {
    // Here: 'x' is 'string'
    console.log("Welcome lone traveler " + x);
  }
}
```

### 6.类型别名

有时候我们会多次用到同一个类型注解，但是不想每次都写，希望用一个简单的名字代替它。比如之前的打印坐标的方法👇，我们将它的参数注解为一个对象，该对象的两个必选属性都是`number`类型。

```typescript
function printCoord(pt: { x: number; y: number }) {
  //...
}
```

现在又有一个方法，参数的要求和 `printCoord` 一样，但是我们懒得写，并且以后会多次用到该注解，那我们就可以给它起个别名（Alias)，用来代替它。使用 `type`关键字来定义一个别名。

```typescript
//类型别名
type Point = {
  x: number;
  y: number;
};

// Exactly the same as the earlier example
function printCoord(pt: Point) { //效果同上例
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}
printCoord({ x: 100, y: 100 });
```

为联合类型取别名👉 ` type ID = number | string;`

### 7.接口

还有一种方式也能给类型命名，即接口（interface），使用关键字`interface` 定义一个接口,仍然以上面的`printCoord`方法为例

```typescript
interface Point {
  x: number;
  y: number;
}

function printCoord(pt: Point) { //效果和使用类型别名一样
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}

printCoord({ x: 100, y: 100 });
```

**接口和类型别名的区别**

接口和类型别名看起来似乎没有什么区别，对的，的确是这样，很多情况下他们能实现同样的功能

> 📌 Almost all features of an `interface` are available in `type` [🔗](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#differences-between-type-aliases-and-interfaces)

比如类型的继承👇

![image-20210726163814978](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210726163814978.png)

虽然如此，他们还是有一些区别，如

- 一个类型别名一旦被创建后就不可修改，而接口可以
- 接口不能用来重命名一个原始类型（如`striing` )，而类型别名可以
- ......更多区别 见[官网🔗](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#differences-between-type-aliases-and-interfaces)

使用接口还是使用别名，取决于个人喜好和实际应用场景。

### 8.类型断言

type assertion 

有时候TS并不能完全知晓一个值的类型，作为开发者，我们对自己的程序可能更加了解。当我们确切地想要将一个值断定为某种类型时，可以使用类型断言（type assertion ）  `value as type`

官网举例[🔗](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-assertions)：

> 📌 比如你使用`document.getElementById`方法，TS只知道该方法会返回某种形式的`HTMLElement `, 但是你知道对于给定的ID，页面上存在一个与之对应的 `HTMLCanvasElement`, 在这种情况下，你可以使用类型断言指明一个更具体地类型，如下👇

```typescript
const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement;
```

也可以使用尖括号语法，（`.tsx`文件代码除外）和上面的例子是等价的

```typescript
const myCanvas = <HTMLCanvasElement>document.getElementById("main_canvas");
```

不过，类型断言只能指定更加具体的类型（或更不具体点的类型），而不能指定八竿子打不着的类型，比如不能将字符串指定为数字类型

```typescript
const x = "hello" as number; //error
```

这样做可能显得有些保守, 因为这样也阻止了一些有这种需求的复杂情况，如果出现这种情况 ，那也可以使用两个断言来实现，先断言为`any`或`unknown` 再断言为想要的类型

```typescript
const a = (expr as any) as T;
```

### 9.字面量类型

除了常见的类型如`string`,`number`等，我们也可以将变量的类型注解为特定的字符串或数字。

就像`const`关键字声明的常量一样，声明为字面量类型的变量是不可修改的。如

```typescript
let x: "hello" = "hello"; //将变量x注解为'hello'类型
// OK
x = "hello";
// ...
x = "howdy"; //报错
//Type '"howdy"' is not assignable to type '"hello"'.
```

这样似乎没什么价值，因为很少有变量只能有一个取值，不过，将字面量和联合类型结合起来，能起到限制方法参数的效果，如下的方法`printText`的参数注解表示：两个参数，第一个参数要求是`string` 类型，第二个参数只能是字符串`left`, `right`,`center`中的一个

<img src = "https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210802191619525.png " style = "width:100%">

```typescript
function printText(s: string, alignment: "left" | "right" | "center") {
  // ...
}
printText("Hello, world", "left");
printText("G'day, mate", "middle"); //报错，参数只能是字符串'left','right','center'中的一个
```

也可以和非字面量参数结合起来使用👇

```typescript
interface Options {
  width: number;
}
function configure(x: Options | "auto") { 
  // ...
}
configure({ width: 100 });
configure("auto");
```

`true`和`false`也是一种字面量（布尔字面量）

需要注意的是,当声明一个对象的属性时, TS会假定属性的值之后会被修改,比如下面的代码, TS会推断`counter`是 `number` 类型,而不是字面量类型 `0 ` ,所以对属性`counter` 的修改是合法的

```typescript
const obj = { counter: 0 };
if (someCondition) {
  obj.counter = 1;
}
```

对于字符串类型也是一样,如下代码,方法 `handleRequest` 要求第二个参数只能是 `"GET"`, `"POST"`字符串中的一个(即字面量联合类型` "GET"|"POST"`), 此时我们将对象 req 的属性 method 作为  handleRequest  的第二个参数,TS会报错, 因为TS推断  `req.method` 为 string类型  , 而不是` "GET"|"POST"`类型

```typescript
const req = { url: "https://example.com", method: "GET" };
handleRequest(req.url, req.method); //报错
```

解决这个报错的方法有两个

1.在以下任意一个位置添加类型断言

```typescript
//  1:
const req = { url: "https://example.com", method: "GET" as "GET" }; //将属性method断言为字面量'GET'类型
//  2:
handleRequest(req.url, req.method as "GET"); //表示此处的 req.method 具有值 "GET"
```

2.在定义req对象时,添加 `as const` 后缀,这样能确保它的所有属性都是字面量类型

```typescript
const req = { url: "https://example.com", method: "GET" } as const;
handleRequest(req.url, req.method); //ok
```

### 10.null和undefined

TS中`null`  和 `undefined` 的表现取决于配置 项`strictNullChecks`

- strictNullChecks `off`

  任意类型的属性,变量都可以赋值为null 和 undefined

  ```typescript
  let i = 1
  // ok
  i = undefined
  // ok
  i = null
  ```

- strictNullChecks `on`

  当 strictNullChecks  设置为 true时 , 不能将 `null` 或 `undefined` 赋值给其他类型

  ```typescript
  let i = 1
  // Type 'undefined' is not assignable to type 'number'
  i = undefined
  // Type 'null' is not assignable to type 'number'
  i = null
  ```

  且使用值为null 或者 undefined的参数,或对象的属性值时,需要对其进行判断(检查),比如:

  ```typescript
  function doSomething(x: string | null) {
    if (x === null) {
      // do nothing
    } else {
      console.log("Hello, " + x.toUpperCase());
    }
  }
  ```

  TS也提供了一个特殊的语法 -后缀`!` ,  (非空断言操作符),   写在变量后,起到一个断言的作用,表示该值不是`null ` 或者 `undefined`, 这样就不必专门写一个判断来检查值是否为空了.

  如

  ```typescript
  function liveDangerously(x?: number | null) {
    // No error
    console.log(x!.toFixed());
  }
  ```

## 3.泛型

Generic



## 4.类



## 5.装饰器









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

### 









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