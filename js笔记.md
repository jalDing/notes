### js的组成  
+ ECMAscript + dom + bom

### js引入
+ 外部 <script src="引用地址"></script>
+ 内部 可以写在head标签里,也可以在body里边所有标签的末尾

### js输出
+ alert() 页面弹出窗口
+ console.log()  控制台打印(一般调试使用)
+ document.write() 在网页上显示
+ prompt() 弹框,用户可输入信息 js里可获取用户输入的信息 var str = prompt('请输入');
+ confirm 弹框, 选择框

### 变量
+ 声明变量 用 var 关键字 

#### 变量的作用域   
+ 函数 内部的变量 外部是无法获取的
+ 函数内部可以使用外部的变量 
+ 如果函数内部的变量 不声明  则会被认为是全局变量 (不推荐)


### 基本数据  基本数据类型作为参数传递的时候,会在函数内部创建这个数据的副本,做的操作,并不会影响原理数据 
+ 字符串 string 将值用''包裹
+ 数字 number 直接写值
+ 布尔值 boolean  true或者false
+ undefined 
+ null

### 复杂数据类型 栈内存存放的地址 复杂数据类型作为参数传递的时候,会影响外部的参数,因为归根结底地址指向的堆内存中的原数据被修改了
+ object  
   - var object{
      key : value;
      key : value;
   }

#### 数组  var list =[1,'2',3,[25,23]] 数组里可以有数字,字符串,数组
+ 创建方法一  var arr = [];
+ 创建方法二  var arr = new Array(); 

##### 数组方法
+ arr.length  数组的长度
+ arr.concat(arr1)  合并数组
+ arr.split(',', ) 以逗号为条件分隔成数组 第二个参数是数组的长度
+ arr.join('')   join把数组转换为字符串 默认为逗号链接
+ arr.push('元素')  向数组末尾插入新元素
+ arr.unshift('元素') 向数组首位插入新元素
+ arr.shift()  删除数组的第一位
+ arr.pop()   删除数组的最后一位
+ arr.toString()  将数组转换成字符串
+ arr.reverse()  翻转数组
+ arr.sort()  
- 无参：按照数组元素的首字符对应的Unicode编码值从小到大排列数组元素
- 带参：参数必须为函数 函数中带有两个参数 
- 如果计算后（第一个参数(a)-第二个参数(b)） 返回值为负数 a排b前面 等于0不动 返回值为正数，b排a前面
+ arr.indexOf() 从左往右查找对应元素  返回对应数值在数组中的下标 如果查找不到 返回-1
+ arr.lastIndexOf()   从右往左查找对应元素   返回的仍是从左往右的下标 如果查找不到 返回-1
+ arr.slice(start,end) 从数组中截取一个新的数组，不影响原来的数组 
- 参数start从0开始,end从1开始  从原数组哪个下标开始,截取到原来数组的哪个长度 
+ arr.splice()  删除或替换当前数组的某些元素  会修改原数组
- 参数start(从哪个下标开始)
- 参数deleteCount(替换掉几位(也就是去掉删除几位)
- 参数options(要替换的新元素,多个新元素用逗号分隔) 
+ arr.length = 0; /  arr = [];  清空数组

#### 函数 关键词 function  具名和匿名函数不调用不执行
- 具名函数   function 函数名 () { 代码 }  调用 函数名();
- 匿名函数   var sing = function () { 代码 }   调用 sing();
- 自执行函数  ;(function (){ 代码 }();

### 比较运算符
+ 大于>  小于<  等于==(数值一样即可)  严格相等===(不仅数值一样,类型也要一样) 

### string 方法
+ str.charAt()  获取相应位置上(从0开始)的字符 字符串中空格也占位置
+ str.charCodeAt() 获取相应位置上(从0开始)的字符的Unicode 编码
+ str.indexOf() 返回字符在字符串中的位置  返回-1 表示不存在
+ str.lastIndexOf()  获取某个字符在字符串中的最后的位置  返回-1 表示不存在
+ str.concat() 连接字符串 不影响原字符串
+ str.slice(提取的起始位置,字符串中第几个字符(从1开始数)) 
- 只有一个参数  从提取的起始位置提取到字符的末尾

+ str.substr(起始位置,[取的个数 从起始位置开始])  
- 只有一个参数  从提取的起始位置提取到字符的末尾

+ str.toUpperCase()   大写
+ str.toLowerCase()   小写


