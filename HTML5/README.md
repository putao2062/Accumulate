# HTML5

## HTML5新增标签兼容性处理

>原理：低版本浏览器下使用 DOM操作创建标签  
>参考链接：[HTML5新标签的兼容性处理](https://www.cnblogs.com/kaizi/p/7245517.html)

```
docment.createElement('header');
```

**已有库：** [html5shiv.js](https://github.com/aFarkas/html5shiv)

## HTML5中属于单独的规范和工作组的技术

### SVG 

### Web 储存

> sessionStorage 与 localStorage 
> Session储存用来储存当前浏览器会话
> Local储存 用来对网站收藏或其他用户数据进行长期储存。还可以监听储存事件，以便监控储存活动并对储存活动作出响应。

**Web储存跨浏览器解决方案：** [PersistJS](https://github.com/jeremydurham/persist-js)

### IndexedDB
> IndexedDB 提供了更强大的在浏览器中长期储存数据的功能，包含查询数据上，可以储存复杂对象

### Web Workers 
> 在主页运行Javascript 的同事可以让用户在底层运行脚本。 可以将时间较长的任务放到底层进程，从而释放浏览器，可以在主要环境中进行持续的交互 

### File API
> 此规范提供了操作Web 应用程序中文件的API 。 XMLHttpRequest 、拖放 和 Web Workers 。  File API 允许直接访问浏览器文件数据

### WebSocket 
>WebSocket API 可以通过一个 TCP 端口在 Web 浏览器和 Web 服务器之间同时双向通讯

**跨浏览器解决方案：** [soketio](https://github.com/socketio/socket.io)

### WebGL 
> Web-based Graphics Library (WebGL) 增强了JavaScript，它具有在浏览器中创建三维交互图形的功能。WebGL 是 canvas HTML 元素的上下文。

**相关库：** [Three.js](https://github.com/mrdoob/three.js)

### XMLHttpRequest Level 2
> XMLHttpRequest Level 2 规范通过一些新特性增强了核心 XMLHttpRequest 对象。其中最有趣的大概就是 Cross-Origin Resource Sharing 了，它一种绕过同源安全策略的安全方式，可以实现 XMLHttpRequest 与第三方服务器交互。

## HTML5中新事件属性
> onabort, onbeforeunload, oncontextmenu, ondrag, ondragend, ondragenter, ondragleave, ondragover, ondragstart, ondrop, onerror, onmessage, onmousewheel, onresize, onscroll, onunload。

## HTML5中的新属性
> HTML 5标签中的新属性有：contenteditable, contextmenu, draggable, irrelevant, ref,registrationmark, template
