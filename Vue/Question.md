# Question

1. Vue 界面如何实现权限控制？

> [基于Vue2.0实现后台系统权限控制](https://forum.vuejs.org/t/vue2-0/28657) 
> 主要思路：用户登录后，获取用role，将role和路由表每个页面的需要的权限作比较，生成最终用户可访问的路由表

> [vue 权限控制](https://segmentfault.com/q/1010000008137883)
> 权限分类 
> - 菜单权限， 根据不同权限显示不同的菜单
> - 操作权限， 比如有些账号没有新增权限， 有些没有修改或者删除权限
> - 数据权限， 比如统计概况， 普通管理员不能看到公司营业概况，但能看到自己所属区域的概况
> - 显示权限， 比如列表， 运营能看到那一列的签约金额，但市场不能看到签约金额这一列

> [Vue + ElementUI 手撸后台管理网站基本框架(二)权限控制](https://blog.csdn.net/harsima/article/details/77949448)
> 前端的权限控制实质上就是用于展示，让操作变得更加友好，真正的安全实际上是由后端控制的

> [Vue2.0用户权限控制解决方案-segmentfault](https://segmentfault.com/p/1210000012206425)
> [Vue2.0用户权限控制解决方案-blog](https://refined-x.com/2017/11/28/Vue2.0%E7%94%A8%E6%88%B7%E6%9D%83%E9%99%90%E6%8E%A7%E5%88%B6%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88/)
> 这是一个博客链接，这个人自己搭建的博客，可以参考一下   


2. 如何不使用构建工具使用vue?

>[如何不用构建工具开发Vue全家桶项目](http://refined-x.com/2017/10/28/%E5%A6%82%E4%BD%95%E4%B8%8D%E7%94%A8%E6%9E%84%E5%BB%BA%E5%B7%A5%E5%85%B7%E5%BC%80%E5%8F%91Vue%E5%85%A8%E5%AE%B6%E6%A1%B6%E9%A1%B9%E7%9B%AE/) 

3. vue redio 和 checkbox 如何默认选中

```
//没有 v-model 的时候
<input type="radio" name="something" id="something" :checked="something == true"  value="1" />

//有v-model的时候 somevalue  和 radio  的值相等 
<input type="radio" name="something" id="something" v-model="somevalue"   value="1" />
```
4. vue-cli 和nuxt 的区别

> [仿Nuxt.js的vue-cli多页面配置](https://www.jianshu.com/p/c15bf8e9c7f4)
