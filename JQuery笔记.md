### jQuery是一个快速、简洁的avaScript代码库（或JavaScript框架）。jQuery设计的宗旨是“write Less，Do More”，即倡导写更少的代码，做更多的事情。它封装JavaScript常用的功能代码，提供一种简便的JavaScript设计模式，优化HTML文档操作、事件处理、动画设计和Ajax交互。

### 1.    获取源文件  2.    引入页面
+ 如果使用了第三方jquery插件（日历、滚动、瀑布流等），必须先引入jquery，再引入该插件。

### 入口函数 
+ $(document).ready(function(){});
+ $(function(){});  推荐
####  入口函数 区别
+ 执行时间   window.onload必须等到页面内包括图片的所有元素加载完毕 $(document).ready()是DOM结构绘制完毕后就执行，不必等到加载完毕
+ 编写个数不同  window.onload不能同时编写多个，会覆盖前一个  $(document).ready()可以同时编写多个，并且都可以得到执行


### jQuery的两个变量：$ 和 jQuery 

### JQ 选择器
+ 类选择器 
+ Id选择器
+ 标签选择器

#### JQ 选择器-层级选择器
+ $(“div  span”)  后代选择器  选择所有的后代元素
+ $(“div > span”)  子代选择器 选择所有的子代元素
+ $(“div + p”)  紧邻选择器  选择紧挨着的下一个元素
+ $(“div ~ p”) 兄弟选择器 选择后面的所有的兄弟元素

#### JQ 选择器-过滤选择器
+ $(“li:eq(index)”)  index是从0开始的一个数字  选择序号为index的元素。选择第一个匹配的元素
+ $(“li:gt(index)”)  选择序号大于index的元素
+ $(“li:lt(index)”)  选择小于index 的元素
+ $(“li:odd”)   选择所有序号为奇数行的元素
+ $(“li:even”)  选择所有序号为偶数的元素
+ $(“li:first”)  选择匹配第一个元素
+ $(“li:last”)   选择匹配的最后一个元素

#### JQ 选择器-属性选择器
+ $(“a[属性名]”)   选择所有包含这个属性的元素
+ $(“a[属性名=属性值]”)    选择所有属性  等于   这个属性值的元素
+ $(“a[属性名!=属性值]”)   选择所有属性  不等于 这个属性值的元素 包括没有这个属性的元素
+ $(“a[属性名^=字符]”)     选择所有以这个字符（例如web）  开头 的元素
+ $(“a[属性名$=字符]”)     选择所有以这个字符（例如web）  结尾 的元素
+ $(“a[属性名*=字符]”)     选择所有包含这个字符的元素，可以是中英文
+ $(“a[属性名][title=’内容’]”)    选择所有符合指定属性规则的元素， 都符合  才会被选中。

####  JQ 选择器-筛选选择器
+ $(“#j_wrap”).find(“li”)   查找指定元素（id为j_wrap）的所有后代元素（子子孙孙）（后代元素li）  
+ $(“#j_wrap”).children(“ul”)  查找指定元素的  直接子元素（亲儿子元素） 
+ $(“#j_wrap”).siblings()   查找所有兄弟元素（不包括自己）
+ $(“#j_wrap”).parent(“ul”)    查找父元素（亲的）
+ $(“li”).eq(2)     查找指定元素的 第index个 元素，index是索引号，从0开始

### JQuery 事件 
+ jquery中 的事件处理都是方法    事件源.onclick = function(){ }
+ js的事件处理是属性  事件源.click( function(){} )

### mouseover事件跟mouseenter事件的区别
+ mouseover/mouseout  每遇到一个子元素就会触发一次
+ mouseenter/mouseleave   鼠标经过的时候只会触发一次 


### DOM对象跟jQuery对象相互转换
+ jQuery对象转换成DOM对象
    - 方式一：$(“#btn”)[0]
    - $(“#btn”).get(0)
+ DOM对象转换成jQuery对象
    - $( document.getElementById(“btn”) );


### JQuery API

#### 操作 样式
+ $(select).css('样式':'值','样式','值')  
+ .css()获取样式

#### 操作 属性
+ $(select).attr('属性','值')   
+ .attr()获取属性    
+ .removeAttr('属性')删除属性

#### 操作值
+ $(select).text()文本  
+ .html()包含标签    
+ .val()获取表单

#### 操作类  不会改变之前类名
+ $(select).addClass('类名')    向被选元素添加一个或多个类 
+ $(select).removeClass('类名')   从被选元素删除一个或多个类 
+ $(select).toggleClass('类名')   对被选元素进行添加/删除类的切换操作  
+ $(select).hasClass()    判断是否存在类,如果不写参数   写参数判断是否存在该类名

#### DOM 查找
+ .siblings()  除了自己以外的所有的兄弟节点
+ .next()	下一个兄弟
+ .nextAll()		后面所有的兄弟
+ .nextUntil()	后面所有的兄弟直到…
+ .prev()	前面的兄弟
+ .prevAll()		前面所有的兄弟
+ .prevUntil()		…
+ .parent()		
+ .parents()		所有的父节点
+ .parentsUntil()


#### JQuery 动画
+ show()  让匹配的元素展示出来  
    - 参数一时间(slow：600ms、normal：400ms、fast：200ms)
    - 参数二 function(){}
+ hide()  让匹配元素隐藏掉   用法参考show方法
+ slideDown(speed(时间),callback(回调函数))  滑入(显示)    默认值：400毫秒  
+ slideUp()  滑出(隐藏)
+ slideToggle(speed,callback)   滑入滑出切换
+ fadeIn(speed, callback)  淡入
+ fadeOut()   淡出
+ fadeToggle() 淡入淡出切换
+ fadeTo(时间, 透明度)    改变透明度到某个值     0全透，1全不透
+ $(selector).animate(styles,speed,easing,callback)    自定义动画
    - 第一个参数表示：要执行动画的CSS属性（必选）
    - 第二个参数表示：执行动画时长（可选）
    - 第三个参数表示：运行的轨迹 
    - 第四个参数表示：动画执行完后立即执行的回调函数（可选）
+  .stop(stopAll,goToEnd)  停止动画
    - stopAll  是否全部停止，默认false 停止队列中所有的动画
    - goToEnd  是否将停止的动画  停止在当前动画的最后一个状态

#### 节点操作
+ 创建元素 var node = $(“#box1”).html('代码')
+ 添加元素
    - append(参数)  在元素的最后一个  子元素  后面追加元素
    - appendTo()  在被选元素内部的最后一个 子元素（或内容）后面  插入内容  
    - prepend() 在元素的 第一个子元素  前面追加内容或节点  
    - after()  在被选元素之后，作为  兄弟元素  插入内容或节点
    - before()  在被选元素之前，作为  兄弟元素  插入内容或节点
+ 清空元素
    - empty()
    - html('')
    - remove()   会把对象也删除
+ clone()   复制元素 

#### 操作form表单  .prop()  多选  单选  是否被选中 

#### 尺寸位置操作（bom）
+ 高度和宽度操作
    - height() / width()   取值类型为num  可以直接参与运算
+ 坐标值操作 
    - offset()  坐标值操作  获取或设置元素  相对于文档  的位置   设置offset后，如果元素没有定位(默认值：static)，则被修改为relativ
    - position()  获取   相对于其  最近  的   具有定位的父元素   的位置    只能获取，不能设置
    - scrollTop()  获取或者设置  元素垂直方向  滚动的位置   例如页面的返回顶部
    - scrollLeft()  获取或者设置  元素水平方向  滚动的位置


###  JQuery 事件机制

#### JQuery 事件绑定
+ bind方式（不推荐，1.7以后的jQuery版本被on取代）
+ delegate方式（特点：性能高，支持动态创建的元素）
+ on方式   建议使用 
####  JQuery 事件解绑  
+ unbind() 方式   解绑 bind方式绑定的事件
+ undelegate() 方式
+ off解绑on方式绑定的事件

#### 事件触发
+ $(selector).trigger(“click”)
+ $(selector).triggerHandler(“click”)
##### triggerHandler与 trigger() 方法相比的不同之处
+ triggerHandler 不会引起事件（比如表单提交）的默认行为
+ trigger() 会操作 jQuery 对象匹配的所有元素，而 .triggerHandler() 只影响第一个匹配元素
+ 由 .triggerHandler() 创建的事件不会在 DOM 树中冒泡；如果目标元素不直接处理它们，则不会发生任何事情
+ triggerHandler()方法的返回的是事件处理函数的返回值，而不是具有可链性的 jQuery 对象。此外，如果没有处理程序被触发，则这个方法返回 undefined

####  事件委托 例如给li绑定点击事件，后添加的li不会绑定点击事件，此时就可以使用事件委托

+ on方法委托  第一个参数：事件类型  第二个参数：将事件给谁  第三个参数：执行程序
```
$('ul').on('click','li',function(){
        alert($(this).text());
 }) 
```
+ 也可以使用even实现事件委托 
```
 $('ul').click(function(event){
     //event.target == $('li')
     alert($(event.target).text());
})
```

#### jQuery事件对象介绍
+ event.currentTarget   绑定事件的元素
+ event.target  触发事件的元素
+ event.stopPropagation()；	阻止事件冒泡
+ event.preventDefault(); 	阻止默认行为
+ event.keyCode  键盘按键代码
+ event.type  事件类型：click....

#### 链式编程 例如:$(select).css({width:'100px',}).css({heigth:'100px',})  .css() 方法执行后返回的是当前事件源this
####  链式编程  end(); // 结束当前链最近的一次过滤操作，并且返回匹配元素之前的状态。 

#### 隐式迭代 在方法的内部会为匹配到的所有元素进行循环遍历，执行相应的方法；而不用我们再进行循环，简化我们的操作，方便我们调用  例如 $('li').click(function(){})  没有循环遍历 也给所有li元素绑定了点击事件

#### each方法 大部分情况下是不需要使用each方法的，因为jQuery的隐式迭代特性 如果要对每个元素做不同的处理，这时候就用到了each方法  $(selector).each(function(index,element){ })  Element是一个 js对象，需要转换成jquery对象

### 多库共存  $.noConflict()  jQuery占用了$ 和jQuery这两个变量  当在同一个页面中引用了jQuery这个js库，并且引用的其他库（或者其他版本的jQuery库）中也用到了$或者jQuery这两个变量，其他一些 JavaScript 框架 某些框架也使用 $ 符号作为简写 两种不同的框架正在使用相同的简写符号，有可能导致脚本停止运行  $.noConflict();让jQuery释放对$的控制权 让其他库能够使用$符号  此后，只能使用   jQuery    来调用jQuery提供的方法


### 自定义插件
+ $.名字 = function() {};  全局jQuery函数扩展方法  调用 $.名字(如果function有参数就写参数) 
+ $.fn. 名字 = function() {}   jQuery对象扩展方法   $(select).名字();

