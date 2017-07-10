# HMTL发展历史

HTML(超文本标记语言)是一种‘标准通用标记语言’，简单的来说就是按照某种特定的结构来描述内容，
就跟JPG是按照某种特定格式描述图片信息；这样我们就能**通过这种标准化的结构传递和展示信息**。

HTML标准基本由W3C（万维网联盟创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构）
制定，越高的版本功能越强大（可以粗糙地理解为支持更多的标签）。

- HTML 2.0——1995年11月作为RFC 1866发布 (支持基于表单的文件上传、表格、国际化等功能)
- HTML 3.2——1997年1月14日，W3C推荐标准 （去除了数学公式支持，采用了网景设计的大多数视觉标记标签等功能）
- HTML 4.0——1997年12月18日，W3C推荐标准 （采用了许多特定浏览器的元素类型和属性，试图淘汰网景的视觉标记功能
（比如网景有一些标签可以定义背景色），将其标记为不赞成使用）
- HTML 5——2014年10月28日，W3C推荐标准


注：W3C也出草了XHTML,这是一个更为严格的HTML版本，比如：

- XHTML 元素名和属性必须小写
- 对非空元素必须闭合标签空标签像`<br>`和`<img>`  应该写为`<br/>`和`<img/>`
- 属性引号不能省略

参考：

- [维基百科-HTML](https://zh.wikipedia.org/wiki/HTML)

- [w3.org-Web发展历史](https://www.w3.org/community/webed/wiki/Zh-cn/Web%E7%9A%84%E5%8E%86%E5%8F%B2)

# HTML4

HTML4是较新而起目前广泛使用的一种标准。

## <!DOCTYPE>声明

由于HTML4提供了三种不同的类型，来适应不同的场景，所以需要在文档的**第一行**使用`<!DOCTYPE>`来**声明该文档类型**


HTML的三种模式区别以及定义方式：

1. HTML 4.01 Strict(严格文档类型)： 包含所有 HTML 元素和属性，但不包括展示性的和弃用的元素（比如 font）。不允许框架集
    ```
    <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
    ```
2. HTML 4.01 Transitional（过渡文档类型）： 包含所有 HTML 元素和属性，包括展示性的和弃用的元素（比如 font）。不允许框架集
     ```
     <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" 
     "http://www.w3.org/TR/html4/loose.dtd">
     ```
3. HTML 4.01 Frameset(框架集文档类型)： 框架集文档类型定义应当被用于带有框架的文档。除 frameset 元素取代了 body 元素之外，等同于过渡文档类型定义
    ```
    <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" 
    "http://www.w3.org/TR/html4/frameset.dtd">
    ```
    
## 标签

HTML4定义了很多的标签来描述文档结构，比如`<h1>` `<p>` `<em>` `<i>`等，需要掌握常用标签的用法。

具体参考：[w3school-标签](http://www.w3school.com.cn/tags/index.asp)

## 标签语义化

定义：根据内容的结构化（内容语义化），选择合适的标签（代码语义化）便于开发者阅读和写出更优雅的代码的
同时让浏览器的爬虫和机器很好地解析。
 
- 举个例子：

    当你写下这段代码`<h1>我的标题</h1>`的时候，谷歌爬虫根据`<h1>`标签认出了它是标题，它不希望你把标题写到`<p>`或者
`<div>`等不能表示标题含义的标签中，以为这样它不能识别出你写的是标题，从而不能很好的结构化你的文档内容。
 
- 另外一个例子： 

    我们可以从`<em>`、`<strong>`、`<b>`、`<i>`的区别来更深刻的理解语义化。
    
    `<b>`和`<i>`: 它们仅仅是简单的外观指令，用来指定标签内的内容为粗体和斜体
    （完全可以用css定义来取代:`{font-weight: bold;}{font-style: italic;}`），而没有任何语义。
    
    
    `<em>`和`<strong>`：更`<i>`和`<b>`相反，它们则是语义化很好的标签，他们分别表示‘强调’和‘更强的强调’。   

# HTML5

## Canvas

你需要知道的是Canvas是H5提供的画图API，因为它，你能将丰富的数据机构转化成一幅幅丰富的画，再运用上定时器，你就能得到美丽的动画。

有一些需要掌握的基础知识：

1. 使用Canvas画一个圆(线、举行、渐变、图片等)有哪些步骤？

   获取Canvas元素c -> cxt = c.getContext()获取绘图上下文 -> cxt.fillStyle设置填充颜色 -> cxt.beginPath()开始一个新路径
   -> cxt.arc绘制弧形 -> cxt.closePath()关闭路径 -> cxt.fill()填充
   
   参考http://www.w3school.com.cn/html5/html_5_canvas.asp
   
2. Canvas和SVG有什么区别？
    
   ||渲染速度|事件处理|分辨率|对搜索引擎友好|
   |---|---|---|---|---|
   |Canvas|快|支持|根据像素定义，固定大小|不支持搜索引擎抓取内容|
   |SVG|慢|支持|宽度自适应|支持搜索引擎抓取内容|
   
   SVG支持DOM事件定义，因为需要处理事件，渲染速度比较慢，但是可以很方便的进行DOM操作，有强大的交互处理能力。
   Canvas不支持DOM事件定义，渲染过程仅仅是绘图，因此很快，适合游戏等图像密集的应用。
   Canvas最后导出的就是一个<canvas></canvas>标签，而SVG则导出丰富的标签，如<rect></rect>、<font></font>等
   
## 本地存储localStorage和sessionStorage

1. cookie和localStorage的相同和不同的地方？

    - 相同点：他们都是用来做本地存储的
    - 不同点：他们最大的不同点就是用http对一个页面进行请求的时候，**header部分会带上cookie，而不会带上localstorage**。
   正是因为这个原因，浏览器为了性能，一般cookie最大一般只能有几K的大小，而localStorage则有几十M的大小。
   不是非得在header携带的信息尽可能存储在localStorage中，非得用cookie携带的信息则存储在cookie中，例如：
   前后端分离的应用中，后端API需要用作权限认证的token，只能存储在cookie中，这样token才能随http请求携带过去进行权限验证
   
2. localStorage和sessionStorage的不同点？
   
   localStorage储存永久生效，sessionStorage在用户关闭浏览器窗口后，数据会被删除
   
   
## 服务器推送

1. 服务器推送怎么做？有什么用？

   服务端： 设置一下header头：'Content-Type: text/event-stream‘和'Cache-Control: no-cache'
   客户端：新建一个EventSource对象，监听该对象的onmsessage方法，获取服务端事件
   
## WebSocket

平行于Http，WebSocket是基于TCP的一种新的网络协议。

1. WebSocket和Http的区别？

    Websocket是一个持久化的协议，相对于HTTP这种非持久的协议（无状态协议）来说。
    
    Http每一次发送接收请求都要经过三次握手，而且每一次请求都是独立的，服务器不知道每一次接收到的请求是谁发送的，
    需要使用到session的技术来分辨两次请求是不是同一个来源。
    
    Websocket是一个持久化的协议，建立了联系以后保持着这个联系，直到关闭连接。在socket打开期间，服务端和客户端
    明确地知道对方的身份，并且可以实时向对方发送数据。
    
2. 实现聊天室功能，有哪些方法？
    
    - AJAX轮循。设置定时器，定时向服务端拉取数据。
    - IFrame轮循。设置定时器，改变IFrame的src属性（指向服务端数据源），从而定时获取服务器数据。
    - Long Poll。客户端把AJAX的timeout时间设置成很长，服务端把请求设为长连接，服务端在有数据推送的时候才respond
    - Flash。socket技术实现长久连接，双工通信。
    - WebSocket。WebSocket技术实现长久连接，双工通信。
   
## 拖拽

增加了这三个ondragstart、ondrop、ondragover事件处理器。

   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   