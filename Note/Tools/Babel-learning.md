# Babel-learning

### 1.安装

```powe
npm install --save-dev @babel/cli @babel/core @babel/preset-env
```

使用

```powershell
# 单个文件转码
npx babel main.js -o compiled.js 
# (main.js 是需要编译的文件，compiled 是编译后的文件) 
# 整个目录转码
npx babel src -d lib
# -s 参数生成source map文件
$ npx babel src -d lib
```

attention： Babel默认只转换新的JavaScript语法（syntax），而不转换新的 API。

如果想让ES6新的API在低版本浏览器正常运行，我们就不能只做语法转换。

在前端web工程里，最常规的做法是使用polyfill，为当前环境提供一个垫片。所谓垫片，是指垫平不同浏览器之间差异的东西。polyfill提供了全局的ES6对象以及通过修改原型链Array.prototype等实现对实例的实现。

polyfill广义上讲是为环境提供不支持的特性的一类文件或库 （[姜瑞涛-babel教程](https://www.jiangruitao.com/babel/use-polyfill/)）

安装 polyfill

```powershell
 npm install --save-dev core-js regenerator-runtime
```

在脚本头部添加代码

```js
require('core-js');
require('regenerator-runtime/runtime');
```

### 2.babel 配置

几种配置方式：

- .babelrc
- .babelrc.js
- .babel.config.js
- 在 package.json 种添加 'babel' : { } 配置项

.babelrc 文件内容如下

```js
 {
    "presets": ["es2015", "react"],
    "plugins": ["transform-decorators-legacy", "transform-class-properties"]
  }
```

presets 预设数组是一组 babel 插件的集合，这里的 'es2015' 全称是 '@babel/preset-es2015'

每个插件或者预设就是一个 npm 包，都需要先安装才能使用

执行顺序：

- 插件比预设先执行
- 插件从前向后执行
- 预设从后向前执行

