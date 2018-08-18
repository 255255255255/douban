## 1、分析整体布局

### 1.1、确定通用的样式：

页面上许多`<a>`标签，当鼠标放上去的时候，背景会变成蓝色，字体会变成白色。


```
//公共样式
a
{
    color: #3377aa;
}
a:hover
{
    background-color: #3377AA;
    color: #fff;
}
```

`<h2>`标签样式

```
h2.title
{
    font-size: 15px;
    font-family: Arial;
    color: #007722;
}
h2.title span
{
    color: #666666;
    font-size: 12px;
}
```

内容区域中的右边区域

```
.right
{
    width: 266px;
    position: absolute;
    right: 0px;
    top: 0px;
}
```
所用到的工具：火狐浏览器的下载小图片工具，或者自己切片。

![ ](http://images.cnblogs.com/cnblogs_com/cliy-10/1270920/o_1.png)

![ ](http://images.cnblogs.com/cnblogs_com/cliy-10/1270920/o_2.png)

在开始制作网页之前，一定要先记着将原设计图保存下来，合理的利用PS，度量各个元素之间的距离。

### 1.2、确定设计图的宽度

找一对较为合适的基准线来量宽度，最好是以图片的某一边作为基准线。

宽950px

## 2、清除默认设置

```
清除默认边距
*
{
    margin: 0px;
    padding: 0px;
}
//清除a标签的下划线
a
{
	text-decoration: none;
}
//清除默认边框
img,input
{
	border:none;
	border:1px solid none;
	//针对IE6，在IE6中即使设置border:none还是会有边线，需要在具体的设置为none

}
li
{
    list-style: none;
}
```

推荐使用`normalize css`库函数来清除默认样式。

## 3、顶部区域的制作：

### 3.1、logo的制作

logo图片的宽度为154px，高度为30px

logo紧贴着左边的基准线，所以有个盒子限制着它，不让它跑出最左侧。

盒子模型的理解：所有元素都包在盒子里面，然后摆弄该盒子，使盒子的布局更加合理。

### 3.2、搜索区域

搜索区域的整体宽度为275px，高度为30px,因为设置了`padding-left:10px`，所以设置搜索区域应为275px-10px=265px。

placeholder(存在兼容性问题)

在低版本的IE6浏览器中并不支持placeholder属性，可以换成text属性，并且需要设置line-height(行高)的值等于文本框的高度值。也就是line-height:30p。

还需要包含一个搜索样式的小图片，小图片的宽度为13px、高度也为13px。

padding：设置元素的内边距

margin：设置元素的外边距

### 3.3、图片精灵

导航条用`<ul><li></li></ul>`标签比较合适

精灵图片的制作：

```
#hd-header ul li a.header-book
{
    background: url(images/logo2.png) no-repeat;
    background-position: 0px 0px;
}

#hd-header ul li a.header-movie
{
    background: url(images/logo2.png) no-repeat;
     background-position: -60px 0px;
}
#hd-header ul li a.header-music
{
    background: url(images/logo2.png) no-repeat;
    background-position: -120px 0px;
}
#hd-header ul li a.header-xiaozu
{
    background: url(images/logo2.png) no-repeat;
    background-position: -180px 0px;
}
#hd-header ul li a.header-city
{
    background: url(images/logo2.png) no-repeat;
    background-position: -240px 0px;
}
#hd-header ul li a.header-fm
{
    background: url(images/logo2.png) no-repeat;
    background-position: -300px 0px;
}
#hd-header ul li a.header-shijian
{
    background: url(images/logo2.png) no-repeat;
    background-position: -359px 0px;
}
#hd-header ul li a.header-shiji
{
    background: url(images/logo2.png) no-repeat;
    background-position: -420px 0px
}
```

如果小图标在大图中的坐标是(10,20)，那么将背景图片向左移动10px,向上移动20px就可以抵消小图标在大图的位置。

### 3.4、注意

* 1.命名的规范性

* 2.居中 `margin: 0 auto`(在标准浏览器才会显示，在IE浏览器中不会显示)

* 3、在position定位和float漂移之间，应该尽量选择position，这样会减少许多浏览器的兼容性问题。

* 4、父元素相对定位(relative)、子元素绝对定位(absolute)，这样不会脱离文档流。

* 5、`<input>`标签需要包裹在`<form>`标签中。

* 6、如果能尽量使用内边距就尽量使用内边距(padding)，而不是选择外边距(margin)，这样可以减少浏览器之间的兼容性问题。

* 7、css的选择器：(继承父级)

`#hd-header .header-search`比直接`.header-search`的形式的选择器有什么好处？

为什么要加上父元素，不加上也明明是可以选择到元素，这是多此一举的做法吗？

不是，这样做有着诸多的优点：权重不一样、继承属性、方便查找等。

* 8、使用绝对定位，如果屏幕分辨率变大或者变小，不会对网页的结构有影响。

## 4、注册区域的制作

### 4.1、宽度为100%的背景区域

### 4.2、加入我们

整体区域宽度为120px，高度为37px。

设置圆角：border-radius:2px;(IE浏览器不支持该属性)

文本左右对齐：text-align:center

设置行高：line-height:37px

伪类:hover，鼠标放上去之后的变化。

### 4.3、发现更多生活

`<p>`元素

### 4.4、登录区域

`<input>`标签需要包裹在`<form>`标签中。

`<input>`标签的宽度为158px，高度为32px。

父元素相对定位，子元素绝对定位。

display:block;将`<a>`元素转化为块级标签。

在设置文字居中显示时，必须要先设置它的行高，再设置它的文本左右居中显示。

```
line-height: 37px;
text-align: center; /* 左右对齐*/
```

![ ](https://www.cnblogs.com/images/cnblogs_com/cliy-10/1270920/o_3.png)

如果顺序颠倒，文本内容不会居中

```
text-align: center; /* 左右对齐*/
line-height: 37px;

```

![ ](http://images.cnblogs.com/cnblogs_com/cliy-10/1270920/o_4.png)

### 4.4、记住我

在这里给`<p>`元素设置宽度为82px，高度为17px是为了解决不同浏览器之间的兼容性问题。

`<P>`元素中包着`<input>`元素(复选框)

重新设置复选框的大小为`13px*13px`，而不是采用复选框的默认大小。

伪类hover事件

父元素绝对定位，子元素绝对定位。

## 5、内容区域的制作

语义化的标签`<h2>`标签，虽然也可以使用`<p>`标签然后调整字体的大小，但还是尽量使用语义化标签

内容区域分为左边、中间和右边三块区域，都是用position定位来固定位置。

### 5.1、左边区域

```
.con-left{
    position :absolute;
    margin-left: 0px;
    margin-top: 0px;
}
```

利用浮动float:left将图片排列整齐，然后调整一下margin-top和margin-left，调整到合适的间距。

```
li{
  float: left;
  margin-left: 10px;
  margin-top: 16px;
}
```

### 5.2、中间区域

使用`<ul><li></li></li></ul>`标签

`<h2>`标签按照正常字体显示：font-weight:normal;

### 5.3、右边区域

通过观察可以发现内容的右边区域和其他区域的右边部分布局是相似的，所以可以放到公共样式中(.right)。

### 5.4、hack技术

CSS hack技术就是利用各种方法解决浏览器兼容性的问题，用hack技术，就说明代码写的不规范，我们应该从根本上杜绝兼容性的问题，而不是亡羊补牢。

### 5.5、广告区域

设置广告区域时，必须设置它的父元素con-right的高度，不然当设置它的子元素绝对定位时会达不到预期的效果。

当制作一个块(`<div>`标签)的小细节时，最好使用定位的方式，而不是float浮动的方式。

## 6、广告区域的制作

为什么要用新窗口打开广告页面？`(__)`==>方便用户操作

## 7、电影区域的制作

## 8、读书区域的制作

## 9、音乐区域的制作

## 10、小组区域的制作

## 11、同城区域的制作

## 12、网页底部的制作

