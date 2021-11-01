# js权威指南第7版，笔记

### 第三章

#### 3.9 类型转换

- undefined 转数字 --> NaN
- null 转数字 --> 0
- number 数组（单个元素) 转数字--> 数组元素，多个元素，其他类型的数组转数字为NaN
- 原始类型转数字：
  - 可以解析为数值的字符串都会转换为对应的数值
  - 字符串转数值：开头和末尾可以含有空格，字符中间有空格，或字符中存在任何不属于数值字面量的非空格字符都会导致转换结果为NaN
- 显示转换
  - Boolean();
  - String() : 除了 null  和 undefined 外，所有的值都有 toString() 方法，这两个方法的返回值相同；
  - Number();
  - 以上三种也作构造函数，产生的对象称为‘包装对象’，现在已经没必要使用了
- 会进行隐式转换的操作符：
  - ‘+’ 任何值与字符串进行 + 操作都会返回字符串
  - **一元操作符** ‘+’ 会把自己的操作数转换为数值（ + null --> 0 , +undefine --> NaN）
  - ！操作符会将自己的操作数转换为布尔值，然后取反
  - ‘-’ 减运算，会将操作数转换为数值进行运算

#### 数值处理：Number  类的方法：

数值格式化

- Number 类的 toString() 方法

  参数可选，（ 2- 36 ） 默认为 10 ，可将数值转换为对应进制的值

- toFixed() 方法，将数值转换为字符串，参数为指定的小数点位数，如 5.00 .toFixed(1) --> 5.0

#### 字符串转数字，方法

- Number()
- parseInt() , 全局函数
- parseFloat()，全局函数

#### 对象转原始值

（大多数对象都没有 `valueOf` 方法 ，因此转换过程中大多数调用 `toString` 方法）

- 对象转布尔值,所有对象都转换为 true
- 对象转换为字符串,调用偏字符串算法（先 `toString` ，再 `valueOf`）
- 对象转换为数值，调用偏数值算法（先` valueOf`，再 `toString`  ）
- 无偏好算法
  由类自己定义的转换规则决定，对于所有 js 内置原始类型 ，只有` Date `类会调用偏字符串算法，其他对象都调用偏数值算法 
-  如何在自定义类中定义自己的对象到原始值的转换？
   给类定义一个 `[Symbol.toPrimitive]` 方法,该方法需要返回一个能够表示对象的原始值
- 什么情况下会调用偏字符串算法？
  对于所有 `js` 内置原始类型 ，只有 `Date` 类会调用偏字符串算法，其他对象都调用偏数值算法 
  对于操作符， `+ `操作符（二元），`== `和` !=` 操作符都会调用 无偏好算法，比较运算符会调用偏数值算法

```js
// 类型转换，对象到原始值的转换
function objToOrigin (obj,type) {
  //对象转布尔值,所有对象都转换为 true,这里不考虑 obj 为null undefined 的情况
  if(type === 'Boolean') {
    return true;
  }else if (type === 'String') {
    // 对象转换为字符串,调用偏字符串算法
    return preferToStr(obj);
  }else if(type === 'Number') {
    // 对象转换为数值，调用偏数值算法
    return preferToStr(obj);
  }
}

// 偏字符串算法
function preferToStr (obj) {
  //先尝试 toString 方法, toString 方法有定义并且返回原始值的情况下，返回原始值（即使不是字符串）
  if(obj.toString && (typeof obj.toString() !== 'object' || obj.toString() === null)) {
    return obj.toString();
  } else if (!obj.toString || obj.toString() instanceof Object){
    // toString 方法有定义但是返回对象,或者 toString 方法不存在,则尝试 valueOf 方法
    if(obj.valueOf && (obj.valueOf() !== 'object' || obj.valueOf() === null)){
      // valueOf 方法有定义并且返回原始值的情况下，返回原始值（即使不是字符串）
      return obj.valueOf();
    } else {
      // 否则抛出类型错误
      throw 'TypeError:can not transfer object to original value';
    }
  } 
}
// 偏数值算法与偏字符串算法类似，不过先尝试 valueOf 方法, 再尝试 toString 方法
function preferToStr (obj) {
  if(obj.valueOf && (typeof obj.valueOf() !== 'object' || obj.valueOf() === null)) {
    return obj.valueOf();
  } else if (!obj.valueOf || obj.valueOf() instanceof Object){
    if(obj.toString&& (obj.toString() !== 'object' || obj.toString() === null)){
      return obj.toString();
    } else {
      throw 'can not transfer object to original value';
    }
  } 
}

console.log(objToOrigin([1,2],"Number"));
console.log(typeof objToOrigin([1],"Number"));
console.log(Number('1'));
```



### 第四章

#### 4.9.1 判断 两个值是否相等 == 操作符执行了哪些转换

- == 操作符不会将其操作数转换为布尔值
- undefined 转换为布尔值是 false ，但是 undefined ==  false  返回 false

### 第六章 - 对象

#### 原型链

- 原型链： 对象通过其`prototype` 属性创建了一个用于**继承属性**的链条，当**访问对象属性**时，如果对象本身没有（自有属性），就会寻着原型链查找直到找到或查询到原型为 `null` 的对象为止。
- 几乎所有对象都有原型，但是大多数对象没有 `prototype` 属性

#### 继承

- 对于继承的属性（来自原型链），如果给对象赋值一个同名属性，则对象会产生一个自有属性（不会对原型链上的属性进行修改），查询属性时会用到原型链，而设置属性时不会影响原型链。

  - 如果继承的属性是 访问器属性（get set)，那么会在当前对象上调用设置方法，而不是创建新的属性，如果设置方法里定义了别的属性，那么也会在对象上定义同样的属性。

  - 继承的只读属性不允许赋值（则该属性就不是自有属性了--> 不能用同名自有属性隐藏只读继承属性）

    ```js
    // 原型上的属性
    ...
    get accessor () {
    	this.x += 1;
        return this.x++;
    },
    ```

#### 对象的属性

- **区分自有属性和继承属性**

  - `hasOwnProperty（）`

    - 结合 `for in ` 遍历所有自有属性

    ```js
    for (let propName in obj) {
        if(!obj.hasOwnProperty(propName)) continue;
    }
    ```

- 属性的**特性**

  - `writable` 是否可修改属性的值
  - `enumerable` 是否可以通过 `for ... in` , `Object.keys()` 枚举属性
  - `configurable` 是否可以删除属性，是否可以修改属性的特性

  对象字面量创建的对象的属性，常规赋值的属性，都是可写，可枚举，可配置的。

- 数据属性和访问器属性

- 删除属性：`delete` 操作符只删除自有属性，操作成功或没有影响返回 true,操作失败返回 false

  不允许删除 不可配置的属性

  严格模式下会报类型错误

- 检查对象中是否存在某个属性

  - `in` 操作符  'propName'  in obj   对象自有属性或继承属性中存在则返回 true 
    - 有些属性存在，但是值被设置为 `undefined` , in 操作符会返回  true
  - `hasOwnProperty（）` 对自有属性返回 true ， 继承属性返回 false
    - 结合 `for in ` 遍历所有自有属性
  - `propertyIsEnumerable` 对自有的 **可枚举属性**  返回 true

### 第七章

#### 数组基础

- 数组的特性：元素，索引（0- 2^32 -2) , 无类型限制 ， 大小动态改变，按需增大，减小，稀疏，元素不一定连续

- 数组的方法：很多继承自 Array.prototype , 大部分可以用于其他类数组对象

- ES6 新增数组类 --> 定型数组( 性能高，支持二进制数据的字节级访问 )

- 创建数组： 

  ```js
  - let array = []; // 可以是任意表达式
  - let array1 = [...'hello'];// 对可迭代对象使用扩展操作符
  - Array(10); // 参数可指定数组初始长度，参数有一个以上则会作为数组元素
  - Array.of(1，2，3) ; 
  - Array.from() // es6
  ```

  `...`并不是操作符，适用于任何可迭代对象，可以用它进行数组的浅拷贝

- 数组去重：利用集合

  ```js
  [...new Setter(array)]
  ```

- 判断一个对象是否是数组

  - array instance of Array -- > true

  - array.constructor (不靠谱，因为 constructor 是可以被修改的)
  - Object.prototype.toString.call(array);  --> `'[object Array]'` 虽然也可以修改原型上的 toString 方法， 但是一般不会这样做
  - Array.isArray(array) ---> true （ES5） 同上，能改但不会。

#### 类数组转数组

- `...` 扩展运算符
- Array.form( iterable ) // 参数为可迭代对象（如字符串），接受第二个参数，传入函数，会对元素依次调用后将返回值代替原始值作为数组元素。
- Array.prototype.slice.call( iterable )  // slice 方法返回一个新对象，不传参数，默认截取从开头到结尾，slice 内部使用 for 循环，将每个元素 push 进入新数组
- 字符串转数组：split() 方法

#### 数组转字符串

- join () 方法
- toString () 方法
- 字符串是类数组对象，也可以通过[index] 访问字符，并且拥有 length 属性，可以利用 call ，apply  对字符串使用一些数组的方法 : Array.prototype.join.call('hello',  '-')  --> 'h-e-l-l-o'

#### 数组和普通对象的比较

- 有属性： length 自动改变，对其赋值将其变小会对数组元素进行删除

- 数组索引值会被转换为字符串，然后将该字符串作为属性名，访问属性
  - 所有的索引都是属性名，只有介于 0 - （ 2^32 -2 ） 之间的整数属性名才是索引 
  - 使用 负整数，非整数，非字符字符串作为数组索引，那该值会成为数组对象的属性
- 类数组对象

#### 稀疏数组与多位数组

- 创建稀疏数组：

  - 对大于数组长度的索引赋值

  -  使用 Array 方法创建 
  - *使用 delete 操作符*

- 创建多维数组 : 数组里嵌套数组

  let array = [[1,2,3],[4],[5,6]];

  访问： array [0] [0] --> 1

#### 常用的数组方法：

(**加粗**的方法会改变原数组)

- 添加和删除数组元素（也可以使用 delete 操作符删除指定索引的元素，像删除对象的属性一样，删除后数组会变稀疏，或者直接改变数组 length 的值） 可以实现 栈，队列 数据结构

  下面的方法都会改变数组长度

  - 向数组末尾添加元素（可以有多个参数，unshift 同）： **push** 返回添加后的数组的长度
  - 向数组开头添加元素：**unshift**  返回添加后的数组的长度，所有元素移动到高一位的索引（0 --> 1 ）
  - 删除数组末尾的元素：**pop** 返回**被删除的**元素
  - 删除数组开头的元素：**shift** 返回**被删除的**元素 , 所有元素移动到低一位的索引（ 1 --> 0 ）
  - 调用数组的 splice 方法删除数组元素( 见下 )
  
- 遍历数组（迭代，映射，过滤）：

  都接受一个函数作为第一个参数，接受第二个可选参数（将作为第一个参数的函数内部的 this 的值）。

  对每个存在的元素（不包括 undefined ）调用一次这个函数，以下的方法都**不会**修改原数组，下面的数组方法都接收 3 个参数，依次是 数组元素，数组索引，数组本身。

  不能提前终止迭代（break,continue)--> **可以利用 return 实现和 continue 一样的效果**

  - forEach ：对每个元素调用一次传入的函数（不必要有( 即非 undefined )返回值）

  - map：对每个元素调用一次传入的函数（通常来说都应该有返回值），**返回**这个函数的返回值构成的数组（**新数组**，与原数组长度一样，保留原数组的 undefined 元素）。

  - filter：传入的数组通常返回 true 或 false ，返回  true 的元素成为返回的新数组的成员，新数组是稠密的，不包含 undefined, filter 会跳过缺失的元素

    ```js
    // 清理掉数组中的空元素
    array = array.filter((item) => item !== undefined && item !== null);
    ```

  - find() 与 findIndex()  ，遍历数组，类似 filter ,不过当有返回 true 的元素就停止迭代，find 返回元素， findIndex f返会索引，遍历完都没有 ，则 find 返回 undefined ，findIndex 返回 -1

  - every 与 some : every 全都返回 true 才返回 true, some 只要有一个返回 true 就返回 true；空数组调用，every 返回 true , some 返回 false

- 数组切片操作

  - slice( ) : 不会修改数组，返回截取的（新）数组，参数可选，无参数则截取整个数组，只有一个参数则截取到末尾，两个参数，截取位置**包含第一个**参数，**不包含第二个**参数： [0,1,2,3,4,5].slice(0,2); --> [0,1]，参数可以是负数，表示从后往前第几个参数：[1,2,3,4,5].slice(-5,5) --> [1,2,3,4,5]

  - **splice( )** :

    第一个参数是起点位置（**包含**）

    第二个参数表示要操作的元素**个数**，没有则操作起点到末尾的元素。

    没有删除元素则返回空数组

    有则返回被删除的元素组成的数组

    由于还有第三个参数，可以在第一个参数指定的位置 **前** 插入元素，所以 splice 也可以实现向数组添加或替换元素

    ```js
    let array = [0,1,2,3,4,5];
    // - 从数组中删除元素 
    array.splice(0,1) // 返回 [0] ,array --> [1,2,3,4,5]
    // - 向数组中插入元素
    let array = [0,1,2,3,4,5];
    array.splice(0,0,0.5) // 返回 [] ,array --> [0.5,1,2,3,4,5]
    // - 替换数组元素
    let array = [0,1,2,3,4,5];
    array.splice(0,2,'a','b') // 返回 [0,1] ,array --> ['a','b',2,3,4,5],
    ```

  - **fill** ： 第一个参数表示要将数组元素**设置为的值** ，第二个参数指定开始设置的索引（默认0），第三个参数指定终止索引（**不包含**）默认到数组末尾，负索引作为参数和 slice 一样，返回修改后的数组

  - **copyWithin**：

- 查找数组元素，数组排序

  - indexOf
  - lastIndexOf
  - includes( ES6 ) 
  - **sort** : 根据 Unicode 编码进行排序，可以传入一个函数指定排序方式
  - **reverse** ：

- 数组转化： 见 [类数组转数组](#类数组转数组)，[数组转字符串](#数组转字符串)

- 其他方法

  - concat () ： 返回一个新数组

#### 遍历一个数组

- 传统的 for 循环

  对于稀疏数组，不想遍历不存在的元素，可以这样写：

  ```js
  for (let i = 0; i < array.length ; i++) {
      if(array[i] === undefined){
          continue;
      }
  }
  ```

- es6 的 for of 语句

  ```JS
  for (let item of array) {
      // do something..
  }
  // 获取索引和元素
  for (let [index,item] of array.entries()) { // 数组的 entries 方法返回一个遍历器，其 next 方法可用于获取原数组的 [key,value]
      // do something...
  }
  ```

- 调用数组方法 forEach  见上一小节

#### 扩展操作符：

`...`

- 只扩展对象的自有属性
- 相同的属性名，后面扩展的属性会覆盖前面的
- 注意在循环或递归中使用扩展操作符可能带来的性能问题

### 第八章：
