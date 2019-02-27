---
title: 使用respond.js(IE6-8响应式方案)注意事项
date: 2018-01-09 22:16:42
tags:
- CSS
---
只有IE9+才支持CSS媒体查询，IE6-8使用媒体查询需要以下插件：

respond.js。文件下载地址：[https://github.com/scottjehl/Respond](http://note.youdao.com/)

关于respond.js的使用，有一些需要注意的地方，一旦不注意，在IE6-8中就无法显示出来。

#### 插件原理

接下来，需要理解respond.js的实现思路：

- 第一步，将head中所有外部引入的CSS文件路径取出来存储到一个数组当中；

- 第二步，遍历数组，并一个个发送AJAX请求
；
- 第三步，AJAX回调后，分析response中的media query的min-width和max-width语法（注意，仅仅支持min-width和max-width），分析出viewport变化区间对应相应的css块；

- 第四步，页面初始化时和window.resize时，根据当前viewport使用相应的css块。

#### 核心结论

那么此时，就可以根据基本的实现思路，得到一些书写代码时要注意的地方：

- 需要启动本地服务器（localhost），不能使用普通本地的url地址（file://开头）；

- 需要外部引入CSS文件，将CSS样式书写在style中是无效的；

- 由于respond插件是查找CSS文件，再进行处理，所以respond文件一定要放置在CSS文件的后面

- 另外，虽然把respond放置在head里还是在body后面都能够实现，但是建议放置在head中（具体原因在下面的文档提示中有提到）

- 可以使用js条件加载respond.js或css

- 最好不要为CSS设置utf-8的编码，使用默认（原因详见下面的文档提示部分）


#### 文档提示

在官方文档当中的一些提示：

1、越早的引入respond.js文件，也就越可能避免IE下出现的闪屏。

2、不支持嵌套的媒体查询

3、只支持CSS with screen and min/max-width media queries

```css
@media screen and (min-width: 480px){
    /** ...styles for 480px and up go here **/
}

@media (min-width: 3200px) and (max-width: 720px){
    /** ...styles for 480px and up go here **/
}

```

4、utf-8的字符编码对respond.js文件的运行有影响。
官方API原文：if CSS files are encoded in UTF-8 with Byte-Order-Mark, they will not work with Respond.js in IE7 or IE8.

基本含义就是：utf-8格式的CSS文件字符编码会对插件造成影响。

但是在我使用IE6-8进行测试的时候，都能够正常显示（无论是在css文件中增加charset设置还是在link标签中增加charset设置）。因此，并不是太清楚这个位置bug的含义。

4、跨域可能会出现闪屏（还没有测试，具体情况不详）

> 其他的支持响应式布局的插件-css3-mediaqueries-js

css3-mediaqueries-js官方文档和demo都没有，相对于respond.js，css3-mediaqueries-js支持几乎所有的media query的语法。

但是会出现闪屏。并不是很推荐使用，虽然能够支持全部的mediaqueries，但min-width和max-width其实就可以满足我们对响应式布局的需要。