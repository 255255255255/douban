# douban

1、首先分析整体布局

1.1、确定通用的样式：

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

1.2、确定设计图的宽度

找一对较为合适的基准线来量宽度，最好是以图片的某一边作为基准线。

宽950px

2、清除默认设置

```
清默认边距
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
```

推荐使用normalize css库函数来清除默认样式。

3、头部的制作：

3.1、logo的制作

logo紧贴着左边的基准线，所以有个盒子限制着它，不让它跑出最左侧。

盒子模型的理解：所有元素都包在盒子里面，然后摆弄该盒子，使盒子的布局更加合理。

命名的规范性

居中 `margin: 0 auto`


在position定位和float漂移之间，应该尽量选择position，这样会减少许多浏览器的兼容性问题。

父级相对定位(relative)、子级绝对定位(absolute)
