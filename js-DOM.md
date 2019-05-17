### DOM   HTML Document Object Model(文档对象模型)
+ HTML DOM则是专门适用于HTML/XHTML的文档对象模型。可以将HTML DOM理解为网页的API。DOM 将文档解析为一个由节点和对象（包含属性和方法的对象）组成的结构集合, 是web页面的完全的面向对象表述，简言之，它会将web页面和脚本或程序语言连接起来。 它能够使用如 JavaScript等脚本语言进行修改。

### DOM节点 (HTML的组成部分)
+ 在HTML当中一切都是节点,整个文档就是一个文档节点,每一个HMTL标签都是一个元素节点,标签中的文字则是文字节点,标签的属性是属性节点

### DOM节点的获得
+ 通过ID名获取  document.getElementById("ID名"); 最准确的，必须有id，而且一个页面不能有重复的id
+ 通过class名获取 获取的是一个数组 所以如果需要精确查找到某一个节点 必须带有下标,下标为这个节点在页面的第几个(从0开始)  document.getElementsByClassName("class名")[下标];  注意:通过类名查找 HTML 元素在 IE 5,6,7,8 中无效
+ 通过标签获取 获取的是一个数组 其他同上  document.getElementsByTagName("标签")[下标];

### DOM节点关系   DOM的节点并不是孤立的，因此可以通过DOM节点之间的相对关系对它们进行访问
+ 父节点 parentNode   一个节点只有一个父节点 调用方式就是  节点.parentNode  
+ 兄弟节点  (上一个与下一个兼容写法原因一样)
- 下一个兄弟节点   兼容写法(兼容写法位置不能交换) 节点.nextElementSibling || 节点.nextSibling
    - nextSibling(嫡出) IE678中指下一个元素节点（标签、注释）,火狐谷歌IE9+(标准)以后都指的是下一个节点（包括空文档和换行节点）
    - nextElementSibling(庶出) 在火狐谷歌IE9+(标准) 都指的是下一个元素节点
- 上一个兄弟节点   兼容写法(兼容写法位置不能交换) 节点.previousElementSibling || 节点.previousSibling
+ 子节点
- 单个子节点 
    - 第一个子元素节点 调用者是父节点 firstChild(嫡出)/firstElementChild(庶出)  同兄弟节点相同
    - 最后一个子元素节点 调用者是父节点 lastChild(嫡出)/lastElementChild(庶出) 同上
- 所有子节点  childNodes(嫡出)/children	(庶出) 
    - childNodes 它是标准属性 返回指定元素的子元素集合 包括HTML节点，所有属性，文本节点,但 火狐 谷歌等高本版会把换行也看做是子节点
    - children 非标准属性  它返回指定元素的子元素集合 它只返回HTML节点，甚至不返回文本节点 但它得到了几乎所有浏览器的支持  children在IE6/7/8中包含注释节点
    - 需要自己封装获取标签子节点的方法 每个节点后又nodeType属性 1代表标签节点(也叫元素节点) 2代表属性节点 3代表文本节点  8代表注释节点

### DOM节点操作(增删改查) 
+ 创建节点  document.createElement();  不插入节点,节点是不会在页面显示
+ 插入节点（使用节点）  
    - 父节点.appendChild();
    - 父节点.insertBefore(要插入的节点，参考节点)；如果参考节点(不能不填,没有需求输入null)为null，那么他将在节点最后插入一个节点。
+ 删除节点 父节点.removeChild（子节点） 不知道父级的情况下，可以这么写：node.parentNode.removeChild(node)
+ 复制节点  被复制的节点.cloneNode（true）   调用这个函数cloneNode()，得到一个新节点 方法内部可以传参，入股是true，深层复制(将元素内所有的元素都进行复制)，如果是false，只复制节点本身

### 节点属性
+ 获取：getAttribute(属性名 例如:class)
+ 设置：setAttribute(属性名, 属性名 )
+ 删除：removeAttribute(属性名)


### 事件
+ 事件源 (要触发的对象)
+ 事件  (怎么触发这个事情,例如:点击事件,)
+ 事件执行的程序代码 (事件处理程序)

#### 常见事件
+ onclick 鼠标点击某个对象
+ onfocus 元素获得焦点
+ onblur 元素失去焦点
+ onchange  用户改变域的内容
+ onmouseover  鼠标被移到某元素之上
+ onmouseout 鼠标从某元素移开



### value和innerHTML和innerText和textContent
+ 老版本的火狐不支持innerText，支持textContent
+ Value只对表单有效果，是属性
+ innerHTML插入可执行的标签，标签和样式会被解析成html，常用于动态生成页面元素
+ innerText 插入文本内容，标签和样式会被当做文本内容处理


### arguments  函数的实参对象 
+ arguments 是一个伪数组 
+ arguments instanceof Array 用于判断  是不是某个构造函数的实例对象  可以判断 是不是数组,是不是函数
+ arguments.callee 返回的是正在执行的函数本身  在使用函数递归调用时推荐使用arguments.callee代替函数本身


### addEventListener 在 html 标签属性中添加事件  可添加多个事件，不会被覆盖
+ 第一个参数: 字符串 事件类型  不带"on"
+ 第二个参数: 函数 (要执行的程序)
+ 第三个参数:  是否捕获执行,默认false   false/true   true==捕获，点此事件先执行
+ 阻止冒泡  event.stopPropagation();  如果不捕获 点重叠位置外层不执行
+ 从里到外   冒泡
+ 从外到里   捕获

### removeEventListener  移除绑定   删除时 ,捕获和冒泡必须是一致的

### setTimeout 延迟定时器 只执行一次 第一个参数要执行的代码 第二个参数 时间（以毫秒为单位）

### setInterval 循环定时器  其他同上

### clearInterval  清除循环定时器

### clearTimeout 清除延迟定时器的 





