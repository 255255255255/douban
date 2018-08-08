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

## 3、头部的制作：

### 3.1、logo的制作

logo图片的宽度为154px，高度为30px

logo紧贴着左边的基准线，所以有个盒子限制着它，不让它跑出最左侧。

盒子模型的理解：所有元素都包在盒子里面，然后摆弄该盒子，使盒子的布局更加合理。

### 3.2.搜索区域

搜索区域的整体宽度为275px，高度为30px,因为设置了`padding-left:10px`，所以设置搜索区域应为275px-10px=265px。

placeholder

还需要包含一个搜索样式的小图片，小图片的宽度为13px、高度也为13px。

padding：设置元素的内边距

margin：设置元素的外边距

### 3.3.图片精灵

导航条用`<ul><li></li></ul>`标签比较合适

精灵图片的制作：

```
#hd-header ul li a.header-book
{
    background: url(images/logo2.png) 0px 0px no-repeat;
}

#hd-header ul li a.header-movie
{
    background: url(images/logo2.png) -60px 0px no-repeat; 
}
#hd-header ul li a.header-music
{
    background: url(images/logo2.png) -120px 0px no-repeat;
}
#hd-header ul li a.header-xiaozu
{
    background: url(images/logo2.png) -180px 0px no-repeat;
}
#hd-header ul li a.header-city
{
    background: url(images/logo2.png) -240px 0px no-repeat;
}
#hd-header ul li a.header-fm
{
    background: url(images/logo2.png) -300px 0px no-repeat;
}
#hd-header ul li a.header-shijian
{
    background: url(images/logo2.png) -359px 0px no-repeat;
}
#hd-header ul li a.header-shiji
{
    background: url(images/logo2.png) -420px 0px no-repeat;
}
```

### 3.4、注意

* 1.命名的规范性

* 2.居中 `margin: 0 auto`

在position定位和float漂移之间，应该尽量选择position，这样会减少许多浏览器的兼容性问题。

父元素相对定位(relative)、子元素绝对定位(absolute)，这样不会脱离文档流。

css的选择器：(继承父级)

`#hd-header .header-search`比直接`.header-search`的形式的选择器有什么好处？

为什么要加上父元素，不加上也明明是可以选择到元素，这是多此一举的做法吗？

不是，这样做有着诸多的优点：权重不一样、继承属性、方便查找等

### 4.
