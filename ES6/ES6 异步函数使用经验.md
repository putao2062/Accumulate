# ES6 异步函数使用经验

## 场景

1. 等待x个异步操作结束后执行相关操作   

```
Promise.all(promises).then(() = >{}) 

```

2. 多个异步操作顺序执行

```
// promise 嵌套
// url ,map  多个 promise 
// 数组 reduce，
promises.reduce(function(t,e){return t.then(()=>e);}, Promise.resolve());


// async 函数  for...of  await


```

3. 多个异步函数顺序执行 并控制终止

```
// Generator 函数 for...of  yield  

var gen = function*(arg) {
            for (let [i, e] of arg.entries()) {

                yield getSerachResult(e, attributeNames, i).then(vualue => vualue);

            }
        }

function run(gen, arg) {
    var g = gen(arg);

    function next(value) {
        var result = g.next(value);

        if (result.done || isStop) return result.value;

        result.value.then((value) => {
            next(value);
        })
    }

    next();
}
run(gen, arg);

```
