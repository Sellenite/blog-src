---
title: 前端JS进阶知识（1）
date: 2017-03-24 21:55:26
tags:
- JS
---

<div class="article-entry" itemprop="articleBody">
    <ol>
        <li>XHTML和HTML有什么区别
            <blockquote>
                <ul>
                    <li>HTML是一种基本的WEB网页设计语言，XHTML是一个基于XML的置标语言
                        <br>最主要的不同：</li>
                    <li>XHTML 元素必须被正确地嵌套。</li>
                    <li>XHTML 元素必须被关闭。</li>
                    <li>标签名必须用小写字母。</li>
                    <li>XHTML 文档必须拥有根元素。</li>
                </ul>
            </blockquote>
        </li>
    </ol>
    <p>2.前端页面有哪三层构成，分别是什么?作用是什么?</p>
    <blockquote>
        <ul>
            <li>结构层 Html 表示层 CSS 行为层 js;</li>
        </ul>
    </blockquote>
    <p>3.你做的页面在哪些流览器测试过?这些浏览器的内核分别是什么?</p>
    <blockquote>
        <ul>
            <li>Ie(Ie内核) 火狐（Gecko） 谷歌（webkit,Blink） opera(Presto),Safari(wbkit)</li>
        </ul>
    </blockquote>
    <p>4.什么是语义化的HTML?</p>
    <blockquote>
        <ul>
            <li>直观的认识标签 对于搜索引擎的抓取有好处，用正确的标签做正确的事情！</li>
            <li>html语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析；
                <br>在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的。搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，利于 SEO。</li>
            <li>使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。</li>
        </ul>
    </blockquote>
    <p>5.HTML5 为什么只需要写 !DOCTYPE HTML？</p>
    <blockquote>
        <ul>
            <li>HTML5 不基于 SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）；而HTML4.01基于SGML,所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。</li>
        </ul>
    </blockquote>
    <p>6.Doctype作用？标准模式与兼容模式各有什么区别?</p>
    <blockquote>
        <ul>
            <li>!DOCTYPE声明位于位于HTML文档中的第一行，处于html 标签之前。告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。</li>
            <li>标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。</li>
        </ul>
    </blockquote>
    <p>7.html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和
        <br>HTML5？</p>
    <blockquote>
        <ul>
            <li>HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。</li>
            <li>绘画 canvas</li>
            <li>用于媒介回放的 video 和 audio 元素</li>
            <li>本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失；</li>
            <li>sessionStorage 的数据在浏览器关闭后自动删除</li>
            <li>语意化更好的内容元素，比如 article、footer、header、nav、section</li>
            <li>表单控件，calendar、date、time、email、url、search</li>
            <li>新的技术webworker, websockt, Geolocation
                <br>移除的元素</li>
            <li>纯表现的元素：basefont，big，center，font, s，strike，tt，u；</li>
            <li>对可用性产生负面影响的元素：frame，frameset，noframes；
                <br>支持HTML5新标签：</li>
            <li>IE8/IE7/IE6支持通过document.createElement方法产生的标签，</li>
            <li>可以利用这一特性让这些浏览器支持HTML5新标签，</li>
            <li>浏览器支持新标签后，还需要添加标签默认的样式：</li>
        </ul>
    </blockquote>
    <p>8.请描述一下 cookies，sessionStorage 和 localStorage 的区别？</p>
    <blockquote>
        <ul>
            <li>cookie在浏览器和服务器间来回传递。 sessionStorage和localStorage不会</li>
            <li>sessionStorage和localStorage的存储空间更大；</li>
            <li>sessionStorage和localStorage有更多丰富易用的接口；</li>
            <li>sessionStorage和localStorage各自独立的存储空间；</li>
        </ul>
    </blockquote>
    <p>9.如何实现浏览器内多个标签页之间的通信?</p>
    <blockquote>
        <ul>
            <li>调用localstorge、cookies等本地存储方式</li>
        </ul>
    </blockquote>
    <h3 id="CSS面试题"><a href="#CSS面试题" class="headerlink" title="CSS面试题"></a>CSS面试题<br><br></h3>
    <p> 1.简要说一下CSS的元素分类</p>
    <blockquote>
        <ul>
            <li>块级元素：div,p,h1,form,ul,li;</li>
            <li>行内元素 : span&gt;,a,label,input,img,strong,em;</li>
        </ul>
    </blockquote>
    <p> 2.CSS隐藏元素的几种方法（至少说出三种）</p>
    <blockquote>
        <ul>
            <li>Opacity:元素本身依然占据它自己的位置并对网页的布局起作用。它也将响应用户交互;</li>
            <li>Visibility:与 opacity 唯一不同的是它不会响应任何用户交互。此外，元素在读屏软件中也会被隐藏;</li>
            <li>Display:display 设为 none 任何对该元素直接打用户交互操作都不可能生效。此外，读屏软件也不会读到元素的内容。这种方式产生的效果就像元素完全不存在;</li>
            <li>Position:不会影响布局，能让元素保持可以操作;</li>
            <li>Clip-path:clip-path 属性还没有在 IE 或者 Edge 下被完全支持。如果要在你的 clip-path 中使用外部的 SVG 文件，浏览器支持度还要低;</li>
        </ul>
    </blockquote>
    <p> 3.CSS清除浮动的几种方法（至少两种）</p>
    <blockquote>
        <ul>
            <li>使用带clear属性的空元素</li>
            <li>使用CSS的overflow属性；</li>
            <li>使用CSS的:after伪元素；</li>
            <li>使用邻接元素处理；</li>
        </ul>
    </blockquote>
    <p> 4.CSS居中（包括水平居中和垂直居中）</p>
    <blockquote>
        <h3 id="内联元素居中方案"><a href="#内联元素居中方案" class="headerlink" title="内联元素居中方案"></a>内联元素居中方案</h3>
        <p><strong>水平居中设置：</strong>
            <br>1.行内元素</p>
        <ul>
            <li>设置 text-align:center；</li>
        </ul>
        <p>2.Flex布局</p>
        <ul>
            <li>设置display:flex;justify-content:center;(灵活运用,支持Chroime，Firefox，IE9+)</li>
        </ul>
        <p><strong>垂直居中设置：</strong>
            <br>1.父元素高度确定的单行文本（内联元素）</p>
        <ul>
            <li>设置 height = line-height；</li>
        </ul>
        <p>2.父元素高度确定的多行文本（内联元素）</p>
        <ul>
            <li>a:插入 table （插入方法和水平居中一样），然后设置 vertical-align:middle；</li>
            <li>b:先设置 display:table-cell 再设置 vertical-align:middle；
                <h3 id="块级元素居中方案"><a href="#块级元素居中方案" class="headerlink" title="块级元素居中方案"></a>块级元素居中方案</h3><strong>水平居中设置：</strong>
                <br>1.定宽块状元素</li>
            <li>设置 左右 margin 值为 auto；</li>
        </ul>
        <p>2.不定宽块状元素</p>
        <ul>
            <li>a:在元素外加入 table 标签（完整的，包括 table、tbody、tr、td），该元素写在 td 内，然后设置 margin 的值为 auto；</li>
            <li>b:给该元素设置 displa:inine 方法；</li>
            <li>c:父元素设置 position:relative 和 left:50%，子元素设置 position:relative 和 left:50%；</li>
        </ul>
        <p><strong>垂直居中设置：</strong></p>
        <ul>
            <li>使用position:absolute（fixed）,设置left、top、margin-left、margin-top的属性;</li>
            <li>利用position:fixed（absolute）属性，margin:auto这个必须不要忘记了;</li>
            <li>利用display:table-cell属性使内容垂直居中;</li>
            <li>使用css3的新属性transform:translate(x,y)属性;</li>
            <li>使用:before元素;</li>
        </ul>
    </blockquote>
    <p> 5.写出几种IE6 BUG的解决方法</p>
    <blockquote>
        <ul>
            <li>双边距BUG float引起的 使用display</li>
            <li>3像素问题 使用float引起的 使用dislpay:inline -3px</li>
            <li>超链接hover 点击后失效 使用正确的书写顺序 link visited hover active</li>
            <li>Ie z-index问题 给父级添加position:relative</li>
            <li>Png 透明 使用js代码 改</li>
            <li>Min-height 最小高度 ！Important 解决’</li>
            <li>select 在ie6下遮盖 使用iframe嵌套</li>
            <li>为什么没有办法定义1px左右的宽度容器（IE6默认的行高造成的，使用over:hidden,zoom:0.08 line-height:1px）</li>
        </ul>
    </blockquote>
    <p> 6.对于SASS或是Less的了解程度？喜欢那个？</p>
    <blockquote>
        <ul>
            <li>语法介绍</li>
        </ul>
    </blockquote>
    <p> 7.Bootstrap了解程度</p>
    <blockquote>
        <ul>
            <li>特点，排版，插件的使用;</li>
        </ul>
    </blockquote>
    <p> 8.页面导入样式时，使用link和@import有什么区别？</p>
    <blockquote>
        <ul>
            <li>link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;</li>
            <li>页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;</li>
            <li>import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;</li>
        </ul>
    </blockquote>
    <p> 9.介绍一下CSS的盒子模型？</p>
    <blockquote>
        <ul>
            <li>有两种， IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 pading;</li>
            <li>盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).</li>
        </ul>
    </blockquote>
    <p> 10.CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？</p>
    <blockquote>
        <ul>
            <li>id选择器（ # myid）</li>
            <li>类选择器（.myclassname）</li>
            <li>标签选择器（div, h1, p）</li>
            <li>相邻选择器（h1 + p）</li>
            <li>子选择器（ul &gt; li）</li>
            <li>后代选择器（li a）</li>
            <li>通配符选择器（ * ）</li>
            <li>属性选择器（a[rel = “external”]）</li>
            <li>伪类选择器（a: hover, li: nth - child）</li>
            <li>可继承的样式： font-size font-family color, UL LI DL DD DT;</li>
            <li>不可继承的样式：border padding margin width height ;</li>
            <li>优先级就近原则，同权重情况下样式定义最近者为准;</li>
            <li>优先级为:<pre><code>!important &gt;  id &gt; class &gt; tag
important 比 内联优先级高
</code></pre></li>
        </ul>
    </blockquote>
    <p> 11.CSS3有哪些新特性？</p>
    <blockquote>
        <ul>
            <li>CSS3实现圆角（border-radius:8px），阴影（box-shadow:10px），
                <br>对文字加特效（text-shadow、），线性渐变（gradient），旋转（transform）</li>
            <li>transform:rotate(9deg) scale(0.85,0.90) translate(0px,-30px) skew(-9deg,0deg);//旋转,缩放,定位,倾斜
                <br>增加了更多的CSS选择器 多背景 rgba</li>
        </ul>
    </blockquote>
    <h2 id="JavaScript面试题"><a href="#JavaScript面试题" class="headerlink" title="JavaScript面试题"></a>JavaScript面试题</h2>
    <p> 1.javascript的typeof返回哪些数据类型</p>
    <blockquote>
        <ul>
            <li>Ｏbject number function boolean underfind;</li>
        </ul>
    </blockquote>
    <p> 2.例举3种强制类型转换和2种隐式类型转换?</p>
    <blockquote>
        <ul>
            <li>强制（parseInt,parseFloat,number）隐式（== – ===）；</li>
        </ul>
    </blockquote>
    <p> 3.数组方法pop() push() unshift() shift()</p>
    <blockquote>
        <ul>
            <li>Push()尾部添加 pop()尾部删除</li>
            <li>Unshift()头部添加 shift()头部删除</li>
        </ul>
    </blockquote>
    <p> 4.ajax请求的时候get 和post方式的区别?</p>
    <blockquote>
        <ul>
            <li>一个在url后面 一个放在虚拟载体里面
                <br>有大小限制</li>
            <li>安全问题
                <br>应用不同 一个是论坛等只需要请求的，一个是类似修改密码的;</li>
        </ul>
    </blockquote>
    <p> 5.call和apply的区别</p>
    <blockquote>
        <ul>
            <li>Object.call(this,obj1,obj2,obj3)</li>
            <li>Object.apply(this,arguments)</li>
        </ul>
    </blockquote>
    <p> 6.ajax请求时，如何解释json数据</p>
    <blockquote>
        <ul>
            <li>使用eval parse,鉴于安全性考虑 使用parse更靠谱;</li>
        </ul>
    </blockquote>
    <p> 7.事件委托是什么</p>
    <blockquote>
        <ul>
            <li>让利用事件冒泡的原理，让自己的所触发的事件，让他的父元素代替执行！</li>
        </ul>
    </blockquote>
    <p> 8.闭包是什么，有什么特性，对页面有什么影响?简要介绍你理解的闭包</p>
    <blockquote>
        <ul>
            <li>闭包就是能够读取其他函数内部变量的函数。</li>
        </ul>
    </blockquote>
    <p> 9.添加 删除 替换 插入到某个接点的方法</p>
    <blockquote>
        <p>obj.appendChidl()
            <br>obj.innersetBefore
            <br>obj.replaceChild
            <br>obj.removeChild</p>
    </blockquote>
    <p> 10.说一下什么是javascript的同源策略？</p>
    <blockquote>
        <ul>
            <li>一段脚本只能读取来自于同一来源的窗口和文档的属性，这里的同一来源指的是主机名、协议和端口号的组合</li>
        </ul>
    </blockquote>
    <p> 11.编写一个b继承a的方法;
        <br>
    </p>
    <figure class="highlight plain">
        <table>
            <tbody>
                <tr>
                    <td class="gutter"><pre><div class="line">1</div><div class="line">2</div><div class="line">3</div><div class="line">4</div><div class="line">5</div><div class="line">6</div><div class="line">7</div><div class="line">8</div><div class="line">9</div><div class="line">10</div><div class="line">11</div></pre></td>
                    <td class="code"><pre><div class="line">function A(name){</div><div class="line">    this.name = name;</div><div class="line">    this.sayHello = function(){alert(this.name+” say Hello!”);};</div><div class="line">}</div><div class="line">function B(name,id){</div><div class="line">    this.temp = A;</div><div class="line">    this.temp(name);        //相当于new A();</div><div class="line">    delete this.temp;       </div><div class="line">     this.id = id;   </div><div class="line">    this.checkId = function(ID){alert(this.id==ID)};</div><div class="line">}</div></pre></td>
                </tr>
            </tbody>
        </table>
    </figure>
    <p></p>
    <p> 12.如何阻止事件冒泡和默认事件
        <br> </p>
    <figure class="highlight plain">
        <table>
            <tbody>
                <tr>
                    <td class="gutter"><pre><div class="line">1</div><div class="line">2</div><div class="line">3</div><div class="line">4</div><div class="line">5</div><div class="line">6</div><div class="line">7</div><div class="line">8</div></pre></td>
                    <td class="code"><pre><div class="line">function stopBubble(e)</div><div class="line">{</div><div class="line">    if (e &amp;&amp; e.stopPropagation)</div><div class="line">        e.stopPropagation()</div><div class="line">    else</div><div class="line">        window.event.cancelBubble=true</div><div class="line">}</div><div class="line">return false</div></pre></td>
                </tr>
            </tbody>
        </table>
    </figure>
    <p></p>
    <p> 13.下面程序执行后弹出什么样的结果?</p>
    <figure class="highlight plain">
        <table>
            <tbody>
                <tr>
                    <td class="gutter"><pre><div class="line">1</div><div class="line">2</div><div class="line">3</div><div class="line">4</div><div class="line">5</div><div class="line">6</div><div class="line">7</div><div class="line">8</div><div class="line">9</div><div class="line">10</div><div class="line">11</div><div class="line">12</div><div class="line">13</div><div class="line">14</div><div class="line">15</div><div class="line">16</div><div class="line">17</div><div class="line">18</div><div class="line">19</div></pre></td>
                    <td class="code"><pre><div class="line">function fn() {</div><div class="line">    this.a = 0;</div><div class="line">    this.b = function() {</div><div class="line">        alert(this.a)</div><div class="line">    }</div><div class="line">}</div><div class="line">fn.prototype = {</div><div class="line">    b: function() {</div><div class="line">        this.a = 20;</div><div class="line">        alert(this.a);</div><div class="line">    },</div><div class="line">    c: function() {</div><div class="line">        this.a = 30;</div><div class="line">        alert(this.a);</div><div class="line">    }</div><div class="line">}</div><div class="line">var myfn = new fn();</div><div class="line">myfn.b();</div><div class="line">myfn.c();</div></pre></td>
                </tr>
            </tbody>
        </table>
    </figure>
    <p> 14.谈谈This对象的理解。</p>
    <blockquote>
        <p>this是js的一个关键字，随着函数使用场合不同，this的值会发生变化。
            <br> 但是有一个总原则，那就是this指的是调用函数的那个对象。
            <br> this一般情况下：是全局对象Global。 作为方法调用，那么this就是指这个对象</p>
    </blockquote>
    <p> 15.下面程序的结果
        <br>
    </p>
    <figure class="highlight plain">
        <table>
            <tbody>
                <tr>
                    <td class="gutter"><pre><div class="line">1</div><div class="line">2</div><div class="line">3</div><div class="line">4</div><div class="line">5</div><div class="line">6</div><div class="line">7</div><div class="line">8</div><div class="line">9</div><div class="line">10</div><div class="line">11</div></pre></td>
                    <td class="code"><pre><div class="line">function fun(n,o) {</div><div class="line">  console.log(o)</div><div class="line">  return {</div><div class="line">    fun:function(m){</div><div class="line">      return fun(m,n);</div><div class="line">    }</div><div class="line">  };</div><div class="line">}</div><div class="line">var a = fun(0);  a.fun(1);  a.fun(2);  a.fun(3);</div><div class="line">var b = fun(0).fun(1).fun(2).fun(3);</div><div class="line">var c = fun(0).fun(1);  c.fun(2);  c.fun(3);</div></pre></td>
                </tr>
            </tbody>
        </table>
    </figure>
    <p></p>
    <blockquote>
        <p>//答案：
            <br>//a: undefined,0,0,0
            <br>//b: undefined,0,1,2
            <br>//c: undefined,0,1,1</p>
    </blockquote>
    <p> 16.下面程序的输出结果
        <br>
    </p>
    <figure class="highlight plain">
        <table>
            <tbody>
                <tr>
                    <td class="gutter"><pre><div class="line">1</div><div class="line">2</div><div class="line">3</div><div class="line">4</div><div class="line">5</div><div class="line">6</div><div class="line">7</div><div class="line">8</div><div class="line">9</div></pre></td>
                    <td class="code"><pre><div class="line">var name = 'World!';</div><div class="line">(function () {</div><div class="line">    if (typeof name === 'undefined') {</div><div class="line">        var name = 'Jack';</div><div class="line">        console.log('Goodbye ' + name);</div><div class="line">    } else {</div><div class="line">        console.log('Hello ' + name);</div><div class="line">    }</div><div class="line">})();</div></pre></td>
                </tr>
            </tbody>
        </table>
    </figure>
    <p></p>
    <p> 17.了解Node么？Node的使用场景都有哪些？</p>
    <blockquote>
        <ul>
            <li>高并发、聊天、实时消息推送</li>
        </ul>
    </blockquote>
    <p> 18.介绍下你最常用的一款框架</p>
    <blockquote>
        <ul>
            <li>jquery,rn,angular等;</li>
        </ul>
    </blockquote>
    <p> 19.对于前端自动化构建工具有了解吗？简单介绍一下</p>
    <blockquote>
        <ul>
            <li>Gulp,Grunt等；</li>
        </ul>
    </blockquote>
    <p> 20.介绍一下你了解的后端语言以及掌握程度</p>
    <h3 id="其它"><a href="#其它" class="headerlink" title="其它"></a>其它</h3>
    <p>
        <br>
        <br> 1.对Node的优点和缺点提出了自己的看法？</p>
    <blockquote>
        <p>(优点）
            <br> 因为Node是基于事件驱动和无阻塞的，所以非常适合处理并发请求，
            <br> 因此构建在Node上的代理服务器相比其他技术实现（如Ruby）的服务器表现要好得多。
            <br> 此外，与Node代理服务器交互的客户端代码是由javascript语言编写的，
            <br> 因此客户端和服务器端都用同一种语言编写，这是非常美妙的事情。
            <br>（缺点）
            <br> Node是一个相对新的开源项目，所以不太稳定，它总是一直在变，
            <br> 而且缺少足够多的第三方库支持。看起来，就像是Ruby/Rails当年的样子。</p>
    </blockquote>
    <p> 2.你有哪些性能优化的方法？</p>
    <blockquote>
        <p>（1） 减少http请求次数：CSS Sprites, JS、CSS源码压缩、图片大小控制合适；网页Gzip，CDN托管，data缓存 ，图片服务器。
            <br> （2）前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数
            <br>（3） 用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能。
            <br>（4） 当需要设置的样式很多时设置className而不是直接操作style。
            <br>（5） 少用全局变量、缓存DOM节点查找的结果。减少IO读取操作。
            <br>（6） 避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)。
            <br>（7） 图片预加载，将样式表放在顶部，将脚本放在底部 加上时间戳。
            <br>（8） 避免在页面的主体布局中使用table，table要等其中的内容完全下载之后才会显示出来，显示div+css布局慢。对普通的网站有一个统一的思路，就是尽量向前端优化、减少数据库操作、减少磁盘IO。向前端优化指的是，在不影响功能和体验的情况下，能在浏览器执行的不要在服务端执行，能在缓存服务器上直接返回的不要到应用服务器，程序能直接取得的结果不要到外部取得，本机内能取得的数据不要到远程取，内存能取到的不要到磁盘取，缓存中有的不要去数据库查询。减少数据库操作指减少更新次数、缓存结果减少查询次数、将数据库执行的操作尽可能的让你的程序完成（例如join查询），减少磁盘IO指尽量不使用文件系统作为缓存、减少读写文件次数等。程序优化永远要优化慢的部分，换语言是无法“优化”的。</p>
        <p>3.http状态码有那些？分别代表是什么意思？
            <br>100-199 用于指定客户端应相应的某些动作。
            <br>200-299 用于表示请求成功。
            <br>300-399 用于已经移动的文件并且常被包含在定位头信息中指定新的地址信息。
            <br>400-499 用于指出客户端的错误。400 1、语义有误，当前请求无法被服务器理解。401 当前请求需要用户验证 403 服务器已经理解请求，但是拒绝执行它。
            <br>500-599 用于支持服务器错误。 503 – 服务不可用
            <br>4.一个页面从输入 URL 到页面加载显示完成，这个过程中都发生了什么？（流程说的越详细越好）</p>
        <ul>
            <li>查找浏览器缓存</li>
            <li>DNS解析、查找该域名对应的IP地址、重定向（301）、发出第二个GET请求</li>
            <li>进行HTTP协议会话</li>
            <li>客户端发送报头(请求报头)</li>
            <li>文档开始下载</li>
            <li>文档树建立，根据标记请求所需指定MIME类型的文件</li>
            <li>文件显示</li>
            <li>浏览器这边做的工作大致分为以下几步：</li>
            <li>加载：根据请求的URL进行域名解析，向服务器发起请求，接收文件（HTML、JS、CSS、图象等）。</li>
            <li>解析：对加载到的资源（HTML、JS、CSS等）进行语法解析，建议相应的内部数据结构（比如HTML的DOM树，JS的（对象）属性表，CSS的样式规则等等）</li>
        </ul>
    </blockquote>
    <p> 5.你常用的开发工具是什么，为什么？</p>
    <blockquote>
        <ul>
            <li>Sublime,Atom,Nodepad++;</li>
        </ul>
    </blockquote>
    <p> 6.说说最近最流行的一些东西吧？常去哪些网站？</p>
    <blockquote>
        <ul>
            <li>Node.js、MVVM、React-native,Angular,Weex等</li>
            <li>CSDN,Segmentfault,博客园,掘金,Stackoverflow等</li>
        </ul>
    </blockquote>
</div>