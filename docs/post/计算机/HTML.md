# 动力节点-课程体系-V9.1.0

课程体系说明：标号1表示必须掌握；标号2表示能够理解；标号3表示简单了解；标号4表示扩展内容，根据学生学习情况自行决定是否讲解。

## WEB前端

### HTML

- HTML概述

	- HTML是什么

	  超文本标记语言（Hyper Text Markup Language），由标签组成，除支持普通文本之外，还支持流媒体（超文本）。

	- HTML与W3C

	  （1）W3C是什么

	  （2）W3C制定了HTML标准

	  （3）HTML的版本（4.0和5.0）

	- HTML怎么开发

	  （1）html文件的扩展名是html/htm

	  （2）使用普通的文本编辑器即可开发

	  （3）可以使用专业的开发工具

	  网页制作三剑客之一DreamWeaver

	  HBuilder

	  其他...

	- HTML怎么运行

	  直接采用浏览器打开执行

	- 世界五大主流浏览器介绍

	  IE

	  FireFox

	  Chrome

	  Opera

	  Safari

	- 安装FireFox和Chrome浏览器
	- 安装HBuilder开发工具

- 第一个HTML

  （1）主要强调HTML的标签都是成对儿的，有开始标签，一般都会有对应的结束标签。

  （2）强调代码的合理缩进

  （3）强调HTML语法松散不严格

  （4）强调HTML不区分大小写

  （5）强调标签的属性，每个属性都包括属性名和属性值，属性值可以使用单引号括起来，也可以使用双引号括起来。

  （6）强调HTML中的注释怎么写

  （7）\<meta charset="UTF-8"/>解决乱码问题

  乱码产生是因为文件采用UTF-8方式，但浏览器打开该文件时采用GBK方式打开的，所以乱码

  该行代码的作用就是告诉浏览器采用哪一种字符编码打开该文件。

- 基本标签

	- 段落标记

	  \<p>\</p>`

	- 标题字

	  h1~h6

	- 换行 
      独目标记的概念。
	  \<br/>

	- 水平线

	  \<hr/>
	  独目属性
	  语法松散

	- 预留格式

	  pre

	- 粗体字

	  \<b>\</b>

	- 斜体字

	  \<i>\</i>

	- 插入字

	  \<ins>\</ins>

	- 删除字

	  \<del>\</del>

	- 右上角加字

	  \<sup>\</sup>

	- 右下角加字

	  \<sub>\</sub>

	- font标签

	  \<font size="3" color="red">This is some text!\</font>

- 实体符号

	- 空格

	  &nbsp;
	  就是代表一个空格
	  a&nbsp;b
	  
	  输出就是a b

	- 大于号

	  &gt;
	  特点：以&开始，以；结束
	  我就想要展示出\<号，没有特殊含义

	- 小于号

	  &lt;
	  特点：以&开始，以；结束
	  =号不冲突

- 表格

	- 基本表格

	  table(表格)里有tr(一行)，tr里又有td(一格)
	  
	  1px就是1像素，
	  60%代表占宽度的60%，随着窗口大小动态变化的。
	  align="center"：td里的属性，代这个单元格中数据居中，table属性中加，代表整个表格居中。
	  
	  ```HTML
	  <table border="1px" width="60%" height="像素或百分比" align="center">
	  
	  	<tr align="center">
	  		<td>test</td>
	  		<td>test</td>
	  		<td>test</td>
	  	</tr>
	  
	  	<tr>
	  		<td align="center">test</td>
	  		<td>test</td>
	  		<td>test</td>
	  	</tr>
	  
	  	<tr>
	  		<td>test</td>
	  		<td>test</td>
	  		<td>test</td>
	  	</tr>
	  
	  </table>
		```

	- 单元格合并

	  行合并：rowspan，找到两个元素，一般去掉后者，再前者的标签里，加上属性rowspan=“2”。
	  
	  列合并：colspan，差不多加rowspan=“2”，但是删谁都无所谓，因为两列都在同一个tr（行）中。

	- th标签

	  th也是单元格标签。
	  td改成th，单元格中内容，自动加粗和居中，

	- thead、tbody、tfoot标签

	  表格切割成三部分
	  
	  tbody：操作表的身体
	  
	  这样操作表格更灵活，便于后期JS代码的编写，
	  
	  ```HTML
	  <table border="1px" width="50%">
	              <!--头-->
	   <thead>
	                  <tr>
	                      <th>员工编号</th>
	                      <th>员工薪资</th>
	                      <th>部门名称</th>
	                  </tr>
	              </thead>
	  
	              <!--体-->
	              <tbody>
	                  <tr>
	                      <td>1</td>
	                      <td>2</td>
	                      <td>3</td>
	                  </tr>
	                  <tr>
	                      <td>a</td>
	                      <td>b</td>
	                      <td rowspan="2">f</td>
	                  </tr>
	                  <tr>
	                      <td colspan="2">d</td>
	                  </tr>
	              </tbody>
	  
	              <!--脚-->
	              <tfoot>
	                  <tr>
	                      <td>1</td>
	                      <td>2</td>
	                      <td>3</td>
	                  </tr>
	              </tfoot>
      ```

- 背景颜色和背景图片

  bgcolor
  background
  这是对背景进行设置
  
  一般html中文件采用什么字符集，meta charset就采用什么字符集
  \<meta charset="GBK">这一行在title标签的上一行，是告诉浏览器采用哪一种字符集打开当前页面，不是设置当前页面的字符编码

- 图片

  （1）\<img src="" width="" height="" alt="" title=""/>
  上面不加斜杠/，就加上结尾标签\</img>
  （2）只设置图片的宽度，高度等比例缩放，不建议设置高度，设置高度容易失真。

设置图片宽度和高度的时候，只设置宽度，高度会进行等比例缩放。

img标签就是图片标签
	
src属性是图片的路径

width设置宽度,height设置高度

title设置鼠标悬停时显示的信息。

alt设置图片加载失败时显示的提示信息。

- 超链接

  （1）超链接的作用
  向服务器发送请求，链接到某个资源
  
  （2）链接到网络中的某个资源
  \<a href="http://www.baidu.com">\</a>
  这里的href：hot reference，热引用
  
  （3）链接到本地的某个资源
  \<a href="本地文件的相对路径或绝对路径都可以，可以是网络中资源的路径">\</a>
  
  （4）图片做超链接
  \<a href="">  \<img src="img/xxx.png" width="120px" />   \</a>
  
  （5）超链接的target属性
  _blank：开启新窗口
  _self：当前窗口
  _parent：顶级窗口
  _top：父窗口
  
  （6）用户点击超链接和在浏览器地址栏上直接输入URL是完全相同的效果，只不过超链接更傻瓜式。

- 列表

	- 有序列表

	  ordered，就是1.xxx 2.xxx 3.xxx
	  ```HTML
	  \<ol type="1/A/a/I">
	  	\<li>中国
	  		\<ol>
	  			\<li>北京\</li>
	  			\<li>天津\</li>
	  			\<li>上海\</li>
	  		\</ol>
	  	\</li>
	  	\<li>美国\</li>
	  	\<li>日本\</li>
	  \</ol>
	  ```
	  不管有序ol还是无序ul，里面都是li标签，里面都可以嵌套子列表

	- 无序列表

	  unordered
	  就是Markdown里的- 语法
	  \<ul type="disc/circle/square">
	  	\<li>中国
	  		\<ul>
	  			\<li>北京\</li>
	  			\<li>天津\</li>
	  			\<li>上海\</li>
	  		\</ul>
	  	\</li>
	  	\<li>美国\</li>
	  	\<li>日本\</li>
	  \</ul>

- 表单

	- 表单起什么作用

	  用户填写表单，提交数据给服务器，所以表单是专门用来收集用户数据的。

	- 第一个表单
	```HTML
	  <form action="http://192.168.101.2:8080/crm/login">
	  用户名<input type="text" name="uname" />
	  密码<input type="password" name="pwd"/>
	  <input type="submit" value="登录"/>
	  <!--普通按钮不具备提交表单的能力-->
	  <input type="button" value="登录"/>
	  </form>
	  <!--submit放到form外部无法提交表单-->
	  <input type="submit" value="登录"/>
	```
	 
	（1）action属性等同于超链接的href属性，填写请求的url
	  
	（2）input标签属于输入域标签，input标签的type属性是text，表示文本框，是password，表示密码框
	
	（3）input标签的type是submit表示提交按钮，该按钮可以提交表单，所谓表单的提交是发送请求url，并携带数据给服务器。
	
	（4）所有按钮的value属性都是用来设置按钮上显示的文本内容
	
	（5）发送请求并提交数据时，数据格式遵循HTTP协议，所有浏览器都会采用这种格式：url?name=value&name=value&name=value...，其中name是input标签的name属性，value是input标签的value属性
	
	（6）文本框和密码框的value不需要开发人员指定，用户填写的数据就是value。
	
	（7）submit按钮放到form标签外面无法提交表单
	
	（8）普通按钮不具备提交表单的能力。

	- 用户注册表单

		- 表单项包括

		  （1）用户名
		  ```HTML 
		  <input type="text" name="username" />
		  ``` 
		  value属性不需要写，用户填写的数据就是value
		  
		  （2）密码
		  ```HTML
		  <input type="password" name="pwd" />
		  ``` 
		  value属性不需要写，用户填写的数据就是value
		  
		  （3）性别
		  ```HTML
		  男<input type="radio" name="gender" value="m"/>，
		  ```
		  性别是单选按钮，用户只能选，所以该标签需要添加value属性
			```HTML
		  女<input type="radio" name="gender" value="f" checked/>
		  ```
		  checked加上，代表这个radio是被默认选中的一个单选按钮，name必须相同提交给服务器的数据是：gender=m 或者 gender=f。
		  
		  name都是gender，代表这两项是一组的，只传一个到服务器上去，，，，单选按钮的value必须手动指定。
		  
		  （4）兴趣
		  ```HTML
		  运动<input type="checkbox" name="aihao" value="sport"/>
		  音乐<input type="checkbox" name="aihao" value="music" />
		  跳舞<input type="checkbox" name="aihao" value="dance" checked/>
		  ``` 
		  checked表示默认选中
		  同一组的复选框，name相同
		  以上三项都被选中的话，提交的数据是：aihao=sport&aihao=music&aihao=dance
		  
		  （5）学历
		  select是复选框
		  ```HTML
		  <select name="xueli">
		  	<option value="gz">高中</option>
		  	<option value="zk">专科</option>
		  	<option value="bk" selected>本科</option>
		  </select>
		  ```
		  selected默认选中
		  当选中本科时，提交的数据为：xueli=bk
		  
		  （6）简介
		  textarea：文本域，没有value属性，填进去的就是value
		  ```HTML
		  \<textarea cols="列数" rows="行数" name="jianjie">\</textarea>
		  ``` 
		  文本域没有value属性，用户填写的内容就是value
		  
		  （7）注册按钮
		   ```HTML
		  <input type="submit" value="注册"/>
		   ```
		   该标签放在form标签内部才起作用
		  
		  （8）重置按钮
		  ```HTML
		  <input type="reset" value="重置" />
		  ```
		  （9）再次强调表单提交时的数据格式
		  
		  `action?name=value&name=value&name=value&name=value...`

		  这是HTTP协议中规定的，这些有规律的数据提交给服务器之后，以后服务器端的java程序要解析这段数据的。
		  
		  要提交给服务器的就加上name属性，不加的不会提交给服务器，value（默认是空字符串）属性默认就是client输入的数据，不需要写出value属性。

		- form表单的method属性

		  （1）method不写或写上get都属于get请求，method写post才是post请求
		  
		  （2）get请求在HTTP协议的请求行上提交数据，最终提交的数据会显示在浏览器地址栏上
		  
		  （3）post请求在HTTP协议的请求体中提交数据，最终提交的数据不会显示到浏览器地址栏上
		  
		  （4）只有当使用form表单，并且method属性设置为post才是post请求，其他请求均为get，超链接也是get请求。
		  
		  超链接也可以提交数据给服务器，但是提交的数据是固定不变的，超链接是get请求，不是post请求
		  
		  post提交的数据和get是一样的，就是不显示value而已。

	- 下拉列表怎么显示多个条目，怎么支持多选
		```HTML
	  	<select multiple="multiple" size="显示的条目数量"></select>
	  ```
	  
	  （1）支持多选：multiple="multiple"
	  （2）显示多个条目：size="3"

	- file控件

	  （1）选择文件，文件上传时使用
	  （2）`<input type="file"/>`

	- hidden控件

	  隐藏域控件，页面上看不到，但提交表单时会提交数据！！！！不想让用户看见，但是必须提交给服务器的时候
	  ```HTML
	  <p hidden="hidden">这是一段隐藏的段落。</p>
	  <p>这是一段可见的段落。</p>
	  <p>是段落的标记
	  ```
	- readonly与disabled

	  （1）readonly：只读，不能修改，提交表单时数据会提交
	  
	  （2）disabled：只读，不能修改，提交表单时数据不会提交
	  
	  同：都是只读不能修改
	  
	  异：readonly可以提交给服务器，disabled数据不会提交(即使有name属性)。

	- input控件的maxlength

	  maxlength 属性规定输入字段的最大长度，以字符个数计。
	  
	  ` <input type="text" maxlength="3"  /> `

- HTML中元素的id属性

  （1）讲述HTML文档是一棵树（DOM树），树上有很多节点，每个节点(元素)一般都会有id属性，id属性具有唯一性，在同一个文档中不能重复，id是该节点的唯一标识。
    
  后期所学的javascript语言可以对DOM树上的节点进行增删改，达到动态效果。
  
  javascript（可以对HTML文档中的任意节点进行CRUD）主要通过节点的id来获取该元素。
  
  （2）
  
  `<a id=""></a>`，超链接有id；
  
  `<form id=""></form>`，form表单有id；
  
  `<input type="text" id="username"/>`，input标签有id。
  
  HTML像一棵树，有很多节点，就叫做D(ocument)OM树

- div和span

  （1）理解div是一种图层，div主要使用在网页布局方面，通过后期所学的CSS可以设置div的宽度、高度、位置等样式。div比table的布局更加灵活。
  
  （2）div图层可以嵌套使用
  
  （3）默认情况下div独占一行，span不会独占行。
  
  （4）div和span是可以定位的，只要定下div的左上角的x y轴坐标即可

- 要求：能用文本编辑器写出来，不用参考东西