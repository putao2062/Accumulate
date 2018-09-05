# Make Bug

> 不会制造bug的developer不是好developer

## 诡异的单击事件没反应

```
<button type="button" class="close-btn">
    <img src="/statics/images/close.svg"  class="close-img">
</button>
```

监听`button ` 内的`img `的单击事件，然后执行关闭窗口的代码，在谷歌浏览器下能对单击事件作出响应，在火狐浏览器下却无反应。

尝试解决办法，转而去监听 `button` 的单击事件，然后执行关闭窗口的代码。

可是火狐这波操作是为什嘛，查看元素的时候把鼠标放到这个按钮上，在谷歌浏览器下查看元素看到的是img，在火狐浏览器下查看元素看到的是button,
所以这属于不同浏览器不同的渲染机制不同的问题？
