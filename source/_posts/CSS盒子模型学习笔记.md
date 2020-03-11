---
title: CSS盒子模型学习笔记
date: 2020-01-31 20:26:47
categories: Web前端
tags: CSS
---
### 1、盒子模型
页面布局要学习3三大核心,盒子模型,浮动和定位，学习好盒子模型能非常好的帮助我们布局页面。

**网页布局过程:**

1.先准备好相关的网页元素。网页元素基本都是盒子Box。

2.利用CSS设好盒子样式,然后摆放到相应位置。

3.往盒子里面装内容。
#### 1.2 盒子模型的组成
所谓盒子模型:就是把HTML页面中的布局元素看作是一个矩形的盒子，也就是一个盛装内容的容器。

CSS盒子模型本质上是一个盒子，封装周围的HTML元素。它包括：边框、外边距、内边距、和实际内容
#### 1.3 边框(border)
border可以设置元素的边框。边框有三部分组成边框宽度(粗细)、边框样式、边框颜色；

语法：
```
border: border-width || border-style || border-color;
```
示例：
```
div {
    width: 300px;
    height: 200px;
    border-width: 2px;
    border-style: solid;
    border-color: rgb(255, 123, 0);
}
```
**复合写法：**
```
border: 2px solid red;
```
没有先后顺序

**上下左右边框设定：**
```
border-top: red 2px solid;
```
上面为上边框，其余边框类似

**边框会影响盒子的实际大小**
#### 1.4 内边距（padding）
padding属性用来设置边框和内容之间的距离；
```
padding-left
padding-right
padding-top
padding-bottom
```
例如：
```
padding-left: 20px;
padding-top: 20px;
```
**复合写法：**
```
padding: 5px; /*一个值，上下左右都设置为5px*/
padding: 5px 10px; /*两个值，上下为5px，左右为10px*/
padding: 5px 10px 20px; /*上5px，左右10px，下20px*/
padding: 5px 10px 20px 30px; /*四个值，分别为上、右、下、左，顺时针*/
```
**内边距也会影响盒子的实际大小**
#### 1.5 外边距（margin）
margin属性用于设置盒子和盒子之间的距离

语法格式：
```
margin-left /*左外边距*/
margin-right
margin-top
margin-bottom
```
**margin的简写方式规则和padding完全一致**

外边距可以让块级盒子水平居中，但是必须满足两个条件:

1、盒子必须指定了宽度( width)；

2、盒子左右的外边距都设置为auto；

常用写法示例：
```
margin: 0 auto;
margin: auto;
margin-left: auto;
margin-right: auto;
```
注意:以上方法是让块级元素水平居中，行内元素或者行内块元索水平居中给期元素添加text-align:center即可。

**嵌套块元素垂直外边距的塌陷**

解决方案:

1、可以为父元素定义上边框。

2、可以为父元素定义上内边距。

3、可以为父元素添加overflow:hidden。
#### 1.6 清除内外边距
```
*{
    padding: 0;
    margin: 0;
}
```
**去除li前面的小圆点**
```
list-style: none;
```
### 2、圆角边框
border-radius属性用于设置元素的外边框圆角

语法：
```
border-radius: length;
<!--border-radius: 30px; 可以使用百分比-->
```
复合写法：
```
 border-radius: 10px 20px 30px 40px;
```
四个值分别为：左上角 右上角 右下角 左下角，顺时针
```
 border-radius: 10px 20px;
```
如果是两个值，是对角线关系，左上角和右下角为10px，右上角和左下角为20px；

也可以这样分开写: border-top-left-radius、 border-top-right-radius、 border-bottom-right-radius 和
border-bottom-left-radius；

**设置圆形**
```
div {
    width: 200px;
    height: 200px;
    margin: 100px auto;
    background-color: pink;
    border-radius: 50%;
}
```
### 3、盒子阴影
CSS3中新增了盒子阴影,我们可以使用box-shadow属性为盒子添加阴影。
语法格式：
```
box-shadow: h-shadow v-shadow blur spread color inset;
```
h-shadow v-shadow为必需，内阴影外阴影默认为outside但是不能写outside

示例：
```
box-shadow: 30px 30px 20px 10px rgba(0, 0, 0, 0.3) inset;
```
综合示例：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            margin: 100px auto;
            background-color: pink;
            border-radius: 50%;
        }

        div:hover {
            box-shadow: 10px 10px 20px 10px rgba(0, 0, 0, 0.3);
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```
### 4、文字阴影
在CSS3中，我们可以使用text-shadow属性将阴影应用于文本。

语法：
```
box-shadow: h-shadow v-shadow blur color;
```