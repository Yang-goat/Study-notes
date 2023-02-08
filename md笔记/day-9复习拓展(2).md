## day-9复习拓展(2)

## 复习

```
布局方式:
1.文档流布局-->默认的布局方式 网页内容是从左往右 从上往下.默认属性 内外边距 块元素独占一行
2.浮动布局(float)-->给元素添加浮动,让他脱离文档流,向左/向右移动 直到遇到边界/其他浮动元素为止
3.定位布局(position)-->通过四个方向设置距离的方式 让元素在指定的位置出现
	绝对定位(absolute):让元素在父级的基础上,基于设置的方向值显示 如果没有其他父级 就以body作为父级单位
	相对定位(relative):让元素在自身的基础上,进行四个方向的位移
	固定定位(fixed):让元素在网页中指定位置 固定位置不会因为滚轮滑动而变动
	父相子绝:父元素为相对定位,子元素为绝对定位
	溢出处理:为元素设置 overflow:hidden
	只是设置定了定位是没有反应的 还需要补充对应的上下左右四个方向什么距离值元素才会移动
	设置偏移量:(左上优先级最高)
	top 顶部偏移
	right 右侧偏移
	bottom 底部偏移
	left 左侧偏移
	
选择器拓展:
	伪类选择器:当满足特定条件 激活里面的样式
	元素:hover{} 当鼠标经过该元素时,触发里面样式
	元素:active{} 当按下元素时 触发里面样式
	元素:visited{} 当a标签被访问过时 触发样式
	元素:link{} 当a标签未被访问过时 触发样式
	
	爱恨准则:love hate
	需按顺序否则可能有些伪类不会生效
	
	伪元素选择器:相当于在网页里生成一个'中看不中用'的元素
		伪元素需要content属性才能激活 (可以空着但是不能不写)
		元素::after{content:'';} 后
		元素::before{content:'';} 前
		
	结构选择器:在一个结构中选中指定的元素
		元素:nth-child(n){}:根据下标指定元素
		元素:first-child{} :选中第一个子元素
		元素:nth-last-child(n){}:根据下标指定元素 (倒着数)
		元素:last-child{}:选中最后一个子元素
		元素:nth-of-type(n){}:根据下标指定元素
		
	flex(弹性盒模型布局)
		flex是目前比较主流的布局方式 布局原理就是把内容通过两条轴分割布局
		主轴:横轴
		副轴:竖轴
		flex容器--容器
		flex内容--项目
		
		主轴的方向:
			flex-direction:row;行 默认方向 左到右
			flex-direction:row-reverse; 方向反转 右到左
			flex-direction:column;列 上到下
			flex-direction:column-reverse;列反转 下到上
		主轴的对齐方式:
			justify-content:flex-start;靠起点
			justify-content:flex-end;靠终点
			justify-content:center;居中
			justify-content:space-around;均分布局
			justify-content:space-between;左中右布局
			
		副轴的对齐方式:
			align-items:flex-start;靠起点
			align-items:flex-end;靠终点
			align-items:center;居中
```

## 周作业讲解

## 小米案例

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
        .bigbox{
            margin: 50px auto;
            width: 1200px;
            height: 600px;
            border: 3px solid rgb(108, 189, 162);
        }
        .box1{
            float: left;
            width: 300px;
            height: 100%;/*代表父级高度的100%*/
            background: url(../img/2.jpg) center/cover;
        }
        .box2{
            float: right;
            width: 900px;
            height: 100%;
        }
        .phone{
            float: left;
            margin: 10px;
            padding: 10px;
            width: 250px;
            height: 250px;
            border: 3px solid rgb(146, 156, 161);
            border-radius: 15px;
            text-align: center;
            line-height: 30px;
        }
        .phone img{
            width: 150px;
            height: 150px;
        }

    </style>
</head>
<body>
    <div class="bigbox">
        <div class="box1"></div>
        <div class="box2">
            <div class="phone">
                <img src="../img/2.jpg" alt="">
                <h3>婷婷老师</h3>
                <p>美丽动人温柔贤淑</p>
                <p>勤俭又持家，男人都爱她</p>
            </div>
            <div class="phone">
                <img src="../img/2.jpg" alt="">
                <h3>婷婷老师</h3>
                <p>美丽动人温柔贤淑</p>
                <p>勤俭又持家，男人都爱她</p>
            </div>
            <div class="phone">
                <img src="../img/2.jpg" alt="">
                <h3>婷婷老师</h3>
                <p>美丽动人温柔贤淑</p>
                <p>勤俭又持家，男人都爱她</p>
            </div>
            <div class="phone">
                <img src="../img/2.jpg" alt="">
                <h3>婷婷老师</h3>
                <p>美丽动人温柔贤淑</p>
                <p>勤俭又持家，男人都爱她</p>
            </div>
            <div class="phone">
                <img src="../img/2.jpg" alt="">
                <h3>婷婷老师</h3>
                <p>美丽动人温柔贤淑</p>
                <p>勤俭又持家，男人都爱她</p>
            </div>
            <div class="phone">
                <img src="../img/2.jpg" alt="">
                <h3>婷婷老师</h3>
                <p>美丽动人温柔贤淑</p>
                <p>勤俭又持家，男人都爱她</p>
            </div>
        </div>

    </div>


    <!-- 1.大盒子
    2.一左一右 划分区域 中盒子
    3.右边盒子 再有六个小盒子 -->
</body>
</html>
```

