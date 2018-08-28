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

内容区域、电影区域、读书区域、音乐区域、小组区域、同城区域中的右边区域

```
.right
{
    width: 266px;
    position: absolute;
    right: 0px;
    top: 0px;
}
```

广告区域的样式：

```
.hd-ad
{
    width: 950px;
    height: 90px;
    margin: 0 auto;
}
.hd-ad img
{
    width: 950px;
    height: 90px;
}
```

电影区域、读书区域、音乐区域、小组区域、同城区域的左侧区域

```
.left
{
    width: 121px; /*根据不同的区域设置不同的高度*/
    position: absolute;
    left: 0px;
    right: 0px;
}
.left .left-title
{
    font-size: 24px;
    color: #2297cc;
}
.left .left-title:hover
{
    color: #fff;
}
.left .left-up
{
    margin-top: 10px;
}
.left .left-up li
{
    font-size: 14px;
    line-height: 24px;
}
.left .left-down
{
    margin-top: 28px;
}
.left .left-down li
{
    width: 70px;
    height: 93px;
}
.left .left-down li a.left-down-pic
{
    border-radius: 6px;
    box-shadow: 3px 3px 3px #999;
    display: block;
    width: 50px;
    height: 50px;
}
.left .left-down li a.left-down-des
{
    display: block;
    margin-top: 10px;
}
```

电影区域、读书区域、音乐区域、小组区域、同城区域的中间区

```
.mid
{
    width: 530px;
    position: absolute;
    left: 121px;
    top: 0px;
}

.mid li
{
    width: 127px;
    text-align: center;//每一个<li>标签居中显示
    float: left;   //让每一个<li>标签左浮动
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

在低版本的IE6浏览器中并不支持placeholder属性，可以换成text属性，并且需要设置line-height(行高)的值等于文本框的高度值。也就是line-height:30px。

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

如果小图标在大图中的坐标是(10,20)，那么将背景图片向左移动10px(-10px),向上移动20px(-20px)就可以抵消小图标在大图的位置。

`background-position: -10px -20px;`

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

### 5.1、内容区域左边区域

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

### 5.2、内容区域中间区域

使用`<ul><li></li></li></ul>`标签

`<h2>`标签按照正常字体显示：font-weight:normal;

### 5.3、内容区域右边区域

通过观察可以发现内容的右边区域和其他区域的右边部分布局是相似的，所以可以放到公共样式中(.right)。

```
#hd-con .con-right li
{
    /*margin-top: 17px;*/
    height:70px; /*固定<li>标签的高度，解决不同浏览器之间的兼容性问题*/
}
```

设置为height:70px;代替设置它的margin-top为17px，是为了固定`<li>`标签的高度，解决不同浏览器之间的兼容性问题，

### 5.4、hack技术

CSS hack技术就是利用各种方法解决浏览器兼容性的问题，用hack技术，就说明代码写的不规范，我们应该从根本上杜绝兼容性的问题，而不是亡羊补牢。

### 5.5、小广告区域

设置广告区域时，必须设置它的父元素con-right的高度，不然当设置它的子元素绝对定位时会达不到预期的效果。

当制作一个块(`<div>`标签)的小细节时，最好使用定位的方式，而不是float浮动的方式。

## 6、广告区域的制作

为什么要用新窗口打开广告页面？`(__)`==>方便用户操作

广告区域的制作放在公共样式中。

## 7、电影区域的制作

大块的区域也可以position定位的方式，但是正确的做法应该使用margin设置大块区域的距离。

```
#hd-movie-background
{
    height: 631px;
    width: 100%;
    background-color: #f7f7f7;
    margin-top: 44px;
    padding-top: 40px; //内边距设置为40px
}
```

因为如果内容区域或者其他区域出现错误不能显示的话，电影区域可以自动顶上去，否则使用定位的话，其他区域出现错误，浏览器将会留出大量的空白区域。(脱离了文档流)

也就是说对于大块区域不能用position定位，需要使用margin外边距来设置一些属性值从而达到效果。

```
#hd-movie-background #hd-movie{
margin: 0 auto;
margin-top: 40px;
}
```


### 7.1、电影区域左边区域

电影区域、读书区域、音乐区域、小组区域、同城区域的左侧区域是类似的，应该放在公共样式中。

利用CSS精灵技术设置不同区域的图片

```
#hd-movie-background #hd-movie .movie-pic
{
    background: url(images/app_icons_50_10.jpg) no-repeat;
    backfround-position:-350px 0px;
}
```

设置圆角：border-radius
设置投影效果：box-shadow
IE6浏览器并不支持CSS3的属性。

### 7.2、电影区域中间区域

电影区域、读书区域、音乐区域、小组区域、同城区域的中间区域也是类似的，应该放在公共样式中。

文字居中显示：text-align:center;

评分的效果(也就是有几颗星星)，利用精灵技术。

```
 background: url(images/xingxing.png) no-repeat;
 background-position:20px 0;
```

当采用精灵技术时：当xxPX大于0时，表示的是移动xx的距离(left),当小于0时表示切图片。

因为`<img>`标签是包在`<a>`标签之中的，`<a>`标签存在默认样式，鼠标放到`<a>`标签，背景颜色就会改变，现在导致鼠标放上去，图片的背景颜色也会改变。

星星图片的高度设置为为16px，然后超出的部分隐藏。(overflow:hidden)

这个`<li>`标签的宽度本来是127px，因为设置了padding-left为80px，所以宽度应该改为47px。

文字上下居中：设置行高。(line-height:23px;)

### 7.3、电影区域右边区域

公共样式地合理使用

确定合适的`<li>`标签的宽度

左浮动：`float:left;`

需要明确的设置`<ul>`标签的高度，不然近期热门这个`<h2>`标签将会跑到上面去。

```
#hd-movie-background #hd-movie .move-right-ul
{
    margin-top: 12px;
    height: 150px;
}
```

将近期热门的宽度设置的和它的父元素的宽度一样，它下面的元素的布局才不会乱。

```
#hd-movie-background #hd-movie .movie-title
{
    margin-top: 20px;
    width: 266px;
}
```

![ ](http://images.cnblogs.com/cnblogs_com/cliy-10/1270920/o_5.png)

每个`<li>`标签都有一个下边框

```
border-bottom: 1px solid #eaeaea;
```

## 8、读书区域的制作

### 8.1、读书区域左边区域

左侧区域和电影区域的左侧类似

但是色调整体与电影区域的色调不同

通过观察可以发现，读书区域的整体色调是相同的，所以在读书区域可以设置成通用样式。

```
#hd-book a
{
    color: #614e3c;
}
#hd-book a:hover
{
    color: #fff;
}
```

公共区域就直接复制粘贴，然后稍作修改即可。

new小图片的制作：

```
#hd-book .hd-book-new img
{
    position: absolute;
    left: 28px;
    top: 69px;
}
```

精灵图片的制作

```
#hd-book .book-read
{
    background: url(images/app_icons_50_10.jpg) no-repeat;
    background-position: 0px 0px;
}
#hd-book .book-write
{
    background: url(images/app_icons_50_10.jpg) no-repeat;
     background-position: -399px 0px;
}
#hd-book .book-goshoping
{
    background :url(images/app_icons_50_10.jpg) -200px 0 no-repeat;
     background-position: -200px 0px;
}
```

### 8.2、读书区域中间区域

合理使用公共样式，不同的地方单独修改即可。

注意绝对定位和相对定位的区别，以及绝对定位和相对定位的混合使用。

`<li>`标签的左浮动，float:left;(在公共样式中)

### 8.3、读书区域右边区域

同电影区域相同，每个`<li>`标签都有一个下边框

```
border-bottom: 1px solid #eaeaea;
```

元素的内边距(padding)和外边距(margin)的区别


## 9、音乐区域的制作

## 10、小组区域的制作

## 11、同城区域的制作

## 12、网页底部的制作

