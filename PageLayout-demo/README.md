视频教程：3天精通网页布局（学完这课网页布局可以随意玩）

- [https://www.bilibili.com/video/BV1aJ411i7jz/](https://www.bilibili.com/video/BV1aJ411i7jz/)

# 一、DIV+CSS页面布局实战

参考页面地址：https://www.lmonkey.com

效果

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230727225927718.png)

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730065539201.png)

页面布局常用标签

```html
<div></div>无意义块状元素标签
<span></span> 无意义行内元素标签
<p></p> 段落标签
<ul></ul> 无序列表
<li></li>  列表项
<a></a>  超链接标签
<img />   图片标签
<i></i> 斜体标签
<b></b>粗体标签
```

页面布局常用选择器

```css
id选择器     #id
类选择器    .class
关系选择器   div p、div>p、div,p
伪类选择器    hover
结构性伪类选择器：E:after、E:before、E:nth-child()、E:first-child、E:last-child
```

页面布局常用属性(一)

```css
字体属性：font-size
文本属性：text-decoration、text-align
首行缩进：text-indent
行高：line-height
宽高属性：width、height、min-height、max-height
背景属性：background
列表属性：list-style
字体颜色：color
```

页面布局应用属性(二)

```css
定位属性：position
布局属性: display
浮动属性：float、clear
盒子模型：border、margin、padding
圆角边框：border-radius
阴影：	text-shadow、box-shadow
```

## 1. CSS 浮动定位

> 应用案例：首页header栏，一左一右浮动

浮动定位指

- 将元素排除在普通流之外

- 元素将不在页面中占据空间

- 将浮动元素放置在包含框的左边或者右边

- 浮动元素依旧位于包含框之内

浮动的框可以向左或者向右移动，直到他的外边缘碰到包含框或另一个浮动框的边框为止

- 浮动元素的外边缘不会超过其父元素的内边缘

- 浮动元素不会互相重叠

- 浮动元素不会上下浮动
- **任何元素一旦浮动，display属性将完全失效均可以设置宽高，并且不会独占一行**

语法：`float:none/left/right;`



CSS 清除浮动：

- 描述：清除浮动是在使用了浮动之后必不可少的，为了网站布局的效果，清除浮动也变得非常麻烦。

属性：clear

值：left、right、both

清除浮动的常用方式：

1.结尾处加空div标签 clear:both （或在下一个元素上加clear:both;）

2.浮动元素的父级div定义 overflow:hidden 

3.浮动元素的父元素定宽高



## 2. 引入font字体和图标

阿里巴巴图标：[https://www.iconfont.cn/](https://www.iconfont.cn/)

引入：

```html
<!--引入字体图标-->
<link rel="stylesheet" href="https://at.alicdn.com/t/font_1362546_avlbbb6hync.css">
```

使用：

```html
// 使用图标需要两个属性：  当前内容的属性， icon的属性 
<i class="icon-icon-test iconfont"></i>
```



## 3. 定位属性 position、z-index

position定位

position属性指定一个元素（静态的，相对的，绝对或固定）的定位方法的类型。

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230728163348842.png)

**1、相对定位**

以当前为参照物移动指定的距离

注意：相对定位，被定位的元素会占据原有的物理位置



**2、绝对定位**

绝对定位的元素不会占据原有的物理位置

以其他元素作为参考物移动指定距离的定位方式

关于绝对定位的参考点：

1.如果元素的外层元素是非static（有了除默认值之外的定位设置）那么这个外层元素就成为该元素的定位参考点

2.如果元素的外层元素没有设置任何position的值，那么该元素将寻找距离自己最近的其他设定过position的外层元素作为参照物(必须为嵌套层)

3.如果该元素的外层元素没有任何一个元素采用position定位，那么此时定位参考元素变为body或者说页面



**3、固定定位**



**4、 堆叠顺序 z-index**

z-index堆叠顺序

一旦修改了元素的定位方式，则元素可能会发生堆叠

可以使用z-index属性来控制元素框出现的重叠顺序

z-index仅能在定位的元素上生效

z-index属性：

- 值为数值，数值越大表示堆叠顺序越高，即离用户越近
- 可以设置为负值，表示离用户更远 ，一般不要设置
- Z-index 仅能在定位元素上奏效



## 4. display属性

display属性	

​		根据CSS规范的规定，每一个网页元素都有一个display属性，用于确定**该元素的类型**，每一个元素都有默认的display属性值，比如div元素，它的默认display属性值为“block”，称为块元素，而span元素的默认display属性值为“inline”，称为“行内”元素。

- 块元素与行元素是可以转换的，也就是说display的属性值可以由我们来改变 。

display常见属性值
1. **none：隐藏对象**
2. **inline：指定对象为内联元素**
3. **block：指定对象为块元素**
4. inline-block：指定对象为内联块元素
5. table-cell：指定对象作为表格单元格
6. **flex：弹性盒**

---

visibility:hidden和display:none和opacity:0的区别：

- 1.visibility:hidden和opacity:0会将元素隐藏，但是物理空间实际存在

- 2.display:none 影藏元素，不保留物理空间

> 块状元素：具有宽高属性，并且独占一行
>
> 行内元素：没有宽高属性，不会独占一行
>
> 行内块元素，具有宽高属性，并且不会独占一行

## 5. 盒子模型（外边距、边框、内边距）

一、盒子模型	

盒子模型是css中一个重要的概念，理解了盒子模型才能更好的排版。W3C组织建议把网页上元素看成是一个个盒子。盒模型主要定义四个区域：**内容(content)、内边距(padding)、边框(border)、外边距(margin)**。

- 转换到我们日常生活中，可以拿手机盒来对比，手机=内容，内边距=盒子中的填充物，边框=盒子的厚度，外边距=两个手机盒之间的距离。



**二、W3C盒模型**

盒模型由内容(content)、填充(padding)、边框(border)、边界(margin)组成

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230728170849184.png)



**1、外边距**

围绕在元素边框周围的空白区域

- 会在元素外创建额外的空白区域

- 外边距是透明的

语法：margin:value;

单边设置

- margin-top/right/bottom/left: value;

- value可取值为像素，%，auto，负值



**外边距简写**

- margin:value(四个方向相同) ;

- margin: value(上下) value(左右);

- margin: value(上) value(左右) value(下);

- margin: value(上) value(右) value(下) value(左);



**外边距合并**

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230728193145604.png)



- **当两个垂直外边距相遇时，他们将形成一个外边距，成为外边距合并**，合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者

- 解决办法：加一像素 实线边框



margin设置元素外边距的宽度，它有这么几个特点

1. 块级元素的垂直相邻外边距会合并
2. 行内元素实际上不占上下外边距。行内元素的的左右外边距不合并
3. 浮动元素的外边距也不会合并
4. 允许指定负的外边距值，不过使用时要小心

---

**2、border边框**

border属性设置一个元素的边框，它有三个要素：**宽、样式、颜色，统称“边框三要素”。**

三要素书写的时候一般如下顺序

border：宽度 样式 颜色 

- border: 1px solid red;

不过不按此顺序来写依然能正常显示。

- div{ border: red solid 2px; }

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230728233013062.png)



border-style设置边框的样式，有五种常用样式可选

- 点状dotted
- 实线solid
- 双线double   （ 需要最起码设置为3像素，不然显示不下）
- 虚线dashed
- 无边框none



border的三要素可以统一写在”border”属性中，也可以单独设置。

统一的写法：border: 1px solid  red;
单独设置的写法：

- border-width:; 

- border-style:;

- border-color:;

要注意，在style属性为空的情况下，整个边框是不会出现的。这不论是统一写在border或是单独设置都是这样的。

- 不写width会有默认3像素的值。

- 不写颜色会默认为黑色。

---

**3、内边距**

内容区域和边框之间的空间

会扩大元素边框所占用的区域

- 语法：padding:value;

单边设置

- padding-top/right/bottom/left:value;

- value可取值为像素，百分比，但不能为负数



内边距的简写

- padding:value(四个方向相同) ;
- padding: value(上下) value(左右);
- padding: value(上) value(左右) value(下);
- padding: value(上) value(右) value(下) value(左);



<font color = "red">padding的宽高要记录在盒子模型的宽高之内，于此相同的是border也要记录在盒子模型的宽高之内，但是margin并不算在宽高之内。所以各位在书写宽高时注意减掉内边距和边框(标准盒模型)</font>



三、怪异盒模型

盒子模型分两种，一种是符合W3C规范的标准例子模型，另一种是IE的盒子模型，IE的盒子模型也被叫怪异盒子。

可以看到 IE 盒子模型也包括 margin、border、padding、content，不过，和标准 盒子模型不同的是：**IE 盒子模型的宽，包含了 border 和 pading。**

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230729182147657.png)

**Box-sizing** 

box-sizing属性允许你以“W3C的盒模型”或“IE盒模型”来定义元素，以适应区域。换句话说，当前元素使用哪种盒模型，可以由box-sizing属性来指定
它有两个值

**content-box（标准）**

padding和border不被包含在width和height内，**元素的实际大小为宽高+border+padding**，此为标准模式下的盒模型。

**border-box（怪异）**

padding和border被包含在定义的width和height中，**元素实际的大小为你定义了多宽就是多宽**。此属性为怪异模式下的盒模型。



## 6. 实战（布局页面）

准备工作



**目录创建**

- ./index.html 首页文件
- ./css/index.css 首页CSS样式文件
- ./js/index.js 首页JS文件
- ./img/image/首页应用图片
- ./img/picture/css背景图片



**编辑器(任选其一)**

- webstorm
- nodpadd++
- sublime



**颜色选取器**

学习猿地官网可下载

学习猿地官网可下载



<font color = "red">**div+css网页布局时注意事项**</font>

1. 对于网页进行分析，划分方块。

2. 选择器的优先级及精确定位需要设置样式的标签。

3. 浮动属性对于其他元素的影响

4. 使用定位属性时，精确找到定位参考点。



# 二、CSS动画

## 1. 浏览器私有前缀

CSS3

CSS3是CSS（层叠样式表）技术的升级版本。CSS3完全向后兼容，不必改变现有的设计，浏览器将永远支持CSS2。W3C的CSS3规范仍在开发。但是，许多新的CSS3属性已在现代浏览器使用。



**一、浏览器内核以及其前缀**

CSS标准中各个属性都要经历从草案到推荐的过程，css3中的属性进展都不一样，浏览器厂商在标准尚未明确情况下提前支持会有风险，浏览器厂商对新属性的支持情况也不同，所以会加厂商前缀加以区分。如果某个属性已经从草案变为了或接近推荐方案，并且厂商已经完全实现了推荐属性，那就不用加厂商前缀。如border-radius已经很成熟，不用加前缀。



根据不同的浏览器内核，css前缀会有不同。最基本的浏览器内核有如下四种，其它的内核都是基于此四种进行再研发的。

**1. Gecko内核**

前缀为-moz-   火狐浏览器

**2.Webkit内核**

前缀为-webkit-   也叫谷歌内核，chrome浏览器最先开发使用，safari浏览器也使用该内核。国内很多浏览器也使用了webkit内核，如360极速、世界之窗、猎豹等。

**3.Trident内核**

前缀为-ms-  也称IE内核

**4.Presto内核**

前缀-o-   目前只有opera采用



## 2. 圆角、阴影、渐变

**1、圆角border-radius**

语法

- border-radius：value；四个角

- border-radius：value value；左上右下、右上左下

- border-radius：value value value value；				

代表设置对象左上角、右上角、右下角、左下角

- **顺时针设置**

```css
/*设置圆角 完整格式  2个参数 8个值  (水平位置 / 垂直位置)*/
/*border-radius: 10px 20px 30px 40px / 10px 20px 30px 40px;*/
/*关于圆角的形成*/
/*
1.从指定角的顶端，向内部引出垂直半径和水平半径
2.将水平半径和垂直半径相较于元素内部的一点(圆心点)
3.以该点为圆心，指定的垂直半径和水平半径画圆或椭圆
4.与边框相交的部分就是圆角部分。
*/
/*设置圆角 完整格式  1个参数 4个值*/
/*border-radius: 10px 20px 30px 40px;*/
/*一个参数两个值 20px 代表左上角和右下角的水平和垂直 60px代表右上角和左下角的水平和垂直*/
/*border-radius:20px 60px;*/
/*一个参数 一个值  四个角的水平和垂直*/
/*border-radius: 10px;*/
/*border-radius:10px / 20px 10px;*/
/*border-radius:10px 20px 30px 40px / 20px 10px;*/
```

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730134242619.png)

**2、box-shadow阴影**

语法：box-shadow: h-shadow v-shadow blur spread color inset;

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730133424799.png)

```css
/*
盒子阴影
格式：box-shadow：阴影1,阴影2……；
阴影的格式：
    水平偏移位置，垂直偏移位置，模糊度，外颜值，颜色，(内置阴影)
*/
```





**3、文字阴影**

语法：text-shadow: h-shadow v-shadow blur color;

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730135628702.png)

```css
/*格式：
    text-shadow:阴影1,阴影2……；
    阴影的格式：
        第一个：横向偏移位置
        第二个：纵向偏移位置
        第三个：模糊的
        第四个阴影的颜色
*/
```

**3、CSS3 渐变**	

CSS3 渐变（gradients）可以让你在两个或多个指定的颜色之间显示平稳的过渡。以前，你必须使用图像来实现这些效果。现在，使用 CSS3 渐变（gradients），通过代码来实现渐变可以减少请求和节约带宽。

CSS3 定义了两种类型的渐变（gradients）

- 线性渐变（Linear Gradients）
- 径向渐变（Radial Gradients）

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730142016851.png)

**1.线性渐变（Linear Gradients）- 向下/向上/向左/向右/对角方向**

- background: linear-gradient(direction, color-stop1, color-stop2, ...);

**2.径向渐变（Radial Gradients）- 由它们的中心定义**

- background: radial-gradient(center, shape， size, start-color, ..., last-color);

- 默认情况下，渐变的中心是 center（表示在中心点），渐变的形状是 ellipse（表示椭圆形）
- 它可以是值 circle 或 ellipse。其中，circle 表示圆形，ellipse 表示椭圆形

​	



## 3. 转换Transform（2D、3D）

**转换Transform（2D转换）**

CSS3中的转换允许我们对元素进行**旋转、缩放、移动或倾斜**。它为分2D转换 或 3D 转换。

在css2时代，如果要做一些图片转换角度，都依赖于图片、Flash或JavaScript才能完成。但是现在借助CSS3就可以轻松倾斜、缩放、移动以及翻转元素。通过CSS变形，可以让元素生成静态视觉效果，但也可以很容易结合CSS3的transition和动画的keyframe产生一些动画效果。



**二、转换Transform 2D的属性**

通常的属性包含了属性名和属性值，而CSS3的transform属性是用函数来定义的。

**Transform 2D函数包括了translate()、scale()、rotate()和skew()。**

- 书写格式:	transform:函数名(x轴值，y轴值);

转换的效果：

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730154104253.png)



**1.translate()函数**

translate()方法，根据左(X轴)和顶部(Y轴)位置给定的参数，从当前元素位置移动。接受CSS的标准度量单位（px）

translate(x,y)：转换，沿着X和Y轴移动元素。



**2.rotate()**	

通过 rotate() 方法，元素顺时针旋转给定的角度。允许负值，元素将逆时针旋转。它以deg为单位，代表了旋转的角度。



**3.scale()**	

通过值把宽和高转换为原始尺寸的n倍，接受两个参数，前面的为宽，后面的为高。

可取值：默认值为1缩小：0-1之间的数放大：大于1的数



**4.skew()**

根据水平轴和垂直轴翻转，接受两个或一个值，两个值时前面为水平，后面为垂直的角度 ，一个值只是水平轴的角度。此函数是指元素的倾斜角度。

```
/*水平和垂直方向移动函数：translate  支持一个参数，代表水平移动*/
/*transform: translate(-30px);
/*旋转
    支持一个参数，指旋转角度 单位 deg
*/
/*transform:rotate(20deg);*/

/*缩放*/
/*
    支持两个参数，代表水平方向和垂直方向的缩放
    也支持一个参数，水平和垂直等于一个值
*/
/*transform:scale(0.5,1.2);*/
/*倾斜*/
transform:skew(40deg,30deg);
```





**三、转换Transform 3D的属性**

Transform 3D常用函数有：

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730154253704.png)



## 4. 过渡Transition

四、过度Transition

1.什么是过渡

使用css的属性值在一段时间内平滑的过渡

比如，鼠标悬停后，背景色在1s内，由白色平滑的过渡到红色

**1）指定四个要素：**

- 过渡属性，如background、color等

- 过渡所需时间

- 过渡函数，即过渡的速度、方式等

- 过渡延迟时间，表示开始执行的时间	

**2）触发过渡**

通过用户的行为触发，如点击、悬浮等

---

**1.过渡属性**

transition-property: none|all|property;

多个属性用逗号隔开

可设置过渡的属性

- 颜色属性

- 取值为数值的属性

- 转换属性
- 渐变属性

- 阴影属性



**2.过渡时间**

transition-duration: s|ms;

默认值为0，意味着不会有效果，所以必须设置transition-duration属性



**3.过渡函数**

transition-timing-function: ;

取值：

- ease：默认值，规定慢速开始，然后变快，然后慢速结束的过渡效果

- linear：匀速

- ease-in：规定以慢速开始，加速效果

- ease-out：规定以慢速结束，减速效果

- ease-in-out：规定以慢速开始和结束，先加速后减速效果



**4.过渡延迟**

transition-delay: s|ms;

改变元素属性值后多长时间开始执行过渡效果



5.简写属性transition

transition属性是一个简写属性，用于设置四个过渡属性

语法：transition:property duration timing-function delay;

```css
#box{
    width: 200px;
    height: 200px;
    background-color: #1fb57b;
    transition: background 4s linear 1s;
}
#box:hover{
    background-color: red;
}
```




## 5. 动画animation

animation属性

animation属性用于**控制动画**

- 调用由@keyframes定义的动画

- 设置动画属性，如时间、次数等

animation属性是一个简写属性

语法为：animation:name  duration timing-function delay iteration-count direction;



**3.动画子属性**

- animation-name: ;	调用动画，规定需要和keyframes的名字一致

- animation-duration: s|ms;	动画完成一个周期所需要的时间

- animation-timing-function: ;	规定动画的速度变化类型

- animation-delay:s|ms ;	播放之前的延迟时间

- animation-iteration-count: 数值|infinite;	播放次数
  - infinite表示无限次播放

- animation-direction: normal|alternate;	动画播放方向

  - normal为默认值，表示正常播放

  - alternate表示轮流播放，即动画会在奇数次正常播放，而在偶数次向后播放

- animation-fill-mode: forwards;	动画停在最后一帧
  - 默认值为none

- animation-play-state:paused|running; 属性规定动画正在运行还是暂停
  - 默认值为running

# 三、伸缩盒模型布局flexbox＋移动端布局

## 1. 伸缩盒布局

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230730203427062.png)

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731065133135.png)

**四、伸缩盒模型flexbox**

伸缩盒模型也叫弹性盒模型，或flexBox。它决定一个盒子在其它盒子中的分布，以及如何处理可用的空间。使用该模型，可以轻松的创建“自适应”浏览器窗口的流动布局。

flexbox是一个很新的东西，在w3c希望可以使用flexbox实现一些更复杂的布局和应用。传统盒模型基于HTML文档流排列，使用弹性盒模型可以规定特定的顺序。要开启弹性盒模型，只需要设置display的属性值 flex，因为它是CSS3中为display新添加的值类型

- 目的：在浏览器窗口变化时，盒子相应改变大小。

- **设置了弹性盒模型后，float，clear和vertical-align在flex中不起作用。**

 

**1、flexbox的基础知识**

由于 flexbox是一个整体的模块，它们之中**一些属性是在父容器上设置，而一些是在子容器上设置**。

一个flexbox的基本结构：

- `.box{ display: flex;}`    最外层的为父容器，定义此容器为弹性布局

- `.item1{ flex-grow: 1; background:pink} `      flex-grow占1比例

- `.item2{ flex-grow: 2; background:orange}`     占2比例
  - `.item3{ flex-grow: 3; background:red}` 	占3比例



```html
<div class="box">
    <div class="item1">1</div>
    <div class="item2">2</div>
    <div class="item3">3</div>
</div>
```

  1.首先规定哪个是父容器，父容器中包含多个“项目”（每个子div），项目是可以在父容器中弹性布局的。

2.其次还可以规定父容器中要怎么来显示它里面的项目，如是否换行、项目排列方向等

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731065738253.png)

**2、父容器常用属性**

1.父容器中的常用属性

- `display: flex;`：定义一个flex容器

新弹性盒 ：**设置父元素是一个弹性盒，子元素会自动水平排列**



2.父容器中的常用属性（水平对齐方式）

- `justify-content: flex-end;`：设置或检索弹性盒子元素在主轴（横轴）方向上的对齐方式

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731070120122.png)



3.父容器常用属性（垂直对齐方式）

- `align-items` 属性定义flex子项在flex容器的当前行的侧轴（纵轴）方向上的对齐方式

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731070453080.png)

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731071043404.png)

4.父容器常用属性

- flex-wrap让弹性盒元素在必要的时候拆行

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731071129557.png)

> 父元素其他属性
>
> `min-width:xxpx；`伸缩的最小宽度
>
> `flex-direction` 设置子容器垂直布局  取值 column 列(垂直布局效果)

5.子元素常用属性

*伸缩盒中的每一个元素称为一个项目。

- `flex-grow: number;   `一个数字，规定项目将相对于其他灵活的项目进行扩展的量。默认值是 0。

- `.item1{ flex-grow: 1; background:pink}`         

- `.item2{ flex-grow: 1; background:orange}`

- `.item3{ flex-grow: 1; background:red}    `





**旧的伸缩盒**

伸缩盒从被提出到如今一直在修改，所以这里涉及到了新老写法

**伸缩盒最老版本**：`display:box;`

- 将对象作为弹性伸缩盒显示（火狐和webkit内核都支持display:-webkit-box;或display:-moz-box;）

- 子元素   `box-flex: ;`

**伸缩盒过渡版本**：`display:flexbox;  `

- 将对象作为弹性伸缩盒显示

伸缩盒最新版本：`display:flex;  `

- 将对象作为弹性伸缩盒显示



## 2. 响应式布局-CSS3媒体查询

**一、Media Query响应式布局—媒体查询**

响应式布局是在2010年5月份提出的一个概念，简而言之，就是**一个网站能够兼容多个终端——而不是为每个终端做一个特定的版本**。这个概念是为解决移动互联网浏览而诞生的。

响应式布局可以为不同终端的用户提供更加舒适的界面和更好的用户体验，而且随着目前大屏幕移动设备的普及，越来越多的网站采用这个技术。



**响应式设计一定是最佳选择吗？**

如果预算充足且形势需要，做一个真正的“手机版”网站是首选。因为响应式设计没有专门设计一个手机版网站的功能多，比如获取当前用户的GPS定位，只是用响应式设计会很难实现。但如果只是根据视口大小为用户提供匹配的视觉效果还是优先选择响应式设计。

优点：

- 1.面对不同分辨率设备灵活性强

- 2.能够快捷解决多设备显示适应问题

缺点：

- 1.兼容各种设备工作量大，效率略慢

- 2.代码累赘，会出现隐藏无用的元素，加载时间加长

- 3.其实这是一种折中性质的设计解决方案，多方面因素影响而达不到最佳效果

- 4.一定程度上改变了网站原有的布局结构，会出现用户混淆的情况

> 页面的布局会根据浏览器的尺寸在1列，2列和4列之间切换



**CSS中的Media Query（媒介查询）是什么？**

作为CSS3规范的一部分，**媒体查询可以针对不同的屏幕尺寸设置不同的样式**，它为每种类型的用户提供了最佳的体验，网站在任何尺寸设置下都能有最佳的显示效果。

通过不同的媒体类型和条件定义样式表规则。

媒体查询让CSS可以更精确作用于不同的媒体类型和同一媒体的不同条件。

媒体查询的大部分媒体特性都接受min和max用于表达“大于或等于”和“小与或等于”。如：width会有min-width和max-width

Media Queries功能是非常强大的，他可以让你定制不同的分辨率和设备，并在不改变内容的情况下，让你制作的web页面在不同的分辨率和设备下都能显示正常，并且不会因此而丢失样式

---

```css
媒体查询实例

通过此实例观察媒体查询的功能后，再来分析语法

body{background-color:grey; }   //正常情况是灰色

@media screen and (min-width: 992px) {//宽度大于 992px 的时候被应用 pc端
.class {background: #666;}  }  

@media screen and (max-width: 768px) { //宽度小于768px的时候被应用  移动端
.class { background: #ccc; }  }

@media screen and (min-width: 768x) and (max-width: 992px) {  //宽度在 768px 和 992px 之间的时候被应用
.class {  background: #333;  }   }
```



**使用Media Query的基本语法**

```css
@media mediatype and|not|only (media feature) {
   CSS-Code;
}
```

- 以上通过@media定义媒体查询，mediatype代表了设备类型，目前只有screen最常用，and|not|only为条件，media feature为媒体特点，通常是写设备的宽度。

- `@media screen and (max-width:960px)`的意思为：当前设备为screen（电脑、平板、手机）时，并且最大宽度为960时，显示的样式。

媒体类型有：

- all 所有设备
- print	用于打印机和打印预览
- screen	用于电脑屏幕，平板电脑，智能手机等
- speech	应用于屏幕阅读器等发声设备



用媒体查询改造我们的设计：

我们都知道，样式表里面，后面的样式会覆盖前面的样式。**因此，我们可以在设置好网站基本样式后，使用媒体查询来进一步重写相应的部分**。例如，在PC端将导航显示成简单的链接，然后再针对小视口，使用媒体查询重写这一部分。理论上讲最好是从小屏幕设备开始设计，然后渐进增强。但实际上我们使用媒体查询要解决的问题，都是已经存在PC端站点了，更多的是要将现有的桌面版网页改造成响应式的。


加载媒体查询的最佳方法：

使用多个独立的CSS文件会增加HTTP请求的数量，使页面加载变慢。所以我们的媒体查询样式的文件尽量放在一个里面，以注释加以区分。

---

**阻止移动浏览器自动调整页面大小**

```html
阻止移动浏览器自动调整页面大小

	ios和android浏览器都基于webkit内核，这两种浏览器和许多其它浏览器都支持用viewport meta元素覆盖默认的画布缩放设置。只需要在HTML的<head>标签中插入一个<meta>标签，meta标签中可以设置具体的宽度或缩放比。下面为示例

<meta name="viewport"  content="initial-scale=1.0,width=device-width" /> 

	name=”viewport”  说明此meta标签定义视口的属性
	initial-scale=2.0   意思是将页面放大两倍
	width=device-width   告诉浏览器页面的宽度等于设备宽度
	
	允许用户将页面最大放大至设备宽度3倍，最小压缩至设备宽度的一半
<meta name=”viewport” content=”width=device-width, maximum-scale=3, minimum-scale=0.5” />
	
	禁止用户缩放，可以在混合APP时，为了使html页面更逼真，使页面无法缩放
<meta name=”viewport” content=”initial-scale=1.0, user-scalable=no” />   //user-scalable=no是禁止缩放
```

---

# 四、栅格系统页面布局

学习猿地官方: http://www.lmonkey.com

bootstrap中文网：https://www.bootcss.com

目标：

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731135336035.png)

## 1. 栅格化布局

网格布局（Grid）是最强大的 CSS 布局方案。

它将网页划分成一个个网格，可以任意组合不同的网格，做出各种各样的布局。以前，只能通过复杂的 CSS 框架达到的效果，现在浏览器内置了。

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731135511850.png)

Grid 布局与 Flex 布局有一定的相似性，都可以指定容器内部多个项目的位置。但是，它们也存在重大区别。

Flex 布局是轴线布局，只能指定"项目"针对轴线的位置，可以看作是一维布局。Grid 布局则是将容器划分成"行"和"列"，产生单元格，然后指定"项目所在"的单元格，可以看作是二维布局。Grid 布局远比 Flex 布局强大。



**基本概念**

**1.容器和项目**

采用网格布局的区域，称为"容器"（container）。容器内部采用网格定位的子元素，称为"项目"（item）

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731135629869.png)

上面代码中，最外层的`<div>`元素就是容器，内层的三个`<div>`元素就是项目。

注意：项目只能是容器的顶层子元素，不包含项目的子元素，比如上面代码的`<p>`元素就不是项目。Grid 布局只对项目生效。



**2.行和列**

容器里面的水平区域称为"行"（row），垂直区域称为"列"（column）

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731135736908.png)

水平的深色区域就是"行"，垂直的深色区域就是"列"



**2.容器中的属性**

`display：grid`  指定一个容器采用网格布局

- 默认情况下，容器元素都是块元素
- inline-grid  设置为行内元素网格布局



grid-template-columns 属性定义每一列的列宽。

grid-template-rows 属性定义每一行的行高




注意，设为网格布局以后，容器子元素（项目）的float、display: inline-block、display: table-cell、vertical-align和column-*等设置都将失效。

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731135808738.png)

## 2. 认识Bootstrap

bootstrap中文网：https://www.bootcss.com



**认识Bootstrap栅格系统**

> https://v3.bootcss.com/css/#grid

Bootstrap 提供了一套响应式、移动设备优先的流式栅格系统，随着屏幕或视口（viewport）尺寸的增加，系统会自动分为最多12列。



栅格系统用于通过一系列的行（row）与列（column）的组合来创建页面布局，你的内容就可以放入这些创建好的布局中。下面就介绍一下 Bootstrap 栅格系统的工作原理：

- “行（row）”必须包含在 `.container` （固定宽度）或 `.container-fluid` （100% 宽度）中，以便为其赋予合适的排列（aligment）和内补（padding）。
- 通过“行（row）”在水平方向创建一组“列（column）”。
- 你的内容应当放置于“列（column）”内，并且，只有“列（column）”可以作为行（row）”的直接子元素。
- 类似 `.row` 和 `.col-xs-4` 这种预定义的类，可以用来快速创建栅格布局。Bootstrap 源码中定义的 mixin 也可以用来创建语义化的布局。
- 通过为“列（column）”设置 `padding` 属性，从而创建列与列之间的间隔（gutter）。通过为 `.row` 元素设置负值 `margin` 从而抵消掉为 `.container` 元素设置的 `padding`，也就间接为“行（row）”所包含的“列（column）”抵消掉了`padding`。
- 负值的 margin就是下面的示例为什么是向外突出的原因。在栅格列中的内容排成一行。
- 栅格系统中的列是通过指定1到12的值来表示其跨越的范围。例如，三个等宽的列可以使用三个 `.col-xs-4` 来创建。
- 如果一“行（row）”中包含了的“列（column）”大于 12，多余的“列（column）”所在的元素将被作为一个整体另起一行排列。
- 栅格类适用于与屏幕宽度大于或等于分界点大小的设备 ， 并且针对小屏幕设备覆盖栅格类。 因此，在元素上应用任何 `.col-md-*` 栅格类适用于与屏幕宽度大于或等于分界点大小的设备 ， 并且针对小屏幕设备覆盖栅格类。 因此，在元素上应用任何 `.col-lg-*` 不存在， 也影响大屏幕设备。



![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230731140457214.png)
