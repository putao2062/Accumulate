# Webpack 入门 Readme

**更新npm**

npm install - g npm

**安装webpack-cli**

管理员身份运行cmd 

npm install --save-dev wepack-cli



```
npm install --save lodash
```

## 安装 出错

更新了nodejs 

> 解决 [NPM Unexpected end of JSON input while parsing near](https://blog.csdn.net/qq_38372358/article/details/79551446) 
>
> first:
>
> ```
> npm install --registry=https://registry.npm.taobao.org --loglevel=silly
>
> ```
>
> then:
>
> ```
> npm cache clean --force
> ```

**卡在checking installable status**

> [卡在checking installable status](https://blog.csdn.net/u011215669/article/details/80470674)

打开资源管理器，地址栏输入 
`C:\Users\用户名\AppData\Roaming`

> 这里需要根据自己用户名修改路径

回车进入npm目录 
找到**npm**和**npm-cache**两个文件夹删除 

重新打开终端尝试npm下载。问题解决

```
npm install -g cnpm --registry=http://r.cnpmjs.org
```

## 设置npm的registry

[设置npm的registry](https://www.cnblogs.com/sghy/p/6840925.html)

1.原npm地址   **有用**

```
npm config set registry http://registry.npmjs.org 
```


 运行`npx webpack`我们的脚本[切入点](https://webpack.js.org/concepts/entry-points)，并`bundle.js`作为[输出](https://webpack.js.org/concepts/output)

## 创建一个包

要将`lodash`依赖关系捆绑在一起`index.js`，我们需要在本地安装库：

```
npm install --save lodash
```

## 模块

import  和  export   

大多数浏览器中都不受支持，但webpack确实支持它们，内部进行了转译

## 使用配置

不使用配置的时候，可以在package.json 中定义`main` 属性，指定入口的js 文件是哪个，

然后在命令行中输入 npx webpack

普通的index.html文档 中的`<script>`标签通过 前后顺序加载，后加载的脚本可调用先加载的脚本的函数，有这种调用关系则这些` <script>` 标签之间存在隐式依赖关系 



**以这种方式管理JavaScript 的问题：**

1、脚本依赖于外部库，但没有明确的信息表明他们的依赖，所以不是显而易见的

2、如果依赖脚本文件缺失或 前后顺序错误，就会导致程序无法执行

3、如果包含依赖文件，却没有使用，则浏览器会被迫下载这些不不要的代码。



**所以使用webpack 可以解决的问题有：**

1、明确脚本之前的依赖关系

2、不用担心脚本缺失和顺序错误导致的bug

3、应用中不包含未使用的脚本 减少浏览器不必要的工作。 

**不使用webpack之前的方案是什么**

1、注意顺序，写好注释，

2、使用 require.js 



#### 使用--config 标志通过 命令行更改配置



运行构建，而是使用我们的新配置文件

```
npx webpack --config webpack.config.js
```

## 配置入口

几种方式：

## 配置出口

`output`webpack配置中属性的最低要求是将其值设置为一个对象，其中包括以下两件事：

- A `filename`用于输出文件。
- 绝对`path`到您的首选输出目录。

## 加载CSS

```
npm install --save-dev style-loader css-loader
```

webpack使用正则表达式来确定应该查找哪些文件并将其提供给特定的加载程序。在这种情况下，任何以文件结尾的文件`.css`将被提供给`style-loader`和`css-loader`。 

```
npm run build
```

## 加载图片

```
npm install --save-dev file-loader
```

## 加载数据中

```
npm install --save-dev csv-loader xml-loader
```

# 输出管理

配置 output 

## 设置HtmlWebpackPlugin

```
npm install --save-dev html-webpack-plugin
```

在构建之前，您应该知道`HtmlWebpackPlugin`默认情况下会生成自己的`index.html`文件，即使我们已经在`dist/`文件夹中有一个文件。这意味着它会用`index.html`新生成的文件替换我们的文件

## 清理`/dist`文件夹

```
npm install clean-webpack-plugin --save-dev
```

# 开发

## 使用源地图

### 使用webpack-dev-server

```
npm install --save-dev webpack-dev-server
```

### 使用webpack-dev-middleware

```
npm install --save-dev express webpack-dev-middleware
```

### 

## 启用HMR

 [webpack hot-module-replacement 原理&踩坑](https://segmentfault.com/a/1190000010796038)

**问题：**这个用处是啥？   可以用刷新浏览器解决的问题，为何使用这个     用于开发的时候用  

# 热模块更换

- 保留完整重新加载期间丢失的应用程序状态。
- 只需更新已更改的内容，节省宝贵的开发时间。
- 调整样式的速度更快 - 几乎可以与浏览器的调试器中的样式相比。



# 生产

*开发*和*生产*的目标差异很大。在*开发中*，我们希望强大的源映射和本地主机服务器的实时重载或热模块替换。在*生产中*，我们的目标转向专注于缩小捆绑，更轻量级源图和优化资产以缩短加载时间。通过这种逻辑分离，我们通常建议为每个环境编写**单独的webpack配置**。  

虽然我们会将*生产*和*开发的*具体数据分离出来，但请注意，我们仍然保持“常见”配置，以保持干燥。为了将这些配置合并到一起，我们将使用一个名为的实用程序[`webpack-merge`](https://github.com/survivejs/webpack-merge)。通过使用“通用”配置，我们不必在环境特定的配置中复制代码。



```
npm install --save-dev webpack-merge
```



