---
title: HTML学习笔记
date: 2020-01-29 23:44:33
tags: HTML
categories: Web前端
---

## 1、标题标签
标题有6种
```html
<h1></h1>
<h2></h2>
.........
<h6></h6>
```
## 2、段落标签
```
<p>段落</p>
```
## 3、换行标签
```
<br>       单标签    语义：强制换行
```
## 4、文本格式化标签
标签语义：突出重要性，比普通文字更重要
```
<strong>加粗</string>   推荐使用，语义更加强烈
<b>加粗</b>
<em>倾斜</em>   推荐使用
<i>倾斜</i>
<del>删除线</del>   推荐使用
<s>删除线</s>
<ins>下划线<ins>    推荐使用
<u>下划线</u>
```
## 5、div和span标签
无语义，用来布局，用来装内容
```
<div>独占一行</div>
<span>跨行<span>
```
## 6、图像标签
```
<img src="图像url" alt="替换文本" title="提示文本" 
width="400" height= "200"" border= "设定边框，单位是像素" >        单标签
```
## 7、链接标签
url要以htttp://或者https://开头，内部链接的话使用html文件名，#代替空链接
下载链接：地址链接为.exe或者zip等压缩形式
网页元素的链接：图片、音频、视频等，放置在替换文本位置
target:打开窗口的方式默认为：_self
```
<a href="链接目标的url" target= "_self或者_blank">代替文本</a>
```
锚点链接：
在href属性中，设置属性值为：#名字 的形式，如:
```
<a href="#two">第二季</a>
```
使用id时不需要#
## 8、注释和特殊字符
注释：
```
<!--注释-->    快捷键  Ctrl + /
```
特殊字符：
```
空格:   &nbsp;  
<:  &lt;
>:  &gt;
```
## 9、表格标签
### 9.1表格
表格用来存放数据；
```
<table> </table>
<tr> </tr> 行，在<table> </table>中
<td> </td> 单元格，在<tr></tr>中
注意：没有列的概念，有几个单元格写几个<td></td>标签
```
### 9.2表头单元格
`<th></th>  标签中的文字会居中加粗`
### 9.3表格的属性（不常用，通过css来设置）
写在`<table>`标签中
```
对齐方式：  align   值为：center为居中  left right
边框：  border
cellpadding 内容与单元格边框间的距离
cellspacing 单元格之间的距离，默认为2
width   表格宽度
height  表格高度
```
### 9.4表格结构标签
```
<thead></thead>     注意：<th>是表头单元格，<thead>是表头区域
<tbody></tbody>
```
### 9.5合并单元格
跨行合并：`rowspan="合并单元格的个数"`

跨列合并：`clospan="合并单元格的个数"`

语法格式：在目标单元格写合并代码

目标单元格：跨行：最上侧单元格为目标单元格；跨行：最左侧单元格为目标单元格

示例：
```
<table border="1" cellspacing = "0" cellpadding = "0" width = "400" height = "200">
        <tr>
            <td colspan="3"></td>
            <!-- <td></td>
            <td></td> -->
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </table>
```
注意：合并了之后需要删除多余的单元格，注意确定是跨行还是跨列合并
## 10、列表
列表主要用来布局；
### 10.1无序列表(重点)
```
    <ul>
        <li>苹果</li>
        <li>香蕉</li>
        <li>橘子</li>
    </ul>
```
### 10.2有序列表
```
    <ol>
        <li>苹果</li>
        <li>香蕉</li>
        <li>橘子</li>
    </ol>
```
### 10.3自定义列表（重点）
```
    <dl>
        <dt>名词1</dt>
        <dd>名词1解释1</dd>
        <dd>名词1解释2</dd>
        <dd>名词1解释3</dd>
    </dl>
```
## 11、表单
表单：表单域、表单控件、提示信息
### 11.1表单域
```
    <form action="url地址，处理表单数据的服务器程序地址"
    method="POST/GET" name="名称指定表单名称"
    >各种各样的控件</form>
```
### 11.2表单控件
#### 11.2.1 input输入表单元素
input是单标签`<input type ="属性值" />`type值有很多，例如：submit、text、radio、reset、button、file等；可以参考[W3School](https://www.w3school.com.cn/)
```
<form>
    用户名：<input type="text"><br>
    密码：<input type="password""><br>
    性别：男<input type="radio" name="sex" id=""> 女<input type="radio" name="sex" id=""><br>
    爱好：吃饭<input type="checkbox"> 睡觉<input type="checkbox"> 玩游戏<input type="checkbox">
</form>
<!--单选按钮和复选按钮可以设置ckecked属性，设置为默认值 -->
性别：男<input type="radio" name="sex" id=""> 女<input type="radio" name="sex" checked="ckecked" id=""><br>
```
#### 11.2.2 select下拉表单元素
```
    籍贯：<select name="" id="">
        <option value="">北京</option>
        <option value="">上海</option>
        <option value="">天津</option>
    </select>
```

#### 11.2.3 textarea文本域表单元素
```
    <textarea name="" id="" cols="30" rows="10">文本域</textarea>
```
## 12、lable标签
```
性别：<label for="nan">男</label><input type="radio" name="sex" id="nan">
    <label for="nv">女</label><input type="radio" name="sex" id="nv"><br>
```
#### PS：以上为比较常用的标签，更加详细的内容参考[W3School](https://www.w3school.com.cn/)


