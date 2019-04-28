### 选择器
   - #id名 ID选择器,ID名具有唯一性
   - .class名 类名选择器,类名可以被多个标签引用,同时一个标签可以有多个类名
   - 标签  标签选择器,不建议使用 
   - 并集选择器(, , ,)
   - 交集选择器(.class1.class2)
   - 后代选择器(.box .inner-box)

### 权重(样式冲突)  权重一样的时候 ,遵循就近原则  
   - 行内样式(1000) 
   - id选择器(100) 
   - class选择器(10) 
   - 标签选择器(1)
   - *通配符,继承属性(0)
 
 
### 外部样式引用 
    <link rel="stylesheet" href="文件路径">
 
### visibility与display的区别
   - visibility:hidden; 占页面位置
   - display:none; 不占页面位置


### 将元素改成块状标签,行内标签,行内块状标签
   - display:inline  行内标签
   - display:inline-block   行内块状标签
      - inline-block 会造成像素间隙解决方法
         1. 将所有元素写在一行,或者将>写在下一行开头以消除换行符(这个方法在chrome浏览器下没有效果，在IE6/7下残留1像素间隙)
         2. 将元素父类的font-size:0;(ie8，firefox，chrome 和 opera 浏览器下已经没有问题了，但是在 低版本safari 浏览器下还是有问题)
   - display:block 块状标签  

### 嵌套崩塌
   - 当两个盒子嵌套时,子类设置margin-top没有效果作用到父类发生这种现象时
      1. 父类CSS里加 overflow: hidden
      2. 父类CSS里设置padding(极小的)

### target属性跳转的页面(当前页面_self/新页面_blank/父窗口_parent/顶级窗口top)


### 上传按钮,multiple属性可实现多选


### 使用float属性时元素会脱离文档流,后边的元素会顶上来, 解决方法:
   - 可以在float的元素的父元素加overflow: hidden;解决这个问题
   - 在元素后方追加 `<div class="clr"></div> `并设置 .clr{clear:both;} 


### 定位 static (默认)
   - 相对定位 position: relative;
   - 绝对定位 position: absolute; 如果是相对于父类做定位,要在元素的父类元素里加上position: relative
   - 固定定位 position: fixed; 相对于浏览器

### 层级 z-index (有定位属性才能设置) 值越大的元素浮现在上方







### flex(父元素属性 display:flex)

#### flex-direction 排列的方向默认从左上开始横排(row)  
   - row-reverse(横排,从右上开始横排)
   - column(竖直排列从左上向下排)
   - column-reverse(竖直排列从左下向上排)

#### flex-wrap 是否换行默认不换(nowrap)  
   - wrap(换 第一行在上边) 
   - wrap-reverse(换行,第二行位置不变,第一行在第二行下边)

#### flex-flow 排列方向,是否换行的简写默认横着排,不换行

#### justify-content 子元素在父元素主轴上(flex-direction)的对齐方式 默认左对齐(flex-start)
   - flex-end：右对齐
   - center： 居中
   - space-between：两端对齐，项目之间的间隔都相等(左边子元素左对齐,右边子元素右对齐,中间的元素左右距离相等)
   - space-around:每个子元素左右距离相等

### flex(子元素属性)

 + flex-shrink 默认值为1  表示父元素空间不够时,子元素等比例缩小
    - 如果有此属性的子元素的值为0时,父元素空间不足其他(没有赋予flex-shrink:0)的子元素等比列缩小,该子元素大小不变


 + flex-basis 设置子元素在父元素内占据的空间大小 默认值为auto(子元素本来的大小) 设置的是长度(如果横排就是宽,如果竖排就是高)
 

 + order  排列顺序默认为0,数字越小排列越靠前

 + flex-grow 
    - 属性默认为0  父元素有剩余空间也不占满
    - 值为1 父元素里的所有有此属性值的子元素平分父元素的剩余空间
    - 值为2 如果父元素空间有空余,这个子元素占满整个剩余空间

 + align-self 给子元素赋予该属性表示可有和其他子元素不同的对齐方式
    - 默认值auto 继承父元素的对齐方式
    - flex-start 
    - flex-end
    - center 

