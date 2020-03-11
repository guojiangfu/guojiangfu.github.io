---
title: CSS学习笔记
date: 2020-01-30 21:51:59
tags: CSS
categories: Web前端
---
### 1、CSS简介
用来布局网页美化页面
### 2、代码风格
```
    <style>
    /* 选择器{样式} */
    p {
        color: red;
        font-sixe: 12px;
    }
    </style>
```
### 3、CSS选择器
#### 3.1选择器的作用
根据不同的需求选择相应的标签
#### 3.2标签选择器
标签名作为选择器

例如：
```
    <style>
    /* 选择器{样式} */
    p {
        color: red;
    }
    </style>
```
#### 3.3类选择器（重点）
```
    <style>
        .red {
            color: red;
        }
    </style>
```
使用class来调用，例如：
```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>SCC字体</title>
    <style>
        .font {
            font-family:'Times New Roman', Times, serif;
            font-size: 18px;
        }
    </style>
</head>
<body class="font">
    <h1>哈哈哈</h1>
    <p class="font">呵呵呵</p>
    嘿嘿嘿
</body>
</html>
```
##### 3.3.1 多类名
一个标签可以通过class来调用类选择器
```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>SCC字体</title>
    <style>
        .font {
            font-family:'Times New Roman', Times, serif;
            font-size: 18px;
        }
        .red {
            color: red;
        }
    </style>
</head>
<body>
    <h1 class="font red">哈哈哈</h1>
    <p class="font">呵呵呵</p>
    <h1 class="red">嘿嘿嘿</h1 class="red">
</body>
</html>
```
#### 3.4 id选择器
通过#定义，通过id进行调用，如：
```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>SCC字体</title>
    <style>
        #red {
            color: red;
        }
    </style>
</head>
<body>
    <h1 id="red">哈哈哈</h1>
</body>
</html>
```
只能调用一次，重复使用没有效果
#### 3.5 通配符选择器
将页面中所有标签选择出来更改样式，不需要进行调用
```
    <style>
        * {
            color: red;
        }
```
### 4、CSS字体属性
#### 4.1字体系列
```
    <style>
        p {
            font-family: 'Times New Roman', Times, serif;
        }
    </style>
```
#### 4.2 字体大小
```
    <style>
        body {
            font-size: 14px;
        }
    </style>
```
标题比较特殊需要手动修改
#### 4.3字体粗细
```
    <style>
        body {
            font-weight: bolder;
        }
    </style>
```
如果使用数字后面不要加单位，700为加粗，400为normal；区间为：100-900
#### 4.4 文字样式
```
    <style>
        body {
            font-style: italic;
        }
    </style>
```
倾斜italic、正常normal等；
#### 4.5 字体复合属性
使用font来进行简写
```
    <style>
        body {
            font: font-style  font-size/font-height  font-family;
        }
    </style>
```
复合属性的顺序不能更改，要按照上面的格式进行编写，size和family不能省略
### 5、文本属性
#### 5.1 文本颜色
```
    <style>
        div {
            color: rgb(119, 36, 78);
        }
    </style>
```
预定义颜色值，十六进制、RGB代码
#### 5.2 文本对齐
```
 div {
            text-align: center;
        }
```
left、center、right
#### 5.3装饰文本
下划线（underline）、删除线（line-through）、上划线（overline）
```
div {
    text-decoration: none;
}
```
#### 5.4 文本缩进
```
p {
    text-indent: 20px;
}
p {
    text-indent: 2em;
}
```
em为当前文字一个字的px，2em两个文字大小
#### 5.5 行间距
```
p {
    line-height: 26px;
}
```
行高由上间距、文本高度、下间距构成，其中上下间距相等；
### 6、CSS的引用
#### 6.1 行内样式表
直接在标签的内部编写
```
 <p style="color: red; font-size: 18px;">行内样式表</p>
```
#### 6.2 内部样式表
放在`<style></style>`标签中；控制范围为整个HTML页面
```
<style>
    body {
        font-size: 18px;
        color: red;
    }
</style>
```
#### 6.3 外部样式表
在外面单独写css文件，之后将css文件引入到HTML中使用；可以控制多个页面

1、文件后缀名为.css

2、在HTML页面中使用`<link>`标签引入这个文件
```
<link rel="stylrsheet" href = "css文件路径">
```
示例：
```
/* CSS文件中存放的代码 */
.red {
    color: red;
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
    <link rel="stylesheet" href="mycss.css">
</head>
<body>
    <p class="red">外部css</p>
</body>
</html>
```
### 7、Emmet语法
emmet语法的前身是Zen coding，它使用缩写来提高HTML/CSS的编写速度，VScode内部已经集成了该语法
#### 7.1 快速生成HTML结构语法
```
1.生成标签直接输入标签名按tab键即可比如div 然后tab键.就可以生成<div> </div>
2.如果想要生成多个相同标签加上*就可以了比如div*3 就可以快速生成3个div
3.如果有父子级关系的标签.可以用>比如ul>li就可以了
4.如果有兄弟关系的标签,用+就可以了比如div+p
5.如果生成带有类名或者id名字的，直接写.demo 或者#two tab 键就可以了
6.如果生成的div类名是有顺序的，可以用自增符号$
7.如果想要在生成的标签内部写内容可以用{}表示

```
#### 7.2 快速生成CSS样式语法
```
CSS基本采取简写形式即可：
1.比如w200按tab可以生成width: 200px;
2.比如Ih26按tab 可以性成line-height 26px;
```
#### 7.3 快速格式化代码
在设置中搜索：`emmet.include`
如图设置：
![](http://q4iddx50w.bkt.clouddn.com/PicGo/VScodeFormat.png)
在json文件中添加以下添加代码：
```
"editor.formatOnType": true,
"editor.formatOnSave": true
```
### 8、复合选择器
在CSS中，可以根据选择器的类型分为==基础选择器==和==复合选择器==，复合选择器建立在基础选择器之上，对基础选择器 进行组合形成的。
#### 8.1 后代选择器（重要）
语法：
```
元素1 元素2 { 样式声名 }
```
例如：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        ol li {
            color: red;
        }

        ul li {
            color: blue;
        }
    </style>
</head>

<body>
    <ol>
        <li>我是ol的li标签</li>
        <li>我是ol的li标签</li>
        <li>我是ol的li标签</li>
    </ol>
    <ul>
        <li>我是ul的li标签</li>
        <li>我是ul的li标签</li>
        <li>我是ul的li标签</li>
    </ul>
</body>

</html>
```
逐层查找就可以，可以是基础选择器的组合
#### 8.2 子选择器（重要）
必须是==亲儿子==，不能是孙子或者其他

语法：
```
元素1>元素2 { 样式声名 }
```
#### 8.3 并集选择器（重要）
并集选择器可以选择多组标签同时为他们定义相同的样式。通常用于集体声明

语法：
```
元素1,元素2 { 样式声名 }
```
并集选择器习惯竖着写，例如：
```
div,
p,
.red li{
    color: red;
}
```
#### 8.4 伪类选择器
伪类选择器用于向某些选择器添加特殊的效果，比如给链接添加特殊效果,或选择第1个,第n个元素。

伪类选择器书写最大的特点是用置号(:)示，比如:hover、:first-child。
##### 8.4.1 链接伪类选择器
```
a:link  /*选择所有未被访问的链接*/
a:visited /*选择所有已被访问的链接*/
a: hover /*选择鼠标指针位于其上的链接*/
a: active /*选择活动链接(鼠标按下末弹起的链接) */
```
代码示例：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        a:link {
            color: black;
            text-decoration: none;
        }

        a:visited {
            color: orange;
        }

        a:hover {
            color: blue;
        }

        a:active {
            color: red;
            font-size: 20px;
        }
    </style>
</head>

<body>
    <a href="#">随心</a>
</body>

</html>
```
注意：这四个链接伪类选择器顺序不能颠倒，LVHA

记忆口诀：love hate或者lv包包hao

**开发中常用方式：**
```
a {
    color: #333;
    text-decoration: none;
}
a:hover {
    color:#369;
    text-decoration: underline;
}
```
##### 8.4.2 :focus伪类选择器
:focus伪类选择器用于选取获得焦点的表单元素。
焦点就是光标，一般情况`<input>`类表单元素才能获取,因此这个选择器也主要针对于表单元素来说。

语法示例：
```
input:focus {
    background-color: red;
}
```
### 9、CSS的元素显示模式
HTML元素一般分为==块元素==和==行内元素==两种类型。
#### 9.1 块元素
常见的块元素有`<h1>~<h6>、<p>、 <div>、<ul>、<ol>、<li>`等 .其中`<div>`标签是最典型的块元素。

**块级元素的特点:**

1、比较霸道，自己独占一行。

2、高度、宽度、外边距以及内边距都可以控制。

3、宽度默认是容器(父级宽度)的100%。

4、是一个容器及盒子,里面可以放行内或者块级元素。

**PS：文字类的元素内不能使用块元素**
#### 9.2 行内元素（内联元素）
常见的行内元素有`<a>、<strong>、 <b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>`等 ,其中
`<span>`标签是最典型的行内元素。有的地方也将行内元素称为内联元素。

**行内元素的特点:**

1、相邻行内元素在一行上,一行可以示多个。

2、高、宽直接设置是无效的。

3、默认宽度就是它本身内容的宽度。

4、行内元素只能容纳文本或其他行内元素。

**PS：链接里不能再放链接，<a>里可以放块元素，但是给<a>转换一下块级模式最安全**
#### 9.3 行内块元素
在行内元素中有几个特殊的标签一`<img/>、<input/>、<td>`它们同时具有块元素和行内元素的特点。有些资料称它们为行内块元素。

**行内块元素的特点:**

1、和相邻行内元素(行内块)在一行上,但是他们之间会有空白缝隙一行可以显示多个(行内元素特点)。

2、默认宽度就是它本身内容的宽度(行内元素特点)。

3、高度,行高、外边距以及内边距都可以控制(块级元素特点)。

### 10、元素显示模式转换
特殊情况下，我们需要元素模式的转换,简单理解一个模式的元素需要另外一 种模式的特性比如想要增加链接`<a>`的触发范围。

**把行内元素转化为 块级元素:**
display: block;

代码示例：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        a {
            color: black;
            text-decoration: none;
            background: red;
            width: 150px;
            height: 50px;
            /* 把行内元素转化为 块级元素 */
            display: block;
        }
    </style>
</head>

<body>
    <a href="#">随心</a>
</body>

</html>
```

- ==转换为块元素: display:block;==

- 转换为行内元素: display:inline;

- ==转换为行内块: display:inline-block,==

综合示例：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>MI</title>
    <style>
        a {
            display: block;
            width: 230px;
            height: 40px;
            background-color: #555555;
            font-size: 14px;
            color: white;
            text-decoration: none;
            text-indent: 3em;
            line-height: 40px;/*文字垂直居中*/
        }

        a:hover {
            background-color: rgb(255, 81, 0);
        }
    </style>
</head>

<body>
    <a href="#">手机 电话卡</a>
    <a href="#">电视 盒子</a>
    <a href="#">笔记本 平板</a>
    <a href="#">出行 穿戴</a>
    <a href="#">智能路由器</a>
    <a href="#">健康 儿童</a>
</body>

</html>
```

### 11、CSS背景
一般情通过CSS背景属性。可以给页面元素添加背景样式。

背景属性可以设置背景颜色、背景图片、背景平铺、背景图片位置、背景图像固定等。
#### 11.1 背景颜色
语法：
```
background-color: 颜色值;
```
一般情况下元素背景颜色默认为：transparent（透明）
#### 11.2 背景图片
background-image属性描述了元素的背景图像。实际开发常见于logo或者一些装饰性的小图片或者是超大的背景图片,优点是非常便于控制位置(精灵图也是一种运用场景)

语法：
```
background-image: none | url();
background-image:url(picture.jpg);
```
#### 11.3 背景平铺
```
/* 默认为平铺 background-repeat: repeat; */
background-repeat: no-repeat;
```
#### 11.4 背景位置
利用background-position属性可以改变图片在背景中的位置。

语法：
```
background-position: x y | 方位名词;
```
**参数是方位名词**

如果指定的两个值都是方位名词，则两个值前后顺序无关,比如left top和top left 效果一致；如果只指定了一个方位名词,另-个值省略,则第二个值默认居中对齐；
示例：
```
body {
    background-image: url(https://ossweb-img.qq.com/upload/webplat/info/yxzj/20200119/137731442987074.jpg);
    background-repeat: no-repeat;
    background-position: center top;
}
```
**参数是精确单位**

如果参数值是精确坐标，那么第一个肯定是x坐标,第二个定是y坐标
如果只指定一个数值.那该数值一定是x坐标，另一个默认垂直居中；

示例：
```
body {
    background-image: url(https://ossweb-img.qq.com/upload/webplat/info/yxzj/20200119/137731442987074.jpg);
    background-repeat: no-repeat;
    background-position: 20px 50px;
    ;
}
```
```
body {
    background-image: url(https://ossweb-img.qq.com/upload/webplat/info/yxzj/20200119/137731442987074.jpg);
    background-repeat: no-repeat;
    background-position: 50px 20px;
    ;
}
```
上面这两个不一样，顺序一定是x，y的顺序

**方位名词和精确单位混合**

如果指定的两个值是精确单位和方位名词混合使用，则第一个值是x坐标，第二个值是y坐标

示例：
```
body {
    background-image: url(https://ossweb-img.qq.com/upload/webplat/info/yxzj/20200119/137731442987074.jpg);
    background-repeat: no-repeat;
    background-position: 50px center;
}
```
```
body {
    background-image: url(https://ossweb-img.qq.com/upload/webplat/info/yxzj/20200119/137731442987074.jpg);
    background-repeat: no-repeat;
    background-position: center 50px;
}
```
#### 11.5 背景图像固定（背景附着）
background-attachment属性设置背景图像是否固定或者随着页面的其余部分滚动。

 background-attachment可以制作视差滚动效果。
 
 语法格式：
 ```
  background-attachment: scroll |fixed;
  /*scroll跟随内容滚动(默认)，fixed固定背景*/
 ```
 示例代码：
 ```
 body {
    background-image: url(https://ossweb-img.qq.com/upload/webplat/info/yxzj/20200119/137731442987074.jpg);
    background-repeat: no-repeat;
    background-position: center top;
    color: #ffffff;
    font-size: 20px;
    background-attachment: fixed;
}
 ```
 #### 11.6 背景复合写法
 为了简化背景属性的代码,我们可以将这些属性合并简写在同一个属性background中。从而节约代码量。
 
 **顺序不像字体要按一定的格式顺序**
 
 一般按照：
 background:背景颜色、背景图片地址、背景平铺、背景图像滚动、背景图片位置:

 
 示例：
 ```
  background: white url(https://ossweb-img.qq.com/upload/webplat/info/yxzj/20200119/137731442987074.jpg) no-repeat fixed center top;
 ```
 #### 11.7 背景颜色半透明
 语法：
 ```
 background: rgba(0, 0, 0, 0.5);
 ```
 最后一个参数是alpha透明度,取值范围在0~1之间。

**综合案例**
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        .nav a {
            display: inline-block;
            width: 120px;
            height: 58px;
            background-color: pink;
            text-align: center;
            line-height: 58px;
            color: white;
            text-decoration: none;
        }

        .nav .bg1:hover {
            background-color: violet;
        }

        .nav .bg2:hover {
            background-color: red;
        }

        .nav .bg3:hover {
            background-color: yellow;
        }

        .nav .bg4:hover {
            background-color: tomato;
        }

        .nav .bg5:hover {
            background-color: blue;
        }
    </style>
</head>

<body>
    <div class="nav">
        <a href="#" class="bg1">是随心吖!</a>
        <a href="#" class="bg2">是随心吖!</a>
        <a href="#" class="bg3">是随心吖!</a>
        <a href="#" class="bg4">是随心吖!</a>
        <a href="#" class="bg5">是随心吖!</a>
    </div>
</body>

</html>
```
### 12、CSS的三大特性
CSS有三个非常重要的三个特性:层曼性、继承性、优先级。
#### 12.1层叠性
相同选择器给设置相同的样式，此时一个样式就会覆盖(层叠)另一个冲突的样式层叠性主要解决样式冲突的问题。

例如：
```
        div {
            color: tomato;
        }

        div {
            color: yellow;
        }
```
遵循就近原则，只覆盖样式冲突的部分；
#### 12.2 继承性
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
        div {
            color: tomato;
            font-size: 20px;
        }
    </style>
</head>

<body>
    <div>
        <p>是随心吖!</p>
    </div>
</body>

</html>
```
div里的p也会有div里文字相关的样式、行高和颜色等，不会教程高度宽度等；并不是所有的样式都继承；
```
body{
    font: 12px/1.5 Microsoft YaHei;
}
```
1.5是指行高为当前文字大小的1.5倍
#### 12.3 优先级
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
        div {
            color: tomato;
            font-size: 20px;
        }

        .test {
            color: black;
        }
    </style>
</head>

<body>
    <div class="test">是随心吖!</div>
</body>

</html>
```
最终颜色为：black

级别的优先级顺序为：（更详细信息请参考元素选择器权重）
1. 继承 或者 *
2. 元素选择器
3. 类选择器、伪类选择器
4. ID选择器
5. 行内样式 style=""
6. !important 重要的
```
<style>
    div {
        color: tomato !important;
        font-size: 20px;
    }

    .test {
        color: black;
    }
</style>
```
继承的权重为0；示例：
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        #father {
            color: red;
        }

        p {
            color: blue;
        }
    </style>
</head>

<body>
    <div id="father">
        <p>是随心吖！</p>
    </div>
</body>

</html>
```
最后color为blue；

**权重叠加，永远不会有进位**
```
div ul li   权重为：0,0,0,3
.nav ul li  权重为：0,0,1,2
a:hover     权重为：0,0,1,1
.nav a      权重为：0,0,1,1
```

