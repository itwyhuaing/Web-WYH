# jQuery 基础

## jQuery 基础认识
* jQuery是一个JavaScript函数库。
* jQuery是一个轻量级的"写的少，做的多"的JavaScript库。
* jQuery库包含以下功能：
    * HTML 元素选取
    * HTML 元素操作
    * CSS 操作
    * HTML 事件函数
    * JavaScript 特效和动画
    * HTML DOM 遍历和修改
    * AJAX
    * Utilities
    * 除此之外，Jquery还提供了大量的插件

##### jQuery 效果

* 隐藏和显示

```
$(selector).hide(speed,callback);

$(selector).show(speed,callback);

$(selector).toggle(speed,callback);

```

* 淡入淡出

```
$(selector).fadeIn(speed,callback);

$(selector).fadeOut(speed,callback);

$(selector).fadeToggle(speed,callback);

$(selector).fadeTo(speed,opacity,callback);

```

* 滑动

```
$(selector).slideDown(speed,callback);

$(selector).slideUp(speed,callback);

$(selector).slideToggle(speed,callback);


```

* 动画

```
$(selector).animate({params},speed,callback);


注:
几乎可以用 animate() 方法来操作所有 CSS 属性 。但必须使用Camel标记法书写所有的属性名。色彩动画并不包含在核心 jQuery 库中。
如果需要生成颜色动画，您需要从 jquery.com 下载 颜色动画 插件。
```

*  停止动画

```
$(selector).stop(stopAll,goToEnd);

注：
jQuery stop() 方法用于停止动画或效果，在它们完成之前。
stop() 方法适用于所有jQuery效果函数，包括滑动、淡入淡出和自定义动画。
可选的 stopAll 参数规定是否应该清除动画队列。默认是 false，即仅停止活动的动画，允许任何排入队列的动画向后执行。
可选的 goToEnd 参数规定是否立即完成当前动画。默认是 false。
因此，默认地，stop() 会清除在被选元素上指定的当前动画。


```

* 链(Chaining)

```
如下代码 ："p1" 元素首先会变为红色，然后向上滑动，再然后向下滑动。

$("#p1").css("color","red").slideUp(2000).slideDown(2000);

```

##### jQuery HTML
* 获取内容和属性

```
text() - 设置或返回所选元素的文本内容。
html() - 设置或返回所选元素的内容（包括 HTML 标记）。
val() - 设置或返回表单字段的值。
attr() 方法用于获取属性值。

```

* 添加元素

```
append() - 在被选元素的结尾插入内容
prepend() - 在被选元素的开头插入内容
after() - 在被选元素之后插入内容
before() - 在被选元素之前插入内容

小结：创建元素的方式
1> 使用 HTML
var t1="<b>I </b>";

2> 使用 jQuery
var t2=$("<i></i>").text("love ");

3> 使用 DOM
var t3=document.createElement("big");
    t3.innerHTML="jQuery!";

```

* 删除元素

```
remove() - 删除被选元素（及其子元素）
empty() - 从被选元素中删除子元素

注：
remove() 方法也可接受一个参数，允许您对被删元素进行过滤。

```

* 获取并设置 CSS 类

```
addClass() - 向被选元素添加一个或多个类
removeClass() - 从被选元素删除一个或多个类
toggleClass() - 对被选元素进行添加/删除类的切换操作
css() - 设置或返回被选元素的一个或多个样式属性
1> 获取 css("propertyname");
2> 设置 css("propertyname","value");
3> css({"propertyname":"value","propertyname":"value",...});

```

* 尺寸

```
width() 方法设置或返回元素的宽度（不包括内边距、边框或外边距）。
height() 方法设置或返回元素的高度（不包括内边距、边框或外边距）。
innerWidth() 方法返回元素的宽度（包括内边距）
innerHeight() 方法返回元素的高度（包括内边距）。
outerWidth() 方法返回元素的宽度（包括内边距和边框）。
outerHeight() 方法返回元素的高度（包括内边距和边框）。

```

##### jQuery 遍历

* 遍历祖先

```
parent() 方法返回被选元素的直接父元素。只会对 DOM 树向上一级进行遍历。$("span").parent();返回每个 <span> 元素的的直接父元素。

parents() 方法返回被选元素的所有祖先元素，它一路向上直到文档的根元素(<html>)。$("span").parents();返回所有 <span> 元素的所有祖先。

parentsUntil() 方法返回介于两个给定元素之间的所有祖先元素。$("span").parentsUntil("div");返回介于 <span> 与 <div> 元素之间的所有祖先元素。
```

* 遍历后代

```
children() 方法返回被选元素的所有直接子元素。只会对 DOM 树向下一级进行遍历。$("div").children();返回每个 <div> 元素的所有直接子元素。

find() 方法返回被选元素的后代元素，一路向下直到最后一个后代。$("div").find("span");返回属于 <div> 后代的所有 <span> 元素。若要获取 <div> 的所有后代，则参数为 "*" 。
```

* 遍历同胞

```
siblings() 方法返回被选元素的所有同胞元素。$("h2").siblings();返回 <h2> 的所有同胞元素。

next() 方法返回被选元素的下一个同胞元素。$("h2").next();返回 <h2> 的下一个同胞元素。

nextAll() 方法返回被选元素的所有跟随的同胞元素。$("h2").nextAll();返回 <h2> 的所有跟随的同胞元素。

nextUntil() 方法返回介于两个给定参数之间的所有跟随的同胞元素。$("h2").nextUntil("h6");返回介于 <h2> 与 <h6> 元素之间的所有同胞元素。

prev(), prevAll() & prevUntil() 与 相应 next 方法只是方向上的差异。
```

* 过滤

```
first() 方法返回被选元素的首个元素。$("div p").first();选取首个 <div> 元素内部的第一个 <p> 元素。

last() 方法返回被选元素的最后一个元素。$("div p").last();选择最后一个 <div> 元素中的最后一个 <p> 元素。

eq() 方法返回被选元素中带有指定索引号的元素，索引号从 0 开始，因此首个元素的索引号是 0 而不是 1。$("p").eq(1);选取第二个 <p> 元素。

filter() 方法允许您规定一个标准。不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回。$("p").filter(".url");返回带有类名 "url" 的所有 <p> 元素。

not() 方法返回不匹配标准的所有元素。not() 方法与 filter() 相反。
```

##### AJAX 简介

* AJAX = 异步 JavaScript 和 XML（Asynchronous JavaScript and XML）。简短地说，在不重载整个网页的情况下，AJAX 通过后台加载数据，并在网页上进行显示。
* jQuery 提供多个与 AJAX 有关的方法。
* 通过 jQuery AJAX 方法，您能够使用 HTTP Get 和 HTTP Post 从远程服务器上请求文本、HTML、XML 或 JSON - 同时您能够把这些外部数据直接载入网页的被选元素中。
* 如果没有 jQuery，AJAX 编程还是有些难度的 。因为不同的浏览器对 AJAX 的实现并不相同，所以使用常规AJAX 代码时就必须要编写额外的代码对不同浏览器进行测试；然而 jQuery 团队为我们解决了这个难题，所以 通过 jQuery 使用 AJAX 就避免以上问题。
* load() 方法从服务器加载数据，并把返回的数据放入被选元素中。
```
$(selector).load(URL,data,callback);
    URL 必需的  参数规定您希望加载的 URL。
    data 可选的 参数规定与请求一同发送的查询字符串键/值对集合。
    callback 可选的参数是load()方法完成后所执行的函数名称。


$("#idx").load("demo_test.txt",function(responseTxt,statusTxt,xhr){

});
    responseTxt - 包含调用成功时的结果内容
    statusTXT - 包含调用的状态
    xhr - 包含 XMLHttpRequest 对象
```
* $.get() 方法通过 HTTP GET 请求从服务器上请求数据。

```
$.get(URL,callback);
    必需的 URL 参数规定您希望请求的 URL。
    可选的 callback参数是请求成功后所执行的函数。

$.get(url,function(data,status){

});

```

* $.post() 方法通过 HTTP POST 请求从服务器上请求数据。

```
$.post(URL,data,callback);
    必需的 URL 参数规定您希望请求的 URL。
    可选的 data 参数规定连同请求发送的数据。
    可选的 callback参数是请求成功后所执行的函数。

$.post(url,
        {
            name:"百度",
            url:"http://www.baidu.com"
        },
        function(data,status){

        }
    );
```

##### 其他

* noConflict() ：jQuery 使用 $ 符号作为 jQuery 的简写，如果其他 JavaScript 框架也使用 $ 符号作为简写，这就会引起冲突。这种冲突的存在也就是该函数所要解决的问题。

```
1. noConflict() 方法会释放  $ 标识符的控制，这样其他脚本就可以使用它。
2. 创建自己的简写。noConflict() 可返回对 jQuery 的引用，把它存入变量，以供稍后使用。var jq = $.noConflict();
3. 将 $ 作为函数参数 ，这样函数内部依旧可以使用 $ ;但函数外不可以。
```
