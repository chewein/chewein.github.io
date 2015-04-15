---
layout: post
author: Chewein
title: CSS盒子的相对定位于绝对定位
category: CSS 
tag: [CSS,绝对,相对] 
---

之前看了CSS的布局与定位，看的云里雾里的，不是太理解，这里做实验总结一下。

为了便于理解，这里引用两个空间：

- 占位空间：元素在文档流中所占据的空间。 
- 物理空间：元素本身所占据的空间。 

另外设置了absolute与relative定位的元素对其他元素影响主要包括：

- 父辈元素。
- 下一个兄弟元素。

后面的实验均以下面的布局为基础，对它们只是设置了颜色，没有设置任何布局，以标准文档流从上下到下布局。

```
<div id="box">
    <div id="box1">box1 </div>
    <div id="box2">box2 </div>
    <div id="box3">box3 </div>
</div>
```

![](/public/img/tech/2015_04_15_CSS_absolute_relative/1.png)


## 相对定位

使用相对定位的盒子的位置常以标准流的排版方式为基础，然后使盒子相对于它在原本的标准位置偏移指定的距离。**相对定位的盒子仍在标准流中，它后面的盒子仍以标准流方式对待它。**

### 用left/top/bottom/right定位

对box2施加下述相对定位：

```
#box2{
	position:relative;
	top:-20px; 
	left:80px;
}
```

![](/public/img/tech/2015_04_15_CSS_absolute_relative/2.png)


空间变化：

- 占位空间任在且不变。
- 物理空间相对占位空间有一个偏移。

影响：

- 父辈元素位置无影响。
- 下一个兄弟元素位置无影响。

但要注意的是：**使用相对定位的元素会覆盖与其重叠的元素**。

### 用margin-left/top/bottom/right定位

对box2施加下述相对定位：

```
#box2{
	position:relative;
	margin-bottom:40px; 
	margin-left:40px;
}
```
![](/public/img/tech/2015_04_15_CSS_absolute_relative/3.png)

这种情况可以这里理解：

1. 首先是box2盒子大小发生变化，margin-bottom与margin-left各增加了40px，导致box3向下移动40px；
2. 然后box2施加了一个偏移为0的relative定位。


## 绝对定位

绝对定位有以下特点：

- 盒子的位置以与它最靠近的已定位好的父辈元素为基准进行偏移，这里已定位好是指设置了relative/absolute/float等属性，如果其父辈/祖父辈均没有设置定位属性，则以浏览器窗口为基准。
- 如果没有设置宽度，那么元素的宽度随内容变化而变化。
- 绝对定位的盒子从标准流中脱离，这意味着**它们对其后的兄弟盒子的定位没有影响，其它的盒子就好像这个盒子不存在一样。**

后面的实验均以下面的布局为基础，对它们只是设置了颜色，没有设置任何布局，以标准文档流从上下到下布局。

```
<div id="box">
    <div id="box1">box1 </div>
	<div id="box2-warp">
        <div id="box2">box2 </div>
	</div>
    <div id="box3">box3 </div>
</div
```

![](/public/img/tech/2015_04_15_CSS_absolute_relative/4.png)


### 浏览器窗口为基准

对box2施加下述绝对定位：

```
#box2{
	position:absolute;
	top:20px; 
	left:40px;
}
```
![](/public/img/tech/2015_04_15_CSS_absolute_relative/5.png)

由于只对box2施加绝对定位，没有对其父辈box-warp，box，body施加定位设置，因此box2以浏览器窗口为基准进行偏移。

### 父辈为基准

在上面代码基础上，对box2父辈box-warp施加下述代码：

```
#box2-warp{
	position:relative
}
```
![](/public/img/tech/2015_04_15_CSS_absolute_relative/6.png)



### 固定定位

当position的属性值为fixed，即固定定位。它与绝对定位有些类似，区别主要在于定位的基准不是祖先，而是浏览器窗口或其它显示设备窗口。也就是当访问者拖动浏览器的窗口滚动条时，固定定位的元素相对于浏览器窗口的位置保持不变。


