# day-3初识CSS与文本背景样式

## 知识回顾:

```
HTML的基本形成框架：生成框架 !+tab/html:5
<html></html> --> 是一个网页核心,所有内容都被它包裹
<head></head> --> 头标签,里面写的内容,主要是写给浏览器看的
<body></body> --> 身体标签,主要是写给用户看的
前端代码称为标签：单标签/双标签

h1-h6标签:显示标题标签
p标签:段落标签 会自动换行
span:行内文本 不会换行
b/strong : 文本加粗
i/em : 斜体字
u/ins : 下划线
强调作用 语义化

标签进阶与属性
标签是由标签名 标签属性 文本内容三部分组成
标签有自带属性和通用属性
例如:src href id title  width 
我们通过设置属性实现想要的效果

img图片标签
 <img src="图片路径" alt="图片描述">
插入图片的写法:
	1.图片和代码在同一个文件夹中--直接图片名
	2.图片和代码文件夹里的另一个文件中--文件名/图片名
	3.图片在代码的上一级目录下--../图片名
	
src图片路径 -->图片的位置.可以用绝对/相对路径/网络路径来获取 不推荐用绝对路径
alt图片描述 --> 告诉浏览器这个是什么图片 帮助爬虫更好的识别

超链接a标签-->传送门
<a href="要跳转的链接路径">描述文本</a>
target属性:_blank 新窗口 _self 覆盖原窗口
a标签除了可以跳转到其他的网页 还可以跳转到当前网页指定的位置/指定文件.
通过给标签设置id,就可以跳转到id处

列表 -- 在前端中保存一些带有关联性的数据 分为三种 有序 无序 自定义列表
	无序列表 -- 商品信息 容器ul 元素li
		默认是一个黑点 嵌套列表里为白点
	有序列表 -- 排行榜 容器ol 元素li
		默认是数字排序 可以通过type修改样式
	自定义列表 -- 合作伙伴 大容器dl 小容器dt 元素dd
```

作业:

1.无序列表type属性不能随意使用 需要改的话只能在容器更改

2.文件命名和id名

3.无序列表和自定义列表 一个是同级别 一个上下级关系

## 什么是css?

```
Cascading Style Sheets (层叠样式表)
是一种用来为html文档加样式(字体 间距  位置 颜色 效果)的计算机语言
```

```
html -->写出内容展示处理
css -->找到html写的东西 并给他们加特效 
	1.怎么找?
	2.怎么加?
	
css -- 层叠样式表 --> 用来对网页进行排版 美化外观设置 性能优化
	文本 (字体 大小 对齐方向 颜色 缩进)
	图片 (宽高 边框 颜色 透明度)
	
html:身体 css:化妆
网页文件的后缀: .html
样式表文件的后缀: .css

css注释写法 /*注释内容*/
```

## css选择器

```
css的工作分为两步:1.找到对象 2.加样式
选择器就是找到模块的一种手段 通过选择器找到一个指定的标签元素

1.标签选择器:选择一个标签 (清空样式)
语法格式:
    标签名{
        属性:值;
        属性:值;

    }
     p{
            color: pink;
            font-size: 70px;
        }
    
2.id选择器:给标签设置id编号 然后通过#id名方式找到标签(id唯一性)
语法格式:
    <标签名 id='id名'>
    #id名{
            属性:值;
            属性:值;

        }
     #tt{
            color:blue;
            font-size:55px;
        }
        
3.类选择器(class)给标签设置class类型 然后可以通过 .类名的方式找到对应的标签 类可以多个 id只能有一个(人的名字 可以多个重名)
语法格式:
<标签名 class='class名'>
    .类名{
            属性:值;
            属性:值;

        }
        
一个标签可以同时有多个类名 类名之间用空格隔开
        .red{
            color: red;
        }
        .grend{
            color: #096;
        }
        .a{
            font-size: 50px;
        }
    <p class="a red">红色</p>
    <p class="a grend">绿色</p>
    <p class="a red">红色</p>
    
    
4.通过符选择器(*) 表示选中网页里的所有元素 (清空样式)
覆盖面广 性能造成浪费一般开发不适用 
本身就有数据 不会改变
语法格式:
    *{
            属性:值;
            属性:值;
	}
      *{
            color: #096;
            font-size: 66px;
        }  
        
        
清空列表样式: list-style: none;
```

## CSS书写位置

```
css代码分为:
内部样式
外部样式
行内样式
```

```
1.内部样式 -->把样式表写在当前页面的style标签中 style写在head标签里
语法格式:
    <head>
        <style>
        css代码
        </style >
    </head>
2.外部样式 -->创建外部样式文件 后缀使用.css,在html文件中使用<link>标签引入外部样式表
	rel=引入文件资源类型 href=引入文件资源的路径
	<link rel="stylesheet" href="css文件地址">
3.行内样式 -->通过style属性 把样式直接写标签里
	<标签名 style='属性':值; '属性2':值2;>
```

```css
    <style>
        .wb{
            color: pink;
        }
    </style>
    <link rel="stylesheet" href="demo.css">
</head>
<body>
    <p class="wb">大家真棒</p>
    <p class="zh">大家真好</p>
    <p style="color:red;font-size: 55px;">大家真帅</p>
```

```
样式表优先级为就近原则 -- 行内样式 >内部样式/外部样式

样式表总结:
1.行内样式
    优点:写起来比较方便 权重比较高
    缺点:灵活性不强 
    频率:较少
    范围:单个标签
2.内部样式
    优点:写起来方便在单个页面时比较灵活
    缺点:可复用性不强
    频率:较多(学习阶段)
    范围:整个网页
3.外部样式
    优点:可复用性高
    缺点:需要导入
    频率:最高(开发项目时)
    范围:整个网站
```

## div盒子标签(division)

```
div本身没有任何含义 只是作为划分区域的标签 可塑性比较强 一般作用域容器
把对应的内容放在div盒子里 分割区域 div本身没有宽高/颜色属性的
```

```
<div>内容</div>

<div id="one"></div> 快速为创建一个id为xx的盒子 #xx
<div class="two"></div> 快速为创建一个class为xx的盒子 .xx
```

## 文本样式(font)

```
通过css中的文本属性可以像操作word文档那样定义网页文本字符 间距 对齐方式 缩进等等
```

```
文本样式:
	1.color: 颜色(https://www.sioe.cn/yingyong/yanse-rgb-16/)
		color: blue;
		color: #096;
		color: rgb(250,250,250)
		颜色有三种写法:
			1.直接写预设好的颜色单词关键字
				red  green pink blue
			2.用十六进制颜色
				#096	
			3.用rgb值设置颜色
				rgb(255,255,255)(0-255之间)
				rgb(0,0,0)	(红 绿 蓝)
				rgb(123,70,200)
	2.font-size: 字体大小  (px像素 em字符单位)	
		font-size: 70px;	
	3.text-indent: 文字缩进
		text-indent: 2em;  缩进两个字		
	4.font-family:  设置字体
		font-family: '字体值';
宋体 SimSun
黑体 SimHei
微软雅黑 Microsoft YaHei
新宋体 NSimSun
新细明体 PMingLiU
细明体 MingLiU
标楷体 DFKai-SB
仿宋 FangSong
楷体 KaiTi
		
			
	5.font-weight: 设置字体粗细值
		font-weight: 100; (设置范围100-900)
	6.font-style: 字体样式(倾斜)	
		font-style:italic;
	7.line-height: 设置字体的上下位置	
		line-height: 30px;
	8.text-align: 设置文本对齐
		text-align	:center;
			left左 center中间 right右
	9.text-decoration: 设置文本样式		
		text-decoration: underline(ande 来); 下划线
						 none;  默认啥都没有(a 标签去除下划线)
						 overline;  上划线
						 line-through; 删除线

```

## 背景样式(background)

```
background-color：颜色
background-image: url(./img/图片1.jpg);图片
调整图片位置
background-position: left;
设置背景大小
background-size: cover;等比缩放
设置背景图片不重复
background-repeat: no-repeat;
```



## 注意:

```
命名:
1.见名知意
2.文件和元素命名全英文小写 禁止驼峰 多个单词建议使用'-'链接符
top-bar
3.不允许命名带有广告等英文单词 防止模块被浏览器当做垃圾广告过滤掉(文件命名一样)

1.写选择器的时候 要遵循一定的顺序 通配符>标签选择器>类/id选择器

2.标签选择器一般不是用来加样式的 而是用来清楚样式(清楚列表样式/内外边距/字体大小)
3.属性值后面要有分号
```



## 作业

```
新建网页.内有3个p标签,内容写三个自己新年愿望
通过三种样式写法.给p标签添加样式(改字号/变颜色都可,自行发挥)

完成网盘图片谷歌图
```

