#### CSS选择器及其优先级
| 选择器         | 格式         | 优先级权重 |
| -------------- | ------------ | ---------- |
| id选择器       | #id          | 100        |
| 类选择器       | .classname   | 10         |
| 属性选择器     | a[ref="eee"] | 10         |
| 伪类选择器     | i:last-child | 10         |
| 标签选择器     | div          | 1          |
| 伪元素选择器   | li:after     | 1          |
| 相邻兄弟选择器 | h1+ p        | 0          |
| 子选择器       | ul > li      | 0          |
| 后代选择器     | li a         | 0          |
| 通配符选择器   | *            | 0          |
+ 对于选择器的优先级：
  - 标签选择器、伪元素选择器：1
  - 类选择器、伪类选择器、属性选择器：10
  - id选择器：100
  - 内联样式：1000

+ 注意事项
  - !important声明的样式的优先级最高
  - 如果优先级相同，则最后出现的样式生效
  - 继承得到的样式的优先级最低
  - 通用选择器（*）、子选择器（>）和相邻同胞选择器（+）并不在这四个等级中，所以它们的权值都为0
  - 样式表的来源不同时，优先级顺序为：内联样式 > 外部样式 > 浏览器用户自定义样式 > 浏览器默认样式

#### CSS中可继承与不可继承属性有哪些
+ 无继承的属性
  - display：规定元素应该生成的框类型
  - 文本属性：vertical-align、text-decoration、text-shadow、white-spae、unicodebidi
  - 盒子模型的属性：width、height、margin、border、padding
  - 背景属性：background、background-color、background-image、background-repeat、background-position、background-attachment
  - 定位属性：float、clear、position、top、right、bottom、left、min-width、min-height、height、max-width、max-height、overflow、clip、z-index
  - 生成内容属性：content、counter-reset、counter-increment、
  - 轮廓样式属性：outline-style、outine-width、outline-color、outline
  - 页面样式属性：size、page-break-before、page-break-after
  - 声音样式属性：pause-before、pause-after、pause、cue-before、cue-after、cue、play-during
+ 有继承的属性
  - 字体系列属性：font-family、font-weight、font-size、font-style
  - 文本系列属性：text-indent、text-align、line-height、word-spacing、letter-spacing、text-transform、color
  - 元素可见性：visibility
  - 列表布局发展：list-style
  - 光标属性：cursor

#### display的属性值及其作用
| 属性值       | 作用                                                     |
| ------------ | -------------------------------------------------------- |
| none         | 元素不显示，并且会从文档流中移除                         |
| block        | 块类型。默认宽度为父元素宽度，可设置宽高，换行显示       |
| inline       | 行内元素类型。默认宽度为内容宽度，不可设置宽高，同行显示 |
| inline-block | 默认宽度为内容宽度，可以设置宽高，同行显示。             |
| list-item    | 像块类型元素一样显示，并添加样式列表标记                 |
| table        | 此元素会作为块级表格来显示                               |
| inherit      | 规定应该从父元素继承display属性的值                      |

#### display的block、inline和inline-block的区别
+ block：会独占一行，多个元素会另起一行，可以设置width、height、margin和padding属性
+ inline：元素不会独占一行，设置width、height属性无效。但可以设置水平方向的margin和padding属性，不能设置垂直方向的padding和margin
+ inline-block：将对象设置为inline对象，但对象的内容作为block对象呈现，之后的内联对象会被排列在同一行内
+ 行内元素
  - 设置宽高无效
  - 可以设置水平方向的margin和padding属性，不能设置垂直方向的padding和margin
  - 不会自动换行
+ 块级元素
  - 可以设置宽高
  - 设置margin和padding都有效
  - 可以自动换行
  - 多个块状，默认排列从上到下

#### 隐藏元素的方法有哪些
+ display: none; 渲染树不会包含该渲染对象，因此该元素不会在页面中占据位置，也不会响应绑定的监听事件
+ visibility: hiden; 元素在页面中仍占据空间，但是不会响应绑定的监听事件
+ opacity：将元素的透明度设置为0，以此来实现元素的隐藏。元素在页面中仍然占据空间，并且能够响应元素绑定的监听事件。
+ position: absolute；通过使用绝对定位将元素移除可视区域内，以此来实现元素的隐藏。
+ z-index: 负值; 使其它元素遮盖住该元素，以此来实现隐藏
+ clip/clip-path：使用元素裁剪的方法来实现元素的隐藏，这种方法下，元素仍在页面中占据位置，但是不会响应绑定的监听事件
+ transform: scale(0, 0)将元素绽放为0，来实现元素的隐藏。这种方法下，元素仍在页面中占据位置，但是不会响应绑定的监听事件

#### link和@iport的区别
+ link是XHTML标签，除了加载CSS外，还可以定义RSS等其它事务；@import属性CSS范畴，只能加载CSS
+ link引用CSS时，在页面载入时同时加载；@import需要页面网页完全载入以后加载
+ link是XHTML标签，无兼容问题；@imort是在CSS2.1提出的，低版本的浏览器不支持
+ link支持使用JavaScrpt控制DOM去改变样式；而@import不支持

#### transition和animation的区别
+ transition是过度属性，强调过度，它的实现需要触发一个事件（比如鼠标移动上去，焦点点击等）才执行动画。它类似于flash的补间动画，设置一个开始关键帧，一个结束关键帧
+ animation是动画属性，它的实现不需要触发事件，设定好时间之后可以自己执行，且可以循环一个动画。它也类似于flash的补间动画，但是它可以设置多个关键帧（用@keyframe定义）完成动画。

#### display: none与visibility:hidden的区别
+ 这两个属性都是让元素隐藏，不可见，两者区别如下：
+ 在渲染树中
  - display: none会让元素完全从渲染树中消失，渲染时不会占据任何空间
  - visibility: hidden 不会让元素从渲染树中消失，渲染的元素一定要会占据相应的空间，只是内容不可见
+ 是否是继承属性
  - display: none 是非继承属性，子孙节点会随着父节点从渲染树消失，通过修改子孙节点的属性也无法显示
  - visibility: hidden 是继承属性，子孙节点消失是由于继承了hidden，通过设置visibility: visible可以让子孙节点显示
+ 修改常规文档流中的display通常会造成文档的重排，但是修改visibility属性只会造成本元素的重绘
+ 如果使用读屏器，设置为display: none的内容不会被读取，设置为visibility: hidden的内容会被读取

#### 伪元素和伪类的区别和作用？
+ 伪元素：在内容元素的前后插入额外的元素或样式，但是这些元素实际上并不在文档中生成。它们只在外部显示可见，但不会在文档的源代码中找到它们，因此，称为"伪"元素。
+ 伪类：将特殊的效果添加到特定选择器上。它是已有元素上添加类别的，不会产生新的元素。
+ 总结：伪类是通过在元素选择器上加入伪类改变元素状态，而伪元素通过对元素的操作对元素的改变

#### 对requestAnimationframe的理解
+ 实现动画效果的方法比较多，Javascript中可以通过定时器setTimeout来实现，CSS3中可以使用transition和animation来实现，HTML5中的canas也可以实现。除此之外，HTML5提供一个专门用于请求动画的API，那就是requestAnimationFrame，顾名思义就是请求动画帧
  - CPU节能：使用SetTinterval实现的动画，当页面被隐藏或最小化时，SetTinterval仍然在后台执行动画任务，由于此时页面处于不可见或不可用状态，刷新动画是没有意义的，完全是浪费CPU资源。而RequestAnimationFrame则完全不同，当页面处理未激活的状态下，该页面的屏幕刷新任务也会被系统暂停，因此跟着系统走的RequestAnimationFrame也会停止渲染，当页面补激活时，动画就从上次停留的地方继续执行，有效节省了CPU开销。
  - 函数节流：在高频率事件中，为了防止在一个刷新间隔内发生多次函数执行，RequestAnimationFrame可保证每个刷新间隔内，函数只被执行一次，这样既能保证流畅性，也能更好的节省函数执行的开销，一个刷新间隔内函数执行多次时是没有意义的，因为多数显示器每16.7ms刷新一次，多次绘制并不会在屏幕上体现出来
  - 减少DOM操作：requestAnimationFrame会把每一帧中的所有DOM操作集中起来，在一次重绘或回流中就完成，并且重绘或回流的时间间隔紧紧蹈随浏览器的刷新频率，一般来说，这个频率为每秒60帧
+ setTimeout执行动画的缺点：它通过设定间隔时间来不断改变图像位置，达到动画效果，但是容易出现卡顿、抖动的现象；原因是：
  - settimeout任务被放入异步队列，只有当主线程任务执行完后才会执行队列中的任务，因此实际执行时间总是比设定时间要晚
  - setTimeout的固定时间间隔不一定与屏幕刷新间隔时间相同，会引起丢帧

#### 对盒模型的理解
+ 标准盒子模型：
  - 标准盒模型的width和height属性的范围只包含了content
  - IE盒模型的width和height属性的范围包含了border、padding和content

#### 为什么有时候用translate来改变位置而不是定位
translate是transform属性的一个值。改变transform或opacity不会触发浏览器重新布避（reflow）或重绘（repaint），只会触发复合（compositions）。而改变绝对定位会触发重新布局，进而触发重绘和复合。transform使浏览器为元素创建一个GPU图层，但改变绝对定位会使用到CPU。因此translate()更高效，可以缩短平滑动画的绘制时间。而translate改变位置时，元素依然会占据其原始空间，绝对定位就不会发生这种情况。

#### li与li之间有看不见的空白间隔是什么原因引起的？如何解决？
+ 浏览器会把inline元素的空白字符（空格、换行、Tab等）渲染成一个空格。为了美观，通常是一个li放在一行，这导致li换行后产生换行字符，它变成一个空格，占用了一个字符的宽度。
+ 解决方法
  - 为li设置float:left。不足：有些容器是不能设置浮动，如左右切换的焦点图等
  - 将所有li写在同一行。不足：代码不美观
  - 将ul内的字符尺寸直接设为0，即font-size:0。不足：ul中的 其它字符尺寸也被设为0，需要额外重新设定其它字符尺寸，且在Safari浏览器依然会出现空白间隔
  
  