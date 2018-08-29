### jQ语法



#####查找元素

* jQuery允许使用css选择器查找元素，其语法形式为：`$('Selector')`，它还提供了一些额外的选择器
  * *通用选择器  selector1, selector2, selectorN群组选择器



##### 基本选择器

* `ancestor descendant`：后代选择器 **->** 返回指定后代元素节点集合；
* `parent > child'`：子类选择器 **->** 返回指定子类元素节点集合；
* `prev + next`：同级元素选择器 **->** 返回指定同级元素节点，当前节点的下一节点；
* `prev ~ sibilings`：同级元素选择器 **->** 返回指定同级元素节点，当前节点后面所有的指定元素节点；



##### 基本筛选器

* `:eq(index)`：选中元素中索引编号为参数中指定数字的元素；*（ jQuery ）*
* `:gt(index)`：选中元素中索引编号大于参数中指定数字的元素；*（ jQuery ）*
* `:lt(index)`：选中元素中索引编号小于参数中指定数字的元素；*（ jQuery ）*
* `header`：所有的 \<h1>到\<h6>元素；*（ jQuery ）*
* `:animated`：正在进行动画的元素；*（ jQuery ）*
* `：focus`：当前拥有焦点的元素；



##### 属性选择器

- `[attribute]`：拥有指定属性的元素（属性值不限）；
- `[attribute  = 'value']`：拥有指定属性，并且值为指定值的元素；
- `[attribute != 'value']`：拥有指定属性，并且值不为指定值的元素；*（ jQuery ）*
- `[attribute ^= 'value']`：属性值以特定值开头；
- `[attribute $= 'value']`：属性值以特定值结尾；
- `[attribute *= 'value']`：属性值含有特定值；



##### 表单

- `:input`：匹配所有 input, textarea, select 和 button 元素；*（ jQuery ）*
- `:text`：匹配所有文本类型的input元素；*（ jQuery ）*
- `:password`：匹配所有密码类型的input元素；*（ jQuery ）*
- `:radio`：匹配所有单选按钮；*（ jQuery ）*
- `:checkbox`：匹配所有复选框；*（ jQuery ）*
- `:submit`：匹配所有提交按钮；*（ jQuery ）*
- `:image`：匹配所有图片按钮；*（ jQuery ）*
- `:reset`：匹配所有重置按钮；*（ jQuery ）*
- `:button`：匹配所有按钮；*（ jQuery ）*
- `:file`：匹配所有文件域；*（ jQuery ）*
- `:selected`：匹配下拉列表中所有被选中的列表项；
- `:enabled`：匹配所有可用元素；


- `:enabled`：匹配所有可用的表单元素；
- `:disabled`：匹配所有禁用的表单元素；
- `:checked`：匹配所有被选中的按钮或复选框；



`this` 是 JavaScript 中的关键字；`$(this)` 是 jQuery 对象；

当变量包含一个jQuery对象时，通常都会在变量名的前面加一个`$`符号用来区分脚本中的其他变量，比如：`let $imgBox = $('#img-box');`

##### .attr()

attr()不仅可以获取元素属性值，还可以设置元素属性，

attr{key, value）;

attr({,,,,,})

#####.html()

- .html()：获取集合中第一个匹配元素的HTML内容
- .html( htmlString )：设置每一个匹配元素的HTML内容

提示：.html() 方法如DOM中的innerHTML()方法，所以在设置与获取上需要注意的一个最重要的问题，这个操作是针对整个HTML内容（不仅仅只是文本内容）

#####.text

- .html与.text的方法操作是一样，只是在具体针对处理对象不同
- .html处理的是元素内容，.text处理的是文本内容
- .html只能使用在HTML文档中，.text 在XML 和 HTML 文档中都能使用
- 如果处理的对象只有一个子文本节点，那么html处理的结果与text是一样的

##### .val()

该方法主要用于处理表单元素的值，比如input、select和textarea。其使用方法有一下3种形式：

- .val()：获取匹配的元素集合中第一个元素的当前值
- .val( value )：设置匹配的元素集合中每个元素的值
- .val( function )：一个用来返回设置值的函数

> 提示：
>
> 1. 通过.val() 处理select元素，当没有选择项被选中时，它返回null
> 2. .val() 方法多用来设置表单字段的值
> 3. 如果select元素由multiple（多选）属性，并且至少一个选择项被选中，.val() 方法返回一个数组，这个数组包含每个选中选择项的值。



##### .data()

// 1、静态接口
jQuery.data( element, key, value )   // 存数据
jQuery.data( element, key )  // 取数据   

// 2、实例接口
.data( key, value ) // 存数据
.data( key ) // 取数据



jQuery.removeData( element [, name ] )

.removeData( [name ] )



#####样式

- .hasClass()

  该方法用于判断元素是否包含某class。

- .addClass()

.removeClass()



##### 位置

- `.height()`：获取/设置匹配元素当前计算的高度值（px）
- `.innerHeight()`：获取第一个匹配元素内部区域高度（包括padding、不包括border）。
- `.outerHieght()`：获取第一个匹配元素外部高度（默认包括padding和border）。
- `.width()`：获取/设置第一个匹配元素当前计算的宽度值（px）。
- `.innerWidth()`：获取第一个匹配元素内部区域宽度（包括padding、不包括border）。
- `.outerWidth()`：获取第一个匹配元素外部宽度（默认包括padding和border）。
- `.scrollTop()`：设置/获取匹配元素相对滚动条顶部的偏移。
- `.scrollLeft()`：设置/获取匹配元素相对滚动条左侧的偏移。
- `offset()`：获取元素偏移，相对于文档而言，有四个选项（`.top, .left, .right, .bottom`）
- `position`：获取元素位置，相对于拥有定位属性的祖先级元素而言，有四个选项（`.top, .left, .right, .bottom`）



### DOM

#####1.创建元素节点

$('<div></div>')；

.append()向每个匹配的元素内部追加内容

$(A).after(B); // 在A的后面添加B
$(A).before(B);// 在A的前面添加B

$(A).prepend(B);   // 把B添加到A中(前面)
$(A).prependTo(B); // 把A添加到B中(前面)

$(A).insertAfter(B);  // 将A插入到B的后面
$(A).insertBefore(B); // 将A插入到B的前面

##### 2.节点删除

#####.empty()

#####.remove()

remove会将元素自身移除，同时也会移除元素内部的一切，包括绑定的事件及与该元素相关的jQuery数据。



##### 3.节点复制与替换

.clone()

//clone处理一
$("div").clone()     // 只克隆了结构，事件丢失

//clone处理二
$("div").clone(true) // 结构、事件与数据都克隆



$(A).replaceWith(B); // 把A替换为B
$(A).replaceAll(B);  // 把B替换为A



.wrap()

如果要将元素用其他元素包裹起来，也就是给它增加一个父元素，针对这样的处理，JQuery提供了一个 *wrap* 方法。

$("p").wrap("<b></b>")



.unwrap()

该方法与wrap方法相反，unwrap方法将匹配元素集合的父级元素删除，保留自身（和兄弟元素，如果存在）在原来的位置。



##### 4.节点遍历

.children()

如果想快速查找集合里面的第一级子元素，此时可以用 *children()* 方法

该方法可以接受参数，用于筛选子元素，如  *"$('.parent').children(.active)"*，匹配子元素中类名为 `active` 的那一个。



.find()

find 与 children 类似，区别在于 children是父子关系查找，find是后代关系查找（包含父子关系）。

.parent()

.parents()



.closest()

*closest()* 方法接受一个匹配元素的选择器字符串。从元素本身开始，在DOM 树上逐级向上级元素匹配，并返回最先匹配的祖先元素。

- 起始位置不同：.closest 开始于当前元素 .parents开始于父元素
- 遍历的目标不同：.closest要找到指定的目标，.parents遍历到文档根元素，closest向上查找，直到找到一个匹配的就停止查找，parents 一直查找到根元素，并将匹配的元素加入集合
- 结果不同：.closest返回的是包含零个或一个元素的jquery对象，parents返回的是包含零个或一个或多个元素的jquery对象



.next()、.nextAll()

- .next()：该方法用于匹配当前元素的下一个元素。
- .nextAll()：查找当前元素之后所有的同辈元素。



.prev()、.prevAll()

- .prev()：该方法用于匹配当前元素的上一个元素。
- .prevAll()：查找当前元素之前所有的同辈元素



.siblings()

该方法用于匹配当前元素的所有兄弟元素。



.each()

$("li").each(function(index, element) {

     index 索引 0,1
     element是对应的li节点 li,li
     this 指向的是li
})

如果需要提前退出，可以通过返回 false以便在回调函数内中止循环。



### 事件

#####1.事件添加

$ele.event( [eventData ], handler(eventObject) )

$(".button").click("Hello, jQuery!", function(e) {
  	// ...
  	// this --> .button
  	// e.data --> "Hello, jQuery!"
})

##### 冒泡事件



通过 stopPropagation（）方法阻止冒泡事件





#####2.鼠标事件

- .click() & .dblclick() ：单击 & 双击事件


- .mousedown()  & .mouseup() ：鼠标按下 & 鼠标抬起（提示：鼠标按下抬起会触发一个点击事件）

- .mousemove() ：鼠标移动事件（只要鼠标移动就会触发该事件，并且会触发多次）

- .mouseover()  & .mouseout() ：鼠标移入 & 鼠标移出

- .mouseenter & .mouseleave() ：鼠标移入 & 鼠标移出（不会冒泡）

- .hover() ：切换事件，类似于css中的hover，

  其语法形式为：*$(selector).hover(handlerIn, handlerOut)* ，在hover方法中传递两个回调函数即可。


$（"a"）.hover(function(){},function(){});










#####3.表单事件

- .focusin()  & .focusout() ：失去焦点事件 & 获取焦点事件
- .blur()  & .focus() ：失去焦点 & 获取焦点（不会冒泡）
- .change() ：值改变事件（常用于input、textarea及select）
- .select() ：当 textarea 或文本类型的 input 元素中的文本被选择时，会发生 select 事件。
- .submit() ：表单提交事件（`type="submit/image" || 按Enter键`）

form元素是有默认提交表单的行为，如果通过submit处理的话，需要禁止浏览器的这个默认行为
传统的方式是调用事件对象  e.preventDefault() 来处理， jQuery中可以直接在函数中最后结尾return false即可



.keydown()  & .keyup() ：键盘按下 & 键盘抬起（当用户在一个元素上第一次按下/抬起键盘上的键的时候，就会触发）

.keypress() ：长按

$("div").one("click", function(){

    // 这个事件只会触发一次
})

- .resize()：调整窗口大小
- .scroll()：窗口滚动



##### 4.事件的绑定和解绑

on() 事件绑定

.on( events ,[ selector ] ,[ data ], fn )

$("#elem").click(function(){})  //快捷方式
$("#elem").on('click',function(){}) //on方式

    $("#elem").on({
    mouseover:function(){},  
    mouseout:function(){}
    });


**将数据传递到处理程序**

```javascript
function hello( event ) {
	console.log('Hello, ' + event.data.name);
}
$('#btn').on('click', {name: 'Henrry'}, hello);
// 点击输出：Hello, Henrry
```

可以通过第二参数（对象），当一个事件被触发时，要传递给事件处理函数的



on() 事件代理

.on( events ,[ selector ] ,[ data ], handler(eventObject) )



参考下面3层结构

```html
<div>
    <p>
        <a>目标节点</a> //点击在这个元素上
    </p>
</div>
```

给出如下代码：

```javascript
$('div').on('click', 'p', function(e) {
	e.target.textContent = 'Hello, world!';
});
```

> 事件绑定在最上层div元素上，当用户触发在a元素上，事件将往上冒泡，一直会冒泡在div元素上。如果提供了第二参数，那么事件在往上冒泡的过程中遇到了选择器匹配的元素，将会触发事件回调函数



##### .toggle()

在toggle（）方法中，可以一次调用n个指定的函数，知道最后一个函数，然后重复对这些函数轮番调用

toggle（fn, fn2, fn3）



##### 5.自定义事件



.trigger()   自动执行



### 动画

##### .hide(speed,easing,fn)

- **speed**：三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
- **easing**：(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
- **fn**：在动画完成时执行的函数，每个元素执行一次。

> 提示：元素隐藏之后会脱离文档流

##### .show()

```js
$("a").click(function(){
    $("img").show(3000,"linear" function(){
        $(this).css("border", "solid 1px #ccc")
    })
});
$("img").click(function(){
    $(this).hide(3000);
});
```

##### toggle()方法

通常需要检测当前元素的显示状态，然后根据该状态在执行元素是否显示或隐藏。用toggle（）方法，切换元素可见

```js
$("img").toggle();

$("img").toggle(3000, function(){
 $this.css();
});
```











#####上卷下拉

##### .slideDown()  下拉动画

.slideDown()：用滑动动画显示一个匹配元素

.slideDown([speed,[easing],[fn]])

```js
$("img").slideDown(3000,"linear",function(){
    
});
```







##### .slideUp() 动画

.slideUp() 上拉动画



##### .slideToggle()方法

.slideToggle(speed,[callback])





##### 淡入淡出

除了通过 *display* 设置元素的显示与隐藏，还有一种方法就是设置元素的不透明度（`opacity`），值范围为` 0~1` ，当不透明度为1时，元素显示，当不透明度为0时，元素隐藏。jQuery淡入淡出效果正是使用了这个原理。只不过，当不透明度为0时，元素虽然隐藏了，但是并没有脱离文档流，但是jQuery中，元素淡出会脱离文档流。

.fadeIn()显示

.fadeOut() 消失

.fadeToggle() 翻转

.fadeTo() 到达某个值



##### 自定义动画

#####.animate()

.animate( prop ,[ speed ], [ easing ], [ complete ] )

- properties：一个或多个css属性的键值对所构成的Object对象，对 **数字属性值** 有效，驼峰命名，可使用快捷方式如‘show/toggle’。
- speed：持续时间，单位ms，提供 'fast' 和 'slow' 字符串，分别表示持续时间为200 和 600毫秒。
- easing：动画运动算法，jQuery库中默认调用 swing。如果需要其他的动画算法，请查找相关的插件
- complete：回调函数

```js
$(".box").click(function () {
   $(this).animate({
       left: "+=50px"
   },1000, function () {
     alert("动画执行完毕！");
   })
});

$(this).animate({
    width:"20%",
    height:"70px"},3000,function(){
    $this.css({"border":"solid 3px #666"})
    .html("变大了")；
});
```

我们可以通过animate提供的第二种设置语法，传递一个对象参数，可以拿到动画执行状态一些通知。

.animate( prop, options )

option参数

- duration：设置动画执行的时间
- easing ：规定要使用的 easing 函数，过渡使用哪种缓动函数
- step：规定每个动画的每一步完成之后要执行的函数
- progress：每一次动画调用的时候会执行这个回调，就是一个进度的概念
- complete：动画完成回调
- queue：布尔值。指示是否在效果队列中放置动画。如果为 false，则动画将立即开始

```
$(".box").click(function () {
    $(this)
        .animate({width  : "50px"}, 1000)
        .animate({height : "50px"}, 1000)
        .animate({opacity: ".5"}, 1000);
});
```



#####.queue（）其它动画

animate 只对数字值的变化有效，如果想要将其他变化（比如颜色变化）加入到动画队列中，可使用 *.queue()* 方法，不过你需要指定 *next* 函数参数并调用，当其他变化执行之后手动执行后续动画队列。

```js
$(".box").click(function () {
    $(this)
        .animate({width  : "100px"}, 1000)
        .animate({height : "100px"}, 1000)
        .animate({opacity: ".5"}, 500)
        .queue(function (next) {
            // next -> 函数
            $(this).css({
                background: "blue"
            });
            next();
        })
        .slideUp(1000);
});
```



##### .dequeue() 列队功能

*.dequeue()* 方法。意思为执行下一个元素列队中的函数。

```js
$(".box").click(function () {
    $(this)
        .animate({width  : "100px"}, 1000)
        .animate({height : "100px"}, 1000)
        .animate({opacity: ".5"}, 500)
        .queue(function () {
            // next -> 函数
            $(this).css({
                background: "blue"
            });
            $(this).dequeue();
        })
        .slideUp(1000);
});
```

#####.clearQueue()

假如我想在执行完第二个动画就不再执行了。那么只要在第二个动画的回调函数那里添加一句 *$(this).clearQueue()* 就可以停止后面的列队动画了。

```js
$(".box").click(function () {
    $(this)
        .animate({width  : "100px"}, 1000)
        .animate({height : "100px"}, 1000)
        .animate({opacity: ".5"}, 500, function(){$(this).clearQueue();/* 清理队列*/})
        .queue(function () {
            // next -> 函数
            $(this).css({
                background: "blue"
            });
            $(this).dequeue();
        })
        .slideUp(1000);
});
```



##### 获取列队长度

```js
function getQueueCount() {
    //获取当前列队的长度，fx 是默认列队的参数
    return $(".box").queue("fx").length;
}
```

#####jQuery.fx.off

关闭页面上所有的动画。



#####jQuery.fx.interval

设置jQuery动画每隔多少毫秒绘制一帧图像 (默认为13 毫秒) 数字越小越流畅，但可能影响浏览器性能。





### Ajax

#### .load()方法 

load(url,  [data], [callback])

$("#tip").load("b.html")



#####$.get()

有时也会遇到使用xml文档保存数据的情况，对于这种格式的数据，jquery使用全局函数$.get()进行访问，语法格式

$.get(url, [data],[callback],[type]);

```js
$.get("userInfo.xml",function(data){
    $("#divTip").empty();//先清空标记中的内容
    var strHtml = "";
    $(data).find("user")
        .each(function(0{
                        var $strUser = $(this);
                strHtml += $strUser.find("name").text();
                strHtml += $strUser.find("sex").text();
                strHtml += $strUser.find("email").text();
                        }));
     $("#divTip").html(strHtml);
});
```



##### $.post()

$.post(url, [data],[callback],[type]);



##### serialize()序列化表单

该方法的功能是讲所选择的dom元素转换成能随ajax传递的字符串，即序列化所选择的dom元素

```js
$.post("userInfo.aspx",$("#frmuserinfo").serialize()//序列化表单数据
       ,function(data){
    $("#divTip").empty();//先清空标记中的内容
    var strHtml = "";
    $(data).find("user")
        .each(function(0{
                        var $strUser = $(this);
                strHtml += $strUser.find("name").text();
                strHtml += $strUser.find("sex").text();
                strHtml += $strUser.find("email").text();
                        }));
     $("#divTip").html(strHtml);
});
```

##### .getJSON()

.getJSON(url,[data],[ca])



##### $.ajax()

除了使用全局函数load()、get()、post()实现页面的异步调用和与服务器交互数据外，在jq中，还有一个功能更为强悍的最底层的方法$.ajax()，该方法不仅可以实现上述三个全局函数的功能，还能更多的实现过程的细节

$.ajax([options]);



##### $.ajaxSetup

有时需要调用多个$.ajax()方法

$.ajaxSetup([options])

```
$.ajaxSetup({
    type:"get",
    url:"userinfo.xml",
    dataType:"xml"
})
$("#button1).click(function(){
    $.ajax({
        success:function(data){
            showData(data,"姓名","name");
        }
    })
})
$("#button2).click(function(){
    $.ajax({
        success:function(data){
            showData(data,"性别","sex");
        }
    })
})
$("#button3).click(function(){
    $.ajax({
        success:function(data){
            showData(data,"邮箱","email");
        }
    })
})
```

### jQuery常用插件

##### 验证插件validate










