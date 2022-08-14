# webpack-quickstart

webpack入门应用

> 官网: [https://webpack.docschina.org/](https://webpack.docschina.org/)

## webpack

webpack 是一个用于现代 JavaScript 应用程序的 静态模块打包工具

## 核心

> - 入口(entity)
> - 输出(output)
> - loader
> - 插件(plugin)
> - 模式（mode)
> - 浏览器兼容性
> - 环境

## 快速入门

- 前提

在开始之前，请确保安装了 Node.js 的最新版本

- 安装webpack

```
npm init -y
npm install webpack webpack-cli --save-dev
```

> webpack: 用于编译 JavaScript 模块
> 
> webpack-cli: 此工具用于在命令行中运行 webpack

- 创建目录

```
project
|- package.json
|- webpack.config.js
|- /dist
    |- index.html
|- /src
    |- index.js
```

- webpack.config.js 配置

```
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```

- npm 脚本

考虑到用 CLI 这种方式来运行本地的 webpack 不是特别方便，我们可以设置一个快捷方式。在 package.json 添加一个 npm 脚本(npm script)：

```
{
  "name": "webpack-quickstart",
  "version": "1.0.0",
  "description": "webpack入门应用",
  "private": true,
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack --config webpack.config.js"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/yangjianzhi22/webpack-quickstart.git"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/yangjianzhi22/webpack-quickstart/issues"
  },
  "homepage": "https://github.com/yangjianzhi22/webpack-quickstart#readme",
  "devDependencies": {
    "webpack": "^5.74.0",
    "webpack-cli": "^4.10.0"
  },
  "dependencies": {
    "lodash": "^4.17.21"
  }
}
```

- 测试

使用npm run build命令， 现在运行以下命令，然后看看你的脚本别名是否正常运行：

![1](/docs/1.png)

> 在浏览器中打开 index.html，如果一切访问都正常，你应该能看到以下文本：'Hello webpack'。

![2](/docs/2.png)
