# App

## web-app
  能完成特定功能的网页
  运行在浏览器中。
## hybrid app
  嵌入到应用中的网页
  [Android Webview](https://developer.android.com/reference/android/webkit/WebView)
  
## native-app
 手机端应用
###  Android  
 Java 语言
###  Ios  
 Objective-C 语言 
 
## 跨平台解决方案

> [React Native - 中文网](https://reactnative.cn/)  和facebook相关 技术栈 react；使用JavaScript和React编写原生移动应用

> [Weex](http://weex.apache.org/cn/guide/)  和阿里相关，技术栈vue ； 使用 JavaScript 和现代流行的前端框架来开发移动应用

> [Flutter](https://flutterchina.club/)  和谷歌相关,dart语言,这......

## 三大前端框架
> 克服HTML在构建应用上的不足而设计的框架

### React

> [ReactJs-中文网](https://reactjs.org.cn/)

### Vue

> [VueJs-中文网](https://cn.vuejs.org/)

### AngularJS

> [AngularJs-中文网](http://www.angularjs.net.cn/)

## 单页应用与多页应用

### 单页应用
> 就是只有一张Web页面的应用，是加载单个HTML页面并在用户与应用交互时动态更新该页面的web应用程序 。 浏览器一开始会加载必需的HTML、CSS和JavaScript，所有的操作都在这张页面上完成，都由JavaScript来控制。因此，对单页应用来说模块化的开发和设计显得相当重要。 —— 来自[百度百科](https://baike.baidu.com/item/SPA/17536313?fr=aladdin) 

**特点** ： 速度、MVVM、ajax重前端、路由（在URL中采用#号来作为当前视图的地址,改变#号后的参数，页面并不会重载。）
**优点** ： 传输数据少（不会频繁更新的代码由前端直接缓存起来），局部刷新服务可以不中断， 前端可按mvc的模式更好地模块化开发
**缺点** ： 首次加载数据大耗时长，极差的SEO，导航需要人为处理（页面前进后退） 


某些浏览器具备一些高级特性，可以提高web应用的用户体验

**相关博客文档**： 

[关于单页应用（SPA）的经验之谈 ](http://www.360doc.com/content/17/0715/10/9200790_671477938.shtml) 该文档中有讲解使用iframe 制作单页应用的代码讲解，这个是很早的一种解决方案。里面关于解决历史回退问题比较有意思。

[web单页应用是什么？它的好处与坏处有哪些（如何解决这些缺点）](http://www.fly63.com/article/detial/286) 该博客列举单页应用的好处时提到服务器不用管展示逻辑和页面合成**吞吐能力会提高几倍**。而且不会出现页面之间切换时出现的“白屏、假死、闪烁现象”。使用iframe在窗体内切换页面会有这些问题，所以新的三大框架的出现可以解决这些问题？ 但首次加载单页应用首屏渲染时间比其他的长.....

1、首次加载耗时比较多：可以采用基于[HTTP Chunk](https://blog.csdn.net/xifeijian/article/details/42921827)的首屏数据渐进式加载方案.
2、 seo问题：可以采用prerender服务 （服务端预渲染，在服务端的一个js 引擎把内容填充完之后再广播给爬虫phantomjs）
3、css命名冲突：使用css预处理，css命名规范
4、 前进、后退、地址栏、书签：使用程序进行管理
