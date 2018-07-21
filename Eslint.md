### Local Installation and Usage
> 如果你想让 ESLint 成为你项目构建系统的一部分，我们建议在本地安装。你可以使用 npm：

````
$ npm install eslint --save-dev
紧接着你应该设置一个配置文件：

$ ./node_modules/.bin/eslint --init
之后，你可以在你项目根目录运行 ESLint：

$ ./node_modules/.bin/eslint yourfile.js
使用本地安装的 ESLint 时，你使用的任何插件或可分享的配置也都必须在本地安装。
````
### Global Installation and Usage
> 如果你想使 ESLint 适用于你所有的项目，我们建议你全局安装 ESLint。你可以使用 npm：

````
$ npm install -g eslint
紧接着你应该设置一个配置文件：

$ eslint --init
之后，你可以在任何文件或目录运行 ESLint：

$ eslint yourfile.js
````

### 命令行

````
npm i -g eslint
这句命令从 npm 仓库安装了 ESLint CLI。使用以下格式运行 ESLint：

eslint [options] [file|dir|glob]*
比如：

eslint file1.js file2.js
或者：

eslint lib/**
````

### 配置

````
module.exports = {
  // 默认情况下，ESLint会在所有父级组件中寻找配置文件，一直到根目录。ESLint一旦发现配置文件中有 "root": true，它就会停止在父级目录中寻找。
  root: true,
  // 对Babel解析器的包装使其与 ESLint 兼容。
  parser: 'babel-eslint',
  parserOptions: {
    // 代码是 ECMAScript 模块
    sourceType: 'module'
  },
  env: {
    // 预定义的全局变量，这里是浏览器环境
    browser: true,
  },
  // 扩展一个流行的风格指南，即 eslint-config-standard
  // https://github.com/feross/standard/blob/master/RULES.md#javascript-standard-style
  extends: 'standard',
  // required to lint *.vue files
  plugins: [
    // 此插件用来识别.html 和 .vue文件中的js代码
    'html',
    // standard风格的依赖包
    "standard",
    // standard风格的依赖包
    "promise"
  ],
  // add your custom rules here
  'rules': {
    // allow paren-less arrow functions
    'arrow-parens': 0,
    // allow async-await
    'generator-star-spacing': 0,
    // allow debugger during development
    'no-debugger': process.env.NODE_ENV === 'production' ? 2 : 0
  }
}
````

### 官网自定义配置

[可以自己搭配，然后下载配置文件](http://eslint.cn/demo/)

### 操作过程中的一些命令
> 因为是局部安装的Eslint所以需要进入到./node_modules/.bin/eslint如下目录去执行命令

> 初始化Eslint
````
./node_modules/.bin/eslint --init
````
> /**表示匹配到子层目录，*.js 表示匹配任意js结尾的文件
````
./node_modules/.bin/eslint ./alipay-saas-web/sass-ui/browser/pages/**/*.js
````
> 根据匹配规则修复文件
````
./node_modules/.bin/eslint --fix  ./alipay-saas-web/sass-ui/browser/pages/index/indexService.js
````
> 检查单一文件
````
./node_modules/.bin/eslint ./alipay-saas-web/sass-ui/browser/pages/index/index.js
````
