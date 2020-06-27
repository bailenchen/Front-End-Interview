# 谈谈你对 HTML 语义化的理解

根据内容的语义化（内容结构化），选择合适的标签（代码语义化），便于开发者阅读和写出更优雅的代码，同时让爬虫和机器阅读更好的解析。

- 为什么要语义化？

1. 为了在没有 css 的情况下，页面也能呈现出很好的内容结构和代码结构。
2. 为了提升用户体验，如：title，alt 用于解释名词或解释图片信息，lable 标签的活用。
   有利于和搜索引擎建立良好的沟通。
3. 方便其他设备解析（如屏幕阅读器，盲人阅读器，移动设备），以意义的方式来渲染网页。
4. 便于团队的开发和维护，语义化更具有可读性，是下一步网页的重要动向，遵循 W3C 标准的团队都遵循这个标准，可以减少差异化。

- 写 HTML 代码时应注意什么？

  - 尽可能少的使用无语义的标签 div 和 span
  - 不要使用纯样式的标签，如：b，font，u 等，改用 css 设置
  - 表单域要用 fieldset 标签包起来，并用 legend 标签说明标签的用途
  - 每个 input 标签对应的文本框都需要使用 label 标签，并关联起来

# 谈谈你对 web 标准以及 W3C 的理解？

- web 标准

  web 标准主要分为结构、表现、行为 3 部分

  - 结构：指我们平时在 body 里面写的标签，主要是由 HTML 标签组成

  - 表现：指更加丰富 HTML 标签样式，主要由 CSS 样式组成

  - 行为：指页面和用户的交互，主要由 JS 部分组成

* W3C

  W3C 对 web 标准提出了规范化的要求，即代码规范

* 对结构的要求

1. 标签字母要小写
2. 标签要闭合
3. 标签不允许随意嵌套

- 对表现和行为的要求

  建议使用外链 CSS 和 js 脚本，实现结构与表现分离、结构与行为分离，能提高页面的渲染效率，更快地显示网页内容

# 前端需要注意哪些 SEO

- 合理的`title`、`description`、`keywords`：
  - 搜索对着三项的权重逐个减小，title 值强调重点即可，重要关键词出现不要超过 2 次，而且要靠前
  - 不同页面 title 要有所不同；
  - description 把页面内容高度概括，长度合适，不可过分堆砌关键词，不同页面 description 有所不同
  - keywords 列举出重要关键词即可
- 语义化的 HTML 代码
  符合 W3C 规范：语义化代码让搜索引擎容易理解网页
- 重要内容 HTML 代码放在最前
  - 搜索引擎抓取 HTML 顺序是从上到下，有的搜索引擎对抓取长度有限制，保证重要内容一定会被抓取
- 重要内容不要用 js 输出
  - 爬虫不会执行 js 获取内容
- 少用 iframe
  - 搜索引擎不会抓取 iframe 中的内容
- 非装饰性图片必须加 alt
- 提高网站速度
  - 网站速度是搜索引擎排序的一个重要指标

# Doctype

- Doctype 作用

`<!DOCTYPE>`声明叫做文件类型定义（DTD），声明的作用为了告诉浏览器该文件的类型。让浏览器解析器知道应该用哪个规范来解析文档。`<!DOCTYPE>`声明必须在 HTML 文档的第一行，这并不是一个 HTML 标签。

- 严格模式与混杂模式如何区分？它们有何意义？

  - 严格模式：又称标准模式，是指浏览器按照 W3C 标准解析代码。
  - 混杂模式：又称怪异模式或兼容模式，是指浏览器用自己的方式解析代码。

如何区分：浏览器解析时到底使用严格模式还是混杂模式，与网页中的 DTD 直接相关。

1. 如果文档包含严格的 DOCTYPE ，那么它一般以严格模式呈现。（**严格 DTD ——严格模式**）
2. 包含过渡 DTD 和 URI 的 DOCTYPE ，也以严格模式呈现，但有过渡 DTD 而没有 URI （统一资源标识符，就是声明最后的地址）会导致页面以混杂模式呈现。（**有 URI 的过渡 DTD ——严格模式；没有 URI 的过渡 DTD ——混杂模式**）
3. DOCTYPE 不存在或形式不正确会导致文档以混杂模式呈现。（**DTD 不存在或者格式不正确——混杂模式**）
4. HTML5 没有 DTD ，因此也就没有严格模式与混杂模式的区别，HTML5 有相对宽松的语法，实现时，已经尽可能大的实现了向后兼容。（**HTML5 没有严格和混杂之分**）

意义：严格模式与混杂模式存在的意义与其来源密切相关，如果说只存在严格模式，那么许多旧网站必然受到影响，如果只存在混杂模式，那么会回到当时浏览器大战时的混乱，每个浏览器都有自己的解析模式。

- 常用的 DOCTYPE 声明

1. HTML5（一种）：`<!DOCTYPE html>`

2. HTML 4.01（三种）：严格模式包含所有 HTML 元素和属性，但不包括展示性的和弃用的元素（比如 font），不允许框架集（Framesets）；过渡模式包含所有 HTML 元素和属性，包括展示性的和弃用的元素（比如 font），不允许框架集（Framesets）；框架模式等同于过渡模式，但允许框架集内容。

3. XHTML 1.0（四种）

- HTML5 为什么只需要写 `<!DOCTYPE html>`

HTML5 不基于 SGML，因此不需要对 DTD 进行引用，但是需要 doctype 来规范浏览器的行为
而 HTML4.01 基于 SGML,所以需要对 DTD 进行引用，才能告知浏览器文档所使用的文档类型

# link 和 @import 有什么区别？

1. 从属关系区别

@import 是 CSS 提供的语法规则，只有导入样式表的作用；link 是 HTML 提供的标签，不仅可以加
载 CSS 文件，还可以定义 RSS、rel 连接属性、引入网站图标等。

2. 加载顺序区别

加载页面时，link 标签引入的 CSS 被同时加载；@import 引入的 CSS 将在页面加载完毕后被加载。

3. 兼容性区别

@import 是 CSS2.1 才有的语法，故只可在 IE5+ 才能识别；link 标签作为 HTML 元素，不存在兼容
性问题。

4. DOM 可控性区别

可以通过 JS 操作 DOM ，插入 link 标签来改变样式；由于 DOM 方法是基于文档的，无法使用 @i
mport 的方式插入样式。

5. 优先级

link 方式的样式的权重 高于@import 的权重。

# title 与 h1 的区别？

title 属性没有明确意义只表示是个标题，h1 则表示层次明确的标题，对页面信息的抓取也有很大的影响。

# b 与 strong 的区别和 i 与 em 的区别？

```
从页面显示效果来看，被 <b> 和 <strong> 包围的文字将会被加粗，而被 <i> 和 <em> 包围的文字将以斜体的形式呈现。

但是 <b> <i> 是自然样式标签，分别表示无意义的加粗，无意义的斜体，表现样式为 { font-weight: bolder}，仅仅表示「这
里应该用粗体显示」或者「这里应该用斜体显示」，此两个标签在 HTML4.01 中并不被推荐使用。

而 <em> 和 <strong> 是语义样式标签。 <em> 表示一般的强调文本，而 <strong> 表示比 <em> 语义更强的强调文本。

使用阅读设备阅读网页时：<strong> 会重读，而 <b> 是展示强调内容。
```

# label 的作用是什么？是怎么用的？

label 标签来定义表单控制间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。

```HTML
<label for="Name">Number:</label>
<input type=“text“ name="Name" id="Name"/>
```

# disabled 和 readonly 的区别？

disabled 指当 input 元素加载时禁用此元素。input 内容不会随着表单提交。

readonly 规定输入字段为只读。input 内容会随着表单提交。

无论设置 readonly 还是 disabled，通过 js 脚本都能更改 input 的 value

# img 的 title 和 alt 有什么区别

alt 是`<img>`的特有属性，是图片内容的等价描述，用于图片无法加载时显示、读屏器阅读图片。可提图片高可访问性，除了纯装饰图片外都必须设置有意义的值，搜索引擎会重点分析。

title 通常当鼠标滑动到元素上的时候显示。title 是全局属性

# iframe 有那些缺点？

iframe 元素会创建包含另外一个文档的内联框架（即行内框架）。

主要缺点有：

1. iframe 会阻塞主页面的 onload 事件。window 的 onload 事件需要在所有 iframe 加载完毕后（包含里面的元素）才会触发。在 Safari 和 Chrome 里，通过 JavaScript 动态设置 iframe 的 src 可以避免这种阻塞情况。
2. 搜索引擎不能够解读 iframe 页面，不利于 seo
3. iframe 和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。
4. 浏览器的后退按钮失效。
5. 小型的移动设备无法完全显示框架。

# head 标签中必不少的是？

`<title>` 定义文档的标题，它是 head 部分中唯一必需的元素。

# XHTML 和 HTML 有什么区别

- 一个是功能上的差别

  - 主要是 XHTML 可兼容各大浏览器、手机以及 PDA，并且浏览器也能快速正确地编译网页

- 另外是书写习惯的差别
  - XHTML 元素必须被正确地嵌套，闭合，区分大小写，文档必须拥有根元素

# 注释

```HTML
<!-- 注释 -->
```

# 页面乱码

网页乱码出现通常是因为网页开发者没有按照规范来设置网页编码，浏览器打开这类网页的时候自动按照默认的编码来打开导致的。

解决办法

```HTML
<head>
<meta charset="UTF-8"> <!-- H5的写法 -->
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<head>
```

# 全局属性

1. id
2. class
3. title
4. style
5. `data-*`: 为元素增加自定义属性
6. draggable: 设置元素是否可拖拽
7. dropzone: 设置元素拖放类型： copy, move, link
8. tabindex: 设置元素可以获得焦点，通过 tab 可以导航
9. accesskey:设置快捷键，提供快速访问元素如 aaa 在 windows 下的 firefox 中按 alt + shift + a 可激活元素
10. translate: 元素和子孙节点内容是否需要本地化
11. contenteditable: 指定元素内容是否可编辑
12. contextmenu: 自定义鼠标右键弹出菜单内容
13. hidden: 表示一个元素是否隐藏。样式上会导致元素不显示，但是不能用这个属性实现样式效果
14. lang: 元素内容的语言
15. spellcheck: 是否启动拼写和语法检查
16. dir: 设置元素文本方向

# Html 规范中为什么要求引用资源不加协议头 http 或者 https？

如果用户当前访问的页面是通过 HTTPS 协议来浏览的，那么网页中的资源也只能通过 HTTPS 协议来引用，否则浏览器会出现
警告信息，不同浏览器警告信息展现形式不同。

为了解决这个问题，我们可以省略 URL 的协议声明，省略后浏览器照样可以正常引用相应的资源，这项解决方案称为
protocol-relative URL，暂且可译作协议相对 URL。

如果使用协议相对 URL，无论是使用 HTTPS，还是 HTTP 访问页面，浏览器都会以相同的协议请求页面中的资源，避免弹出类似
的警告信息，同时还可以节省 5 字节的数据量。

# meta 有哪些常见的值？

```HTML
<meta name="keywords" content="your tags" />
<meta name="description" content="150 words" />
<meta name="robots" content="index,follow" />
<meta http-equiv="refresh" content="0;url=" />
<meta name="author" content="author name" />
<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">
关闭自动识别数字为电话号码
<meta content="telephone=no" name="format-detection" />
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
```

# 简述一下 src 与 href 的区别

src 用于替换当前元素，href 用于在当前文档和引用资源之间确立联系。

src 是 source 的缩写，指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求 src 资源时会将其指向的资源下载并应用到文档内，例如 js 脚本，img 图片和 frame 等元素

```Javascript
<script src ="js.js"></script> 当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于将所指向资源嵌入当前标签内。这也是为什么将js脚本放在底部而不是头部
```

href 是 Hypertext Reference 的缩写，指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，如果我们在文档中添加

`<link href="common.css" rel="stylesheet"/>`那么浏览器会识别该文档为 css 文件，就会并行下载资源并且不会停止对当前文档的处理。这也是为什么建议使用 link 方式来加载 css，而不是使用@import 方式

# input 与 textarea 的区别

- 相同点：

1. 都是用于接收用户输入
2. 都支持  H5  新属性  autofocus(自动获得焦点) 、autocomplete(自动记忆上次输入的值)
3. 都支持  display 、readonly  控制
4. 都支持   使用  placeholder（H5）设置输入的提示信息
5. 当  input  输入  type  为  text, email, search, password, tel,  或  url  时,  两者都可以通过  minlength/maxlength  控制输入的最少/最大内容长度
6. 使用 js  获取值时，都可以使用 .value  获取

- 不同点：

1. input  使用  type  属性指定接受的类型，包括但不限于文本。textarea  接收多行文本输入。
2. input  是单标签类型，没有结束标签；textarea  是双标签类型，必须要有结束标签。
3. 设置初始内容时，input  放在  value 属性中：`<input type="text" value="这是内容">`， textarea 放在起止标签内：`<textarea>这是内容</textarea>`
4. textarea 使用  rows、cols 控制多行结构，input  只是单行
5. textarea 默认可手动拖动缩放

# HTML5 有哪些新特性、移除了那些元素？

HTML5 现在已经不是 SGML 的子集。

- 语意化标签 article、aside、nav、header、footer、section、
- 增强表单控件 calendar、date、time、email、url、search
- 新的文档属性 document.visibilityState
- 绘画 canvas、svg;
- 媒体播放的 video 和 audio
- 拖拽释放(Drag and drop) API
- 本地存储 localStorage 和 sessionStorage
- 新增选择器 document.querySelector、document.querySelectorAll
- 地理位置 Geolocation
- 多任务 webworker
- 全双工通信协议 websocket
- 历史管理 history
- 跨域资源共享(CORS) Access-Control-Allow-Origin
- 页面可见性改变事件 visibilitychange
- 跨窗口通信 PostMessage
- Form Data 对象
- 绘画 canvas
- 离线应用 manifest
- 桌面通知 Notifications

* 移除的元素有：

  - 纯表现的元素：basefont，big，center，font, s，strike，tt，u;
  - 对可用性产生负面影响的元素：frame，frameset，noframes；

# 如何处理 HTML5 新标签的浏览器兼容问题？

- 通过 document.createElement 创建新标签

IE8/IE7/IE6 支持通过 document.createElement 方法产生的标签，可以利用这一特性让这些浏览器支持 HTML5 新标签，浏览器支持新标签后，还需要添加标签默认的样式。

- 使用垫片 html5shiv.js

```HTML
<!--[if lt IE 9]>
  <script type="text/javascript" src="scripts/html5shiv.js"></script>
<![endif]-->
```

# HTML5 元素的分类

HTML4 中，元素被分成两大类: inline（内联元素）与 block（块级元素）。但在实际的开发过程中，因为页面表现的需要，前
端工程师经常把 inline 元素的 display 值设定为 block （比如 a 标签），也经常把 block 元素的 display 值设定为
inline 之后更是出现了 inline-block 这一对外呈现 inline 对内呈现 block 的属性。因此，简单地把 HTML 元素划分为
inline 与 block 已经不再符合实际需求。

HTML5 中，元素主要分为 7 类：

- Metadata
- Flow
- Sectioning
- Heading
- Phrasing
- Embedded
- Interactive

# data- 属性的作用？

data-是 H5 新增的自定义的属性，这些属性集可以通过元素的 dataset(对象) 属性获取，不支持该属性的浏览器可以通过 getAttribute 方法获取 :

需要注意的是：data-之后的以连字符分割的多个单词组成的属性，获取的时候使用驼峰风格。 所有主流浏览器都支持 `data-*` 属性。

即：当没有合适的属性和元素时，自定义的 data 属性是能够存储页面或 App 的私有的自定义数据

```HTML
<div data-my="haha"></div>
```

```Javascript
var el = document.querySelector('div')
console.log(el.dataset.my); // haha
```

# HTML5 的 form 的自动完成功能是什么？

autocomplete 属性规定输入字段是否应该启用自动完成功能。默认为启用，设置为 autocomplete=off 可以关闭该功能。

自动完成允许浏览器预测对字段的输入。当用户在字段开始键入时，浏览器基于之前键入过的值，应该显示出在字段中填写的选项。

autocomplete 属性适用于 `<form>`，以及下面的 `<input>` 类型：text, search, url, telephone, email, password, datepickers, range 以及 color。

```HTML
<form action="demo-form.php" autocomplete="on">
  First name:<input type="text" name="fname"><br>
  Last name: <input type="text" name="lname"><br>
  E-mail: <input type="email" name="email" autocomplete="off"><br>
  <input type="submit">
</form>
```

当提交后刷新页面，并点击输入域获得焦点后**可以看到以前的输入记录**，而 email 关闭了 autocomplete，所以也就没有输入记录。

# 常见的浏览器端的存储技术有哪些？

浏览器常见的存储技术有 cookie、localStorage 和 sessionStorage。

还有两种存储技术用于大规模数据存储，webSQL（已被废除）和 indexDB。

IE 支持 userData 存储数据，但是基本很少使用到，除非有很强的浏览器兼容需求。

# cookies，sessionStorage 和 localStorage 的区别

浏览器端常用的存储技术是 cookie 、localStorage 和 sessionStorage。

cookie 其实最开始是服务器端用于记录用户状态的一种方式，由服务器设置，在客户端存储，然后每次发起同源请求时，发送给服务器端。cookie 最多能存储 4 k 数据，它的生存时间由 expires 属性指定，并且 cookie 只能被同源的页面访问共享。

sessionStorage 是 html5 提供的一种浏览器本地存储的方法，它借鉴了服务器端 session 的概念，代表的是一次会话中所保存的数据。它一般能够存储 5M 或者更大的数据，它在当前窗口关闭后就失效了，并且 sessionStorage 只能被同一个窗口的同源页面所访问共享。

localStorage 也是 html5 提供的一种浏览器本地存储的方法，它一般也能够存储 5M 或者更大的数据。它和 sessionStorage 不同的是，除非手动删除它，否则它不会失效，并且 localStorage 也只能被同源页面所访问共享。

上面几种方式都是存储少量数据的时候的存储方式，当我们需要在本地存储大量数据的时候，我们可以使用浏览器的 indexDB 这是浏览器提供的一种**本地的数据库存储**机制。它不是关系型数据库，它内部采用对象仓库的形式存储数据，它更接近 NoSQL 数据库。

# 如何实现浏览器内多个标签页之间的通信?

实现多个标签页之间的通信，本质上都是通过中介者模式来实现的。因为标签页之间没有办法直接通信，因此我们可以找一个中介者，
让标签页和中介者进行通信，然后让这个中介者来进行消息的转发。

第一种实现的方式是使用 websocket 协议，因为 websocket 协议可以实现服务器推送，所以服务器就可以用来当做这个中介者。
标签页通过向服务器发送数据，然后由服务器向其他标签页推送转发。

第二种是使用 ShareWorker 的方式，shareWorker 会在页面存在的生命周期内创建一个唯一的线程，并且开启多个页面也只会使
用同一个线程。这个时候共享线程就可以充当中介者的角色。标签页间通过共享一个线程，然后通过这个共享的线程来实现数据的交
换。

第三种方式是使用 localStorage 的方式，我们可以在一个标签页对 localStorage 的变化事件进行监听，然后当另一个标签页
修改数据的时候，我们就可以通过这个监听事件来获取到数据。这个时候 localStorage 对象就是充当的中介者的角色。

还有一种方式是使用 postMessage 方法，如果我们能够获得对应标签页的引用，我们就可以使用 postMessage 方法，进行通信。

# webSocket 如何兼容低版本浏览器？

- Adobe Flash Socket
- ActiveX HTMLFile (IE)
- 基于 multipart 编码发送 XHR
- 基于长轮询的 XHR

# 页面可见性（Page Visibility API） 可以有哪些用途？

这个新的 API 的意义在于，通过监听网页的可见性，可以预判网页的卸载，还可以用来节省资源，减缓电能的消耗。比如，一旦用户不看网页，下面这些网页行为都是可以暂停的。

1. 对服务器的轮询
2. 网页动画
3. 正在播放的音频或视频

# Canvas 和 SVG 有什么区别？

Canvas 是一种通过 JavaScript 来绘制 2D 图形的方法。Canvas 是逐像素来进行渲染的，因此当我们对 Canvas 进行缩放时，
会出现锯齿或者失真的情况。

SVG 是一种使用 XML 描述 2D 图形的语言。SVG 基于 XML，这意味着 SVG DOM 中的每个元素都是可用的。我们可以为某个元素
附加 JavaScript 事件监听函数。并且 SVG 保存的是图形的绘制方法，因此当 SVG 图形缩放时并不会失真。

# HTML5 的离线储存怎么使用，工作原理能不能解释一下？

在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件

原理：HTML5 的离线存储是基于一个新建的.appcache 文件的缓存机制(不是存储技术)，通过这个文件上的解析清单离线存储资源，这些资源就会像 cookie 一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示

如何使用：

- 页面头部像下面一样加入一个 `manifest` 的属性；
- 在 `cache.manifest` 文件的编写离线存储的资源
- 在离线状态时，操作 `window.applicationCache` 进行需求实现

```
CACHE MANIFEST
#v0.11
CACHE:
js/app.js
css/style.css
NETWORK:
resourse/logo.png
FALLBACK:
/offline.html


CACHE: 表示需要离线存储的资源列表，由于包含 manifest 文件的页面将被自动离线存储，所以不需要把页面自身也列出来。

NETWORK: 表示在它下面列出来的资源只有在在线的情况下才能访问，他们不会被离线存储，所以在离线情况下无法使用这些资源。不过，如果在 CACHE 和 NETWORK 中有一个相同的资源，那么这个资源还是会被离线存储，也就是说 CACHE 的优先级更高。

FALLBACK: 表示如果访问第一个资源失败，那么就使用第二个资源来替换他，比如上面这个文件表示的就是如果访问根目录下
```

在离线状态时，操作 window.applicationCache 进行离线缓存的操作。

- 如何更新缓存：

1. 更新 manifest 文件
2. 通过 javascript 操作
3. 清除浏览器缓存

- 注意事项：

1. 浏览器对缓存数据的容量限制可能不太一样（某些浏览器设置的限制是每个站点 5MB）。
2. 如果 manifest 文件，或者内部列举的某一个文件不能正常下载，整个更新过程都将失败，浏览器继续全部使用老的缓存。
3. 引用 manifest 的 html 必须与 manifest 文件同源，在同一个域下。
4. FALLBACK 中的资源必须和 manifest 文件同源。
5. 当一个资源被缓存后，该浏览器直接请求这个绝对路径也会访问缓存中的资源。
6. 站点中的其他页面即使没有设置 manifest 属性，请求的资源如果在缓存中也从缓存中访问。
7. 当 manifest 文件发生改变时，资源请求本身也会触发更新。

# 浏览器是怎么对 HTML5 的离线储存资源进行管理和加载的呢

在线的情况下，浏览器发现 html 头部有 `manifest` 属性，它会请求 `manifest` 文件，如果是第一次访问 app，那么浏览器就会根据 `manifest` 文件的内容下载相应的资源并且进行离线存储。如果已经访问过 app 并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的 `manifest` 文件与旧的 `manifest` 文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。

离线的情况下，浏览器就直接使用离线存储的资源。

# 用一个 div 模拟 textarea 的实现

```CSS
div {
  width: 400px;
  min-height: 100px;
  max-height: 300px;
  _height: 100px; /* IE6 */
  margin-left: auto;
  margin-right: auto;
  padding: 3px;
  outline: 0;
  border: 1px solid #a0b3d6;
  font-size: 12px;
  word-wrap: break-word;
  overflow-x: hidden;
  overflow-y: auto; /* 超过最大高度就出现滚动条 */
  _overflow-y: visible;
}
```

```HTML
<div contenteditable="true">
  .....此处省略.....
</div>
```
