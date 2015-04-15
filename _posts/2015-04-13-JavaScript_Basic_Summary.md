---
layout: post
author: Chewein
title: JavaScript基础总结
category: JavaScript
tag: [JavaScript,总结] 
---

在慕课网在线学习javaScript学的快，去的也快。慕课网将知识点分成一个一个的小点，每个小点内容不多，解释的也很详细，很好懂，但学完之后没什么印象，这里总结一下。

-----------------------------------------

## 数据类型与运算

-----------------------------------------

### 变量

声明一个变量：**var 变量名**
变量可以在声明时赋值，也可以声明完之后另起一行在赋值。既可以赋值数字，也可以赋值字符串，赋值字符串时要用双引号括起来。

-----------------------------------------

### 表达式

JavaScript的表达式在给字符串赋值时很方便，可以直接使用"+"号连接多个字符串。

-----------------------------------------

### 运算符

JavaScript支持各种运算，如：

- 算术运算符：+、-、#、/
- 比较操作符: >、>=、<、<=、==、!= 
- 逻辑操作符：&&、||、! 

这几种运算符的优先级顺序为：**算术操作符 → 比较操作符 → 逻辑操作符 → "="赋值符号**

-----------------------------------------

### 数组

#### 一唯数组

- 声明一个数组时使用关键字**new Array**，且无需指明数组大小：
```
 var myarr=new Array(); 
``` 
- 数组成员赋值：
```
 myarr[0]="hello world"; 
``` 
- 增加数组成员：只需使用下一个未用的索引；
- 引用数组成员：下标从0开始；
- 获取数组大小：数组属性**array.length**


#### 二唯数组

- 声明一个二维数组：
```
var myarr    = new Array(); 
    myarr[0] = new Array();
```
- 引用二维数组：**myarr[][]**注意下标从0开始


-----------------------------------------

## 流程控制

JavaScript的流程控制语法很类似C/C++相关语法。

### if判断
```
if(条件1){ 
    条件1成立时执行的代码
}
else if(条件2){
    条件2成立时执行的代码
}
...
...
...
else{ 
    条件1、2至n不成立时执行的代码
}

```

-----------------------------------------

### switch选择
```
switch(表达式)
{
    case 值1:
            执行代码块 1
            break      ;
    case 值2:
            执行代码块 2
            break      ;
    ...
	...
	...
    case 值n:
            执行代码块 n
            break      ;
    default:
           break       ;
}
```

-----------------------------------------

### for循环
```
for(初始化变量;循环条件;循环迭代){     
    循环语句 
}
```

-----------------------------------------

### while循环
```
while(判断条件){
    循环语句
}
```
-----------------------------------------

### Do(  )while循环())
```
do{
    循环语句
}
while(判断条件)
```
-----------------------------------------

### 退出循环break

在while、for、do...while、while循环中使用break语句退出当前循环，直接执行后面的代码。

-----------------------------------------

### 继续循环continue

continue的作用是仅仅跳过本次循环，而整个循环体继续执行。


-----------------------------------------

## 函数

- 声明函数：

```
function function-name(parameter...){
    function-body;
} 
```

- 函数返回值：若有返回值，只需加上```return var;```
- 函数调用：函数定义好后，是不能自动执行的，需要调用它,直接在需要的位置写函数名
   - 第一种情况:在\<script>标签内调用；
   - 在HTML文件中调用，如通过点击按钮后调用定义好的函数。

-----------------------------------------

## 事件响应


### 鼠标事件

- 鼠标单击事件(onclick)：

```
<input name="button" type="button" value="点击提交" onclick="add2()/>
```
- 鼠标经过事件(onmouseover):

```
<input name="button" type="button" value="点击提交" onmouseover="info()/>
```
- 鼠标移开事件(onmouseout)：

```
<input name="button" type="button" value="点击提交" onmouseout="message()/>
```
- 鼠标聚焦事件(onfocus)：

```
<input name="button" type="button" value="点击提交" onfocus="message()/>
```
- 鼠标失焦事件(onblur)：

```
<select name="career" onblur="message() id="new1"> 
```


###文本事件

当文本框或者文本域中的文字被选中时或改变时会触发文本事件。

- 文本内容选中事件(onselect)： 

```
<textarea name="summary" cols="60" rows="5" onselect="message()">请写入个人简介，不少于200字！</textarea>
```
- 文本内容改变事件(onchange)： 

```
<textarea name="summary" cols="60" rows="5" onchange="message()">请写入个人简介，不少于200字！</textarea>
```

### 页面事件

当页面加载完毕或者离开关闭页面时或触发页面事件。

- 加载事件(onload)：<body onload="message()"> </body>
- 卸载事件(onunload)：window.onunload = onunload_message;  然后定义onunload_message()函数。

-----------------------------------------

## JavaScript内置对象

### Date对象

日期对象可以储存任意一个日期，并且可以精确到毫秒数(1/1000 秒)，另外Date对象中处理时间和日期的常用方法。

- 定义一个时间对象```var Udate=new Date(); ```
- 如果要自定义初始值，可以用以下方法：```var d = new Date(2012, 10, 1);``` 
- ```get/setDate()``` 返回/设置日期 get/setFullYear() 返回/设置年份，用四位数表示 get/setYear()年份
- ```get/setMonth()``` 返回/设置月份【0表示一月，11表示十二月，所以要给这个数值加上一】
- ```get/setDay(```) 返回/设置星期【0表示星期天】 get/setHours() 返回/设置小时【24小时制】
- ```get/setMinutes()``` 返回/设置分钟数 get/setSeconds() 返回/设置秒钟数

-----------------------------------------

### String字符串对象

- 定义字符串的方法就是直接赋值：```var mystr = "I love JavaScript!"```；
- 字符串长度：```mystr.length;```；
- 返回指定位置的字符：**mystr.charAt()**返回的字符是长度为 1 的字符；
- 返回指定的字符串首次出现的位置：**mystr.indexOf(substring, startpos)**从startpos开始首次出现substring的位置；
- 字符串分割：**mystr.split(separator,limit)**，以separator作为分隔符，最多分割limit个；
- 提取字符串：**mystr.substring(starPos,stopPos)**，提取字符串中介于两个指定下标之间的字符；
- 提取指定数目的字符：**mystr.substr(startPos,length)**，提取从 startPos位置开始的指定数目的字符串；

-----------------------------------------

### Math对象

Math对象，提供对数据的数学计算。

- Math对象属性：
  - Math.E： 算数常量e
  - Math.LN2： 2的自然对数
  - Math.LN10： 10的自然对数
  - Math.LOG2E： 以2为底的 e 的对数
  - Math.LOG10E： 以10为底的 e 的对数
  - Math.PI： 圆周率
  - Math.SQRT1_2： 2的平方根的倒数
  - Math.SQRT2： 2的平方根
- Math 方法：
  - Math.abs(x)： 绝对值
  - Math.acos(x)： 反余弦
  - Math.asin(x)： 反正弦
  - Math.atan(x)： 反正切
  - Math.atan2(x,y)： x 轴到点(x,y)的角度
  - Math.ceil(x)： 向上舍入
  - Math.cos(x)： 余弦
  - Math.exp(x)： e的指数
  - Math.floor(x)： 向下舍入
  - Math.log(x)： x的自然对数（以e为底）
  - Math.max(x,y)： x 和 y 中的最大值
  - Math.min(x,y)： x 和 y 中的最小值
  - Math.pow(x,y)： x 的 y 次幂
  - Math.random()： 0-1 间的随机数
  - Math.sin(x)： 正弦
  - Math.sqrt(x)： x的平方根
  - Math.tan(x)： 正切
  - Math.toSource()： 该对象的源代码
  - Math.valueOf()： Math对象的原始值

-----------------------------------------

### Array 数组对象

数组对象是一个对象的集合，里边的对象可以是不同类型的。数组的每一个成员对象都有一个从零开始的"下标"，用来表示它在数组中的位置。

- 定义数组
  - 定义了一个空数组：```var  myarr= new Array();```
  - 定义时指定有n个空元素的数组：```var myarr =new Array(n);```
  - 定义数组的时候，直接初始化数据：```var  数组名 = [<元素1>, <元素2>, <元素3>...];```
- 数组方法
  - Array.concat( )：连接数组 
  - Array.join( )：将数组元素连接起来以构建一个字符串 
  - Array.length：数组的大小 
  - Array.pop( )：删除并返回数组的最后一个元素 
  - Array.push( )：给数组添加元素 
  - Array.reverse( )：颠倒数组中元素的顺序 
  - Array.shift( ) 将元素移出数组 
  - Array.slice( ) 返回数组的一部分 
  - Array.sort( )：对数组元素进行排序 
  - Array.splice( )：插入、删除或替换数组的元素 
  - Array.toLocaleString( )：把数组转换成局部字符串 
  - Array.toString( )：将数组转换成一个字符串 
  - Array.unshift( )：在数组头部插入一个元素
  
-----------------------------------------

## 浏览器对象

### window对象

window对象是BOM的核心，window对象指当前的浏览器窗口。window对象具有以下方法：

-  alert()：显示带有一段信息和一个确认按钮的警示框
-  prompt()：显示可提示用户输入的对话框
-  confirm()：-显示带有一段消息及确认按钮和取消按钮的对话框
-  window.open()：打开一个新的浏览器窗口或查找一个已命名的窗口
-  window.close()：关闭浏览器窗口
-  window.print()：打印当前窗口的内容
-  window.focus()：把键盘焦点给予一个窗口
-  window.blur()：把键盘焦点从顶层窗口离开
-  window.moveBy()：相对窗口的当前坐标把它移动指定的像素
-  window.moveTo()：把窗口的左上角移动到指定的坐标
-  window.resizeBy()：按照指定的像素调整窗口的大小
-  window.resizeTo()：把窗口的大小调整到指定的宽度和高度
-  window.scrollBy()：按照指定的像素值来滚动内容
-  window.scrollTo()：把内容滚动到指定的坐标

-----------------------------------------

### JavaScript 计时器

在JavaScript中，我们可以在设定的时间间隔之后来执行代码，而不是在函数被调用后立即执行。
- setTimeout()：指定的延迟时间之后来执行代码
- clearTimeout()：取消setTimeout()设置
- setinterval()：每隔指定的时间执行代码
- Clearinterval()：取消setinterval()设置

-----------------------------------------

### History对象

history对象记录了用户曾经浏览过的页面(URL)，并可以实现浏览器前进与后退相似导航的功能。

- history.length //浏览器历史列表中的URL数量
- history.go()：加载history列表的某个url
- history.back()：加载history列表的上一个url
- history.forward()：加载history列表的下一个ur

-----------------------------------------

### Location对象

location用于获取或设置窗体的URL，并且可以用于解析URL。

- location 对象属性：
  - location.hash - 设置或返回从#号开始的URL
  - location.host - 设置或返回主机名和当前的端口号（包括 hostname 和 port）
  - location.hostname - 设置或返回当前URL 的主机名
  - location.href - 设置或返回完整的 URL
  - location.pathname - 设置或返回当前URL 的路径部分（host 至 ? 之间的内容）
  - location.port - 设置或返回当前 URL 的端口号
  - location.portocol - 设置或返回当前 URL 的协议
  - location.search - 设置或返回从 ? 开始的URL

- location 对象方法：
  - location.assign() 加载新的文档
  - location.reload() 重新加载当前文档
  - location.replace() 用新的文档替换当前文档


-----------------------------------------

### Navigator对象

Navigator 对象包含有关浏览器的信息，通常用于检测浏览器与操作系统的版本。

- Navigator.appCodeName 浏览器代码名的字符串表示
- Navigator.appName 返回浏览器的名称
- Navigator.AppVersion 返回浏览器的平台和版本信息
- Navigator.platform 返回运行浏览器的操作系统平台
- Navigator.userAgent 返回由客户机发送服务器的user-agent头部的值


-----------------------------------------

### screen对象

screen对象用于获取用户的屏幕信息。

screen.availHeight:窗口可使用的高度
screen.availWidth：窗口可使用的宽度
screen.colorDepth:用户的颜色表示位数，通常为32位
screen.prixelDepth:同上（IE不支持）
screen.height：屏幕的高度
screen.widht：屏幕的宽度

-----------------------------------------

##DOM对象

文档对象模型DOM（Document Object Model）定义访问和处理HTML文档的标准方法。DOM 将HTML文档呈现为带有元素、属性和文本的树结构（节点树）。

- HTML DOM 方法：
  - document.getElementById()：返回带有指定 ID 的元素；
  - document.getElementsByTagName()：返回包含带有指定标签名称的所有元素的节点列表(集合/节点数组)；
  - document.getElementsByClassName()：返回包含带有指定类名的所有元素的节点列表；
  - document.createElement(tagName)：方法可创建元素节点。此方法可返回一个 Element 对象；
  - document.createTextNode： 方法创建新的文本节点，返回新创建的 Text 节点；

- 节点方法： 
  - node.appendChild(newnode)：指定节点的最后一个子节点列表之后添加一个新的子节点。
  - node.removeChild(node)：删除子节点node。
  - node.replaceChild(newnode,oldnode)：newnode替换子节点oldnode。
  - node.insertBefore(newnode,node)：在指定的子节点node前面插入新的子节点newnode。
  - node.getAttribute(name)方法：通过元素节点的属性名称获取属性的值。
  - node.setAttribute(name,value)方法：增加/修改一个指定名称和值的属性。
