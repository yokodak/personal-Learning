# 一些知识点暂记

2020.11.26 22：25

### 1.异步编程：

摘自 [阮一峰 es6 入门教程](https://es6.ruanyifeng.com/#docs/promise)

#### 1.传统方法 [🔗](https://es6.ruanyifeng.com/#docs/generator-async#%E4%BC%A0%E7%BB%9F%E6%96%B9%E6%B3%95)

ES6 诞生以前，异步编程的方法，大概有下面四种。

- 回调函数
- 事件监听
- 发布/订阅
- Promise 对象

Generator 函数将 JavaScript 异步编程带入了一个全新的阶段。

#### 2.异步概念：

所谓"异步"，简单说就是一个任务不是连续完成的，可以理解成该任务被人为分成两段，先执行第一段，然后转而执行其他任务，等做好了准备，再回过头执行第二段。

非连续的执行，需要等待的任务

比如，有一个任务是读取文件进行处理，任务的第一段是向操作系统发出请求，要求读取文件。然后，程序执行其他任务，等到操作系统返回文件，再接着执行任务的第二段（处理文件）。**这种不连续的执行，就叫做异步**。

相应地，连续的执行就叫做同步。由于是连续执行，不能插入其他任务，所以操作系统从硬盘读取文件的这段时间，程序只能干等着。

#### 3.浏览器多线程与js单线程

[浏览器多线程与js单线程](https://juejin.cn/post/6844903812642111501)

[事件循环（ event loop ） 宏任务与微任务]( https://zhuanlan.zhihu.com/p/78113300)

#### 3.回调函数

JavaScript 语言对异步编程的实现，就是回调函数。

所谓回调函数，就是把任务的第二段单独写在一个函数里面，等到重新执行这个任务的时候，就直接调用这个函数。回调函数的英语名字`callback`，直译过来就是"重新调用"。



#### 4.回调地狱：

 回调函数本身并没有问题，它的问题出现在多个回调函数嵌套。假定读取`A`文件之后，再读取`B`文件，代码如下。 

```javascript
fs.readFile(fileA, 'utf-8', function (err, data) {
  fs.readFile(fileB, 'utf-8', function (err, data) {
    // ...
  });
});
```

 不难想象，如果依次读取两个以上的文件，就会出现多重嵌套。代码不是纵向发展，而是横向发展，很快就会乱成一团，无法管理。

因为多个异步操作形成了强耦合，只要有一个操作需要修改，它的上层回调函数和下层回调函数，可能都要跟着修改。这种情况就称为"回调函数地狱"（callback hell）。 

 Promise 对象就是为了解决这个问题而提出的。它不是新的语法功能，而是一种**新的写法**，允许将回调函数的嵌套，改成**链式调用**。采用 Promise，连续读取多个文件，写法如下：

```javascript
var readFile = require('fs-readfile-promise');

readFile(fileA)
.then(function (data) {
  console.log(data.toString());
})
.then(function () {
  return readFile(fileB);
})
.then(function (data) {
  console.log(data.toString());
})
.catch(function (err) {
  console.log(err);
});
```

#### 5.promise使用

> 下面的` resolve` 都指 promise 的状态从 `pending` 变为 `fulfilled `

- **基本使用**

  创建一个 promise 对象

  下面使用 `setTimeout ` 方法模拟了异步操作，表示200ms 后结果才返回 

  ```js
  let myPromise = new Promise ((resolve,reject) => {
    setTimeout(() => {
      resolve('success!') //  resolve 的作用是将 promise 对象的状态从 未完成 变成 成功
    }, 200);              //  resolve 的参数作为异步操作的结果传递给 resolve 状态的回调函数
  });                     
  ```

  `resolve`状态的回调函数是 `then` 方法的第一个匿名函数,  `reject` 状态的回调函数是 `then` 方法的第二个参数， `then ` 方法的两个参数都是可选的，都接受 `promise `对象传出的值作为参数

  ```js
  // 调用 promise 的 then 方法，此时，resolve 的实参会作为参数传递进 message 
  myPromise.then((message) => {
    console.log(message);    // 输出 success！
  },(error) => {
    console.log(error);	   // 因为没有调用 reject 方法 ，所以这部分代码不会执行
  })
  ```

  **例1：** `promise ` 实现 `ajax ` 操作的例子，对 `XMLHttpRequest` 的封装

  ```js
  const getJSON = function(url) {   // 返回一个 Promise 对象👇
    const promise = new Promise(function(resolve, reject){
      // 定义请求的响应状态改变后的回调函数
      const handler = function() {
        if (this.readyState !== 4) {
          return;
        }
        if (this.status === 200) {
          resolve(this.response); // 请求成功，将结果传递给 resolve 的回调函数 --> 输出请求结果
        } else {
          reject(new Error(this.statusText)); // 请求失败，将失败信息传递给 reject 的回调函数 --> 输出错误信息
        }
      };
      const client = new XMLHttpRequest(); // 创建 XMLHttpRequest 对象发送 ajax 请求
      client.open("GET", url);
      client.onreadystatechange = handler; // 请求的响应状态改变后，调用回调函数 handler
      client.responseType = "json";
      client.setRequestHeader("Accept", "application/json");
      client.send();
  
    });
    return promise;
  };
  
  // 使用封装后的 ajax 操作
  getJSON("/posts.json").then(function(json) {
    console.log('Contents: ' + json);
  }, function(error) {
    console.error('出错了', error);
  });
  ```

  `resolve` 方法的参数是  `promise ` 实例的情况 

  下面代码中，`p2` 的  `resolve` 方法的参数，是 另一个`promise` 实例 `p1` ， 1s 后 `p2 `的状态已经变为 `resolve ` ，但此时 `p1` 还在 `pending` 所以 ` p2 `的回调函数会等待 `p1` 的状态改变，即此时的 `p2` 自己的状态无效了。

  3s 后 `p1`  的状态变为 `rejected`  ，则 `p2 ` 的 `catch`  方法指定的回调函数立刻执行，打印 `error: fail`

  ```js
   // p1是一个 promise ，3s 后状态变为 rejected 
   const p1 = new Promise(function (resolve, reject) {
    setTimeout(() => reject(new Error('fail')), 3000)
  })
   // p2的状态 1s 后变为 fulfilled
   const p2 = new Promise(function (resolve, reject) {
    setTimeout(() => resolve(p1), 1000) // p1 的状态决定了 p2 的状态
  })
   
   p2
    .then(result => console.log(result)) // 不会执行，因为要等待 p1 的状态改变
    .catch(error => console.log(error))  // 如果 p1 的状态已经是 rejected p2 的回调函数会立刻执行
  // Error: fail
  ```

  一般来说，调用 resolve 或 reject 以后，Promise 的使命就完成了，**后继操作应该放到then方法里面**，而不应该直接写在resolve或reject的后面。

  所以，最好在它们前面加上return语句，这样就不会有意外。

  ```js
  new Promise((resolve, reject) => {
    return resolve(1);
    // 后面的语句不会执行
    console.log(2);
  })
  ```

   promise 的状态一旦改变，就不会再变

  ```js
  const promise3 = new Promise(function(resolve, reject) {
    resolve('ok'); //这里只会调用 then 里的回调函数，错误将不会被捕获
    throw new Error('test');
  });
  promise3
    .then(function(value) { console.log(value) }) 
    .catch(function(error) { console.log(error) }); // 错误不会被捕获，catch 方法不会执行
  // 输出: ok
  ```

  一般来说，不要在 then 方法里定义 `reject` 状态的回调，总是使用 `catch` 方法，这样结构更清晰，且还能捕获 then 方法的错误。

- **链式调用**

  因为 `then `方法返回的是一个新的 `Promise` 实例 , 因此 `then ` 方法可以链式调用，这样使异步操作能像同步一样书写，从而解决多个回调函数嵌套（回调地狱）的问题。

  前一个回调函数的返回值会作为下一个 `then` 方法中的回调函数的参数

  ```typescript
  getJSON("/posts.json").then(function(json:any) {
    return json.post;           // json.post 作为第二个promise resolved状态的回调函数的参数
  }).then(function(post) {
    // ...                 
  });
  ```

  如果前一个回调函数的返回值是一个 promise ，那么下一个回调函数会等待该 promise 的状态发生改变再调用

  ```js
  getJSON("/post/1.json").then(function(post:any) {
    return getJSON(post.commentURL); // 返回一个 promise 
  }).then(function (comments) {      // 等待 promise 的状态变化 ，resolved 则调用第一个回调函数，rejected 则调用第二个回调函数
    console.log("resolved: ", comments);
  }, function (err){
    console.log("rejected: ", err);
  });
  ```

- **错误处理**

  **catch** 方法 

  ` Promise.prototype.catch()` 方法是 `.then(null, rejection)` 或

   `.then(undefined, rejection)` 的 别名，用于指定发生错误时的回调函数，  会捕获` promise `对象内产生的错误和 `then` 方法指定的**回调函数**的错误

  ```js
  getJSON('/posts.json').then(function(posts) {
    // ...
  }).catch(function(error) {
    // 处理 getJSON 和 前一个回调函数运行时发生的错误
    console.log('发生错误！', error);
  });
  ```

  **例2：**

  ```js
  const promise = new Promise(function(resolve, reject) {
    throw new Error('test');
  });
  promise.catch(function(error) {
    console.log(error);           // 会捕获
  });
  // Error: test
  
  // 写法二
  const promise2 = new Promise(function(resolve, reject) {
    reject(new Error('test'));        // reject 方法的作用等同于抛出错误
  });
  promise2.catch(function(error) {
    console.log(error);
  });
  ```

  promise 内部的错误不会影响到 promise 外部的代码

  ```js
  const someAsyncThing = function() {
    return new Promise(function(resolve, reject) {
      // 下面一行会报错，因为x没有声明，但是并不会终止脚本执行
      // resolve(x + 2);   
    });
  };
  
  someAsyncThing().then(function() {
    console.log('everything is great'); // 因为出错，resolved 对应的回调函数不会被执行
  });
  setTimeout(() => { console.log(123) }, 2000); // 照常执行
  // Uncaught (in promise) ReferenceError: x is not defined
  // 123
  ```

- **finally，all 方法**

#### 6.promise的问题：

`Promise`也有一些缺点。

首先，无法取消`Promise`，一旦新建它就会立即执行，无法中途取消。

其次，如果不设置回调函数，`Promise`内部抛出的错误，不会反应到外部。

第三，当处于`pending`状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。 

 Promise 的最大问题是代码冗余，原来的任务被 Promise 包装了一下，不管什么操作，一眼看去都是一堆`then`，**原来的语义变得很不清楚**。 

### 2.Iterator（遍历器）的概念 [§](https://es6.ruanyifeng.com/#docs/iterator#Iterator（遍历器）的概念) [⇧](https://es6.ruanyifeng.com/#docs/iterator)

#### 1.简介：

 遍历器（Iterator）就是这样一种机制。它是一种接口，为各种不同的数据结构提供统一的访问机制。任何数据结构只要部署 Iterator 接口，就可以完成遍历操作（即依次处理该数据结构的所有成员）。 

#### 2.作用：

 Iterator 的作用有三个：

一是为各种数据结构，提供一个统一的、简便的访问接口；

二是使得数据结构的成员能够按某种次序排列；

三是 ES6 创造了一种新的遍历命令`for...of`循环，**Iterator 接口主要供`for...of`消费。** 

#### 3.Iterator 的遍历过程

是这样的。

（1）创建一个指针对象，指向当前数据结构的起始位置。也就是说，遍历器对象本质上，就是一个指针对象。

（2）第一次调用指针对象的`next`方法，可以将指针指向数据结构的第一个成员。

（3）第二次调用指针对象的`next`方法，指针就指向数据结构的第二个成员。

（4）不断调用指针对象的`next`方法，直到它指向数据结构的结束位置。

每一次调用`next`方法，都会返回数据结构的当前成员的信息。具体来说，就是返回一个包含`value`和`done`两个属性的对象。其中，`value`属性是当前成员的值，`done`属性是一个布尔值，表示遍历是否结束。

#### 4. 模拟遍历器的生成方法 

```javascript
var it = makeIterator(['a', 'b']);

it.next() // { value: "a", done: false }
it.next() // { value: "b", done: false }
it.next() // { value: undefined, done: true }

function makeIterator(array) {
  var nextIndex = 0;
  return {
    next: function() {
      return nextIndex < array.length ?
        {value: array[nextIndex++], done: false} :
        {value: undefined, done: true};
    }
  };
}
```

遍历器对象的`next`方法的运行逻辑如下。

（1）遇到`yield`表达式，就暂停执行后面的操作，并将紧跟在`yield`后面的那个表达式的值，作为返回的对象的`value`属性值。

（2）下一次调用`next`方法时，再继续往下执行，直到遇到下一个`yield`表达式。

（3）如果没有再遇到新的`yield`表达式，就一直运行到函数结束，直到`return`语句为止，并将`return`语句后面的表达式的值，作为返回的对象的`value`属性值。

（4）如果该函数没有`return`语句，则返回的对象的`value`属性值为`undefined`。

#### 5.默认的Iterator

Iterator 接口的目的，就是为所有数据结构，提供了一种统一的访问机制，即`for...of`循环（详见下文）。当使用`for...of`循环遍历某种数据结构时，该循环会自动去寻找 Iterator 接口。

一种数据结构只要部署了 Iterator 接口，我们就称这种数据结构是“可遍历的”（iterable）。

ES6 规定，默认的 Iterator 接口部署在数据结构的`Symbol.iterator`属性，或者说，一个数据结构只要具有`Symbol.iterator`属性，就可以认为是“可遍历的”（iterable）。`Symbol.iterator`属性本身是一个函数，==就是当前数据结构默认的遍历器生成函数==。执行这个函数，就会返回一个遍历器。至于属性名`Symbol.iterator`，它是一个表达式，返回`Symbol`对象的`iterator`属性，这是一个预定义好的、类型为 Symbol 的特殊值，所以要放在方括号内

### 3.Generator

#### 1.概念：

 Generator 函数是 ES6 提供的一种异步编程解决方案，语法行为与传统函数完全不同 ， 语法上，首先可以把它理解成，Generator 函数是一个状态机，封装了多个内部状态。

  执行 Generator 函数会返回一个遍历器对象，也就是说，Generator 函数除了状态机，还是一个遍历器对象生成函数 

 形式上，Generator 函数是一个普通函数，但是有两个特征。

一是，`function`关键字与函数名之间有一个星号；

二是，函数体内部使用`yield`表达式，定义不同的内部状态（`yield`在英语里的意思就是“产出”） 

例如：

```javascript
function* helloWorldGenerator() {
  yield 'hello';
  yield 'world';
  return 'ending';
}

var hw = helloWorldGenerator();
```

 上面代码定义了一个 Generator 函数`helloWorldGenerator`，它内部有两个`yield`表达式（`hello`和`world`），即该函数有三个状态：hello，world 和 return 语句（结束执行） 

 调用 Generator 函数后，该函数并不执行，返回的也不是函数运行结果，而是一个指向内部状态的指针对象，也就是上一章介绍的遍历器对象（Iterator Object） 

#### 2.调用：

 必须调用遍历器对象的`next`方法，使得指针移向下一个状态。也就是说，每次调用`next`方法，内部指针就从函数头部或上一次停下来的地方开始执行，直到遇到下一个`yield`表达式（或`return`语句）为止。

换言之，Generator 函数是分段执行的，`yield`表达式是暂停执行的标记，而`next`方法可以恢复执行。 

 调用 Generator 函数，返回一个遍历器对象，代表 Generator 函数的内部指针。以后，每次调用遍历器对象的`next`方法，就会返回一个有着`value`和`done`两个属性的对象。`value`属性表示当前的内部状态的值，是`yield`表达式后面那个表达式的值；`done`属性是一个布尔值，表示是否遍历结束。 

```javascript
hw.next()
// { value: 'hello', done: false }

hw.next()
// { value: 'world', done: false }

hw.next()
// { value: 'ending', done: true }

hw.next()
// { value: undefined, done: true }
```

#### 3.yield

 由于 Generator 函数返回的遍历器对象，只有调用`next`方法才会遍历下一个内部状态，所以其实提供了一种可以暂停执行的函数。`yield`表达式就是暂停标志。 

```js
function* gen() {
  yield  123 + 456; // 不会立即求值，只有当 next 方法将指针移到这一句代码时，才会求值
}
```

 `yield`表达式后面的表达式，只有当调用`next`方法、内部指针指向该语句时才会执行 。

 `yield`表达式只能用在 Generator 函数里面，用在其他地方都会报错。 

#### 4.yield和return的区别：

 `yield`表达式与`return`语句既有相似之处，也有区别。

相似之处在于，都能返回紧跟在语句后面的那个表达式的值。

区别在于每次遇到`yield`，函数暂停执行，下一次再从该位置继续向后执行，

而`return`语句不具备位置记忆的功能。

并且一个函数里面，只能执行一次（或者说一个）`return`语句，但是可以执行多次（或者说多个）`yield`表达式。

正常函数只能返回一个值，因为只能执行一次`return`；

Generator 函数可以返回一系列的值，因为可以有任意多个`yield`。

从另一个角度看，==也可以说 Generator 生成了一系列的值，这也就是它的名称的来历==（英语中，generator 这个词是“生成器”的意思）。 

#### 5.暂缓执行函数：

 Generator 函数可以不用`yield`表达式，这时就变成了一个单纯的暂缓执行函数。  

`f`如果是普通函数，在为变量`generator`赋值时就会执行,

但是，函数`f`是一个 Generator 函数，只有调用`next`方法时，函数`f`才会执行 。

```js
function* f() {
  console.log('执行了！')
}

var generator = f();

setTimeout(function () {
  generator.next()
}, 2000);
```

#### 6.使对象具有 Iterator 接口 :

任意一个对象的`Symbol.iterator`方法，等于该对象的遍历器生成函数，调用该函数会返回该对象的一个遍历器对象。

由于 Generator 函数就是遍历器生成函数，因此可以把 Generator 赋值给对象的`Symbol.iterator`属性，从而使得该对象具有 Iterator 接口。

```javascript
var myIterable = {};
myIterable[Symbol.iterator] = function* () {
  yield 1;
  yield 2;
  yield 3;
};

[...myIterable] // [1, 2, 3]
```

 **==除了`for...of`循环以外，扩展运算符（`...`）、解构赋值和`Array.from`方法内部调用的，都是遍历器接口==** 

### 4.Generator 函数的异步应用：

#### 1.协程：

传统的编程语言，早有异步编程的解决方案（其实是多任务的解决方案）。其中有一种叫做"协程"（coroutine），意思是多个线程互相协作，完成异步任务。

协程有点像函数，又有点像线程。它的运行流程大致如下。

- 第一步，协程`A`开始执行。
- 第二步，协程`A`执行到一半，进入暂停，执行权转移到协程`B`。
- 第三步，（一段时间后）协程`B`交还执行权。
- 第四步，协程`A`恢复执行。

上面流程的协程`A`，就是异步任务，因为它分成两段（或多段）执行

举例来说，读取文件的协程写法如下。

```javascript
function* asyncJob() {
  // ...其他代码
  var f = yield readFile(fileA);
  // ...其他代码
}
```

上面代码的函数`asyncJob`是一个协程，它的奥妙就在其中的`yield`命令。它表示执行到此处，执行权将交给其他协程。也就是说，`yield`命令是异步两个阶段的分界线。

协程遇到`yield`命令就暂停，等到执行权返回，再从暂停的地方继续往后执行。它的最大优点，就是代码的写法非常像同步操作，如果去除`yield`命令，简直一模一样。

#### 2.协程的 Generator 函数实现

Generator 函数是**协程在 ES6 的实现**，最大特点就是可以交出函数的执行权（即暂停执行）。

 整个 Generator 函数就是一个封装的异步任务，或者说是异步任务的容器。异步操作需要暂停的地方，都用`yield`语句注明。 

Generator 函数的执行方法如下。

```javascript
function* gen(x) {
  var y = yield x + 2;
  return y;
}

var g = gen(1);
g.next() // { value: 3, done: false }
g.next() // { value: undefined, done: true }
```

上面代码中，调用 Generator 函数，会返回一个==内部指针==（即遍历器）`g`。

这是 Generator 函数不同于普通函数的另一个地方，即执行它不会返回结果，返回的是指针对象。

调用指针`g`的`next`方法，会移动内部指针（即执行异步任务的第一段），指向第一个遇到的`yield`语句，上例是执行到`x + 2`为止。

换言之，==`next`方法的作用是分阶段执行`Generator`函数==。

每次调用`next`方法，会返回一个对象，表示当前阶段的信息（`value`属性和`done`属性）。`value`属性是`yield`语句后面==表达式的值==，表示当前阶段的值；

`done`属性是一个布尔值，表示 Generator 函数是否执行完毕，即是否还有下一个阶段。

 **Generator 函数可以暂停执行和恢复执行，这是它能封装异步任务的根本原因。** 

#### 3.Generator 函数的数据交换和错误处理

Generator 函数可以暂停执行和恢复执行，这是它能封装异步任务的根本原因。除此之外，它还有两个特性，使它可以作为异步编程的完整解决方案：函数体内外的数据交换和错误处理机制。

`next`返回值的 value 属性，是 Generator 函数向外输出数据；

==`next`方法还可以接受参数==，向 Generator 函数体内输入数据。

```javascript
function* gen(x){
  var y = yield x + 2;
  return y;
}

var g = gen(1);
g.next() // { value: 3, done: false }
g.next(2) // { value: 2, done: true }
```

上面代码中，第一个`next`方法的`value`属性，返回表达式`x + 2`的值`3`。

第二个`next`方法带有参数`2`，这个参数可以传入 Generator 函数，**作为上个阶段异步任务的返回结果**，被函数体内的变量`y`接收。因此，这一步的`value`属性，返回的就是`2`（变量`y`的值）。

Generator 函数内部还可以部署错误处理代码，捕获函数体外抛出的错误。

```javascript
function* gen(x){
  try {
    var y = yield x + 2;
  } catch (e){
    console.log(e);
  }
  return y;
}

var g = gen(1);
g.next();
g.throw('出错了');
// 出错了
```

上面代码的最后一行，Generator 函数体外，使用指针对象的`throw`方法抛出的错误，可以被函数体内的`try...catch`代码块捕获。这意味着，出错的代码与处理错误的代码，实现了时间和空间上的分离，这对于异步编程无疑是很重要的

### 5.async:

#### 1.介绍：

ES2017 标准引入了 async 函数，使得异步操作变得更加方便。

async 函数是什么？一句话，它就是 Generator 函数的语法糖。

 `async`函数就是将 Generator 函数的星号（`*`）替换成`async`，将`yield`替换成`await`，仅此而已 

`async`函数对 Generator 函数的改进，体现在以下四点。

（1）内置执行器。

Generator 函数的执行必须靠执行器，所以才有了`co`模块，而`async`函数自带执行器。也就是说，`async`函数的执行，与普通函数一模一样，只要一行。

```javascript
asyncReadFile();
```

上面的代码调用了`asyncReadFile`函数，然后它就会自动执行，输出最后结果。这完全不像 Generator 函数，需要调用`next`方法，或者用`co`模块，才能真正执行，得到最后结果。

（2）更好的语义。

`async`和`await`，比起星号和`yield`，语义更清楚了。`async`表示函数里有异步操作，`await`表示紧跟在后面的表达式需要等待结果。

（3）更广的适用性。

`co`模块约定，`yield`命令后面只能是 Thunk 函数或 Promise 对象，而`async`函数的`await`命令后面，可以是 Promise 对象和原始类型的值（数值、字符串和布尔值，但这时会自动转成立即 resolved 的 Promise 对象）。

（4）返回值是 Promise。

`async`函数的返回值是 Promise 对象，这比 Generator 函数的返回值是 Iterator 对象方便多了。你可以用`then`方法指定下一步的操作。

进一步说，`async`函数完全可以看作多个异步操作，包装成的一个 Promise 对象，而`await`命令就是内部`then`命令的语法糖。

#### 2.基本用法:

`async`函数返回一个 Promise 对象，可以使用`then`方法添加回调函数。当函数执行的时候，==一旦遇到`await`就会先返回==，等到异步操作完成，再接着执行函数体内后面的语句。

下面是一个例子。

```javascript
async function getStockPriceByName(name) {
  const symbol = await getStockSymbol(name);
  const stockPrice = await getStockPrice(symbol);
  return stockPrice;
}

getStockPriceByName('goog').then(function (result) {
  console.log(result);
});
```

 上面代码是一个获取股票报价的函数，函数前面的`async`关键字，表明该函数内部有异步操作。调用该函数时，会立即返回一个`Promise`对象。 

### 6.super关键字：

Class 可以通过`extends`关键字实现继承，这比 ES5 的通过修改原型链实现继承，要清晰和方便很多。

```javascript
class Point {
}

class ColorPoint extends Point {
}
```

上面代码定义了一个`ColorPoint`类，该类通过`extends`关键字，继承了`Point`类的所有属性和方法。但是由于没有部署任何代码，所以这两个类完全一样，等于复制了一个`Point`类。下面，我们在`ColorPoint`内部加上代码。

```javascript
class ColorPoint extends Point {
  constructor(x, y, color) {
    super(x, y); // 调用父类的constructor(x, y)
    this.color = color;
  }

  toString() {
    return this.color + ' ' + super.toString(); // 调用父类的toString()
  }
}
```

上面代码中，`constructor`方法和`toString`方法之中，都出现了`super`关键字，它在这里表示父类的构造函数，用来新建父类的`this`对象。

子类必须在`constructor`方法中调用`super`方法，否则新建实例时会报错。这是因为子类自己的`this`对象，必须先通过父类的构造函数完成塑造，得到与父类同样的实例属性和方法，然后再对其进行加工，加上子类自己的实例属性和方法。如果不调用`super`方法，子类就得不到`this`对象。

```javascript
class Point { /* ... */ }

class ColorPoint extends Point {
  constructor() {
  }
}

let cp = new ColorPoint(); // ReferenceError
```

上面代码中，`ColorPoint`继承了父类`Point`，但是它的构造函数没有调用`super`方法，导致新建实例时报错。

ES5 的继承，实质是先创造子类的实例对象`this`，然后再将父类的方法添加到`this`上面（`Parent.apply(this)`）。ES6 的继承机制完全不同，实质是先将父类实例对象的属性和方法，加到`this`上面（所以必须先调用`super`方法），然后再用子类的构造函数修改`this`。

### 7.XSS攻击：

https://tech.meituan.com/2018/09/27/fe-security.html

#### 1.常用的XSS注入手段：

下面我们来系统的看下 XSS 有哪些注入的方法：

- 在 HTML 中内嵌的文本中，恶意内容以 script 标签形成注入。
- 在内联的 JavaScript 中，拼接的数据突破了原本的限制（字符串，变量，方法名等）。
- 在标签属性中，恶意内容包含引号，从而突破属性值的限制，注入其他属性或者标签。
- 在标签的 href、src 等属性中，包含 `javascript:` 等可执行代码。
- 在 onload、onerror、onclick 等事件中，注入不受控制代码。
- 在 style 属性和标签中，包含类似 `background-image:url("javascript:...");` 的代码（新版本浏览器已经可以防范）。
- 在 style 属性和标签中，包含类似 `expression(...)` 的 CSS 表达式代码（新版本浏览器已经可以防范）。

总之，==如果开发者没有将用户输入的文本进行合适的过滤，就贸然插入到 HTML 中==，这很容易造成注入漏洞。攻击者可以利用漏洞，构造出恶意的代码指令，进而利用恶意代码危害数据安全。

#### 2.什么是XSS:

 Cross-Site Scripting（跨站脚本攻击）简称 XSS，是一种代码注入攻击。攻击者通过在目标网站上注入恶意脚本，使之在用户的浏览器上运行。利用这些恶意脚本，攻击者可获取用户的敏感信息如 Cookie、SessionID 等，进而危害数据安全。 

**XSS 的本质是：恶意代码未经过滤，与网站正常的代码混在一起；浏览器无法分辨哪些脚本是可信的，导致恶意脚本被执行。**

而由于直接在用户的终端执行，恶意代码能够直接获取用户的信息，或者利用这些信息冒充用户向网站发起攻击者定义的请求。

#### 3.XSS分类：

 根据攻击的来源，XSS 攻击可分为存储型、反射型和 DOM 型三种。 

##### 1.存储型 XSS

存储型 XSS 的攻击步骤：

1. 攻击者将恶意代码提交到目标网站的**数据库**中。
2. 用户打开目标网站时，网站服务端将恶意代码从数据库取出，**拼接在 HTML 中**返回给浏览器。
3. 用户浏览器接收到响应后解析执行，混在其中的恶意代码也被执行。
4. 恶意代码窃取用户数据并发送到攻击者的网站，或者冒充用户的行为，调用目标网站接口执行攻击者指定的操作。

这种攻击常见于**带有用户保存数据**的网站功能，如论坛发帖、商品评论、用户私信等。

##### 2.反射型 XSS

反射型 XSS 的攻击步骤：

1. 攻击者构造出特殊的 **URL**，其中包含恶意代码。
2. 用户打开带有恶意代码的 URL 时，网站服务端将恶意代码从 URL 中取出，**拼接在 HTML 中**返回给浏览器。
3. 用户浏览器接收到响应后解析执行，混在其中的恶意代码也被执行。
4. 恶意代码窃取用户数据并发送到攻击者的网站，或者冒充用户的行为，调用目标网站接口执行攻击者指定的操作。

==反射型 XSS 跟存储型 XSS 的区别是：存储型 XSS 的恶意代码存在数据库里，反射型 XSS 的恶意代码存在 URL 里。==

反射型 XSS 漏洞常见于通过 URL 传递参数的功能，如网站搜索、跳转等。

由于需要用户主动打开恶意的 URL 才能生效，攻击者往往会结合多种手段诱导用户点击。

##### 3.DOM 型 XSS

DOM 型 XSS 的攻击步骤：

1. 攻击者构造出特殊的 URL，其中包含恶意代码。
2. 用户打开带有恶意代码的 URL。
3. 用户浏览器接收到响应后解析执行，前端 JavaScript 取出 URL 中的恶意代码并执行。
4. 恶意代码窃取用户数据并发送到攻击者的网站，或者冒充用户的行为，调用目标网站接口执行攻击者指定的操作。

DOM 型 XSS 跟前两种 XSS 的区别：DOM 型 XSS 攻击中，取出和执行恶意代码由浏览器端完成，属于前端 JavaScript 自身的安全漏洞，而其他两种 XSS 都属于服务端的安全漏洞。

#### 4.XSS攻击的预防：

XSS 攻击有两大要素：

1. 攻击者提交恶意代码。
2. 浏览器执行恶意代码。

##### 1.输入过滤：

 输入侧过滤能够在某些情况下解决特定的 XSS 问题，但会引入很大的不确定性和乱码问题。在防范 XSS 攻击时应避免此类方法。 

 当然，对于明确的输入类型，例如数字、URL、电话号码、邮件地址等等内容，进行输入过滤还是必要的。 

既然输入过滤并非完全可靠，我们就要通过“防止浏览器执行恶意代码”来防范 XSS。这部分分为两类：

- 防止 HTML 中出现注入。
- 防止 JavaScript 执行时，执行恶意代码。

##### 2.预防存储型和反射型 XSS 攻击

存储型和反射型 XSS 都是在服务端取出恶意代码后，插入到响应 HTML 里的，攻击者刻意编写的“数据”被内嵌到“代码”中，被浏览器所执行。

预防这两种漏洞，有两种常见做法：

- 改成纯前端渲染，把代码和数据分隔开。
- 对 HTML 做充分转义。

**纯前端渲染的过程：**

1. 浏览器先加载一个静态 HTML，此 HTML 中不包含任何跟业务相关的数据。
2. 然后浏览器执行 HTML 中的 JavaScript。
3. JavaScript 通过 Ajax 加载业务数据，调用 DOM API 更新到页面上。

 在很多内部、管理系统中，采用纯前端渲染是非常合适的。但对于性能要求高，或有 SEO 需求的页面，我们仍然要面对拼接 HTML 的问题。 

##### 3.转义 HTML

如果拼接 HTML 是必要的，就需要采用合适的转义库，对 HTML 模板各处插入点进行充分的转义

 要完善 XSS 防护措施，我们要使用更完善更细致的转义策略 

 HTML 的编码是十分复杂的，在不同的上下文里要使用相应的转义规则。 

##### 4.预防 DOM 型 XSS 攻击

DOM 型 XSS 攻击，实际上就是网站前端 JavaScript 代码本身不够严谨，把不可信的数据当作代码执行了。

在使用 `.innerHTML`、`.outerHTML`、`document.write()` 时要特别小心，不要把不可信的数据作为 HTML 插到页面上，==而应尽量使用 `.textContent`、`.setAttribute()` 等。==

如果用 Vue/React 技术栈，并且不使用 `v-html`/`dangerouslySetInnerHTML` 功能，就在前端 render 阶段避免 `innerHTML`、`outerHTML` 的 XSS 隐患。

DOM 中的内联事件监听器，如 `location`、`onclick`、`onerror`、`onload`、`onmouseover` 等，`` 标签的 `href` 属性，JavaScript 的 `eval()`、`setTimeout()`、`setInterval()` 等，都能把字符串作为代码运行。如果不可信的数据拼接到字符串中传递给这些 API，很容易产生安全隐患，请务必避免。

##### 5.其他 XSS 防范措施

虽然在渲染页面和执行 JavaScript 时，通过谨慎的转义可以防止 XSS 的发生，但完全依靠开发的谨慎仍然是不够的。以下介绍一些通用的方案，可以降低 XSS 带来的风险和后果。

###### 1.CSP

Content Security Policy

严格的 CSP 在 XSS 的防范中可以起到以下的作用：

- 禁止加载外域代码，防止复杂的攻击逻辑。
- 禁止外域提交，网站被攻击后，用户的数据不会泄露到外域。
- 禁止内联脚本执行（规则较严格，目前发现 GitHub 使用）。
- 禁止未授权的脚本执行（新特性，Google Map 移动版在使用）。
- 合理使用上报可以及时发现 XSS，利于尽快修复问题。

###### 2.输入内容长度控制

对于不受信任的输入，都应该限定一个合理的长度。虽然无法完全防止 XSS 发生，但可以增加 XSS 攻击的难度。

###### 3.其他安全措施

- HTTP-only Cookie: 禁止 JavaScript 读取某些敏感 Cookie，攻击者完成 XSS 注入后也无法窃取此 Cookie。
- 验证码：防止脚本冒充用户提交危险操作。

#### 6.XSS 的检测

1. 使用通用 XSS 攻击字符串手动检测 XSS 漏洞。
2. 使用扫描工具自动检测 XSS 漏洞。

#### 7.总结：

1.防范存储型和反射型 XSS 是后端 RD 的责任。而 DOM 型 XSS 攻击不发生在后端，是前端 RD 的责任。防范 XSS 是需要后端 RD 和前端 RD 共同参与的系统工程。 

2.转义应该在输出 HTML 时进行，而不是在提交用户输入时。

3.不同的上下文，如 HTML 属性、HTML 文字内容、HTML 注释、跳转链接、内联 JavaScript 字符串、内联 CSS 样式表等，所需要的转义规则不一致。 业务 RD 需要选取合适的转义库，并针对不同的上下文调用不同的转义规则。  

4.整体的 XSS 防范是非常复杂和繁琐的，我们不仅需要在全部需要转义的位置，对数据进行对应的转义。而且要防止多余和错误的转义，避免正常的用户输入出现乱码。

虽然很难通过技术手段完全避免 XSS，但我们可以总结以下原则减少漏洞的产生：

- **利用模板引擎** 开启模板引擎自带的 HTML 转义功能。例如： 在 ejs 中，尽量使用 `<%= data %>` 而不是 `<%- data %>`； 在 doT.js 中，尽量使用 `{{! data }` 而不是 `{{= data }`； 在 FreeMarker 中，确保引擎版本高于 2.3.24，并且选择正确的 `freemarker.core.OutputFormat`。
- **避免内联事件** 尽量不要使用 `onLoad="onload('{{data}}')"`、`onClick="go('{{action}}')"` 这种拼接内联事件的写法。在 JavaScript 中通过 `.addEventlistener()` 事件绑定会更安全。
- **避免拼接 HTML** 前端采用拼接 HTML 的方法比较危险，如果框架允许，使用 `createElement`、`setAttribute` 之类的方法实现。**或者采用比较成熟的渲染框架，如 Vue/React 等。**
- **时刻保持警惕** 在插入位置为 DOM 属性、链接等位置时，要打起精神，严加防范。
- **增加攻击难度，降低攻击后果** 通过 CSP、输入长度配置、接口安全措施等方法，增加攻击的难度，降低攻击的后果。
- **主动检测和发现** 可使用 XSS 攻击字符串和自动扫描工具寻找潜在的 XSS 漏洞。

### 8.CSRF攻击：

https://tech.meituan.com/2018/10/11/fe-security-csrf.html

 CSRF（Cross-site request forgery）**跨站请求伪造**：攻击者诱导受害者进入第三方网站，在第三方网站中，向被攻击网站发送跨站请求。利用受害者在被攻击网站已经获取的注册凭证，绕过后台的用户验证，达到冒充用户对被攻击的网站执行某项操作的目的。 

#### 1.CSRF的特点

- 攻击一般发起在第三方网站，而不是被攻击的网站。被攻击的网站无法防止攻击发生。
- 攻击利用受害者在被攻击网站的登录凭证，冒充受害者提交操作；而不是直接窃取数据。
- 整个过程攻击者并不能获取到受害者的登录凭证，仅仅是“冒用”。
- 跨站请求可以用各种方式：图片URL、超链接、CORS、Form提交等等。部分请求方式可以直接嵌入在第三方论坛、文章中，难以进行追踪。

CSRF通常是==跨域==的，因为外域通常更容易被攻击者掌控。但是如果本域下有容易被利用的功能，比如可以发图和链接的论坛和评论区，攻击可以直接在本域下进行，而且这种攻击更加危险。

#### 2.防护策略

CSRF通常从第三方网站发起，被攻击的网站无法防止攻击发生，只能通过增强自己网站针对CSRF的防护能力来提升安全性。

CSRF的两个特点：

- CSRF（通常）发生在第三方域名。
- CSRF攻击者不能获取到Cookie等信息，只是使用。

针对这两点，我们可以专门制定防护策略，如下：

- 阻止不明外域的访问

  - 同源检测
  - Samesite Cookie

- 提交时要求附加本域才能获取的信息

  - CSRF Token
  - 双重Cookie验证

  ##### 1.同源检测

  既然CSRF大多来自第三方网站，那么我们就直接禁止外域（或者不受信任的域名）对我们发起请求。

#### 防护策略总结

简单总结一下上文的防护策略：

- CSRF自动防御策略：同源检测（Origin 和 Referer 验证）。
- CSRF主动防御措施：Token验证 或者 双重Cookie验证 以及配合Samesite Cookie。
- 保证页面的幂等性，后端接口不要在GET页面中做用户操作。

为了更好的防御CSRF，最佳实践应该是结合上面总结的防御措施方式中的优缺点来综合考虑，结合当前Web应用程序自身的情况做合适的选择，才能更好的预防CSRF的发生。

### 9.Symbol：

https://es6.ruanyifeng.com/#docs/symbol

#### 1.概述：

ES6 引入了一种新的原始数据类型`Symbol`，表示独一无二的值。它是 JavaScript 语言的第七种数据类型，前六种是：`undefined`、`null`、布尔值（Boolean）、字符串（String）、数值（Number）、对象（Object）。

Symbol 值通过`Symbol`函数生成。这就是说，**对象的属性名现在可以有两种类型，一种是原来就有的字符串，另一种就是新增的 Symbol 类型**。凡是属性名属于 Symbol 类型，就都是独一无二的，可以保证不会与其他属性名产生冲突。

 `Symbol`函数前不能使用`new`命令，否则会报错。这是因为生成的 Symbol 是一个原始类型的值，不是对象。也就是说，由于 Symbol 值不是对象，所以不能添加属性。基本上，它是一种类似于字符串的数据类型。 

#### 2.内置的 Symbol 值 [§](https://es6.ruanyifeng.com/#docs/symbol#内置的-Symbol-值) [⇧](https://es6.ruanyifeng.com/#docs/symbol)

除了定义自己使用的 Symbol 值以外，ES6 还提供了 11 个内置的 Symbol 值，指向语言内部使用的方法。

##### 1.Symbol.hasInstance

对象的`Symbol.hasInstance`属性，指向一个内部方法。当其他对象使用`instanceof`运算符，判断是否为该对象的实例时，会调用这个方法。比如，`foo instanceof Foo`在语言内部，实际调用的是`Foo[Symbol.hasInstance](foo)`。

##### 2.Symbol.iterator

对象的`Symbol.iterator`属性，指向该对象的默认遍历器方法。

```javascript
const myIterable = {};
myIterable[Symbol.iterator] = function* () {
  yield 1;
  yield 2;
  yield 3;
};

[...myIterable] // [1, 2, 3]
```

对象进行`for...of`循环时，会调用`Symbol.iterator`方法，返回该对象的默认遍历器

### 10.localStorage

https://segmentfault.com/a/1190000010400892

https://segmentfault.com/a/1190000018748168?utm_source=sf-related

#### 1.介绍：

在HTML5发布后，提供了一种新的客户端本地保存数据的方法，那就是Web Storage，它也被分为：LocalStorage和SessionStorage，它允许通过JavaScript在Web浏览器中以键值对的形式保存数据。而相比Cookie有如下优点：

1. 拥有更大的存储容量，Cookie是4k，Web Storage为5M。
2. 操作数据相比Cookie更简单。
3. 不会随着每次请求发送到服务端。

#### 2.LocalStorage与SessionStorage的区别

LocalStorage和SessionStorage之间的主要区别在于浏览器窗口和选项卡之间的数据共享方式不同。

LocalStorage可跨浏览器窗口和选项卡间共享。就是说如果在多个选项卡和窗口中打开了一个应用程序，而一旦在其中一个选项卡或窗口中更新了LocalStorage，则在所有其他选项卡和窗口中都会看到更新后的LocalStorage数据。

但是，SessionStorage数据独立于其他选项卡和窗口。如果同时打开了两个选项卡，其中一个更新了SessionStorage，则在其他选项卡和窗口中不会反映出来。举个例子：假设用户想要通过两个浏览器选项卡预订两个酒店房间。由于这是单独的会话数据，因此使用SessionStorage是酒店预订应用程序的理想选择。

您可以根据您的使用情况选择LocalStorage与SessionStorage。如果您的应用程序需要在多个浏览器窗口和标签页中共享数据，请使用LocalStorage，否则请使用SessionStorage。

SessionStorage和LocalStorage都容易受到XSS攻击。因此，请避免将敏感数据存储在浏览器存储中。

最后，虽然WebStorage很好用，还是建议你在如下的情况下使用：

- 没有敏感数据
- 数据尺寸小于 5MB
- 高性能并不重要

### 11.HTTP/2：

http://www.ruanyifeng.com/blog/2016/08/http.html

### 12.HTTPS/TLS

http://www.ruanyifeng.com/blog/2014/02/ssl_tls.html

### 13.缓存：

https://github.com/amandakelake/blog/issues/43

### 14.webpack:

https://juejin.cn/post/6844903781847695367

### 15.防抖节流：

防抖// 第一版
```js
function debounce(func, wait) { 
    var timeout;
    return function () {
        clearTimeout(timeout)
        timeout = setTimeout(func, wait);
    }
}
```

节流

// 第一版

```js
function throttle(func, wait) {
    var context, args;
    var previous = 0;
return function() {
    var now = +new Date();
    context = this;
    args = arguments;
    if (now - previous > wait) {
        func.apply(context, args);
        previous = now;
    }
}
```
}

### 16.computed和watch的区别：

 答：
首先，computed 和 watch都可以添加实现监听。
其次，我去从他们的本质和运用场景区分一下他们。

第一个方面就是从本质来说：
computed： 它是计算属性，依赖其它属性值，并且 computed 的==值有缓存==，只有它依赖的属性值发生改变，下一次获取 computed 的值时才会重新计算 computed 的值，它可以设置getter和setter.

watch： 更多的是「观察」的作用，类似于某些数据的监听回调 ，每当监听的数据变化时都会执行回调进行后续操作,它只能设置getter。

第二个方面就是他们的运用场景不同：
computed：当我们==需要进行数值计算==，并且依赖于其它数据时，应该使用 computed，因为可以利用 computed 的缓存特性，避免每次获取值时，都要重新计算；
watch：当我们需要在数据变化时执行异步或开销较大的操作时，应该使用 watch，使用 watch 选项允许我们执行异步操作 ( 访问一个 API )，限制我们执行该操作的频率，并在我们得到最终结果前，设置中间状态。这些都是计算属性无法做到的。 

### 17.进程与线程

http://www.ruanyifeng.com/blog/2013/04/processes_and_threads.html

