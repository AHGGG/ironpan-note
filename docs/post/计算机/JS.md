# 动力节点-课程体系-V9.1.0

课程体系说明：标号1表示必须掌握；标号2表示能够理解；标号3表示简单了解；标号4表示扩展内容，根据学生学习情况自行决定是否讲解。

## WEB前端

### JavaScript

- JavaScript概述

  （1）简称JS
  
  （2）一种脚本语言，脚本语言的特点
  
  （3）JavaScript和JScript的关系
  
  （4）JavaScript主要用来操作HTML中的节点，产生动态效果
  
  （5）JavaScript和Java的区别
  
  JS是一门事件驱动的语言，JS中有很多事件，有一个叫click鼠标单击。任何事件都对应一个事件句柄：onclick，（事件和事件句柄区别是句柄是在事件前加on），事件句柄是以HTML标签的属性存在的，例如`<input type="button" value="hello" onclick="js代码" />`
  
  只是把JS代码注册到按钮的click事件上了，发生事件后，就会被浏览器自动调用
  
  上面的js代码，可以；号结尾，也可以不写

- JavaScript包括三块：ECMAScript、DOM、BOM

  （1）ECMAScript是ECMA制定的262标准，JavaScript和JScript都遵守这个标准，ECMAScript是JavaScript核心语法
  
  （2）DOM（Document Object Model，文档对象模型）编程是通过JavaScript对HTML中的dom节点进行操作，DOM是有规范的，DOM规范是W3C制定的。对网页这个DOM树进行操作的，树上有各种标签----->`var domObj = (window.)document.getElementById(“id”)；//这里其实是省略了window的，window代表这个浏览器窗口，`
  
  （3）BOM编程是对浏览器本身操作，例如：前进、后退、地址栏、关闭窗口、弹窗等。由于浏览器有不同的厂家制造，所以BOM缺少规范，一般只是有一个默认的行业规范。BOM是包含DOM（网页上的东西）的

- 嵌入JS三种方式以及JS的注释

	- 行间事件

	  （1）`<input type="button" value="hello" onclick="window.alert('hello js')" />`
	  
	  （2）JS是一种基于事件驱动型的编程语言，当触发某个事件之后，执行一段代码
	  
	  （3）JS中的任何一个事件都对应一个事件句柄，例如鼠标单击事件click，对应的事件句柄就是onclick，事件句柄都是以标签的属性方式存在。在事件句柄后面可以编写JS代码，当触发这个事件之后，这段JS代码则执行了。在onclick后面的JS代码中，可以调用script标签中，定义的函数。
	  
	  （4）JS中的字符串可以使用单引号括起来，也可以使用双引号括起来
	  
	  （5）window是JS中的内置BOM顶级对象，代表当前浏览器窗口，window对象有一个alert()函数，该函数可以在浏览器上弹出消息框。
	  
	  （6）JS中的一条语句结束后可以使用“;”结尾，也可以不写。
	  
	  （7）window.alert()中的window.可以省略。

	- 页面script标签嵌入

	  （1）对比
		```js
	  <script type="text/javascript">JS代码</script>
	  
	  <style type="text/css">css代码</style>
	    ```

	  （2）`window.alert()`的执行会阻塞当前页面的加载
	  
	  （3）一个页面中可以写多个脚本块
	  
	  （4）脚本块的位置没有限制
	  
	  （5）暴露在脚本块中的JS代码在页面打开的时候遵循自上而下的顺序依次逐行执行
	  
	  alert函数有阻塞整个页面加载的作用

	- 外部引入

	  （1）
	  ```JS 
	  <script type="text/javascript" src="js文件路径"></script>
	  ```
	  （2）
	  ```JS
	  <script type="text/javascript" src="js文件路径">这里不能写JS代码</script>
	  ```
	  （3）这种写法错误：
	  ```JS 
	  <script type="text/javascript" src="js文件路径"/>
	  ```

	  （4）这里是`src`，什么时候是`href`，总结整理！！！

- 标识符和关键字

  （1）标识符命名规则和规范按照java执行
  
  （2）关键字不需要刻意记

- 变量

	- 变量的声明与赋值

	  （1）变量未赋值，系统默认赋值undefined
	  
	  （2）JS是一种弱类型编程语言，一个变量可以接收任何类型的数据
	  
	  （3）一行上也可以声明多个变量

	- 函数的定义与调用

	  （1）函数类似于java语言中的方法，是一段可以完成某个功能的可以被重复利用的代码片段
	  
	  （2）定义函数的两种语法
	  第一种：普通函数定义，这种方式较多

	  ```JS
	  function 函数名(形式参数列表){
	  	函数体;
	  }
	  ```
	  例如：
	  
	  ```JS
	  function sum(a, b){
	  	return a + b;
	  }
	  ```

	  >注意：
	  a和b是形式参数列表，也是两个局部变量。
	  JS中的函数不需要指定返回值类型，因为JS是弱类型编程语言，变量可以接收任何类型的数据，也就是说JS中的函数可以返回任何类型的数据，当然也可以不返回任何数据。返回数据使用return语句。
	  >>JS中的函数在调用的时候，实参可以随意，例如调用以上的sum函数，可以这样调用：sum()，没有传任何实参的时候a和b变量没有赋值，则a和b都是undefined。也可以这样调用sum(10)，这样就表示a变量赋值10，b变量仍然是undefined。还可以这样调用：sum(1,2)，这样则表示a是1，b是2。
	  
	  
	  第二种：如果是把函数的声明当做类进行定义这种方式较多
	  
	  ```JS
	  函数名 = function(形式参数列表){
	  	函数体;
	  }
	  ```
	  例如：
	  
	  ```JS
	  sum = function(a, b){
	  	return a + b;
	  }
	  ```

	  （3）JS中的函数定义在脚本块中，页面在打开的时候，函数并不会自动执行，函数是需要手动调用才能执行的。
	  
	  （4）由于JS是一种弱类型编程语言，所以函数不能同名，没有重载机制
	  
	  （5）这样的代码顺序是可以的，页面打开的时候会先进行所有函数的声明，函数声明优先级较高。

	  ```JS
	  <script type="text/javascript">
	  	sayHello();
	  	
	  	function sayHello(){
	  		alert("Hello JS");
	  	}
	  </script>
	  ```

	  （6）用户点击按钮，调用函数

	  ```JS
	  <script type="text/javascript">
	  	function sayHello(){
	  		alert("hello js");
	  	}
	  </script>
	  <input type="button" value="hello" onclick="sayHello();"/>
	  ```
	  比较：
	  ```JS
	  var a,b,c=200; 
	  ```
	  只有c是200，其他都是undefined

	- 局部变量和全局变量

	  （1）局部变量：函数的形参是局部变量，另外使用var关键字在函数体中声明的变量是局部变量，函数执行结束之后，局部变量的内存就释放了。
	  
	  （1.1）函数开始执行，局部变量的内存空间开辟，函数执行结束后偶，局部变量的内存空间释放。
	  
	  （2）全局变量：在函数体外声明的变量属于全局变量，另外不使用var关键字声明的变量无论位置在哪，它都是全局变量，全局变量在浏览器关闭时销毁。少用，占用浏览器资源
	  
	  （2.1）如果一个变量在声明的时候，没有加上var关键字，无论在哪儿声明的都是全局变量。

- JS数据类型

	- typeof运算符

		- JS中为什么会有typeof运算符

		  可以在程序的运行阶段动态的获取变量的数据类型，你写完函数了，别人可能传入其他的数据类型，反正都是弱类型

		- typeof运算符怎么用，代码怎么写

		  语法格式是：
		  ```JS
		  	function sum(a, b){
		  		if("number" === typeof a && "number"=== typeof b){
		  			return a + b;
		  		}
		  		alert("数据格式不合法");
		  		return 0;
		  	}
			```
		- typeof运算符的运算结果都是全部小写的字符串

		  "undefined"
		  
		  "number"
		  
		  "string"
		  
		  "boolean"
		  
		  "object" （typeof null）输出就是object，而不是原始类型的null
		  
		  "function"
		  
		  >typeof运算符的运算结果都是这几个小写的字符串之一
		  
		  字符串比较使用`==`完成
		  
		  ```JS
		  function sum(a,b){
		  if(typeof a == "number" && typeof b == "number"){
		  	return a+b;
		  }
		  alert(a+","+b+"必须都是数字");
		  }
		  ```

	- ES6版本之前的数据类型有6种

		- Undefined

		  只有一个值undefined，变量声明没赋值，系统默认赋值undefined

		- Number

		  （1）Number类型包括哪些值：0,1，-1,3.14,12,300，NaN，Infinity（除数为0的时候）
		  
		  NaN：运算结果本来是一个数字，但是运算过程导致不是一个数字的时候，就是NaN，比如100/“中国人”，/除法的结果本来应该是数字，但是不是，就是NaN。+号两边只要有一边是字符串，**优先做拼接**，不是求和。
		  
		  （2）`parseInt()函数`：将字符串自动转换成数字，并且取整数位
		  
		  （3）`parseFloat()函数`：自动将字符串转换成数字。
		  
		  （4）`Math.ceil()函数`：向上取整
		  
		  （5）`isNaN(数字)函数`：如果不是一个数字，结果是true。

		- String

		  （1）可以使用单引号，也可以用双引号
		  
		  两种方式：
		  第一种：
		  ```JS
		  var s = "abc";
		  ```

		  第二种（使用JS内置的支持类String）： 
		  ```JS
		  var s2 = new String("abc");
		  ```

		  需要注意的是：String是一个内置的类，可以直接用，String的父类是Object。
		  
		  // 小string(属于原始类型String)

		  ```JS
		  var x = "king";
		  alert(typeof x); // "string"
		  ```   

		  // 大String(属于Object类型):
		  ```JS
		  var y = new String("abc");
		  alert(typeof y); // "object"
		  ```

		  （2）JS中的字符串包括小String，也包括大String，小String属于原始类型，大String是JS的内置对象，大String属于Object类型。
		  
		  （3）无论大String还是小String，它们的属性(**“abc”.length**:字符串abc的长度)和方法都是**通用的**。
		  
		  （4）字符串中常用方法讲一些，主要讲解字符串的substr()和substring()的区别。函数原型：
		  ```JS
		  substr(startIndex, length)
		  
		  substring(startIndex, endIndex) //注意:不包含endIndex
		  ```

		  常用函数：
		  indexOf：获取指定字符串在当前字符串中第一次出现处的索引，>=0就包含，其他情况就不包含

		  lastIndexOf：获取指定字符串在当前字符串中最后一次出现处的索引
		  
		  replace：替换
		  
		  substr：截取子字符串
		  
		  substring：截取子字符串
		  
		  toLowerCase：转换小写
		  
		  toUpperCase：转换大写
		  
		  split：拆分字符串

		- Null

		  （1）该类型只有一个值：null
		  
		  （2）typeof运算符的执行结果是"object"

		- Boolean

		  （1）只有两个值：true和false
		  
		  （2）Boolean()函数：阿静非布尔类型转换成布尔类型，
		  
		  （3）JS中的if语句自动调用Boolean()函数！！！规律：“有”就转换成“true”，“没有”就转换成“false”，
		  
		  >true：1、“abc”、Infinity，
		  
		  >false：0、“”、null、NaN、undefined

		- Object

		  （1）JS中如何定义一个类。
		  
		  （2）JS中如何创建一个对象。
		  
		  （3）JS中如何访问对象属性，调用对象的方法。
		  
		  （4）JS中的一个函数，既是函数声明，又是类的定义，同时函数名也可以看做构造方法名。直接调用函数表示普通函数调用，如果使用new运算符来调用该函数则会创建对象。
		  
		  （5）使用prototype属性动态的给对象扩展属性以及方法。
		  
		  ---
		  
		  Object类型:  
		  
		  1、Object类型是所有类型的超类，自定义的任何类型，默认继承Object。
		  
		  2、Object类包括哪些属性？
		  
		  prototype属性（常用的，主要是这个）：作用是给类动态的扩展属性和函数。
		  
		  constructor属性
		  
		  3、Object类包括哪些函数？
		  
		  toString() 
		  
		  valueOf() 
		  
		  toLocaleString()
	
		  4、在JS当中定义的类默认继承Object，会继承Object类中所有的属性以及函数。
		      换句话说，自己定义的类中也有prototype属性。
		      
		  
		  5、在JS当中怎么定义类？怎么new对象？
		          定义类的语法：
		              第一种方式：
		  ```js
		                  function 类名(形参){
		                      
		                  }
		  ```
		              第二种方式：
		  ```js
		                  类名 = function(形参){
		                      
		                  }
		  ```
		          创建对象的语法：
		  ```js
		              var name = new 构造方法名(实参); // 构造方法名和类名一致。
		  ```

		  ---
		  
		  如果使用了new，就把这个当做类 来创建对象，不使用 就当做普通的函数来调用
		  
		  ---
		  
		  ```js
		  // JS中的类的定义,同时又是一个构造函数的定义
		  // 在JS中类的定义和构造函数的定义是放在一起来完成的.
		  function User(a, b, c){ // a b c是形参,属于局部变量.
		      // 声明属性 (this表示当前对象)
		      // User类中有三个属性:sno/sname/sage
		      this.sno = a;
		      this.sname = b;
		      this.sage = c;
		  }
		  
		  ---
		  
		  // 创建对象
		  var u1 = new User(111, "zhangsan", 30);
		  // 访问对象的属性
		  alert(u1.sno);
		  alert(u1.sname);
		  alert(u1.sage);
		  
		  var u2 = new User(222, "jackson", 55);
		  alert(u2.sno);
		  alert(u2.sname);
		  alert(u2.sage);
		  
		  // 访问一个对象的属性,还可以使用这种语法
		  alert(u2["sno"]);
		  alert(u2["sname"]);
		  alert(u2["sage"]);
		  
		  ---
		  - 在类中定义函数: 
		  Product = function(pno,pname,price){
		      // 属性
		      this.pno = pno;
		      this.pname = pname;
		      this.price = price;
		      // 函数
		      this.getPrice = function(){
		          return this.price;
		      }
		  }
		  
		  var xigua = new Product(111, "西瓜", 4.0);
		  var pri = xigua.getPrice();
		  alert(pri); // 4.0
		  
		  ---
		  
		  - prototype给类添加属性
		  Product.prototype.getPname = function(){
		      return this.pname;
		  }
		  
		  // 调用后期扩展的getPname()函数
		  var pname = xigua.getPname();
		  alert(pname)
		  
		  ---
		  
		  // 给String扩展一个函数
		  String.prototype.suiyi = function(){
		      alert("这是给String类型扩展的一个函数，叫做suiyi");
		  }
		  
		  "abc".suiyi();
		  ```
		  ---
		  
		   - java和js定义类的比较
		      java语言怎么定义类，怎么创建对象？（强类型）
		  ```java
		          public class User{
		              private String username;
		              private String password;
		              public User(){
		                  
		              }
		              public User(String username,String password){
		                  this.username = username;
		                  this.password = password;
		              }
		          }
		          User user = new User();
		          User user = new User("lisi","123");
		  ```
		          
		      JS语言怎么定义类，怎么创建对象？（弱类型）
		  ```js
		          User = function(username,password){
		              this.username = username;
		              this.password = password;
		          }
		          var u = new User();
		          var u = new User("zhangsan");
		          var u = new User("zhangsan","123");
		  ```

			- 引用类型

	- ES6版本及之后包括的数据类型有7种

	  除了以上6种类型之外，还有一种类型叫做：Symbol

- null NaN undefined区别

  （1）=、==、===三者的区别
  
  （2）null NaN undefined三者类型不同，null和undefined的值可以等同
  
  NaN：not a number，两个undefined相加，就是NaN，"jack"+undefined--->jackundefined
  
  两个同名函数，谁在后面声明，谁就做主，后面的会覆盖前面声明的函数
  
  null是object类型，undefined是undefined类型，NaN是number类型
  
  null和undefined可以等同，其他的几种搭配，都不能等同
  
  ==：等同运算符，只比较值
  ===：判断值和数据类型是否相等

- JS中的事件

	- 常用事件

	  （1）blur失去焦点，光标去别的地方
	  
	  （2）change下拉列表选中项改变，或文本框内容改变
	  
	  （3）click鼠标单击
	  
	  （4）dblclick鼠标双击
	  
	  （5）focus获得焦点
	  
	  （6）keydown键盘按下
	  
	  （7）keyup键盘弹起
	  
	  （8）load页面中所有的元素加载完毕，天天用
	  
	  （9）mousedown鼠标按下
	  
	  （10）mouseover鼠标经过

	  （11）mousemove鼠标移动
	   
	  （12）mouseout鼠标离开
	  
	  （13）mouseup鼠标弹起
	  
	  （14）reset表单重置
	  
	  （15）select文本框中文字被选定

	  （16）submit表单提交


	- 注册事件的两种方式

	  （1）在标签中使用事件句柄的方式注册事件onclick，后面执行js代码
	  `<body onload="sayHello()"></body>`

	  // 对于当前程序来说,sayHello函数被称为回调函数(callback函数)
	  
	  // 回调函数的特点:自己把这个函数代码写出来了,但是这个函数不是自己负责调用,由其他程序负责调用该函数.
	  
	  回调函数：我写好了，不管了，你们去调，在我看来那个函数就是回调函数
	  
	  这里sayHello注册到按钮上，等待click时间发生后，被浏览器调用，称这个函数为回调函数。
	  
	  （2）在页面加载完毕后使用JS代码给元素绑定事件
	  ```js 
	  <script>
	  	window.onload = sayHello;
	  </script>
	  <script>
	  	window.onload = function(){
	  	}
	  </script>
	  ```
	  
	  重点：通过事件注册，理解回调函数的概念
	  
	  // 第一步:先获取这个按钮对象(document是全部小写，内置对象，可以直接用，document就代表整个HTML页面)
	  ```js
	  var btnObj = document.getElementById("mybtn");
	  ```
	  // 第二步:给按钮对象的onclick属性赋值
	  ```js
	  btnObj.onclick = doSome; // 注意:千万别加小括号. btnObj.onclick = doSome();这是错误的写法.
	  ```
	  // 这行代码的含义是,将回调函数doSome注册到click事件上.这里要求要将doSome()函数先写出来，但是也可以写匿名函数：：：：
	  ```js
	  mybtn1.onclick = function(){ // 这个函数没有名字,叫做匿名函数,这个匿名函数也是一个回调函数.
	      alert("test.........."); // 这个函数在页面打开的时候只是注册上,不会被调用,在click事件发生之后才会调用.
	  }
	  ```

	  ---
	  
	  第三种：以后都这么写
	  
	  ```js
	  document.getElementById("mybtn2").onclick = function(){
	      alert("test22222222.........");
	  }
	  ```

		- 属性的使用

		  在点击的时候文本框，修改为复选框
		  ```js
		  <script type="text/javascript">
		      window.onload = function(){
		          document.getElementById("btn").onclick = function(){
		              var mytext = document.getElementById("mytext");
		              // 一个节点对象中只要有的属性都可以"."来修改
		              mytext.type = "checkbox";
		          }
		      }
		  </script>
		  
		  <input type="text" id="mytext"/>
		  
		  <input type="button" value="将文本框修改为复选框" id="btn"/>
		  ```

	- 代码的执行顺序

	  这是一种错误的写法：

	  ```js
	  <body>
	  	<script type="text/javascript">
	  		var elt = document.getElementById("btn");//返回null，执行到此处btn元素还没有加载到内存
	  	</script>
	  	<input type="button" id="btn" value="mybtn"/>
	  </body>
	  ```

	  这样写：
	  ```js
	  <body>
	  	<input type="button" id="btn" value="mybtn"/>
	  	<script type="text/javascript">
	  		var elt = document.getElementById("btn");
	  	</script>
	  </body>
	  ```

	  或者这样写：
	  ```js
	  <body>
	  	<script type="text/javascript">
	  		window.onload = function(){
	  			var elt = document.getElementById("btn").onclick = function(){alert("hello js");}
	  		}//第一个回调函数在页面加载完后执行(onload)，第二个回调函数在鼠标点击后执行，页面打开的时候只是注册函数到事件上去
	  	</script>
	  	<input type="button" id="btn" value="mybtn"/>
	  </body>
	  ```

	- 通过keydown事件演示回车键13，ESC键27

		- 回调函数、接收参数
		  
		  ```js	
		  usernameElt.onkeydown = function(event){
		      if(event.keyCode === 13){
		          alert("正在进行验证....");
		      }
		  }
		  ```
		  
		  这里的onkeydown事件发生后，会调用后面的匿名函数，匿名函数接受“浏览器”传入的事件(可以测试参数个数，只有一个)，然后判断值、类型是不是13就行了，event就是个名字，键盘类的事件都有keyCode属性

- JS运算符之void

  运算符就讲这一个，告诉学生其它运算符和java一样用。void主要讲：javascript:void(0)的用法。
  
  ```js
  <a href="javascript:void(0)" onclick="window.alert('test code')">
      既保留住超链接的样式，同时用户点击该超链接的时候执行一段JS代码，但页面还不能跳转。
  </a>
  ```

  void() 这个小括号当中必须有表达式
  
  其中**javascript:**作用是告诉浏览器，：号后面是一段JS代码。
  
  void(0)代表什么都不返回，是js代码，不是null，不是false，不是undefined

- JS之控制语句

  告诉学生控制语句和Java一样用，课堂上不再讲解。只讲一下for..in语句的使用，使用for..in语句遍历数组，以及遍历一个对象的属性。
  
  java中创建数组：

  ```java
  public class Test{
      public static void main(String[] args){
          int[] arr = {1,2,3,4,5,6};
          int[] arr2 = new int[5]; // 等同于：int[] arr2 = {0,0,0,0,0};
          String[] arr3 = {"a","b","c"};
          String[] arr4 = new String[3]; // 等同于：String[] arr4 = {null,null,null};
      }
  }
  ```

  js中创建数组：
  ```js
  var arr = [false,true,1,2,"abc",3.14]; // JS中数组中元素的类型随意.元素的个数随意.js是自动扩容，放多少个都可以
  
  // 遍历数组
  for(var i = 0; i < arr.length; i++){
      alert(arr[i]);
  }
  
  // for..in，这里的i是数组元素的下标
  for(var i in arr){
      //alert(i);
      alert(arr[i]);
  }
  
  //for遍历属性
  for(var shuXingMing in u){
      //alert(shuXingMing)
      //alert(typeof shuXingMing) // shuXingMing是一个字符串
      alert(u[shuXingMing]);//和.号访问元素是一样的，详细的使用方法在下面
  }
  
  //访问元素的两种方法
  User = function(username,password){
      this.username = username;
      this.password = password;
  }
  
  var u = new User("张三", "444");
  alert(u.username + "," + u.password);
  alert(u["username"] + "," + u["password"]);
  //上面都是访问User类元素的username属性和password属性，注意：第二种方式[]号里面要用“”号框起来，所以上面的for(var 属性名 in u)遍历，要访问数组元素，只能使用第二种方式，u["属性名"]，，for里面的属性名默认是用“”框起来的？？应该是
  ```

- JS内置对象

	- Array

	  （1）了解Array创建数组
	  
	  （2）JS中的数组特点
	  
	  （3）JS中数组对象常用方法：push，pop，join，reverse等。
	  
	  （4）数组遍历
	  
	  创建数组
	  ```js
	  var array = [xx,xs,dfs,12,"asdf"];
	  ```

	  自动扩容，中间凡是没有传值的都是undefined。
	  
	  数组的for循环遍历，和C是一样的。

		- 009-内置支持类Array.html

	- Date

	  （1）new Date() 获取当前系统时间

	  （2）new Date().getTime()获取时间戳

	  （3）new Date().getFullYear()、getMonth()等方法。

- BOM和DOM的区别与联系
- DOM编程案例

	- innerHTML innerText操作div和span

	  innerText和innerHTML属性有什么区别？
	      相同点：都是设置元素内部的内容。
	      不同点：
	          innerHTML会把后面的“字符串”当做一段HTML代码解释并执行。
	          innerText，即使后面是一段HTML代码，也只是将其当做普通的字符串来看待。

	- JS的正则表达式(Regular Expression)

		- 正则表达式概述

		  （1）正则表达式是一门独立的学科，不止用在JS中
		 
		  （2）正则表达式专门用来做字符串格式匹配的

		- 常用的正则表达式符号

		  参考30分钟入门正则表达式：
		  ```text
		  ^    字符串开始
		  $    字符串结束
		  \s    空白
		  *    0~N次
		  +    1~N次
		  ?    0或1次
		  {3}    3次
		  {3,}    3~N次
		  {3,5}    3~5次
		  (a|b)    a或b
		  [a-z]    a到z
		  [^abc]    不是abc
		  ```

		- 会写简单的正则表达式

		  （1）qq号正则
		 
		  （2）必须由数字和字母组成，不能含有其它符号的正则
		 
		  （3）给学生一些常用的正则表达式

		- 会创建JS中的正则表达式对象

		  （1）
		  ```js
		  var regExp = new RegExp("^[1-9][0-9]{4,}$")/，“flags“;
		  ```

		  （2）
		  ```js
		  var regExp = /^[1-9][0-9]{4,}$/flags;
		  ```

		  关于flags：
		  ```text
		      g：全局匹配
		      i：忽略大小写
		      m：多行搜索（ES规范制定之后才支持m。）当前面是正则表达式的时候，m不能用。只有前面是普通字符串的时候，m才可以使用。
		  ```

		  如果第二种，//中是正则表达式，flags不能使用m

		- 会调用JS中正则表达式对象的test()函数

		  写一个校验用户名只能由数字和字母组成的案例

		- 案例

			- qq号匹配
			```js
			  QQ号的正则表达式：
			  ^[1-9][0-9]{4,}$ 
			  ^:字符串开始 
			  $:字符串结束 
			  [1-9]:1-9的任意数字一次默认后面加上了{1}次数，出现一次，
			  [0-9]{4,}:0-9的数字出现4或更多次
			```
			- -号不同的意思
				```js
			  [A-Za-z0-9]：表示A-Z a-z 0-9中的任意1个字符
			  ```
			  ```js
			  [A-Za-z0-9]-：表示A-Z、a-z、0-9、-号中的任意1个字符，前面的-号代表范围，最后一个-号
			  ```

			- 邮箱匹配
			  ```js
			  <body>
			  <script text="javascript">
			  window.onload = function(){
			          // 给按钮绑定click
			          document.getElementById("btn").onclick = function(){
			              var email = document.getElementById("email").value;
			              var emailRegExp = /^\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$/;
			              var ok = emailRegExp.test(email);
			              if(ok){
			                  //合法
			                  document.getElementById("emailError").innerText = "邮箱地址合法";
			              }else{
			                  // 不合法
			                  document.getElementById("emailError").innerText = "邮箱地址不合法";
			              }
			          }
			          // 给文本框绑定focus，光标回去的时候，后面的文字就消失
			          document.getElementById("email").onfocus = function(){
			              document.getElementById("emailError").innerText = "";
			          }
			      }
			      
			  </script>
			  
			  <input type="text" id="email" />
			  <span id="emailError" style="color: red; font-size: 12px;"></span>
			  <br>
			  <input type="button" value="验证邮箱" id="btn" />
			  
			  </body>
			  ```

			- trim函数
			  ```js
			  <script text="javascript">
			              window.onload = function(){
			                  document.getElementById("btn").onclick = function(){
			                      // 获取用户名
			                      var username = document.getElementById("username").value;
			                      // 去除前后空白
			                      username = username.trim();
			                      // 测试
			                      alert("--->" + username + "<----");
			                  }
			          </script>
			          <input type="text" id="username" />
			          <input type="button" value="获取用户名" id="btn" />
			  ```

				- 手动扩展trim函数
				  ```js
				  String.prototype.trim = function(){
				      // alert("扩展之后的trim方法");
				      // 去除当前字符串的前后空白
				      // 在当前的方法中的this代表的就是当前字符串.
				      //return this.replace(/^\s+/, "").replace(/\s+$/, "");
				      return this.replace(/^\s+|\s+$/g, "");
				  }
				  ```
				  
				  以上代码是在script标签里的js代码

	- 表单验证

	  （1）用户名不能为空
	  
	  （2）用户名必须在6-14位之间
	  
	  （3）用户名只能有数字和字母组成，不能含有其它符号（正则表达式）
	  
	  （4）密码和确认密码一致，邮箱地址合法。
	  
	  （5）统一失去焦点验证，鼠标离开就验证
	  
	  （6）错误提示信息统一在span标签中提示，并且要求字体12号，红色。
	  
	  （7）文本框再次获得焦点后，清空错误提示信息，如果文本框中数据不合法要求清空文本框的value
	  
	  （8）最终表单中所有项均合法方可提交

	- 复选框全选和取消全选

	  `document.getElementById()`
	  
	  `document.getElementsByName()`：得到的是名字一样的标签的集合，注意要传入的“xxx”，要用双引号“”框起来传入。
	  
	  `document.getElementsByTagName()`

		- 006-复选框的全选和取消全选.html

	- 获取下拉列表选中项的value

	  change事件

		- 007-获取下拉列表选中项的value.html

	- 显示网页时钟

	  `window.setInterval()`
	  `window.clearInterval()`
	  主要两个函数
	  捎带着提一下`window.setTimeout()`

		- 008-显示网页时钟.html

	- 拼接html的方式，设置table的tbody

	  ```js
	  <table>
	  	<thead></thead>
	  	<tbody id="userListTbody"></tbody>
	  </table>
	  <script>
	  	var html = "";
	  	html += "<tr>";
	  	html += "<td>";
	  	html += "zhangsan";
	  	html += "</td>";
	  	html += "<td>";
	  	html += "2000-10-11";
	  	html += "</td>";
	  	html += "</tr>";
	  	html += "<tr>";
	  	html += "<td>";
	  	html += "lisi";
	  	html += "</td>";
	  	html += "<td>";
	  	html += "2001-10-11";
	  	html += "</td>";
	  	html += "</tr>";
	  	var userListTbody = document.getElementById("userListTbody");
	  	userListTbody.innerHTML = html;
	  <script>
	  ```

	- 要求学生在此之后会使用浏览器的F12

	  会使用F12调试面板：第一会调错；第二会定位并查看HTML页面元素。

	- 案例

		- 将第一个文本框中的value赋值到第二个文本框上

		  ```js
		  <input type="text" id="username" />
		          <input type="button" value="获取文本框的value" id="btn"/>
		          
		          <hr>
		          
		          <script type="text/javascript">
		              window.onload = function(){
		                  document.getElementById("setBtn").onclick = function(){
		                      document.getElementById("username2").value = document.getElementById("username1").value;
		                  }
		              }
		          </script>
		          
		          <input type="text" id="username1" />
		          <br>
		          <input type="text" id="username2" />
		          <br>
		          <input type="button" value="将第一个文本框中的value赋值到第二个文本框上" id="setBtn" />
		  ```

		- 失去焦点事件

		  ```js
		  <input type="text" onblur="alert(this.value)" />
		  ```
		  
		  this代表的是当前input节点对象，this.value就是当前节点的value属性

		- 在div中的文本框
		  ```js
		  <script type="text/javascript">
		      window.onload = function(){
		          var btn = document.getElementById("btn");
		          btn.onclick = function(){
		              // 设置div的内容
		              // 第一步:获取div对象
		              var divElt = document.getElementById("div1");
		              // 第二步:使用innerHTML属性来设置元素内部的内容
		              // divElt.innerHTML = "fjdkslajfkdlsajkfldsjaklfds";
		              // divElt.innerHTML = "<font color='red'>用户名不能为空！</font>";
		              divElt.innerText = "<font color='red'>用户名不能为空！</font>";
		          }
		      }
		  </script>
		  ```

- BOM编程案例

	- `window.open()`和`window.close()`
	- `window.alert()`和`window.confirm()`
	- 如果当前窗口不是顶级窗口，将当前窗口设置为顶级窗口
	  ```js
	  if(window.top != window.self){
	  	window.top.location = window.self.location;
	  }//注意有location，location代表地址，这里是将顶级窗口的location地址，设置为当前窗口self的location。
	  
	  // ?????????????????
	  if(window.top != window.self){
	  	window.top = window.self;
	  }
	  ```

	- 历史记录

	  `window.history.back()`; 就是后退

	  ```js
	  <input type="button" value="后退" onclick="window.history.back()"/>
	  onclick 后面的是js代码，也可以调用写在<script>标签里的function，
	  
	  window.history.go(-1); 
	  window.history.go(1);
	  ```

	- window.location.href

	  提示一下document.location.href也可以完成同样功能

	- 可以通过B向S发送请求的方法

	  总结，有哪些方法可以通过浏览器往服务器发请求？
		
		1、表单form的提交。
		
		2、超链接。`<a href="http://localhost:8080/oa/save?username=zhangsan&password=123">用户只能点击这个超链接</a>`
	  
		3、document.location
	  
		4、window.location
	  
	      5、window.open("url")
	  
	      6、直接在浏览器地址栏上输入URL，然后回车。（这个也可以手动输入，提交数据也可以成为动态的。）
	  
	  以上所有的请求方式均可以携带数据给服务器，只有通过表单提交的数据才是动态的。

- JSON对象

	- eval函数
	  ```js
	  <script>
	  
	  window.eval("vat i = 100;");
	  //eval将字符串当成js代码来解释执行
	  </script>
	  ```

	  // java连接数据库,查询数据之后,将数据在java程序中拼接成JSON格式的“字符串”,将json格式的字符串响应到浏览器
	  
	  // 也就是说java响应到浏览器上的仅仅是一个"JSON格式的字符串",还不是一个json对象.
	  
	  // 可以使用eval函数,将json格式的字符串转换成json对象.

	- 怎么创建json对象以及访问json对象的属性

	  // 将以上的json格式的字符串转换成json对象
	  ```js
	  window.eval("var jsonObj = " + fromJava);
	  ```
	  ```js
	  alert(jsonObj.name + "," + jsonObj.password); // 在前端取数据
	  ```

	- json在开发中有什么用

	  数据交换作用
	  
	  只要系统之间通信，就可以用json

	- 写一个这样的JSON

	  描述一个班级的总人数，另外包括描述班级中每个学生的信息，这样的JSON怎么写

	- JS中[]和{}的区别

	  面试题：
	      在JS当中：[]和{}有什么区别？
	  
	  [] 是数组。
	  
	  {} 是JSON。
	  
	  java中的数组：`int[] arr = {1,2,3,4,5};`

	  JS中的数组：`var arr = [1,2,3,4,5];`
	  
	  JSON：`var jsonObj = {"email" : "zhangsan@123.com","age":25};`
	  
	  JSON是一种行业内的数据交换格式标准。
	  JSON在JS中以JS对象的形式存在。

	- xml、json

	  1、什么是JSON，有什么用？
	      JavaScript Object Notation（JavaScript对象标记），简称JSON。(数据交换格式)
	      JSON主要的作用是：一种标准的数据交换格式。（目前非常流行，90%以上的系统，系统A与系统B交换数据的话，都是采用JSON。）
	 
	  2、JSON是一种标准的轻量级的数据交换格式。特点是：
	      体积小，易解析。
	 
	  3、在实际的开发中有两种数据交换格式，使用最多，其一是JSON，另一个是XML。
	      XML体积较大，解析麻烦，但是有其优点是：语法严谨。（通常银行相关的系统之间进行数据交换的话会使用XML。）
	      用xml、json来完成两种语言的数据交换，比如C和java的数据交换

	- json中访问对象属性

	  ```js
	  // JS中访问json对象的属性
	  alert(json.username);
	  
	  // JS中访问json对象的属性
	  alert(json["username"]);
	  ```

- 总结一下浏览器向服务器发送请求的常见方式

  （1）直接在浏览器地址栏上写URL，get请求。
  
  （2）点击页面超链接，get请求。
  
  （3）提交form表单，可以是get，也可以是post。
  
  （4）window.open(url);
  
  （5）window.location.href=url;
  
  （6）document.location.href=url;

