# Cross-Origin Resource Sharing

**跨域资源共享** ： 是一种允许当前domain（使用cors技术的服务端）的资源（html/js/web service）被其他域的脚本请求访问的机制。
[HTTP访问控制CORS-mozilla](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS)

通常由于 the same-origin security policy 同源安全策略 浏览器会禁止这种跨域请求（限制发起跨域请求或拦截跨域请求的返回结果）。
(为了保护当前domian的资源安全)

**同源策略**：同源策略是一种约定，是浏览器最核心和最基本的安全功能。
[Same-origin_policy-mozilla](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#Cross-origin_network_access)

**AJAX(Asynchronous Javascript and XML)与
[XSS](https://baike.baidu.com/item/%E8%B7%A8%E7%AB%99%E8%84%9A%E6%9C%AC%E6%94%BB%E5%87%BB/8186208?fr=aladdin)(Cross Site Scripting)**：
跨站攻击一般是为了收集用户信息，攻击者通常会在有漏洞的程序中插入Javascript,VBScript,ActiveX或Flash 欺骗用户，使得代码在当前服务器中执行盗取数据。

AJAX技术最大优点是可以不用更新整个页面来维护数据，web应用可以更迅速地响应用户请求。

1.AJAX会处理来自Web服务器及源自第三方的丰富信息，这对XSS攻击提供了良好的机会。

2.AJAX应用架构会泄漏更多应用的细节，如函数和变量名称、函数参数及返回类型、数据类型及有效范围等。

3.AJAX应用架构还有着较传统架构更多的应用输入，这就增加了可被攻击的点



