视频教程：3天精通网页布局（学完这课网页布局可以随意玩）

- [https://www.bilibili.com/video/BV1aJ411i7jz/](https://www.bilibili.com/video/BV1aJ411i7jz/)

# 一、DIV+CSS页面布局实战

参考页面地址：https://www.lmonkey.com

效果

![](https://cdn.jsdelivr.net/gh/Unicorn-acc/blogimgs/imgs05/image-20230727225927718.png)

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

语法：float:none/left/right;



CSS 清除浮动：

- 描述：清除浮动是在使用了浮动之后必不可少的，为了网站布局的效果，清除浮动也变得非常麻烦。

属性：clear

值：left、right、both

清除浮动的常用方式：

1.结尾处加空div标签 clear:both （或在下一个元素上加clear:both;）

2.浮动元素的父级div定义 overflow:hidden 

3.浮动元素的父元素定宽高

