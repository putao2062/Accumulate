# es6  promise

## promise 的含义

异步编程解决方案，

比事件和回调更合理强大

容器，保存未来才会结束的事件

对象，可以获取异步操作的消息

提供统一的api



### 特点

1、对象状态不受外界影响

promise 代表一个异步操作

三种状态： pending  进行中    fullfilled  已成功    rejected 已失败 

只有异步操作的结果可以决定当前是哪一种状态  其他操作无法改变这个状态，此为承诺的由来



2、一旦状态改变，就不会再变，任何时候都可以得到这个结果

状态从 pending （进行） 到 fullfilled （填满）  和 从 pending到 rejected  （拒绝） 两种   ，这两种情况发生，状态就凝固了，不会再变，一直保持这个结果，这时就称为resolved  (已决定)

如果改变已经发生了，你再对`Promise`对象添加回调函数，也会立即得到这个结果。

这与事件（Event）完全不同，事件的特点是，如果你错过了它，再去监听，是得不到结果的。

## 好处

有了`Promise`对象，就可以将异步操作以同步操作的流程表达出来，避免了层层嵌套的回调函数。此外，`Promise`对象提供统一的接口，使得控制异步操作更加容易。

## 缺点

`Promise`也有一些缺点。

首先，无法取消`Promise`，一旦新建它就会立即执行，无法中途取消。

其次，如果不设置回调函数，`Promise`内部抛出的错误，不会反应到外部。

第三，当处于`pending`状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。
