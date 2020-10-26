# 动力节点-课程体系-V9.1.0

课程体系说明：标号1表示必须掌握；标号2表示能够理解；标号3表示简单了解；标号4表示扩展内容，根据学生学习情况自行决定是否讲解。

## WEB前端

### CSS

- CSS的作用

  层叠样式表语言，修饰HTML，让HTML更好看，是HTML的化妆品

- HTML中嵌入CSS样式的三种方式

	- 内联定义方式
		```CSS
	  <div style="font-size:12px; text-align:center;">HTML中引用CSS的行内式方法</div>
	  ```

	- 样式块

	  （1）`<style type="text/css"></style>`
	  id选择器
	  标签选择器
	  class选择器

	  （2）CSS的注释怎么写
	  
	  ```CSS
	          <style type="text/css">
	              /*
	                  这是CSS的注释。
	              */
	  
	              /*
	                  id选择器
	                  语法格式：
	                      #id{
	                          样式名 : 样式值;
	                          样式名 : 样式值;
	                          样式名 : 样式值;
	                          ....
	                      }
	              */
	              #id{
	                  color : red;
	                  font-size : 12px;
	              }
	  
	              /*
	                  标签选择器
	                  语法格式：
	                      标签名 {
	                          样式名 : 样式值;
	                          样式名 : 样式值;
	                          样式名 : 样式值;
	                          ....
	                      }
	                  标签选择器作用的范围比id选择器广。但凡是这个标签，都应用这个样式
	              */
	              
	  			div {
	                  background-color : black;
	                  border : 1px solid red;
	                  width : 100px;
	                  height : 100px;
	              }
	  
	              /*
	                  类选择器
	                  语法格式：
	                      .类名{
	                          样式名 : 样式值;
	                          样式名 : 样式值;
	                          样式名 : 样式值;
	                          ....
	                      }
	  因为不同的标签，要应用同样的样式，那么就很麻烦，就将两个标签的属性都加上class="class_name"，这样下面就可以用.class_name来应用css样式了。
	              */
	              .CLASS{
	                  border : 1px solid red;
	                  width : 400px;
	                  height : 30px;
	              }
	  
	          </style>
		```
	- 引入外部独立的CSS样式文件

	  ```CSS
	  <link href="css文件路径" rel="stylesheet" type="text/css" />
	  ```

- 边框

  （1）
  ```CSS
  div{
  	border : 1px solid red;
  }
  ```
  不用||，用空格隔开就行了
  
  （2）
  ```CSS
  div{
  	border-width : 1px;
  	border-style : solid;
  	border-color : red;
  }
	```
- 隐藏

	```CSS
  div{

  	display : none;

  }
  ```

- 字体

	```CSS
  div{

  	font-size : 12px;

  	color : red;
  }
  ```

- 文本装饰
	```CSS
  a{
  	text-decoration : none;
  }
  a{
  	text-decoration : underline;
  }
  ```
  这里的a是标签选择器，装饰超链接标签a

- 列表
	```CSS
  ul{

  	list-style-type : none;

  }
	```
- 设置鼠标悬停效果

  :hover

- 定位
	```CSS
  div{
  	position : absolute;
  	left : 100px;
  	top : 100px;
  }
  
  <style type="text/css">
  	#div{
  		background-color : red;
  		border : 1px solid;
  		width : 300px;
  		height : 300px;
  		position : absolute;/*绝对定位*/
  		left : 100px;
  		top : 100px;
  }
  <\style>
	```

- 鼠标小手
	```CSS
  div{
  	cursor : pointer;
  }
	```
