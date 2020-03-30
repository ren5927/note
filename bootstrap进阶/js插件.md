## 导入JavaScript插件

Bootstrap除了包含丰富的Web组件之外，如前面介绍的下拉菜单、按钮组、导航、分页等。他还包括一些JavaScript的插件。

Bootstrap的JavaScript插件可以单独导入到页面中，也可以一次性导入到页面中。因为在Bootstrap中的JavaScript插件都是依赖于jQuery库，所以不论是单独导入还一次性导入之前必须先导入jQuery库。

**一次性导入：**

Bootstrap提供了一个单一的文件，这个文件包含了Bootstrap的所有JavaScript插件，即bootstrap.js（压缩版本：bootstrap.min.js）。

具体使用如下（或见右侧代码编辑器28-29行）：

```
<!—导入jQuery版本库，因为Bootstrap的JavaScript插件依赖于jQuery -->
<script src="http://libs.baidu.com/jquery/1.9.0/jquery.js"></script>
<!—- 一次性导入所有Bootstrap的JavaScript插件（压缩版本） -->
<script src="js/bootstrap.min.js"></script>
```

特别声明：jQuery版本库也可以加载你本地的jQuery版本。

**单独导入：**

为方便单独导入特效文件，Bootstrap V3.2中提供了12种JavaScript插件，他们分别是：

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **动画过渡（Transitions）:**对应的插件文件“transition.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **模态弹窗（Modal）:**对应的插件文件“modal.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **下拉菜单（Dropdown）：**对应的插件文件“dropdown.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **滚动侦测（Scrollspy）：**对应的插件文件“scrollspy.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **选项卡（Tab）：**对应的插件文件“tab.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **提示框（Tooltips）：**对应的插件文件“tooltop.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **弹出框（Popover）：**对应的插件文件“popover.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **警告框（Alert）：**对应的插件文件“alert.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **按钮（Buttons）：**对应的插件文件“button.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **折叠/手风琴（Collapse）：**对应的插件文件“collapse.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **图片轮播Carousel：**对应的插件文件“carousel.js”

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png)** **自动定位浮标Affix：**对应的插件文件“affix.js”

上述单独插件的下载可到github去下载（https://github.com/twbs/bootstrap）。

[![img](http://img.mukewang.com/544f63040001519f10430466.jpg)](http://img.mukewang.com/544f63040001519f10430466.jpg)

下载后可查看js文件夹，如下图：

[![img](http://img.mukewang.com/544f639a0001116608640668.jpg)](http://img.mukewang.com/544f639a0001116608640668.jpg)

接下来依次向大家介绍这些插件如何使用，至于插件源码分析，在本系列不做过多的阐述，具体源码可以阅读各插件的代码。

**注意：**在后面的例子中我们为了方便都采用**一**次性导入的方法，即引入“bootstrap.min.js”文件（小伙伴们可以在自己的项目中跟据需要选择单独导入还是一次性导入）。



## 下拉菜单--属性声明式方法（一）

**属性声明式方法：**

一般下拉菜单都是出现在导航条中，比如下图的一个效果，用户点击带有三角形的菜单项都会弹出下拉菜单项：

[![img](http://img.mukewang.com/541a81cc0001caab06720153.jpg)](http://img.mukewang.com/541a81cc0001caab06720153.jpg)

```
<div class="navbar navbar-default" id="navmenu">
    <a href="##" class="navbar-brand">W3cplus</a>
    <ul class="nav navbar-nav">
        <li class="dropdown">
            <a href="##" data-toggle="dropdown" class="dropdown-toggle" role="button" id="tutorial">教程<b class="caret"></b></a>
            <ul class="dropdown-menu" role="menu" aria-labelledby="tutorial">
                <li role="presentation"><a href="##">CSS3</a></li>
                <li role="presentation"><a href="##">HTML5</a></li>
                <li role="presentation"><a href="##">Sass</a></li>
            </ul>
        </li>
        <li><a href="##">前端论坛</a></li>
        <li><a href="##">关于我们</a></li>
    </ul>
</div>
```

除了这种导航条之外，在胶囊式导航中也具有下拉菜单，其结构如：

```
<ul class="nav nav-pills">
    <li class="dropdown">
        <a href="##" data-toggle="dropdown" class="dropdown-toggle" role="button" id="tutorial">教程<b class="caret"></b></a>
        <ul class="dropdown-menu" role="menu" aria-labelledby="tutorial">
            <li role="presentation"><a href="##">CSS3</a></li>
            <li role="presentation"><a href="##">HTML5</a></li>
            <li role="presentation"><a href="##">Sass</a></li>
        </ul>
    </li>
    <li class="active"><a href="##">前端论坛</a></li>
    <li><a href="##">关于我们</a></li>
</ul>
```

运行效果如下：

[![img](http://img.mukewang.com/541a82ac0001a25706600253.jpg)](http://img.mukewang.com/541a82ac0001a25706600253.jpg)

## 下拉菜单--属性声明式方法（二)

从上一节的两个示例，我们可以知道，用户只需要点击有向下三角形的按钮链接或者直接点击三角形就会弹出下拉菜单。实现这个效果，都是依赖于HTML相关元素自定义的属性完成。所以在编写HTML结构的时候必须满足下面的规则：

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 按照制作菜单的结构编写结构，如前面“下拉菜单”一节(5-21)所介绍

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 被点击的菜单项链接或按钮需要添加自定义属性 data-toggle="dropdown"

```
<div class="navbar navbar-default" id="navmenu">
    <a href="##" class="navbar-brand">W3cplus</a>
    <ul class="nav navbar-nav">
        <li class="dropdown">
            <a href="##" data-toggle="dropdown" class="dropdown-toggle" role="button" id="tutorial">教程<b class="caret"></b></a>
            <ul class="dropdown-menu" role="menu" aria-labelledby="tutorial">
                <li role="presentation"><a href="##">CSS3</a></li>
                 ...
            </ul>
        </li>
        <li><a href="##">前端论坛</a></li>
        <li><a href="##">关于我们</a></li>
    </ul>
</div>
```

**实现下拉菜单原理：**

Dropdown插件加载时，对所有带 有“data-toggle=dropdown”样式的元素绑定了事件，用户单击带有“data-toggle=dropdown”样式的链接或按钮时， 会触发JavaScript事件代码。当用户点击带有“data-toggle=dropdown”样式的链接或按钮时，下拉菜单的父容器（上面的示例是 “<li class="dropdown">”）会添加一个open类名，此时下拉菜单显示；再次单击时，JavaScript会删除刚添加的open类 名，此时下拉菜单将隐藏。

简单的说，要制作下拉菜单，其结构基本如下：

```
<div class="dropdown">
    <a data-toggle="dropdown" href="#">下拉菜单触发器</a>
    <ul class="dropdown-menu" role="menu" aria-labelledby="dLabel"> ... </ul>
</div>
```

如果触发下拉菜单的元素是一个链接元素，为了避免点击链接，页面跳到顶部，可以使用data-target="#"来替代href="#"：

```
<div class="dropdown">
    <a id="dLabel" role="button" data-toggle="dropdown" data-target="#" href="/page.html"> Dropdown <span class="caret"></span></a>
    <ul class="dropdown-menu" role="menu" aria-labelledby="dLabel"> ... </ul>
</div>


<h3>示例1</h3>
<div class="navbar navbar-default" id="navmenu">
    <a href="##" class="navbar-brand">W3cplus</a>
    <ul class="nav navbar-nav">
        <li class="dropdown">
			<a href="##" data-toggle="dropdown" class="dropdown-toggle" role="button" id="tutorial">教程<b class="caret"></b></a>
			<ul class="dropdown-menu" role="menu" aria-labelledby="tutorial">
				<li role="presentation"><a href="##">CSS3</a></li>
				<li role="presentation"><a href="##">HTML5</a></li>
				<li role="presentation"><a href="##">Sass</a></li>
			</ul>
		</li>
		<li><a href="##">前端论坛</a></li>
		<li><a href="##">关于我们</a></li>
	</ul>
</div>

<!--代码任务部分-->
<ul class="nav nav-pills">
    <li><a href="##">教程</a></li>
	<li class="active"><a href="##">前端论坛</a></li>
	<li><a href="##">关于我们</a></li>
</ul>
```

## 下拉菜单--JavaScript触发方法

和模态弹出窗一样，Bootstrap框架中的下拉菜单也支持JavaScript方法触发下拉菜单显示。使用JavaScript触发下拉菜单和声明式原理是基本类似的，不同的是使用JavaScript方法可以按照自己的方式省略一些元素或者样式。同样用一个简单的示例来做演示：

```
<ul class="nav nav-pills">
    <li class="dropdown">
        <a href="##"  class="dropdown-toggle" role="button" id="tutorial">教程<b class="caret"></b></a>
        <ul class="dropdown-menu" role="menu" aria-labelledby="tutorial">
            <li role="presentation"><a href="##">CSS3</a></li>
            <li role="presentation"><a href="##">HTML5</a></li>
            <li role="presentation"><a href="##">Sass</a></li>
        </ul>
    </li>
    <li class="active"><a href="##">前端论坛</a></li>
    <li><a href="##">关于我们</a></li>
</ul>
```

使用JavaScript调用dropdown()方法后，单击激活按钮，会弹出下拉菜单，再次单击的时候会收起下拉菜单。

```
$(function(){
    $(".dropdown-toggle").dropdown();
})
```

还可以使用参数“toggle”。当下拉菜单隐藏时，调用dropdown(“toggle”)方法可以显示下拉菜单，反之，如果下拉菜单显示时，调用dropdown(“toggle”)方法可以让下拉菜单隐藏。

```
$(function(){
    $(".dropdown-toggle").dropdown("toggle");
})
```

不过使用该参数，每次单击都要两次toggle，就会一直是一个不变的状态。所以，一般情况下，使用示例中不带参数的方法。就算你需要使用参数“toggle”，也建议使用jQuery的one方法：

```
$(".dropdown-toggle").one("click",function(){
    $(this).dropdown("toggle");
})
```

