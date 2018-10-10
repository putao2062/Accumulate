# ES6  for...of  

> Iterator 的作用有三个：一是为各种数据结构，提供一个统一的、简便的访问接口；
> 二是使得数据结构的成员能够按某种次序排列；
> 三是 ES6 创造了一种新的遍历命令for...of循环，Iterator 接口主要供for...of消费。


## 使用经验

1. for...of中循环一个数组 并获取 索引值

```
//用到了es6的结构赋值、map数据集合、for...of

for(let [e, i] of new Map( arr.map( ( e, i ) => [ e, i ] ) )){
　　//...
}


// 使用数组实例的entries()

for (let [index, elem] of arr.entries()) {
    console.log(index, elem);
}
```
