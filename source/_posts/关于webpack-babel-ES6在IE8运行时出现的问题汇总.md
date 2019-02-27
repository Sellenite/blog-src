---
title: 关于webpack+babel+ES6在IE8运行时出现的问题汇总
date: 2018-01-12 18:40:22
tags:
- JS
---

- 使用babel，babel-polyfill和es5-shim依然不能够在IE8运行，并且合并报错的原因是，合并js中含有javascript的保留字delete和catch等问题，会报“SCRIPT1010: 缺少标识符”


- 同样会报“SCRIPT1010: 缺少标识符”的另一个原因是JSON的格式，如下json的格式也会报这个错误，结尾那个逗号，在IE下会报错，注意：
```javascript
{
    "firstName":"John" , 
    "lastName":"Doe" ,
}
```

- IE10不支持条件注释，条件注释会被当做一般注释，处理方法，使用meta采用IE9行为：
```html
<html>
  <meta http-equiv="X-UA-Compatible" content="IE=EmulateIE9">
  <!--[if IE]>
    This content is ignored in Internet Explorer 10 and other browsers.
    In older versions of Internet Explorer, it renders as part of the page.
  <![endif]-->
</html>
```

- 在webpack的dev环境中增加对编译文件的sourcemap，可以很方便的在调试工具中跳转到打包前的js运行错误或打印的地方，方便调试

- 使用插件做兼容手段：

1. webpack 进行babel对ES6，7语法的转码。
2. webpack 引用es3ify-loader 解决es3语法兼容问题（解决react的babel会把 export(非import) 编译成 
3. Object.defineProperty的方式）。
模块导出不能使用 export default ，改为export { xxx } （default关键字）
4. 使用add-module-exports，仅仅解决default的问题
5. 全局引用babel-polyfill,es5-shim/es5-sham,console-polyfill,JSON的polyfill等
6. 不要在代码中用Object.defineProperty设置访问器属性，不要使用Object.create()的第二个参数定义属性操作符，因为ES5以前有着polyfill无法模拟的Object.defineProperty
7. IE8的defineProperty只存在于DOM上，尝试对Object访问该方法会报错

参考资料：[http://blog.csdn.net/deng_gene/article/details/53004735](http://note.youdao.com/)