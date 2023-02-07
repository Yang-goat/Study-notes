# day-4盒子模型与样式排版

## 知识回顾

```
css层叠样式表 --> 找到网页里的一些html元素 然后实现美化/性能优化效果
-->颜色 背景 排版 大小
做的事: 1.找到元素 2.给元素加样式

找到标签元素 --选择器
1.标签选择器-->标签名{属性:值;}
2.id选择器-->#id名{属性:值;}
3.class选择器-->.class名{属性:值;}
4.通配符选择器-->*{属性:值;}

样式表写法:
1.行内样式表-->把样式写在标签里(用的不多)
2.内部样式表-->把样式写head里的style标签中
3.外部样式表-->把样式写head里的link标签中

文本样式(font):
font-size:设置字体大小
font-family:设置字体
font-style:字体样式(倾斜)
font-weight:设置字体的粗细值
text-align:设置对齐方式
line-height:设置行高 
背景样式(background)
background-color:背景颜色
background-image:背景图片
```

## 块级元素基础特性(block)

```
常用的块元素:
div p h1-h6 ol ul dl dd dt

概念:常用于网页上布局和网页结构的搭建
(地主 每个人都只有自己的一块地)

特性:
1.块元素总是独占一行
2.块元素有宽高,高度,边距属性,这些都可以自己设置
3.块元素的宽度默认是浏览器的100% 高度为内容的高度
4.块元素可以包含行内元素/其他元素
但是:p标签里不能放块级元素
(p标签中不要嵌套div p h )
```

## 行内元素基础特性(inline)

```
常用的行内元素:
span a b strong i u 

概念:用于控制页面中文本的样式 只是用来包裹文字
仅靠自身字体大小和图像本身的尺寸来支撑
(打工人 没有自己的地盘)


特性:
1.行内的默认宽高是自身属性
2.行内元素设置宽高没有意义 不具备结构能力
3.行内元素不会独占一行 默认都是放在一起
4.行内元素不能放块元素 只能放其他的行内元素

a标签特殊-->他和用户体验相关 所以a标签可以包裹块元素 主要是为了移动端方便(a标签不能放a标签 进行截断) 

img:行内元素 (置换元素)
img属于行内元素 性质是跟inline-block一样
```

## 行内块元素(inline-block)

```
行内块元素是行内和块元素的集合体 同时具有两者的特征(主块 辅行)
1.和相邻的行内元素(行内块)在一行时,末尾会有一个空格
2.默认宽度是内容宽度
3.宽高内外边距都可以设置
```

## 元素类型转换

```
display:类型转换样式
	display:block;把标签转为块元素
	display:inline;把标签转为行内元素
	display:inline-block;把标签转为行内块元素
```

## 盒子模型(div)

```
盒子的组成:
内容区(content)
内边距(padding)
边框(border)
外边距(margin)

内边距padding:
	盒子里的内容距离盒子边框的距离
	
外边距:margin:
	盒子距离外部便捷的距离
	
```

```
盒子核心属性:
	width:宽度 默认为浏览器的100%
	height:高度 默认为盒子的内容
	overflow:溢出处理
		hidden;隐藏溢出的部分
		visible;照常显示溢出的部分(默认)
		scroll;通过滚动条显示溢出的部分
		auto;让浏览器自己看着办(一般情况下会scroll结果)
		
```

## 盒模型标签属性:

```
复合写法
background image color size position
background:url() center/cover; 快捷方式:插入图片 居中显示+等比例缩放

margin -- 设置外边距
padding -- 设置内边距

margin和padding里面  写1-4个数值的时候 意思是不同的
padding:10px; 距离上下左右10px
padding:10px 15px; 1.上下 2左右
padding:10px 15px 15px; 1.上 2.左右 3.下
padding:10px 15px 15px 15px; 1.上 2.右 3.下 4.左

margin设置左右居中:
margin:随便 auto;
auto会自动计算容器的宽度来实现居中的效果

单独设置方向:
margin-top-->设置上外边距
margin-right-->设置右外边距
margin-bottom-->设置下外边距
margin-left-->设置左外边距

padding-top-->设置上内边距
padding-right-->设置右内边距
padding-bottom-->设置下内边距
padding-left-->设置左内边距

一般只有左右居中 不怎么上下居中
1.flex
2.给body设置宽高行高 把要居中的内容设置为行内块元素
```

## 边框(border)

```
边框复合写法:
border:1px solid #096; 粗细 样式 颜色

border-width-->设置边框粗细
border-color-->设置边框颜色
border-style-->设置边框样式
none 没有样式
solid 实线
double 双实线
dashed 虚线
dotted 点线

border-radius-->设置边框圆角

border-top-->设置上边框
border-right-->设置右边框
border-bottom-->设置下边框
border-left-->设置左边框
```

## 作业

 ```
完成网盘作业
 ```

