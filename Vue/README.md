# Vue 

> [vue 中文官网](https://cn.vuejs.org/) 

> [vue.js教程-菜鸟教程](http://www.runoob.com/vue2/vue-tutorial.html)  简单易懂 可用来快速熟悉vue相关语法


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
   
   
   



