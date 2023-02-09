# day-10初识JavaScript

## JavaScript介绍

```
首先学js前几节课都非常的舒服 -->概念知识跟我们的Python相同
逻辑相通 但是语法不同 不要记混

JavaScript简称js 是一种浏览器解释型语言 是可以嵌入在html文件中交给浏览器解释执行.主要用来实现网页的动态效果 用户交互以及前后端的数据传输等.
```

```
前端三剑客 -- html css JavaScript
	html:网页的组成/内容的展示 -->身体
	css:网页的样式/排版布局美化设计 -->衣服/化妆品
	JavaScript:动态效果,网页交互 -->技能,行为
	
我们后续的开发,涉及到的前端知识中,主要是用到html/js
	1.写爬虫的时候要了解一个网页是怎么组成的,他有什么容器,选择器-->(html标签,选择器)
	2.写后端数据的时候,要知道前端用了什么html容器接受,并且通过js的方法进行交互 
	
java/JavaScript
	JavaScript是一种轻量级的编程语言('脚本语言'),用于使网页交互,
	java是一种面向对象的编程语言.
	两者不能说一点关系都没有,因为最初js是受java启发而设计目的是蹭一下java热度
	
JavaScript能做什么:
	1.网页的动态效果
    2.前后端交互(数据提交 人机交互)
    3.进阶 前端高端框架(vue.js React.js Nonde.js) VR/AR开发(Three.js)
    
html/css :不是编程语言 
JavaScript:是一个正经的编程语言 并且语法逻辑概念和Python/c都有一定的重合 
```

## JavaScript的组成

- ECMA Script --> ES -->简称ES 可以理解为是js语法规则,目前最新版本是ES13 不过我们不用那么新教学内容基于ES6

  ECMA 是一个欧洲计算机制造商协会 主要做一些评估  开发和计算机标准

- BOM--Browser object model-->浏览器对象模型 主要对浏览器进行操作(交互 弹窗 输入框)

- DOM--Document  object model-->文档对象模型 负责对网页的内容进行操作(网页里所有内容都称为文档)

## JavaScript书写位置

- 内部JavaScript: 直接写在html文件里 用script标签包住

  ```
  语法: <script>js代码</script>
  ```

  ```JavaScript
  <script>
          document.write('大家多喝岩浆吃饱喝足睡觉觉')
  </script>
  ```

  

- 外部JavaScript:JavaScript代码写在以.js结尾的文件里通过script标签,引入到html页面中

  ```
  语法: <script src="js文件路径"></script>
  ```

  ```javascript
  <script src="demo.js"></script>
  <!-- 在这个标签里写js代码是无效的 -->
  <!-- document.write('吃麻辣烫') -->
  ```

- 注意:

  ```
  引入js最好放在网页内容的最后/body的最后-->网页的加载顺序由上往下
  如果位置不对 有可能就出现先用js操作 在出现网页的内容情况
  提升页面的加载性能
  
  
  js的脚本测试内容是在控制台里显示而不是在网页中
  怎么进控制台:
  	1.按下f12-->选择console/控制台
  	2.快捷方式 ctrl+shift+j
  ```

  

## js输入输出

### 注释

```
单行注释: //注释内容
多行注释: /*注释内容*/
```

### 输出

```
输出语句:
	document.write:在网页里写一行内容 写的如果是标签能被识别 字符串需要用引号包裹 数字不用
	语法格式:
		document.write(内容)
	案例代码:
		document.write(666)
		document.write('多喝岩浆')
		document.write('<i>多喝汽水</i>')
		
	console.log:控制台输出日志,在控制台输出一个信息(主要是用来测试js数据的)
	语法格式:
		console.log(内容)
	案例代码:
		console.log(888)
		console.log('螺蛳粉')
	alert:弹窗 在网页显示一个弹窗
    语法格式:
    	alert(内容)
    案例代码:
		alert('1-11前端补充班牛逼')	
```

### 输入

```
输入语句:
	prompt:在进入网页时 弹出输入框,让用户输入内容,输入框里可以放提示文本
	语法格式:
		prompt()
		prompt('提示内容')
	案例代码:
    	prompt('请输入你的名字')

用输入来赋值 prompt得到的数据是字符串类型(输入的方法给变量赋值)
	let name = prompt('请输入你的姓名')
	alert('欢迎你'+name)
```

```javascript
prompt('请输入你的名字')
let name = prompt('请输入你的姓名')
alert('欢迎你'+name)
```

## js变量

```
一个用来存储东西的容器 取个有意义的名字 方便后续使用

命名规范:
    1.变量名可以由数字,字母,下划线,$组成,禁止以数字开头(中文不推荐)
    2.变量名严格区分大小写
    3.不要用关键字命名
    4.见名知意
    

var/let =声明符 标识符 在声明变量前需要加上
let:es6新出的语法 作用和var类似但是在作用域上let更严谨 这次教学里统一let 

变量使用:
    1.声明变量
    	let 变量名 //声明一个空变量没有赋值
    	let 变量名=变量值
    	
    	let name
    	let age=18
    2.声明多个变量
    	let 变量名=变量值,变量名=变量值
    	
    	let name='婷婷',age=18
    3.输出变量
    	console.log(变量名)
    	document.write(变量名)
    	alert(变量名)
    4.输出多个变量
    	console.log(变量名,变量名)
    	document.write(变量名,变量名)
    	alert(变量名,变量名)
    	
1.直接写 变量名=变量值 不写let写法上是允许 但是非常不推荐
2.变量使用let关键字声明但是未被赋值 变量初始值为undefined 不会报错
```

```javascript
		let name='婷婷'
    	let age=18
        let sex='女',money=9.9 
        document.write(age,name)
        console.log(sex,money)
```

## js基本数据类型

```
区分类型: 使我们更方便运行和操作管理数据
js中查看数据类型-->typeof 
console.log(typeof 数据)
console.log(typeof name,typeof age)
```

### string(字符串)

```
通过单引号'' 双引号"" 或者反引号`` 包裹起来的数据都叫字符串-->文字信息/名字/地址
语法格式:
	let 变量名='字符'
	let 变量名="字符"
	
		let name='吴彦祖'
	    let age=18
	    console.log(typeof name,name)
        document.write(typeof age,age)
```

```
反引号主要是作为模板字符串使用(类似f-str),帮助我们更好的输出一些带有变量的数据
```

```
`字符${变量名}字符`
	let name =`王大锤`,age=18
	console.log(`我叫${name}我今年${age}`)
```

### number(数值类型)

```
JavaScript不区分整数 浮点数等等 统一都叫number-->年龄/身高/体重
	
	let 变量名=数值
	let age=18
	let money=9.9
	console.log(age,money)
	console.log(typeof money,money)
```

### boolean(布尔类型)

```
布尔类型主要作用于逻辑判断 只有两值 true/false
	let 变量名=true/false
	
		let is_login=true
        let not_login=True//会报错 没有被定义
	    console.log(is_login,typeof is_login)
注意:js里的布尔值首字母不需要大写   
```

### undefined(未定义)

```
undefined即是类型也是值 指的是未定义的意思 当你声明的变量没有赋值时,他的值就是为undefined
	let 变量名
	let test
	console.log(test,typeof test)
```

### null(空)

```
null和python里none类似 表示的就是值为空 输出类型为对象(空对象)
	let food =null
	console.log(food,typeof food)
```



## js转义字符

```
\n 换行
\t 制表符tab键
\\ 正常输出一个斜杠
\' 正常输出一个引号
```

```javascript
<script>
        console.log('想想今晚\t吃什么')
        console.log('刘水东\n吃什么')
</script>
```

## js类型转换

```
在开发/学习过程中,经常会遇到需要把一个数据转为其他的类型使用 这个时候就需要转换
	1+'1'//'11'
	1-'1'//'0'
	
	隐式类转换:
    	程序运行过程中自动执行 自动发生一种转换机制 主要体现在字符串和数值进行运算时
    	+号会优先识别为拼接 其他的就是正常数值运算
    	
    强制类型转换
    	手动的把数据转为指定的数据类型
    	Number(数据)--把数据转为number类型
    		1.如果数据转换失败 结果为NaN
    		2.NaN也是number类型 表示的是非数字 Not a Number
    	String(数据)--把数据转为string类型
    	Boolean(数据)--把数据转为Boolean类型
    	在转换时 有值为真 无值为假(0 -0 undefined null)
```

## 运算符类型

```

```



## 作业

```
涉及到输入的内容.提交截图即可
1.声明变量给自己建立个角色信息,并输出(姓名 年龄 性别 来自哪里 兴趣爱好 单身与否)
2.用prompt输入自己的名字,需要带提醒
3.用输出或者输入的方式, 打出自己在VIP班遇到过主讲/班主任老师名字
4.用一个console.log输出以下内容(转义字符)
	爱你所爱		行你所行
	听从你心		无问西东
5.填空题
	let a = 520     a的类型为__number
	let b = 'True'  b的类型为__string
	let c = '520'   c的类型为__string
	let d			d的类型为__undefined
	let e = 6.66    e的类型为__number
	let f = 0.0		f的类型为__unmber
	let g = true	g的类型为__boolean
	let h = False	h的类型为__undefined
```