# day-7选择器进阶

## 知识回顾

```
浮动float--> 让标签元素脱离原来的文档流 向左/向右浮动 一直到父级边界/其他浮动元素位置

position-->定位 让标签属性基于上下左右坐标的方式来调整自身的位置
	绝对定位-->让标签基于父级元素 在指定的位置出现
	相对定位-->让标签基于自身原来的位置 向指定的方向移动(适合小范围的移动)
```



## 选择器补充

```
之前学的选择器:
*{}:通配符选择器 选择网页里的所有元素
.class名{}:类选择器 选择网页里的所有带有class='xx'的标签元素
#id名{}:id选择器 选择网页里的带有id='xx'的标签元素
body{}:标签选择器 选中网页里的所有标签

ul,li{}-->并集选择器 一次选择多个目录
.msg p{}-->后代选择器 选择.msg里的所有p标签
.msg > p{}-->子代选择器 选择msg里的子元素的p标签 孙子曾孙不选
```

### 伪类选择器

相当于在特定的情况下 给标签触发样式

```
元素:hover{} -->当鼠标经过/悬停时 触发样式
元素:active{} -->当按下元素时 触发样式
元素:visited{} --> 当a标签被访问过时 触发样式
元素:link{} --> 当a标签未被访问过时 触发样式

元素:hover 是最为常用的
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        p:hover{
            color: #096;
        }
        p:active{
            color: pink;
        }
        a:visited{
            color: blue;
        }
        a:link{
            color: tomato;
        }
    </style>
</head>
<body>
    <p>张家炳</p>
    <a href="http://cccpism.com/">我是渣渣辉</a>
    <a href="https://www.taobao.com/">我是丢的辉</a>
</body>
</html>
```

> 爱恨准则(先爱后恨)
>
> LOVE HATE
>
> css有个规定 四个伪类顺序必须按照(爱恨准则)否则会有伪类不生效
>
> :link --> :visited -->:hover -->:active-->

### 伪元素选择器

相当于创建一个虚拟元素

```
元素::before{content:'内容'}-->在元素前面添加一个子元素
元素::after{content:'内容'}-->在元素后面添加一个子元素

before:前 after:后
必须拥有content属性样式 上述两个伪元素才会被激活

作用:如果你希望网页的内容部分(文字/图片)不能被选中/下载 就用伪元素
    1.性能更好 伪元素并不真实存在的 只能看 不能用 不能被选中 所以减少了交互需求 
    2.安全性更好 只能看不能用不能取内容
    3.伪元素可以利用css创建元素 而不需要html标签 简化了html的结构
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .box::before{
            content: '螺蛳粉';
        }
        .box::after{
            content: '麻辣烫';
        }
    </style>
</head>
<body>
    <div class="box">
        <span>晚上吃顿好的</span>
    </div>
</body>
</html>
```

### 结构选择器

```
元素:nth-child(下标){}:根据下标指定元素 数据从1开始计算
元素:first-child{}:选中第一个子元素
元素:last-child{}:选中最后一个子元素
元素:nth-last-child(下标){}:根据下标指定元素 数据从最后开始计算
元素:nth-of-type(下标){}:根据下标指定元素(优先指定类型 忽略其他的类型)

快捷方式: p{我是$仙女}*7
```

## 手风琴案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }
        .box{
            width: 900px;
            height: 280px;
            border: 1px solid black;
            margin: 50px auto;
            overflow: hidden;

        }
        .pic{
            width: 100px;
            float:left;
        }
        img{
            width: 400px;
            height: 280px;
        }
        ul li:hover{
            width: 400px;
            transition: 0.5s;
        }
    </style>
</head>
<body>
    <ul class="box">
        <li class="pic"><img src="../img/海月f(1).jpg" alt=""></li>
        <li class="pic"><img src="../img/海月f(1).jpg" alt=""></li>
        <li class="pic"><img src="../img/海月f(1).jpg" alt=""></li>
        <li class="pic"><img src="../img/海月f(1).jpg" alt=""></li>
        <li class="pic"><img src="../img/海月f(1).jpg" alt=""></li>
        <li class="pic"><img src="../img/海月f(1).jpg" alt=""></li>
        <li class="pic"><img src="../img/海月f(1).jpg" alt=""></li>
    </ul>
</body>
</html>
```







## 表单（form）

提供一个让用户进行交互的窗口(输入框 选择框 提交按钮)

```
form的属性:
	action=数据提交的位置
	method=数据提交的方式(默认get/post)
	
form的功能控件
	input-->输入框
	textarea-->多行输入框
	都可以设置输入提醒属性:placeholder
	
	select:下拉菜单
	option:下拉菜单里的选项
	
	button:按钮 一般结合js操作
	
input的类型:
text-->文本框
password-->密码框
checkbox-->多选框
radio-->单选框 基于name判断

submit-->提交按钮
file-->文件上传
reset-->重置表达内容

value:设置控件值
name:设置控件名
```

```
表单有很多感兴趣的话：http://c.biancheng.net/view/7564.html
```

## Label标签

通常写在表单内 他通常关联一个控件

for属性功能表示这个lable是为哪个控件服务的 为鼠标用户改进了可用性

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">

    <title>Document</title>
</head>
<body>
    <label >love me <input type="text"></label>

    <label for="username">姓名</label><input type="text" id="username">
</body>
</html>
```











