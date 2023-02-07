# day-8 flex布局

## 知识回顾

```
选择器拓展:
伪类选择器: 当满足特定的条件时 触发对应样式
	元素:hover{} 当鼠标经过元素时 激活样式
伪元素选择器: 创建一个虚假元素 不能被选中 不存在网页的dom中(私密/性能)
	元素::before{content:'内容'}
	元素::after{content:'内容'}
结构选择器:选择一个结构中的指定元素
	元素:nth-child(n){} -->选择指定序号的子元素
	元素:first-child{} -->选择第一个子元素
	元素:last-child{} -->选择最后一个子元素
	
表单:
	form
	负责写一些提供用户交互的窗口 --输入框/勾选框/确认框
		input -- 输入框
		textarea -- 多行输入框
		button -- 按钮
		
		select -- 下拉框
		option -- 下拉框里的选项
		
	input有很多种类型
		text 文字
		password 密码
		radio 单选框
		checkbox 多选框
		file 文件提交
		submit 提交
		reset 重置
```



## 小黄鸭代码调试法

```
通过自言自语把它提升到一个新的层次

在电脑旁边放一只鸭子 遇到问题的时候 你把你的问题和他说一遍可能就解决

旁观者清 尝试把你的代码思路/流程和对方说一遍 自然的梳理你的过程
过程中就看到解决了问题
```

## 阿里图标

```
原理:将小图标定义为字体,通过引入字体来展示这些小图标 因此此时的小图标相当于一个文字 所以支持文字对应的所有样式(字体大小 颜色等等)
```

```
免费将图标以字体的形式加载页面

	使用步骤：
	（百度： 阿里巴巴矢量图标库）
	1.  打开阿里图标官网：https://www.iconfont.cn/
	2.  注册/登录
	3.  选择需要的图标加入购物车
	4.  下载代码
	
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="../font_3frgs696zqn/iconfont.css">
</head>
<body>
    <p class="iconfont icon-meishi"></p>
</body>
</html>
```

## flex布局(弹性盒模型)

```
flex是当前比较主流的布局方式-->他布局起来更加方便 取代了float的作用
浮动布局有缺陷 会脱离文档流可能会导致布局崩塌

用flex布局的元素称为flex容器 他里面的子元素称为容器项目/flex项目
父级:容器 子级:项目

flex布局原理:就是通过两种轴 把网页分割成一行行/一列列
		flex主轴是从左往右 副轴从上往下
		
flex的使用:
	display:flex;
	
flex样式说明:
	设置主轴的方向:flex-direction
	row; 行 默认属性 从左到右
	column; 列 从上往下
	row-reverse; 行反转 从右往左
	column-reverse; 列反转 从下往上
	
	设置主轴的对齐方向:justify-content
	flex-start; 默认值 按照起点对齐 左上
	flex-end; 终点对齐 右下
	space-between;两端对齐
	space-around; 均分布局
	
	设置副轴的对齐方式:align-itmes
	center; 居中
	flex-start; 靠起点
	flex-end;靠终点
	
	设置换行(如果主轴装不下内容):flex-wrap
	no-wrap;缩放不换行
	wrap;换行
	
	flex项目属性:
	order:项目的顺序 数值越小 排列越靠前 默认为0
	
```

## 登录页面

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
        }
        html,body{
            height: 100%;/*浏览器的高度为整个页面的高度*/
        }
        body{
            display: flex;
            background: url(https://lmg.jj20.com/up/allimg/4k/s/01/210924155T04M5-0-lp.jpg) no-repeat;
            background-size: 100%;/*背景大小*/
            justify-content: center;/*主轴横轴 居中*/
            align-items: center;/*副轴竖轴居中*/

        }
        #login_box{
            width: 350px;
            height: 400px;
            background-color: rgba(48, 44, 44, 0.49);
            text-align: center;
            margin: auto;
            margin-top: 10%; /*上边的外边距距离*/
            padding: 50px 50px;
            border-radius: 10px;
        }
        h2{
            color: darkgrey;
            text-align: center;
        }
        #input_box{
            display: flex;
            flex-direction: column;/*把主轴从横改为竖的*/
            justify-content: space-around;/*均分布局空间*/
            align-items: center;/*副轴居中*/
            height: 100px;/*设置表格高度*/
            
        }
        input{
            border: 0;/*边框为0 对于浏览器来讲是渲染 但是我没去掉边框*/
            background: transparent;/*透明色*/
            width: 60%;/*父级的百分之60*/
            font-size: 15px;
            outline: none;/*给表格双击选择的时候边框去样式*/
            border-bottom: 2px  solid #fff;
            padding: 5px 10px;
            margin-top: 10px;
        }
        button{
            width: 250px;
            height: 30px;
            border-radius: 10px;
            border: 0;
            color: #fff;
            background-color: darkgreen;
            margin-top: 50px;
            line-height: 30px;
            font-size: 15px;
        }
    </style>

</head>
<body>
    <div id="login_box">
        <h2>LOGIN</h2>
        <form action="" id="input_box">
            <input type="text" placeholder="请输入用户名">
            <input type="password" placeholder="请输入密码">
        </form>
        <button>登录</button>
    </div>
</body>
</html>
```





