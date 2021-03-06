# Vue 

> [vue 中文官网](https://cn.vuejs.org/) 

> [vue.js教程-菜鸟教程](http://www.runoob.com/vue2/vue-tutorial.html)  简单易懂 可用来快速熟悉vue相关语法

> [vue router](https://router.vuejs.org/zh/) vue 路由

> [vuex](https://vuex.vuejs.org/zh/guide/)  vue 状态（state）  

> [vue-cli](https://cli.vuejs.org/zh/) vue.js开发的标准工具


## vue 官网示例

> [vue 官网示例](https://cn.vuejs.org/v2/examples/)，官方给了12个vue的应用示例

1. **[Markdown 编辑器](https://cn.vuejs.org/v2/examples/index.html)**

   简单的一个多文本表单，一个输出内容的`div `；
   
   表单值属性初始值已定为data中的某个值，监听多文本表单的`input`事件；
   
   `div`的`v-html`指令输出`html`代码，其值为计算属性，其逻辑中引用多文本表单的值;
   
   用户在多文本表单中编辑，触发`input`的事件，事件处理函数对data中的某个值进行动态赋值，
   data中的值改变，计算属性的相关依赖发生改变而重新取值，计算属性改变，`div`中的`html`重新渲染
   
2. **[GitHub提交](https://cn.vuejs.org/v2/examples/commits.html)**

   >这个例子从 Github 的 API 中获取了最新的 Vue.js 提交数据，并且以列表形式将它们展示了出来。你可以轻松地切换 master 和 dev 分支。
   
   一个一级标题，一个单选表单的模板`template`，一个段落，一个`ul`列表
   
   data中预定义branches数组，储存分支名称，单选表单模板中使用`v-for`指令根据branches数组输出单选`input`表单和对应`label` ;
   
   在表单元素中使用`v-model`指令创建双向数据绑定，单选选项发生改变，绑定的值改变，段落中的相关值跟着改变；
   
   实例生命周期`crated:`当这个实例创建时执行获取数据的方法；
   
   `watch`侦听器侦听 `currentBranch`数据，当数据发生变化时执行获取数据的方法（数据变化时执行异步活开销较大的操作时最有用）;
   
   列表中使用`{{}}`输出文本，并且使用了过滤器.
   过滤器可以用在两个地方：双花括号插值和 v-bind 表达式 (后者从 2.1.0+ 开始支持)。
   过滤器应该被添加在 JavaScript 表达式的尾部，由“管道”符号指示：`{{ message | capitalize }}`
   
3. **[网格组件](https://cn.vuejs.org/v2/examples/grid-component.html)** 
   
   > 该示例创建了一个可复用组件，可结合外部数据来使用它。
   
   一个 search 表单,`v-model`双向绑定`searchQuery`值；一个自定义组件，组件标签`demo-grid`，其属性`filter-key`的值为`searchQuery` ;
   一个`component template` ,模板用的`script`标签，`type`值为‘text/x-template’，模板id值与`Vue.component()`第二个对象参数中定义的template参数对应；
   
   全局组件语法`Vue.component(tagName, options)`，通过`<tagName></tagName>`来调用组件，prop 是父组件用来传递数据的一个自定义属性。父组件（root element）的数据需要通过 props 把数据传给子组件（被调用的组件），子组件需要显式地用 props 选项声明 "prop"。
   
   `demo-grid`组件中，使用 `v-for`指令循环输出table head，使用class属性绑定`:class="{ active: sortKey == key }`，根据sortKey显示类名，也可以通过表达式计算得到具体的类名`:class="sortOrders[key] > 0 ? 'asc' : 'dsc'"`；
   
   嵌套循环输出
   
   ```
    <tr v-for="entry in filteredData">
        <td v-for="key in columns">
          {{entry[key]}}
        </td>
    </tr>
    ```
   
4. **[树形视图](https://cn.vuejs.org/v2/examples/tree-view.html)** 

   > 该示例是一个简单的树形视图实现，它展现了组件的递归使用。

    用到了 计算属性，data属性，本文三元运算，`v-if`指令 `v-show`指令 `v-for`指令，嵌套调用item组件（重点是数据的结构）。

    计算属性的运用，判断该item的model数据中是否有children属性来设置isFolder的布尔值

    子组件中的props中的属性在methods的函数中可以通过this点的方式调用，methods中的方法也可以通过this点的方法调用 

    Vue.set( target, key, value ) `Vue.set(this.model, 'children', [])` 设置属性值
    
5. **[SVG图表](https://cn.vuejs.org/v2/examples/svg.html)**

   > 该示例展示了一个结合体，它由常用组件、计算属性、2 种绑定方式和 SVG 的支持组成。
   里面用到了svg的多边形标签，圆形标签，文本标签，可以看下该示例中的值转换成点坐标的帮助函数，里面都是初中的几何知识.....其实都很简单，就是不用会觉得陌生。
   
    组件中定义的组件只能在父模板中调用. 

6. **[模式组件](https://cn.vuejs.org/v2/examples/modal.html)**

   > 使用到的特性：组件，prop 传递，内容插入(content insertion)，过渡 (transitions)
   
   1、父组件可以使用 props 把数据传给子组件。
   2、子组件可以使用 $emit 触发父组件的自定义事件。
   vue 提供了内置的过渡封装组件，感觉这种过渡组件的使用方式很奇怪
   
7. **[具有伸缩性的 Header](https://cn.vuejs.org/v2/examples/elastic-header.html)**

   > 用到了事件修饰符，svg路径
   
   交互，拖拽头部div可以产生果冻效果 。用到了 http://dynamicsjs.com  这个js。
   svg path 路径中的值引用data中的属性，动态改变对应的data属性值产生交互效果
   
8. **[内嵌组件 ](https://cn.vuejs.org/v2/examples/select2.html)**

   > 该例中，整合了第三方 jQuery 插件 (select2)，怎么做到的呢？就是把它内嵌在一个常用组件中。用到了特殊特性slot
   
    下拉列表的选择，用到了`this.$el`可以直接操作dom ,这个例子有点没看明白啊~  用到了https://select2.org/  jq插件select2,得先去看这个插件....
    
9. **[实时 deepstreamHub](https://cn.vuejs.org/v2/examples/deepstream.html)**

   > 这个例子使用 deepstreamHub 在客户端之间实时同步数据、发送事件、远程程序调用 (可以多开几个浏览器窗口试一试)。
   
   > https://cdnjs.cloudflare.com/ajax/libs/deepstream.io-client-js/2.1.1/deepstream.js
   
   这个示例中使用了多个组件，可以看看该示例的代码组织方式  
   
10. **[Firebase + 验证](https://cn.vuejs.org/v2/examples/firebase.html)**

    > 该示例使用 Firebase 作为数据存储后端，同时在客户端进行数据实时同步 (可以在多个浏览器窗口去打开它来验证)。
    另外，它通过计算属性实时验证，并且添加／移除选项时触发 CSS 过渡。
   
    有表单验证，以及数据动态添加  。写表单验证的时候可以看看该示例 

11. **[TodoMVC](https://cn.vuejs.org/v2/examples/todomvc.html)**

    > 该示例是一个完全和规范一致的 TodoMVC 实现，只用了 120 行有效的 JavaScript (不包含注释和空行)。
    
    用到了`v-cloak` 指令，这个指令保持在元素上直到关联实例结束编译，用来隐藏元素？延后加载？
    
12. **[HackerNews 克隆](https://cn.vuejs.org/v2/examples/hackernews.html)**

    > HackerNews 克隆是基于 HN 的官方 firebase API 、Vue 2.0 、Vue Router 和 Vuex 来构建的，使用服务器端渲染。
    
    > 示例代码在github https://github.com/vuejs/vue-hackernews-2.0
    
    这个示例有结构图
    
## 其他示例

1. **[tab页切换](https://jsfiddle.net/Lp20op9o/4848/)** 

   
##  vue.js 与后台数据交互

   > 搜到的博客 [vue.js与后台数据交互](https://blog.csdn.net/qq_17505335/article/details/79137758) ->  [vue-resource插件使用](http://www.cnblogs.com/axl234/p/5899137.html) ->[ webpack+vue项目实战（四，前端与后端的数据交互和前端展示数据）](https://segmentfault.com/a/1190000010063757) 
   
### vue-resource

> [vue-resource-github](https://github.com/pagekit/vue-resource)

> 这是个Vue.js的插件，提供了使用XMLHttpRequest或JSONP 发出Web请求和处理响应的服务
   
> [vue axios全攻略-blog](https://www.cnblogs.com/libin-1/p/6607945.html)   这篇博客里说vue-resource不再继续维护，然后axios被越来越多的人知道

> axios具有以下特征
> - 从浏览器中创建 XMLHttpRequest
> - 从 node.js 发出 http 请求
> - 支持 Promise API
> - 拦截请求和响应
> - 转换请求和响应数据
> - 取消请求
> - 自动转换JSON数据
> - 客户端支持防止 CSRF/XSRF
 
## vue 相关应用框架

>  [NUXT-vue.js通用应用框架](https://zh.nuxtjs.org/)

>  [vue-element-admin](https://github.com/PanJiaChen/vue-element-admin)
 
>  [element](http://element-cn.eleme.io/#/zh-CN) 基于 Vue 2.0 的桌面端组件库

>  [vuetifyjs](https://vuetifyjs.com/zh-Hans/) 为移动而生的Vue JS 2.0组件框架
   
## vue 服务端渲染

> [vue服务端渲染文档](https://cn.vuejs.org/v2/guide/ssr.html)

> [vue ssr 服务器端渲染指南](https://ssr.vuejs.org/zh/)  

> 如果你调研服务器端渲染(SSR)只是用来改善少数营销页面（例如 /, /about, /contact 等）的 SEO，那么你可能需要预渲染。无需使用 web 服务器实时动态编译 HTML，而是使用预渲染方式，在构建时(build time)简单地生成针对特定路由的静态 HTML 文件。优点是设置预渲染更简单，并可以将你的前端作为一个完全静态的站点。

> Nuxt.js
> 从头搭建一个服务端渲染的应用是相当复杂的。幸运的是，我们有一个优秀的社区项目 Nuxt.js 让这一切变得非常简单。Nuxt 是一个基于 Vue 生态的更高层的框架，为开发服务端渲染的 Vue 应用提供了极其便利的开发体验。更酷的是，你甚至可以用它来做为静态站生成器。推荐尝试。

**疑问**： 为了seo和页面更快地呈现在客户面前，还有生成静态站......这些以前的技术就可以实现，那使用vue的意义何在.....

## 一些问题
> [解决npm 安装部分依赖失败问题总结](https://www.jianshu.com/p/dfbed90f7882) 根目录创建.npmrc文件

```
sass_binary_site=https://npm.taobao.org/mirrors/node-sass/
phantomjs_cdnurl=https://npm.taobao.org/mirrors/phantomjs/
electron_mirror=https://npm.taobao.org/mirrors/electron/
registry=https://registry.npm.taobao.org

```
