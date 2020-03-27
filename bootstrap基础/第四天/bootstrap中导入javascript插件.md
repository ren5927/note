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

## 动画过渡（Transitions）

这一小节我们先来讲“动画过渡（Transitions）”这个插件的使用，源文件：transition.js

Bootstrap框架默认给各个组件提供了基本动画的过渡效果，如果要使用，有两种方法：

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 调用统一编译的bootstrap.js；

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 调用单一的过渡动画的JavaScript插件文件transition.js（右侧第29行引入Bootstrap上对外公布的transition.js的地址）。

transition.js文件为Bootstrap具有过渡动画效果的组件提供了动画过渡效果。不过需要注意的是，这些过渡动画都是采用CSS3来实现的，所以IE6-8浏览器是不具备这些过渡动画效果。

默认情况之下，Bootstrap框架中以下组件使用了过渡动画效果：

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 模态弹出窗（Modal）的滑动和渐变效果；

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 选项卡（Tab）的渐变效果；

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 警告框（Alert）的渐变效果；

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 图片轮播（Carousel）的滑动效果。

右侧举了一个“模态弹出窗（Modal）的滑动和渐变效果”源代码例子。

## 模态弹出框（Modals）

这一小节我们先来讲解一个“模态弹出框”，插件的源文件：modal.js。

右侧代码编辑器（30行）就是单独引入 bootstrap 中发布出的“modal.js”文件。

样式代码：

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) LESS版本：modals.less

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) Sass版本：_modals.scss

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 编译后的Bootstrap：对应bootstrap.css文件第5375行～第5496行

在 Bootstrap 框架中把模态弹出框统一称为 Modal。这种弹出框效果在大多数 Web 网站的交互中都可见。比如点击一个按钮弹出一个框，弹出的框可能是一段文件描述，也可能带有按钮操作，也有可能弹出的是一张图片。如下图所示：

[![img](http://img.mukewang.com/541a3ecc00016cc606940246.jpg)](http://img.mukewang.com/541a3ecc00016cc606940246.jpg)



## 模态弹出框--结构分析

Bootstrap框架中的模态弹出框，分别运用了“modal”、“modal-dialog”和“modal-content”样式，而弹出窗真正的内容都放置在“modal-content”中，其主要又包括三个部分：

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 弹出框头部**，一般使用“modal-header”表示，主要包括标题和关闭按钮

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 弹出框主体**，一般使用“modal-body”表示，弹出框的主要内容

 **![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) 弹出框脚部**，一般使用“modal-footer”表示，主要放置操作按钮

如下图所示：

[![img](http://img.mukewang.com/541a3f4f000177d406700212.jpg)](http://img.mukewang.com/541a3f4f000177d406700212.jpg)

模态弹出窗的结构如下：

```
<div class="modal show">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal"><span aria-hidden="true">&times;</span><span class="sr-only">Close</span></button>
                <h4 class="modal-title">模态弹出窗标题</h4>
            </div>
            <div class="modal-body">
                <p>模态弹出窗主体内容</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                <button type="button" class="btn btn-primary">保存</button>
            </div>
        </div><!-- /.modal-content -->
    </div><!-- /.modal-dialog -->
</div><!-- /.modal -->
```

**弹出窗的主体样式实现：**

但是对于一个模态弹出窗而言，modal-content才是样式的关键。其主要设置了弹出窗的边框、边距、背景色和阴影等样式。

```
/*bootstrap.css文件第5412行～第5423行*/
.modal-content {
  position: relative;
  background-color: #fff;
  -webkit-background-clip: padding-box;
          background-clip: padding-box;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, .2);
  border-radius: 6px;
  outline: 0;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, .5);
          box-shadow: 0 3px 9px rgba(0, 0, 0, .5);
}
```

除此之外，modal-content中的modal-header、modal-body和modal-footer三个部分样式设置：

```
/*bootstrap.css文件第5441行～第5461行*/
.modal-header {
  min-height: 16.42857143px;
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
```

这三个部分主要控制一些间距的样式。而modal-footer都是用来放置按钮，所以底部还对包含的按钮做了一定的样式处理。

```
/*bootstrap.css文件第5462行～第5471行*/
.modal-footer .btn + .btn {
  margin-bottom: 0;
  margin-left: 5px;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
```

## 模态弹出框--实现原理解析（一）

**实现原理解析：**

bootstrap中的“模态弹出框”有以下几个特点：

1、模态弹出窗是固定在浏览器中的。

2、单击右侧全屏按钮，在全屏状态下，模态弹出窗宽度是自适应的，而且modal-dialog水平居中。

3、当浏览器视窗大于768px时，模态弹出窗的宽度为600px。

固定在浏览器(源代码)实现：

```
/*bootstrap.css文件第5379行～第5389行*/
.modal {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  display: none;
  overflow: hidden;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
```

水平居中(源代码)实现：

```
/*bootstrap.css文件第5407行～第5411行*/
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
```

当浏览器视窗大于768px时，模态弹出窗的宽度为600px（源代码）实现：

```
/*bootstrap.css文件第5479行～第5491行*/
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, .5);
            box-shadow: 0 5px 15px rgba(0, 0, 0, .5);
  }
  .modal-sm {
    width: 300px;
  }
}
```



## 模态弹出框--实现原理解析（二）

**蒙板样式实现：**

大家或许注意到了，在做模态弹出窗时，底部常常会有一个透明的黑色蒙层效果，如下图所示：

[![img](http://img.mukewang.com/541a428200016e9806930230.jpg)](http://img.mukewang.com/541a428200016e9806930230.jpg)

在Bootstrap框架中为模态弹出窗也添加了一个这样的蒙层样式“modal-backdrop”，只不过他默认情况下是全屏黑色的：

```
/*bootstrap.css文件第5424行～第5432行*/
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
```

同样，给其添加了一个过渡动画，从fade到in，把opacity值从0变成了0.5。上图展示的就是in状态下的效果：

```
/*bootstrap.css文件第5433行～第5440行*/
.modal-backdrop.fade {
  filter: alpha(opacity=0);
  opacity: 0;
}
.modal-backdrop.in {
  filter: alpha(opacity=50);
  opacity: .5;
}
```

**两种尺寸选择：**

除此之外，Bootstrap框架还为模态弹出窗提供了不同尺寸，一个是大尺寸样式“modal-lg”，另一个是小尺寸样式“modal-sm”。其结构上稍做调整：

```
<!-- 大尺寸模态弹出窗 -->
<div class="modal fade bs-example-modal-lg" tabindex="-1"role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true">
    <divclass="modal-dialog modal-lg">
       <divclass="modal-content"> ... </div>
    </div>
</div>
<!-- 小尺寸模态弹出窗 -->
<divclass="modal fade bs-example-modal-sm"tabindex="-1"role="dialog" aria-labelledby="mySmallModalLabel" aria-hidden="true">
    <divclass="modal-dialog modal-sm">
       <divclass="modal-content"> ... </div>
    </div>
</div>
```

来简单的看一个示例效果：

[![img](http://img.mukewang.com/541a42f4000194dc06890148.jpg)](http://img.mukewang.com/541a42f4000194dc06890148.jpg)

[![img](http://img.mukewang.com/541a430800019bf006220370.jpg)](http://img.mukewang.com/541a430800019bf006220370.jpg)

对于这两种尺寸的模态弹出窗，Bootstrap在媒体查询中做过处理：代码同上见bootstrap.css



## 模态弹出框--触发模态弹出窗2种方法

众所周知，模态弹出窗在页面加载完成时，是被隐藏在页面中的，只有通过一定的动作（事件）才能触发模态弹出窗的显示。在Bootstrap框架中实现方法有2种，接下来分别来介绍这2种触发模态弹出窗的使用方法。

**声明式触发方法**：

**方法一：**模态弹出窗声明，只需要自定义两个必要的属性：data-toggle和data-target（bootstrap中声明式触发方法一般依赖于这些自定义的data-xxx 属性。比如data-toggle="" 或者 data-dismiss=""）。例如：

```
<!-- 触发模态弹出窗的元素 -->
<button type="button" data-toggle="modal" data-target="#mymodal" class="btn btn-primary">点击我会弹出模态弹出窗</button>
<!-- 模态弹出窗 -->
<div class="modal fade" id="mymodal">
    <div class="modal-dialog">
        <div class="modal-content">
        <!-- 模态弹出窗内容 -->
        </div>
    </div>
</div>
```

**注意以下事项：**

1、data-toggle必须设置为modal(toggle中文翻译过来就是触发器)；

2、data-target可以设置为CSS的选择符，也可以设置为模态弹出窗的ID值，一般情况设置为模态弹出窗的ID值，因为ID值是唯一的值。

**方法二：**触发模态弹出窗也可以是一个链接****元素，那么可以使用链接元素自带的href属性替代data-target属性，如：

```
<!-- 触发模态弹出窗的元素 -->
<a data-toggle="modal" href="#mymodal" class=" btn btn-primary" >点击我会弹出模态弹出窗</a>
<!-- 模态弹出窗 -->
<div class="modal fade"  id="mymodal" >
    <div class="modal-dialog" >
        <div class="modal-content" >
        <!-- 模态弹出窗内容 -->
        </div>
    </div>
</div>
```

不过建议还是使用统一使用data-target的方式来触发。

点击按钮就能触发弹出窗：

[![img](http://img.mukewang.com/541a76680001447f06640188.jpg)](http://img.mukewang.com/541a76680001447f06640188.jpg)



## 模态弹出框--为弹出框增加过度动画效果

**为模态弹出框增加过度动画效果：**

可通过给“.modal”增加类名“fade”为模态弹出框增加一个过渡动画效果。

```
<button class="btn btn-primary" data-toggle="modal" data-target=".bs-example-modal-sm">
小的模态弹出窗
</button><div class="modal fade bs-example-modal-sm" tabindex="-1" role="dialog" aria-labelledby="mySmallModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-sm">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal"><span aria-hidden="true">&times;</span><span class="sr-only">Close</span></button>
                <h4 class="modal-title">模态弹出窗标题</h4>
            </div>
            <div class="modal-body">
                <p>模态弹出窗主体内容</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                <button type="button" class="btn btn-primary">保存</button>
            </div>
        </div>
    </div>
</div>
```

源代码实现：

```
/*bootstrap.css文件第5390行～第5402行*/
.modal.fade .modal-dialog {
  -webkit-transition: -webkit-transform .3s ease-out;
       -o-transition:      -o-transform .3s ease-out;
          transition:         transform .3s ease-out;
  -webkit-transform: translate3d(0, -25%, 0);
       -o-transform: translate3d(0, -25%, 0);
          transform: translate3d(0, -25%, 0);
}

.modal.in .modal-dialog {
  -webkit-transform: translate3d(0, 0, 0);
       -o-transform: translate3d(0, 0, 0);
          transform: translate3d(0, 0, 0);
}
```

## 模态弹出框--模态弹出窗的使用（data-参数说明）

除了通过data-toggle和data-target来控制模态弹出窗之外，Bootstrap框架针对模态弹出框还提供了其他自定义data-属性，来控制模态弹出窗。比如说:是否有灰色背景modal-backdrop，是否可以按ESC键关闭模态弹出窗。有关于Modal弹出窗自定义属性相关说明如下所示：

[![img](http://img.mukewang.com/544f09480001d6c409000872.jpg)](http://img.mukewang.com/544f09480001d6c409000872.jpg)

(单击可放大)

## 模态弹出框--模态弹出窗的使用（JavaScript触发）

**JavaScript****触发方法**

除了使用自定义属性触发模态弹出框之外，还可以通过JavaScript方法来触发模态弹出窗。通过给一个元素一个事件，来触发。比如说给一个按钮一个单击事件，然后触发模态弹出窗。如下面的一个简单示例：

```
<!-- 触发模态弹出窗元素 -->
<button class="btn btn-primary" type="button">点击我</button>
<!-- 模态弹出窗内容 -->
<div class="modal" id="mymodal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal"><span aria-hidden="true">&times;</span><span class="sr-only">Close</span></button>
                <h4 class="modal-title">模态弹出窗标题</h4>
            </div>
            <div class="modal-body">
                <p>模态弹出窗主体内容</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                <button type="button" class="btn btn-primary">保存</button>
            </div>
        </div><!-- /.modal-content -->
    </div><!-- /.modal-dialog -->
</div><!-- /.modal -->
```

JavaScript触发的弹出窗代码：

```
$(function(){
  $(".btn").click(function(){
    $("#mymodal").modal();
  });
});
```

运行效果如下：

[![img](http://img.mukewang.com/541a7d580001e8a606490343.jpg)](http://img.mukewang.com/541a7d580001e8a606490343.jpg)



## 模态弹出框--JavaScript触发时的参数设置（一）

使用JavaScript触发模态弹出窗时，Bootstrap框架提供了一些设置，主要包括属性设置、参数设置和事件设置。

**属性设置**

模态弹出窗默认支持的自定义属性主要有：

[![img](http://img.mukewang.com/544f0bd50001b34409020384.jpg)](http://img.mukewang.com/544f0bd50001b34409020384.jpg)

比如你不想让用户按ESC键关闭模态弹出窗，你就可以这样做：

```
$(function(){
    $(".btn").click(function(){
        $("#mymodal").modal({
            keyboard:false
        });
    });
});
```

这一节，我们对JavaScript触发模态弹出窗的属性设置进行了介绍，下一节我们将继续对参数设置和事件设置进行介绍。



## 模态弹出框--JavaScript触发时的参数设置（二）

上一节，我们对JavaScript触发模态弹出窗的属性设置进行了介绍，现在我们接着对参数设置和事件设置进行介绍。

**参数设置：**

在Bootstrap框架中还为模态弹出窗提供了三种参数设置，具体说明如下：

| 参数   | 使用方法                      | 描述                                                         |
| ------ | ----------------------------- | ------------------------------------------------------------ |
| toggle | $(“#mymodal”).modal(“toggle”) | 触发时，反转模态弹出窗的状态。如果模态弹出窗是显示的，则关闭；反之，如果模态弹出窗是关闭的，则显示 |
| show   | $(“#mymodal”).modal(“show”)   | 触发时，显示模态弹出窗                                       |
| hide   | $(“#mymodal”).modal(“hide”)   | 触发时，关闭模态弹出窗                                       |

**事件设置：**

模态弹出窗还支持四种类型的事件，分别是模态弹出窗的弹出前、弹出后，关闭前、关闭后，具体描述如下：

| 事件类型        | 描述                                                         |
| --------------- | ------------------------------------------------------------ |
| show.bs.modal   | 在show方法调用时立即触发（尚未显示之前）；如果单击了一个元素，那么该元素将作为事件的relatedTarget属性 |
| shown.bs.modal  | 该事件在模态弹出窗完全显示给用户之后（并且等CSS动画完成之后）触发；如果单击了一个元素，那么该元素将作为事件的relatedTarget事件 |
| hide.bs.modal   | 在hide方法调用时（但还未关闭隐藏）立即触发                   |
| hidden.bs.modal | 该事件在模态弹出窗完全隐藏之后（并且CSS动画漂完成之后）触发  |

调用方法也非常简单：

```
$('#myModal').on('hidden.bs.modal', function (e) {
    // 处理代码...
})
```