---
layout: post
author: Chewein
title: Jquery基础总结
category: JavaScript
tag: [JavaScript,Jquery,总结] 
---

在慕课网在线学习jquery学的快，去的也快。慕课网将知识点分成一个一个的小点，每个小点内容不多，解释的也很详细，很好懂，但学完之后没什么印象，这里总结一下。

## 环境搭建 

- 下载jQuery文件库：在[jQuery](http://jquery.com)中，下载最新版本的jQuery文件库。
- 引入jQuery文件库：在页面的<head></head>中加入如下代码：

```
<script language="javascript" type="text/javascript" src="js/jquery.js"></script>
```


-------------------------------------

## jQuery 基础选择器

通过选择器可以选择HTML的id或者标签，然后修改这些id或者标签的属性/CSS等等。

- **#id 选择器**：$("#my_id")，返回唯一一个元素。
- **element 选择器**：$("element")。
- **.class 选择器**：$(".class")。
- **\* 选择器**：$("*")，获取页面中的全部元素。
- **sele1,sele2,seleN选择器**：$("sele1,sele2,seleN")选择任意多个指定的元素。
- **ance desc选择器**：$("ance desc")ance参数表示父元素；desc参数表示**所有**后代元素，即包括子元素、孙元素等等。
- **parent > child选择器**：$("parent > child")获取parent元素的子元素，但不包括孙辈。
- **prev + next选择器**：$("prev + next")查找与"prev"元素紧邻的下一个"next"元素，仅取一个。
- **prev ~ siblings选择器**：$("prev ~ siblings")查找prev元素之后的所有相邻元素。


-------------------------------------

## jQuery过滤性选择器

- **first过滤选择器**： $("li:first")获取第1个\<li>元素。
- **eq(index)过滤选择器**：$("li:eq(3)")获取第3个\<li>元素。
- **contains(text)过滤选择器**：$("li:contains(text)")含有text内容的\<li>元素。
- **has(selector)过滤选择器**：$("li:has(p)")含有\<p>元素的\<li>元素。
- **hidden过滤选择器**：$("p:hidden")获取不可见的\<p>元素。
- **visible过滤选择器**：$("p:visiable")获取可见的\<p>元素。
- **attribute=value属性选择器**：$("li[attr=value]")属性attr值为value的\<li>元素。
- **attribute!=value属性选择器**：$("li[attr!=value]")属性attr值为value的\<li>元素。
- **attribute*=value属性选择器**：$("li[attr*=value]")属性attr值中包含有value的所有\<li>元素。
- **first-child子元素过滤选择器**：$("li:first-child")所有\<li>元素父元素的第一个\<li>子元素的集合。
- **last-child子元素过滤选择器**：$("li:last-child")所有\<li>元素父元素的最后一个\<li>子元素的集合。

-------------------------------------

## jQuery表单选择器

下面的#frmTest指一个id为frmTest的\<div>容器。

- **input表单选择器**：$("#frmTest:input")返回全部的表单元素，包括所有\<input>,\<textarea>、\<select> 和\<button>标记的表单元素。
- **text表单文本选择器**：:$("#frmTest:text")可以获取表单中全部单行的文本输入框元素
- **password表单密码选择器**：$("#frmTest:password")要获取密码输入文本框
- **radio单选按钮选择器**：$("#frmTest:radio")轻松获取表单中的单选按钮元素。
- **checkbox复选框选择器**：$("#frmTest:checkbox")可以快速定位并获取表单中的复选框元素。
- **submit提交按钮选择器**：$("#frmTest:submit")可获取表单中的这个提交按钮元素。
- **image图像域选择器**：$("#frmTest:image")可以快速获取\<input>元素的“"type"属性值设为"image"时的元素。
- **button表单按钮选择器**：$("#frmTest:button")能获取且只能获取\<button>元素和"type"属性值为"button"的\<input>元素。
- **checked选中状态选择器**：$("#frmTest:checked")获取处于选中状态的复选框、单选按钮元素。
- **selected选中状态选择器**：$("#frmTest:selected")能获取\<select>下拉列表框中全部处于选中状态的\<option>选项元素。


-------------------------------------

## jQuery 操作DOM元素

- **attr()**：$("#nid").attr(aname[,avalue])获取id为nid的元素属性aname(并改为avalue)。
- **html()/text()**：$("#nid").html([newvalue])/text([newvalue])方法操作元素的内容(并设置为newvalue)。
- **操作元素的样式**：$("#nid").addClass()/css()。
- **移除属性和样式**：$("#nid").removeAttr(name)/removeClass(class)移去相关属性或样式。
- **使用append()方法向元素内追加内容**：$("#nid").append(content)向id为nid的元素中追加内容。
- **使用appendTo()方法向被选元素内插入内容**：$(content).appendTo($("#nid"))向id为nid的元素中追加内容。
- **使用before()和after()在元素前后插入内容**：$(selector).before(content)/after(content)可以在元素的前后插入内容。
- **使用clone()方法复制元素**：$(selector).clone()生成一个被选元素的副本。
- **替换内容**：$(selector).replaceWith(content)和$(content).replaceAll(selector)。
- **使用wrap()和wrapInner()方法包裹元素和内容**：$(selector).wrap(wrapper)和$(selector).wrapInner(wrapper)。
- **使用remove()和empty()方法删除元素**：remove()方法删除所选元素本身和子元素，可以通过添加过滤参数指定需要删除的某些元素，而empty()方法则只删除所选元素的子元素。
- **使用each()方法遍历元素**：

```
$(selector).each(function(index){

});
```


-------------------------------------

## jQuery 事件与应用

- **ready()**：页面加载时触发事件```$(document).ready(function(){})```。
- **bind()**：绑定元素的事件```$(selector).bind(event,[data] function(){})```。
- **hover()**：当鼠标移到所选元素上时，执行方法中的第一个函数，鼠标移出时，执行方法中的第二个函数```$(selector).hover(function(){},function(){});```。
- **toggle()**：绑定多个函数```$(selector).toggle(function(){},function(){},...);```。
- **unbind()**：移除元素绑定的事件```$(selector).unbind(event,function(){});```。
- **one()**：绑定元素的执行一次性事件```$(selector).one(event,[data],function(){});```。
- **trigger()**：手动触发指定的事件```$(selector).trigger(event)```。
- **live()**：绑定动态元素的事件，```$(selector).live(event,[data],fun)```。
- **focus/blur**：文本框的事件，可以作为上述应用的event参数。
- **change()**：下拉列表框的事件，可以作为上述应用的event参数。


-------------------------------------

## jQuery 动画特效

这些动画主要作用在元素上，因此有有前缀$(selector)。

- **show()/hide()**：显示和隐藏元素，callback是回调函数，```$(selector).hide/show(speed,[callback])```。
- **toggle()**：实现动画切换效果，```$(selector).toggle(speed,[callback])```。
- **slideUp()/slideDown()**：滑动效果，```$(selector).slideUp/slideDown(speed,[callback])```。
- **slideToggle()**：在slideUp()/slideDown()之间自动切换，```$(selector).slideToggle(speed,[callback])```。
- **fadeIn()/fadeOut()**：实现淡入淡出效果，```$(selector).fadeIn/fadeOut(speed,[callback])```。
- **fadeTo()**：设置淡入淡出效果的不透明度，```$(selector).fadeTo(speed,opacity,[callback])```。
- **animate()**：自定义简单的动画效果，params参数为制作动画效果的CSS属性名与值，```$(selector).animate({params},speed,[callback])```。
- **stop()**：停止当前所有动画效果，clearQueue和goToEnd表示是否停止正在执行的动画/是否完成正在执行的动画，默认为false，```$(selector).stop([clearQueue],[goToEnd])```。
- **delay()**：延时执行动画效果，```$(selector).delay(duration)```。


-------------------------------------

## jQuery 实现Ajax应用

在下面的Ajax应用中url为请求地址，data为请求时发送数据，callback参数为请求成功后执行的回调函数，请求返回数据作为callback的参数。

- **load()**：异步请求数据，```$(selector).load(url,[data],[callback])```。
- **getJSON()**：异步加载JSON格式数据，```jQuery.getJSON(url,[data],[callback])/$.getJSON(url,[data],[callback])```。
- **getScript()**：异步加载并执行js文件，```jQuery.getScript(url,[callback])/$.getScript(url,[callback])```。
- **get()**：以GET方式从服务器获取数据，```$.get(url,[callback])```。
- **post()**：以POST方式从服务器发送数据，```$.post(url,[data],[callback])```。
- **serialize()**：序列化表单元素值，```$(selector).serialize()```。
- **ajaxSetup()**：设置Ajax请求的一些全局性选项值，设置完成后，后面的Ajax请求将不需要再添加这些选项值，```jQuery.ajaxSetup([settings])/$.ajaxSetup([settings])```。
- **ajaxStart()/ajaxStop()**：Ajax请求发出前/完成后触发函数，```$(selector).ajaxStart(function())/$(selector).ajaxStop(function())```。
- **ajax()**：加载服务器数据，jQuery.ajax([settings])/$.ajax([settings])，如：

```
$.ajax({
        url: "http://www.baidu.com",
        data: { num: $("#txtNumber").val() },
        type: "post",
        success: function (data) {
            ...
        }
```

-------------------------------------

## jQuery 常用插件

### 表单验证插件validate

该插件自带包含必填、数字、URL在内容的验证规则，即时显示异常信息，此外，还允许自定义验证规则，插件调用方法如下：

```
$(form).validate({options})
```
其中：
- form参数表示表单元素名称
- options参数表示调用方法时的配置对象，

举例：

```
$("#frmV").validate({
    /*自定义验证规则*/
    rules: {
        email: {
          required: true,
          email: true
        }
    },
    /*错误提示位置*/
    errorPlacement: function (error, element) {
        error.appendTo(".tip");
	}
	});
```

### 表单插件——form

通过表单form插件，调用ajaxForm()方法，实现ajax方式向服务器提交表单数据，并通过方法中的options对象获取服务器返回数据，调用格式如下：

```
$(form). ajaxForm ({options})
```
其中：
- form参数表示表单元素名称
- options参数表示调用方法时的配置对象，

举例：

```
        $(function () {
            var options = {
                url: "http://www.baidu.com", 
                target: ".tip"
            }
            $("#frmV").ajaxForm(options);
        });

```


### 图片灯箱插件——lightBox

该插件可以用圆角的方式展示选择中的图片，使用按钮查看上下张图片，在加载图片时自带进度条，还能以自动播放的方式浏览图片，调用格式如下：

```
$(function () {
    $(".divPics a").lightBox({
        overlayBgColor: "#666",   //图片浏览时的背景色
        overlayOpacity: 0.5,      //背景色的透明度
        containerResizeSpeed: 600 //图片切换时的速度
    })
});
```		

### 图片放大镜插件——jqzoom

在调用jqzoom图片放大镜插件时，需要准备一大一小两张一样的图片，在页面中显示小图片，当鼠标在小图片中移动时，调用该插件的jqzoom()方法，显示与小图片相同的大图片区域，从而实现放大镜的效果。

```
$(function (){
     $("#jqzoom").jqzoom({  //绑定图片放大插件jqzoom
        zoomWidth: 123,     //小图片所选区域的宽
        zoomHeight: 123,    //小图片所选区域的高
        zoomType: 'reverse' //设置放大镜的类型
});
```

### cookie插件——cookie

使用cookie插件后，可以很方便地通过cookie对象保存、读取、删除用户的信息，还能通过cookie插件保存用户的浏览记录。
- 保存：$.cookie(key，value)。
- 读取：$.cookie(key)。
- 删除：$.cookie(key，null)。


### 提示插件——autocomplete

搜索插件的功能是通过插件的autocomplete()方法与文本框相绑定，当文本框输入字符时，绑定后的插件将返回与字符相近的字符串提示选择。

```
$(textbox).autocomplete(urlData,[options]);
```

- textbox参数为文本框元素名称。
- urlData为插件返回的相近字符串数据。
- 可选项参数options为调用插件方法时的配置对象。

举例：

```
    $("#txtSearch").autocomplete(arrUserName,{
        minChars: 0,                         //双击空白文本框时显示全部提示数据
        formatItem: function (data, i, total) {
            return "<I>" + data[0] + "</I>"; //改变匹配数据显示的格式
        },
        formatMatch: function (data, i, total) {
            return data[0];
        },
        formatResult: function (data) {
            return data[0];
        }
    }).result(SearchCallback); 
    function SearchCallback(event, data, formatted) {
        $(".tip").show().html("您的选择是：" + (!data ? "空" : formatted));
    }
```

### 自定义对象级插件——lifocuscolor插件

自定义的lifocuscolor插件可以在<ul>元素中，鼠标在表项<li>元素移动时，自定义其获取焦点时的背景色，即定义<li>元素选中时的背景色，调用格式为：

```
$(Id).focusColor(color)
```

### 自定义类级别插件—— twoaddresult

通过调用自定义插件twoaddresult中的不同方法，可以实现对两个数值进行相加和相减的运算，导入插件后，调用格式分别为：

```
$.addNum(p1,p2)/$.subNum(p1,p2)
```

其中p1和p2为任意数值。


-------------------------------------

## jQuery UI型插件

### 拖曳插件——draggable

拖曳插件draggable的功能是拖动被绑定的元素，当这个jQuery UI插件与元素绑定后，可以通过调用draggable()方法，实现各种拖曳元素的效果。

```
$(function () {
    $("#x").draggable({axis:"x"});
    $("#y").draggable({axis:"y"})
});

```

### 放置插件——droppable

droppable UI插件将拖曳后的任意元素放置在指定区域中，类似购物车效果。

```
$("#divtest").children(':first').droppable({
    drop:function(){
        sum--;
        $(".cart").removeClass("focus");
        $("#tip").html("还没有产品");
        $(".title span").html(sum);
    }
});
```
drop函数为当被接收的拖曳元素完全进入接收元素的容器时，所触发的函数。

### 拖曳排序插件——sortable

拖曳排序插件的功能是将序列元素（例如<option>、<li>）按任意位置进行拖曳从而形成一个新的元素序列，实现拖曳排序的功能。

```
$(function () {
    $("ul").sortable({
        delay:2,     // 延时2秒
        opacity:0.35 //透明度
    })
});
```

### 面板折叠插件——accordion

面板折叠插件可以实现页面中指定区域类似“手风琴”的折叠效果，即点击标题时展开内容，再点另一标题时，关闭已展开的内容。
accordion下有多个标题，每个标题下还有内容。


```
    $(function () {
        $("#accordion").accordion();
    });
```
### 选项卡插件——tabs

使用选项卡插件可以将\<ul>中的\<li>选项定义为选项标题，在标题中，再使用\<a>元素的“href”属性设置选项标题对应的内容。

```
<div id="tabs">
    <ul>
        <li><a href="#tabs-1">最爱吃的水果</a></li>
        <li><a href="#tabs-2">最喜欢的运动</a></li>
    </ul>
    <div id="tabs-1">
        <p>橘子</p>
    </div>
    <div id="tabs-2">
        <p>足球</p>
    </div>
</div>

$(function () {
   $("#tabs").tabs ({
        //设置各选项卡在切换时的动画效果
        fx: { opacity: "toggle", height: "toggle" },
        event: "mousemove" //通过移动鼠标事件切换选项卡
    })
});
```

### 对话框插件——dialog

对话框插件可以用动画的效果弹出多种类型的对话框，实现JavaScript代码中alert()和confirm()函数的功能。

```
$(function (){
    $("#btnDelete").bind("click", function () {  //询问按钮事件
        if ($("#spnName").html() != null) {      //如果对象不为空
            sys_Confirm("您真的要删除该条记录吗？");
            return false;
        }
    });
});
function sys_Confirm(content) { //弹出询问信息窗口
   $("#dialog-modal").dialog ({
        height: 140,
        modal: true,
        title: '系统提示',
        hide: 'slide',
        buttons: {
            '确定': function () {
                $("#spnName").remove();
                $(this).dialog("close");
            },
            '取消': function () {
                $(this).dialog("close");
            }
        },
        open: function (event, ui) {
            $(this).html("");
            $(this).append("<p>" + content + "</p>");
        }
    });
}
```

### 菜单工具插件——menu

菜单工具插件可以通过\<ul>创建多级内联或弹出式菜单，支持通过键盘方向键控制菜单滑动，允许为菜单的各个选项添加图标。

```
<ul id="menu">
    <li><a href="#">小明一中</a>
        <ul>
            <li><a href="#">高中部</a>
                <ul>
                    <li><a href="#">高一(1)班</a></li>
                        <ul>
                            <li><a href="#">小胡</a></li>
                            <li><a href="#">小李</a></li>
                        </ul>
                    </li>
                </ul>
            </li>
        </ul>
    </li>
</ul>
        
<script type="text/javascript">
    $(function () {
        $("#menu").menu();
});

```

### 微调按钮插件——spinner

微调按钮插件不仅能在文本框中直接输入数值，还可以通过点击输入框右侧的上下按钮修改输入框的值，支持键盘的上下方向键改变输入值。

```
$(function () {
//定义变量
var intR = 0, intG = 0, intB = 0, strColor;
$("input").spinner({
    //初始化插件
    max: 10,
    min: 0,
    //设置微调按钮递增/递减事件
    spin: function (event, ui) {
        if (ui.value == 8)
            spnPrev.style.backgroundColor = "red";
        else
            spnPrev.style.backgroundColor = "green";
    },
    //设置微调按钮值改变事件
    change: function (event, ui) {
        var intTmp = $(this).spinner("value");
        if (intTmp < 0) $(this).spinner("value", 0);
        if (intTmp > 10) $(this).spinner("value", 10);
        if (intTmp == 8)
            spnPrev.style.backgroundColor = "red";
        else
            spnPrev.style.backgroundColor = "green";
    }
});
```

### 工具提示插件——tooltip

工具提示插件可以定制元素的提示外观，提示内容支持变量、Ajax远程获取，还可以自定义提示内容显示的位置。

```
$(function(){
    $("#name").tooltip({
        show: {
            effect: "slideDown",
            delay: 350
        },
        hide: {
            effect: "explode",
            delay: 350
        },
        position: {
            my: "left top",
            at: "left bottom"
        }
    });
});
```

-------------------------------------

## jQuery 工具类函数


### 获取浏览器的名称与版本信息

$.browser对象可以获取浏览器的名称和版本信息。

- $.browser.chrome为true，表示当前为Chrome浏览器。
- $.browser.mozilla为true，表示当前为火狐浏览器。
- $.browser.version方式获取浏览器版本信息。

### 检测浏览器是否属于W3C盒子模型

浏览器的盒子模型分为两类，一类为标准的w3c盒子模型，另一类为IE盒子模型，两者区别为在Width和Height这两个属性值中是否包含padding和border的值，w3c盒子模型不包含，IE盒子模型则包含，而在jQuery 中，可以通过$.support.boxModel对象返回的值，检测浏览器是否属于标准的w3c盒子模型。

### 检测对象是否为空

**$.isEmptyObject(obj)**的工具函数，检测一个对象的内容是否为空，如果为空，则该函数返回true，否则，返回false值。

### 检测对象是否为原始对象
**$.isPlainObject(obj)**的工具函数，能检测对象是否为通过{}或new Object()关键字创建的原始对象，如果是，返回true，否则，返回false值。

### 检测两个节点的包含关系

**$.contains (container, contained)**的工具函数，能检测在一个DOM节点中是否包含另外一个DOM节点，如果包含，返回true，否则，返回false值。

### 字符串操作函数

**$.trim(str)**的工具函数，能删除字符串中左右两边的空格符，但该函数不能删除字符串中间的空格。

### URL操作函数

**$. param(obj)**的工具函数，能使对象或数组按照key/value格式进行序列化编码，该编码后的值常用于向服务端发送URL请求。

### $.extend()扩展工具函数和对象

#### $.extend()扩展工具函数

**$.extend({options})**的工具函数，可以对原有的工具函数进行扩展，自定义类级别的jQuery插件。

```
(function ($) $.extend ({
    "MinNum": function (p1, p2) {
        return (p1 > p2) ? p2 : p1;
    }
    });
})(jQuery);
```
然后可以直接$.MinNum调用该函数。

#### $.extend()扩展对象

**$.extend(obj1,obj2,…objN)**用于在扩展对象，两个对象将进行合并，当存在相同属性名时，后者将覆盖前者。














