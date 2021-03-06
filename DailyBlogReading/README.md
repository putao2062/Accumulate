# Daily Blog Reading

## 宝藏博客

1. [从html5Canvas海草舞代码解读中发现的github链接继而找到的博客](https://rosszurowski.com/)   沉稳风格英文
2. [从百度webpack不适用的场景阅读转载博客时发现的博客](http://refined-x.com/)  简约黑白风格 中文
3. [持续部署单页应用的7大技巧](https://blog.codeship.com/continuously-deploying-single-page-apps/) 国外的一个博客网，其中的一篇博客
4. [小火柴前端手册](https://xiaohuochai.site/) [小火柴前端小站](https://www.xiaohuochai.cc/) [小火柴博客-博客园](https://www.cnblogs.com/xiaohuochai/)  搜全屏布局时找到的博客，博客博文风格有趣，详实。

## 前端收藏夹

1. [front-end-collect](https://github.com/foru17/front-end-collect) 
2. [f2e-awesome-knowledge](https://github.com/f2e-awesome/knowledge) 
3. [前端涉及的所有知识体系](https://blog.csdn.net/fair_feng/article/details/72865140) 
4. [TypeScript + 大型项目实战](https://www.imooc.com/article/47096)

## 多读几遍

## 博客阅读记录

### 2018/09/02

> [Webpack是答案吗--不适合打包的场景-博客园](https://www.cnblogs.com/videring/articles/7096524.html)

这是一篇转载博客，之所以留下上面的链接，是因为该博客的一二级标题经过了美化，直观上更容易让阅读者分清文章的主次。

> [Webpack是答案吗--不适合打包的场景-原作者](http://refined-x.com/2017/06/16/Webpack%E6%98%AF%E7%AD%94%E6%A1%88%E5%90%97/)

这篇是原作者的博客链接，之所以留下该链接，是因为这个作者有自己的博客网站，有自己的开源作品，他的个人简介十分简洁，这应该是个**宝藏博客**，应该多去学习。

这个博客的UI风格十分简洁，这应该是我第二次无目的地从其他地方进入的博客，所以宝藏+1

### 2018/09/06

> [说说RESTFUL中的方法：GET、POST、PUT、PATCH、DELETE、OPTIONS、HEAD、TRACE-csdn](https://blog.csdn.net/mingjia1987/article/details/79651241)

  从5月初参加一个开发者大会听主持人讲架构的时候了解到了RESTFUL架构，今天在百科里面看CORS时又见到了“get/post/put/delete请求”所以真的需要再去了解下restful，希望下次遇到不要再有陌生感。
  
  **REST**: Representational State Transfer 是指一组软件架构设计约束，它们带来了高效，可靠和可扩展的分布式系统。当一个系统遵守这些约束时，它就被称为RESTful。
  
  > [RESTful 架构详解-runoob](https://www.runoob.com/w3cnote/restful-architecture.html)  
  
  > HTTP的响应代码可用于应付不同场合，正确使用这些状态代码意味着客户端与服务器可以在一个具备较丰富语义的层次上进行沟通。
    例如，201（"Created"）响应代码表明已经创建了一个新的资源，其URI在Location响应报头里。
    假如你不利用HTTP状态代码丰富的应用语义，那么你将错失提高重用性、增强互操作性和提升松耦合性的机会。
    

  > [https://www.restapitutorial.com/](https://www.restapitutorial.com/) 这网站致力于跟踪REST API最佳实践并提供可用
  
  > [http://restcookbook.com/](http://restcookbook.com/) REST并不像初看起来那么容易。处理HATEOAS 按需代码和统一接口可能非常棘手
  
  ### 2018/09/07
  
  > [初识Spring HATEOAS-csdn](https://blog.csdn.net/i_forever/article/details/80635470) 
  
  在restcookbook站点浏览 [Mediatypes](http://restcookbook.com/Mediatypes/json/)时，看到REST的一个关键约束是RESTful API 必须使用超媒体格式（HATEOAS约束）。为了明白HATEOAS约束所以搜到了上面那篇博文
  
  > **REST约束：** 
 1.  **客户端-服务器结构**。通过一个统一的接口来分开客户端和服务器，使得两者可以独立开发和演化。客户端的实现可以简化，而服务器可以更容易的满足可伸缩性的要求。
 
2. **无状态**。在不同的客户端请求之间，服务器并不保存客户端相关的上下文状态信息。任何客户端发出的每个请求都包含了服务器处理该请求所需的全部信息。

3. **可缓存**。客户端可以缓存服务器返回的响应结果。服务器可以定义响应结果的缓存设置。

4. **分层的系统**。在分层的系统中，可能有中间服务器来处理安全策略和缓存等相关问题，以提高系统的可伸缩性。客户端并不需要了解中间的这些层次的细节。

5. **按需代码（可选）**。服务器可以通过传输可执行代码的方式来扩展或自定义客户端的行为。这是一个可选的约束。

6. **统一接口**。该约束是 REST 服务的基础，是客户端和服务器之间的桥梁。该约束又包含下面 4 个子约束。

   1.  **资源标识符**。每个资源都有各自的标识符。客户端在请求时需要指定该标识符。在 REST 服务中，该标识符通常是 URI。客户端所获取的是资源的表达（representation），通常使用 XML 或 JSON 格式。
   
   2. **通过资源的表达来操纵资源**。客户端根据所得到的资源的表达中包含的信息来了解如何操纵资源，比如对资源进行修改或删除。
   
   3. **自描述的消息**。每条消息都包含足够的信息来描述如何处理该消息。
   
   4. **超媒体作为应用状态的引擎（HATEOAS）**。客户端通过服务器提供的超媒体内容中动态提供的动作来进行状态转换。这也是本文所要介绍的内容。
  
  ### 2018/09/11
  
  > [关于单页应用（SPA）的经验之谈——360doc ](http://www.360doc.com/content/17/0715/10/9200790_671477938.shtml) 
  
  该文档中有讲解使用iframe 制作单页应用的代码讲解，这个是很早的一种解决方案。里面关于解决历史回退问题比较有意思。

  > [web单页应用是什么？它的好处与坏处有哪些（如何解决这些缺点）](http://www.fly63.com/article/detial/286) 

  该博客列举单页应用的好处时提到服务器不用管展示逻辑和页面合成**吞吐能力会提高几倍**。而且不会出现页面之间切换时出现的“白屏、假死、闪烁现象”。使用   iframe在窗体内切换页面会有这些问题，所以新的三大框架的出现可以解决这些问题？ 
  
  之前的web产品是由后端负责模板渲染，输出页面工作。单页应用前后端分离使得后端的API通用化，同一套后端程序代码，不用修改就可以用于Web界面、手机、平板等多种客户端。
  
  > [HTML渲染过程详解——博客园](https://www.cnblogs.com/dojo-lzz/p/3983335.html) 
  
  看完这篇博客又重温了一下浏览器渲染页面的过程。该作者的博文里有相关控制台network 瀑布流的截图，可以看看。关于浏览器的渲染工作以及了解，那么再去看服务端渲染做了哪些工作。（此渲染和彼渲染的区别需要深入了解下，实在不行以后相关的术语就都用英文进行记录）
  
  **客户端渲染和服务器端渲染的区别**
  > 客户端渲染路线：1. 请求一个html -> 2. 服务端返回一个html -> 3. 浏览器下载html里面的js/css文件 -> 4. 等待js文件下载完成 -> 5. 等待js加载并初始化完成 -> 6. js代码终于可以运行，由js代码向后端请求数据( ajax/fetch ) -> 7. 等待后端数据返回 -> 8. 客户端从无到完整地，把数据渲染为响应页面

  > 服务端渲染路线：2. 请求一个html -> 2. 服务端请求数据( 内网请求快 ) -> 3. 服务器初始渲染（服务端性能好，较快） -> 4. 服务端返回已经有正确内容的页面 -> 5. 客户端请求js/css文件 -> 6. 等待js文件下载完成 -> 7. 等待js加载并初始化完成 -> 8. 客户端把剩下一部分渲染完成( 内容小，渲染快 )
  
  看完上面两段渲染流程之后，其区别就在于向服务器请求页面的时候，服务器返回的HTML文档是否是准备好并且完整的。嗯，姑且这么理解吧......
 
  ### 2018/12/14 
   > [用JSON-server模拟REST API ](https://www.cnblogs.com/ys-wuhan/p/6387791.html) 
   
   使用json-server 模拟api
