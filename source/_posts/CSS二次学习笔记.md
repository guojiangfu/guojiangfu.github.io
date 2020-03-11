---
title: CSS二次学习笔记
date: 2020-02-02 11:55:13
tags: CSS
categories: Web前端
---
### 1、精灵图
**为什么需要精灵图**

一个网页中往往会应用很多小的背景图像作为修饰,当网页中的图像过多时.服务器就会频繁地接收和发送请求图片。造成服务器请求压力过大,这将大大降低页面的加载速度。

因此,为了有效地减少服务器接收和发送请求的次数,提高页面的加载速度，出现了CSS精灵技术(也称CSS Sprites. CSS雪碧)。

核心原理:将网页中的一些小背景图像整合到一张大图中,这样服务器只需要-次请求就可以了。

**使用精灵图核心:**
1. 精灵技术主要针对于背景图片使用。就是把多个小背景图片整合到一张大图片中；
2. 这个大图片也称为sprites精灵图或者雪碧图；
3. 移动背景图片位置，此时可以使用background-position；
4. 移动的距离就是这个目标图片的x和y坐标。注意网页中的坐标有所不同；
5. 因为一般情况下都是往上往左移动,所以数值是负值。

示例：
```
width: 60px;
height: 60px;
margin: 100px auto;
background: url( images/sprites . png) no-repeat -182px 0;
```
### 2、字体图标
字体图标使用场景:主要用于显示网页中通用、常用的一些小图标。

精灵图是有诸多优点的，但是缺点很明显。

1. 图片文件还是比较大的。
2. 图片本身放大和缩小会铁真。
3. 一旦图片制作完毕想要更换非常复杂。

此时，有一种技术的出现很好的解决了以上问题,就是字体图标iconfont。

字体图标可以为前端工程师提供一种方便高效的图标使用方式,展示的是图标,本质属于字体。

**使用字体图标的优点**

- 轻量级:一个图标字体要比一系列的图像要小一旦字体加载了，图标就会马上渲染出来减少了服务器请求
- 灵活性:本质其实是文字，可以很随意的改变颜色产生阴影、透明效果、旋转等
- 兼容性:几乎支持所有的浏览器，请放心使用

字体图标是一些网页常见的小图标，我们直接网上下载即呵。因此使用可以分为:
1. 字体图标的下载
2. 字体图标的引入(引入到我们htm页面中)
3. 字体图标的追加(以后添加新的小图标)

**下载地址:**
1. [icomoon字库](http://icomoon.io)
2. [阿里icofont字库](http://www.iconfont.cn/)


1. 下载之后将font文件夹放入我们页面文件目录；
2. 在CSS样式中全局声明字体:简单理解把这些字体文件通过css引入到我们页面中。（一定注意字体文件路径的问题。）
3. style文件里可以复制格式代码；
4. Demo文件夹里可以复制字体图标

**字体图片的追加**
### 3、CSS三角
示例：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        .box1 {
            width: 0;
            height: 0;
            /* border: 10px solid skyblue; */
            border-top: 10px solid skyblue;
            border-right: 10px solid blue;
            border-bottom: 10px solid red;
            border-left: 10px solid green;
        }

        .box2 {
            width: 0;
            height: 0;
            /* border: 10px solid skyblue; */
            border-top: 50px solid red;
            border-right: 50px solid transparent;
            border-bottom: 50px solid transparent;
            border-left: 50px solid transparent;
            margin: auto;
        }
    </style>
</head>

<body>
    <div class="box1"></div>
    <div class="box2"></div>

</body>

</html>
```
### 4、CSS用户界面样式
#### 4.1 更改用户鼠标样式
语法：
```
li{
    cursor: pointer
}
```
属性值：
- default 默认
- pointer 小手
- move 移动
- text 文本
- not-allowed 禁止
示例：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>鼠标样式</title>
</head>

<body>
    <ul>
        <li style="cursor: default;">默认</li>
        <li style="cursor: pointer;">小手</li>
        <li style="cursor: move;">移动</li>
        <li style="cursor: text;">文本</li>
        <li style="cursor: not-allowed;">禁止</li>
    </ul>
</body>

</html>
```
#### 4.2 表单轮廓
```
input {
    outline: none;
}
```
#### 4.3 防止表单域拖拽
```
textarea {
    resize: none;
    outline: none;
}
```
### 5、vertical-align属性应用
CSS的vertical-align属性使用场景:经常用于设图片或者表单(行内块元素)和文字垂直对齐。
语法：
```
vertical-align: baseline;
```
属性值：
- baseline 默认，元素放在父元素的基线上
- top 把元素的顶端与行中最高元素的顶端对齐
- middle 把此元素放在父元素的中部
- bottom 把元素的顶端与行中最低的元素的顶端对齐

#### 5.1 解决图片底部默认空白缝隙问题
bug :图片底侧会有一个空白缝隙 ,原因是行内块元素会和文字的基线对齐。

解决方案：

1. 给图片添加vertical-align:middle| topl bottom等。(提倡使用的)
2. 把图片转换为块级元素display: block;

### 6、溢出文字省略号
#### 6.1 单行文本溢出
需要满足条件：
1. 先强制一行内显示文本 white-space: nowrap;
2. 超出部分隐藏 overflow: hidden;
3. 文字用省略号代替超出的部分 text-overflow: ellipsis;

#### 6.2 多行文本溢出
多行文本溢出显示省略号,有较大兼容性问题，适合于webKit浏览器或移动端(移动端大部分是webkit内核)
```
1. 超出部分隐藏 overflow: hidden;
2. 文字用省略号代替超出的部分 text-overflow: ellipsis;
3. 弹性伸缩盒子模型显示 display: -webkit-box;
4. 限制在一个块元素显示的文本的行数 -webkit-line-clamp: 2;
5. 设置或检索伸缩盒对象的子元素的排列方式-webkit-box-orient: vertical;
```
### 7、常见布局技巧
#### 7.1 margin 负值
```
ul li {
    float: left;
    list-style: none;
    width: 150px;
    height: 200px;
    border: 1px solid black;
    margin-left: -1px;
}
```
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        ul li {
            /* position: relative; */
            float: left;
            list-style: none;
            width: 150px;
            height: 200px;
            border: 1px solid black;
            margin-left: -1px;
        }

        ul li:hover {
            position: relative;
            /* z-index: 1; */
            border: 1px solid red;
        }
    </style>
</head>

<body>
    <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</body>

</html>
```
#### 7.2 文字围绕浮动元素
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        .box {
            width: 300px;
            height: 70px;
            background-color: pink;
            margin: 100px auto;
            padding: 5px;
        }

        .pic {
            float: left;
            width: 80px;
            height: 70px;
            background-color: red;
            margin-right: 5px;
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="pic"></div>
        <p>随心贰拾肆随心贰拾肆
            随心贰拾肆随心贰拾肆
            随心贰拾肆</p>
    </div>
</body>

</html>
```
#### 7.3 行内块巧妙运用
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        .box a {
            display: inline-block;
            width: 36px;
            height: 36px;
            background-color: pink;
            border: 1px solid red;
            text-align: center;
            line-height: 36px;
            text-decoration: none;
            color: black;
            margin: 100px auto;
        }

        .box .prev {
            width: 85px;
        }

        .box .next {
            width: 85px;
        }
    </style>
</head>

<body>
    <div class="box">
        <a href="#" class="prev">&lt;&lt;上一页</a>
        <a href="#">2</a>
        <a href="#">3</a>
        <a href="#">4</a>
        <a href="#">5</a>
        <a href="#">6</a>
        <a href="#">7</a>
        <a href="#" class="next">&gt;&gt;下一页</a>
    </div>
</body>

</html>
```
### 8、CSS初始化
不同浏览器对有些标签的默认值是不同的，为了消滁不同浏览器对HTML文本呈现的差异，照顾刘览器的兼容，我们需要对CSS初始化；

**简单理解：**
CSS初始化是指重设浏览器的样式。(也称为CSSreset )