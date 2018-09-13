# Canvas 

## 开发调试

> [使用Chrome开发工具调试Canvas——csdn博客](https://blog.csdn.net/sanxian_li/article/details/41801881) 

> [webgl报告](http://webglreport.com/?v=1) 检测浏览器对webgl的支持

> [WebGL-Inspector](http://benvanik.github.io/WebGL-Inspector/) webgl检查工具，暂时打不开需要vpn 

## 图片处理

> [前端图片转base64，转格式，转blob，上传的总结](https://blog.csdn.net/wangzhanzheng/article/details/78923013)  

file 类型的input表单中的accept属性可以指定上传文件的格式。哎呀，居然都不知道用一下的说....格式不对会有啥提示么？哎呦，居然在选择文件的时候直接不显示指定格式外的文件！ 可以，这个记下说不定用的上。

html5的文件操作api——FileReader对象可以获取到图片的base64编码，可以把base64直接设置给img的src属性，用做图片回显用。我的确这么干过.....

图片转base64
```
//通过 FileReader
$(function() {
    $("#up").change(function() {
        var file = this.files[0];
        if (undefined == file) {
            return;
        }
        r = new FileReader();
        r.readAsDataURL(file);
        r.onload = function(e) {
            var base64 = e.target.result;

        }
    });
});

```
该博文中还有 canvas转base64——[canvas.toDataURL('image/png')](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLCanvasElement/toDataURL) ，通过 canvas改变宽高来缩小图片，canvas转blob,base转blob。  其写博文的思路也比较清晰 。

```
//canvas 绘制图片压缩图片
var suofang = function(base64, bili, callback) {
	console.log("执行缩放程序,bili=" + bili);
	//处理缩放，转格式
	var _img = new Image();
	_img.src = base64;
	_img.onload = function() {
		var _canvas = document.createElement("canvas");
		var w = this.width / bili;
		var h = this.height / bili;
		_canvas.setAttribute("width", w);
		_canvas.setAttribute("height", h);
		_canvas.getContext("2d").drawImage(this, 0, 0, w, h);
	}
}
```

```
// canvas 转base64
var base64 = canvas.toDataURL("image/png");
```

```
//canvas转blob
_canvas.toBlob(function(blob) {
			console.log(blob.size);
}, "image/jpeg");
```

```
//base64转
function dataURItoBlob(base64Data) {
	var byteString;
	if(base64Data.split(',')[0].indexOf('base64') >= 0)
		byteString = atob(base64Data.split(',')[1]);
	else
		byteString = unescape(base64Data.split(',')[1]);
	var mimeString = base64Data.split(',')[0].split(':')[1].split(';')[0];
	var ia = new Uint8Array(byteString.length);
	for(var i = 0; i < byteString.length; i++) {
		ia[i] = byteString.charCodeAt(i);
	}
	return new Blob([ia], {
		type: mimeString
	});
}

```
## 数据库储存图片的方案抉择

储存图片的做法有两种：

1. 把图片直接以二进制形式储存在数据库中，blob

2. 图片储存在磁盘上，数据库字段保存的是图片的路径

第一种方法要考虑数据库的类型和版本，文件过大可以使用文件流，读图片要经过二进制转换。 缺点是对数据库有要求，影响数据库的速度和性能;优点是信息好维护

第二种方法，在B/S系统中使用的比较多。优点：数据库只需存路径，缺点：多客户端，数据不好维护(文件储存路径设计好之后应该好维护吧)

**几篇可能有用的博文

[把图片保存到数据库中和从数据库中读取图片--项目琐碎总结](https://www.cnblogs.com/ysyn/p/3660131.html)

[关于图片或者文件在数据库的存储方式归纳](https://www.cnblogs.com/xlz307/p/3467816.html)



