#### src和hef的区别
+ src: 表示对资源的引用，它指向的内容会嵌入到当前标签所在的位置。src会将其指向的资源下载并应用到文档内，如请求js脚本。当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将该资源加载、编译、执行完毕，所以一般js脚本会放在页面底部。
+ href：表示超文本引用，它指向一些网络资源，建立和当前元素或本文档的链接关系。当浏览器识别到它他指向的文件时，就会并行下载资源，不会停止对当前文档的处理。常用在a、link等标签上。

#### 对HTML语义化的理解
+ 语义化是指根据内容的结构化（内容语义化），选择合适的标签（代码语义化）。通俗来讲就是用正确的标签做正确的事情。
+ 优点：
  - 对机器友好，带有语义的文字表现力丰富，更适合搜索引擎的爬虫爬取有效信息，有利于SEO.除此之外，语义类还支持读屏软件，根据文章可以自动生成目录。
  - 对开发者友好，使用语义类标签增强了可读性，结构更加清晰，开发者能清晰的看出网页的结构，便于团队的开发与维护

#### DOCTYPE（文档类型）的作用
+ DOCTYPE是HTML5中一种标准通用标记语言的文档类型声明，它的目的是告诉浏览器（解析器）应该以什么样（html或xhtml）的文档类型定义来解析文档，不同的渲染模式会影响浏览器对CSS代码甚至JavaScript脚本的解析。它必须声明在HTML文档的第一行。
+ 浏览器渲染页面的两种模式（可通过document.compatMode获取）
  - CSS1Compat：标准模式，默认模式（Strick mode），浏览器使用W3C的标准解析渲染页面。在标准模式中，浏览器心其支持的最高标准呈现页面。
  - BackCompat：怪异模式（Quick mode），浏览器使用自己的怪异模式解析渲染页面。在怪异模式中，页面以一种比较宽松的向后兼容的方式显示。

#### script标签中defer和async的区别
+ defer和async属性都是去异步加载外部的JS脚本文件，它们都不会阻塞页面的解析，其区别如下
  - 执行顺序：多个带async属性的标签，不能保证加载的顺序；多个带defer属性的标签，按照加载顺序执行。
  - 脚本是否并行执行：async属性，表示后续文档的加载和执行与js脚本的加载和执行是并行进行的，即异步执行；fefaer属性，加载后续文档的过程笔js脚本的加载（此时仅加载不执行）是并行进行的（异步），js脚本需要等到文档所有元素解析完成之后才执行，DOMContentLoaded事件触发执行之前。

#### 常用的meta标签有哪些
meta标签由 name和content属性定义，用来描述网页文档的属性，比如网页的作者，网页描述，关键词等，除了HTTP标准固定一些name作为大家使用的共识，开发者还可以自定义name。
+ 常用的meta标签：
  - charset，用来描述HTML文档的编码类型：`<meta charset="UTF-8">`
  - keywords，页面关键词：`<meta name="keywords" content="关键词">`
  - description，页面描述：`<meta name="description" content="页面描述内容">`
  - refresh，页面重定向和刷新：`<meta http-equiv="refresh" content="0;url=">`
  - viewport，适配移动端，可以控制视口的大小和比例：`<meta name="viewport" content="width=device-width, initial-scale=1, maximun-scale=1">`
  - robots，搜索引擎索引方式：`<meta name="robots" content="index,follow">`

#### HTML5有哪些更新
+ 语义化标签
  - header
  - nav
  - footer
  - article — 定义文章内容
  - section — 定义文档中的节
  - aside — 定义其所处内容之外的内容（侧边）
+ 媒体标签
  - audio：音频
  - video：视频
  - source：因为浏览器对视频格式支持程度不一样，为了能够兼容不同的浏览器，可以通过source来指定视频源。
+ 表单类型
  - email：能够验证当前输入的邮箱地坛是否合法
  - url：验证URL
  - number：只能输入数字，其它输入不了，而且自带上下增大减小箭头，max属性可以设置为最大值，min可以设置为最小值，value为默认值。
  - search：输入框后面会给提供一个小叉，可以删除输入的内容，更加人性化。
  - range：可以提供一个范围，其中可以设置max和min以及value，其中value属性可以设置为默认值
  - color：提供了一个颜色拾取器
  - time： 时分秒
  - data：日期选择年月日
  - datatime：时间和日期（目前只有Safari支持）
  - datatime-local：日期时间控件
  - week：周控件
  - month：月控件

+ 表单属性：
  - placeholder：提示信息 
  - autofocus：自动获取焦点
  - autocomplete：表单必须提交过，必须要有name属性
  - required：要求输入框不能为空，必须有值才能够提交
  - pattern：里面写入想要的正则模式
  - mutiple：可以选择多个文件或者多个邮箱
  - form：form表单的ID

+ 表单事件
  - onipnut 每当input里的输入框内容发生变化都会触发此事件
  - oninvalid 当验证不通过时触发此事件

+ 进度条、度量器
  - progress标签：用来表示任务的进度（IE、Safair不支持），max用来表示任务的进度，value表示已完成多少
  - meter属性：用来显示剩余容量或剩余库存（IE、Safari不支持）

+ DOM查询操作
  - document.querySelector()
  - document.querySelectorAll()

+ Web存储
  - localStorage — 没有时间限制的数据存储
  - sessionStorage — 针对一个session的数据存储

+ 其他
  - `<img draggable="true">`
  - `<canvas></canvas>`
  - `SVG`

+ 总结
  - 新增语义化标签：nav、header、footer、aside、section、article
  - 音频、视频标签：audio、video
  - 数据存储：localStorage、sessionStorage
  - Canvas（画布）、Geolocation（地理定位）、websocket（通信协议）
  - input标签新增属性：placeholder、autocomplete、autofocus、required
  - history API：go、forward、back、pushstate

#### img的srcset属性的作用
+ 响应式页面中经常用到根据屏幕密度设置不同的图片。
+ `<img src="image-128.png" srcset="image-256.png 2x">`

#### 行内元素有哪些？块级元素有哪些？空元素有哪些
+ 行内元素有：`a b span img input select strong`
+ 块级元素有：`div ul ol li dl dt dd h1 h2 h3 h4 h5 h6 p`
+ 空元素：
  - 常见的有：`<br>、<hr>、<img>、<input>、<link>、<meta>`
  - 鲜见的有：`<area>、<base>、<col>、<colgroup>、<command>、<embed>、<keygen>、<param>、<source>、<track>、<wbr>`

#### 说一下web worker
+ 在HTML页面中，如果在执行脚本时，页面的状态是不可相应的，直到脚本执行完成后，页面才变成可相应。web worker是运行在后台的js，独立于其他脚本，不会影响页面的性能。并且通过postMessage将结果回传到主线程。这样在进行复杂操作的时候，就不会阻塞主线程了。
+ 如何创建web worker：
  - 检测浏览器对于web worker的支持性
  - 创建web worker文件（js，回传函数等）
  - 创建web worker对象

#### HTML5的离线储存怎么使用，它的工作原理是什么
+ 离线存储指的是：在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。
+ HTML5的离线存储是基于一个新建的.appcache文件的缓存机制，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示
+ 使用方法：创建一个和html同名的manifest文件，然后在页面头部加入manifest属性`<html lang="en" manifest="index.manifest">`

#### 浏览器是如何对HTML5的离线储存资源进行管理和加载
+ 在线的情况下：浏览器发现html头部有manifest属性，它会请求manifest文件，如果是第一次访问页面，那么浏览器就会根据manifest文件的内容下载相应 的资源并且进行离线存储。如果已经访问过页面并且资源已经进行离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，就会重新下载文件中的资源并进行离线存储。
+ 离线的情况下：浏览器会直接使用离线存储的资源

#### title与h1的区别、b与strong的区别、i与em的区别
+ title属性没有明确意义只表示是个标题，H1则表示层次明确的标题，对页面信息的抓取有很大的影响
+ strong标签有语义，是起到加重语气的效果，而b标签是没有的，b标签只是一个简单加粗标签。b标签之间的字符都设为粗体，strong标签加强字符的语气都是通过粗体来实现的，而搜索引擎更侧重strong标签。
+ i内容展示为斜体，em表示强调的文本

#### iframe有哪些优点和缺点
+ 优点
  - 用来加载速度较慢的内容
  - 可以使脚本并行下载
  - 可以实现跨子域通信
+ 缺点
  - iframe会阻塞主页面的onload事件
  - 无法被一些搜索引擎识别
  - 会产生很多页面，不容易管理

#### label的作用是什么？如何使用？
+ label标签来定义表单控件的关系：当用户选择label标签时，浏览器会自动将焦点转到和label标签相关的表单控件上
  - 使用方法1：`<label for="mobiel">Number:</label><input type="text" id="mobile">`
  - 使用方法2：`<label>Date：<input type="text" /></label>`

#### Canvas和SVG的区别
+ SVG：SVG可绽放矢量图形是基于可扩展标记语言XML描述的2D图形的语言，SVG基于XML就意味着SVG DOM中的每个元素都是可用的，可以为某个元素附加Javascript事件处理器。在SVG中，每个被绘制的图形均被视为对象。如果SVG对象的属性发生变化，那么浏览器能够自动重现图形。
  - 不依赖分辨率
  - 支持事件处理器
  - 最适合带有大型渲染区域的应用程序
  - 复杂度高会减慢渲染速度
  - 不适合游戏应用
+ Canvas：Canvas是画面，通过JavaScript来绘制图形，是逐像素进行渲染的。其位置发生改变，就会重新进行绘制。
  - 依赖分辨率
  - 不支持事件处理器
  - 弱的文本渲染能力
  - 能够以.png或.jp格式保存结果图像
  - 最适合图像密集形的游戏，其中的许多对象会被频繁重绘

#### head标签有什么作用，其中什么标签必不可少
+ 标签用于定义文档的头部，它是所有头部元素的容器。head中的元素可以引用脚本、指示浏览器在哪里找到样式表，提供元信息等
+ 文档的头部描述了文档的各种属性和信息，包括文档的标题、在Web中的位置以及和其他文档的关系等。绝大多数文档头部包含的数据都不会真正作为内容显示给读者。
  - 下面这些标签可用在head部分：`<base>、<link>、<meta>、<script>、<style>、<title>`
  - 其中title定义文档的标题，它是head部分中唯一必需元素。

#### 文档声明（Doctype）和<!Doctype html>有何作用？严格模式与混杂模式如何区别？它们有何意义
+ 文档声明的作用：文档声明是为了告诉浏览器，当前HTML文档使用什么版本的HTML来写的，这样浏览器才能按照声明的版本来正确的解析
+ <!Doctype html>的作用：让浏览器进入标准模式，使用最新的HTML5标准来解析渲染页面；如果不写，浏览器就会进入混杂模式，我们需要避免此类情况发生。
+ 区分：网页中的DTD，直接影响到使用的是严格模式还是浏览模式，可以说DTD的使用与这两种方式的区别息息相关。
  - 如果文档包含严格的DOCTYPE，那么它一般以严格模式呈现（严格DTD———— 严格模式）
  - 包含过渡DTD和URI的DOCTYPE，也以严格模式呈现（严格 DTD ——严格模式）
  - DOCTYPE不存在或形式不正确会导致文档以混杂模式呈现（DTD不存在或者格式不正确———混杂模式）
  - HTML5没有DTD，因为也就没有严格模式与混杂模式的区别，HTML5有相对宽松的法，实现时，已经尽可能大的实现了向后兼容（HTML5没有严格和混杂之分）

#### 浏览器乱码的原因是什么？如何解决？
+ 产生乱码的原因：
  - 网页源代码是gbk的编码，而内容中的中文字是utf-8编码的，这样浏览器打开即会出现html乱码，反之也会出现乱码
  - html网页编码是gbk，而程序从数据库中调出呈现是utf-8编码的内容也会造成编码乱码
  - 浏览器不能自动检测网页编码，造成网页乱码

+ 解决办法
  - 使用软件编缉HTML网页内容
  - 如果网页设置编码是gbk，而数据库储存数据编码格式是UTF-8，此时需要程序查询数据库数据显示数据前进程序转码
  - 如果浏览器浏览时候出现网页乱码，在浏览器中找到转换编码的菜单进行转换

#### 渐进增强和优雅降级之间的区别
+ 渐进增加：主要是针对低版本的浏览器进行页面重构，保证基本的功能情况下，再针对高级浏览器进行效果、交互等方面的改进和追加功能，以达到更好的用户体验。
+ 优雅降级：一开始就构建完整的功能，然后再针对低版本的浏览器进行兼容
+ 两者区别：
  - 优雅降级是从复杂的现状开始的，并试图减少用户体验的供给；而渐进增强是从一个非常基础的，能够起作用的版本开始的，并在此基础上不断扩充，以适应未来环境的需要
  - 降级意味着往回看，而渐进增强则意味着往前看，同时保证其根基处于安全地带

#### 说一 下HTML5 drag API
dragstart：事件主体是被拖放元素，在开始拖放被拖放元素时触发。
drag：事件主体是被拖放元素，在正在拖放被拖放元素时触发。
dragenter：事件主体是目标元素，在被拖放元素进入某元素时触发
dragover：事件主体是目标元素，在被拖放在某元素内移动时触发
dragleave：事件主体是目标元素，在被拖放元素移出目标元素时触发
drop：事件主体是目标元素，在目标元素完全接受被拖放元素时触发。
dragend：事件主体是被拖放元素，在整个拖放操作结束时触发。
  
