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