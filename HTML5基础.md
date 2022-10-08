# HTML5基础

##一. 标签基础（集合）

### `<!DOCTYPE>`

文档类型声明，在代码的第一行出现；

### `<html>`

+ 根元素标签；

- 属于有结束语`</html>`的标签
- 包含两个标签：`<head>`,`<body>`;

### `<head>`

+ 有结束语`</head>`
+ 包含`<title>`和`<meta>`两个标签

### `<title>`

+ 有结束语`</title>`
+ 在其与结束语之间的文字为网页上的标题

### `<base>`

+ 基础地址标签

+ 用于为页面上的所有链接设置默认的<u>URL地址</u>（网页地址，Internet用来描述信息资源地址的字符串，也是统一资源定位符）或目标targe。

+ 其作用在于补全URL地址（即用base指定路径，而主体部分中若只单纯给出一个补全的路径，就会产生自动不全的效果）

+ `<base>`的属性如下：

  |值|描述|
  |:---|:---|
  |_blank|在新窗口中打开被链接文档。|
  |_self|默认。在相同的框架中打开被链接文档。|
  |_parent|在父框架中打开被链接文档。|
  |_top|在整个窗口中打开被链接文档。|
  |framename|在指定的框架中打开被链接文档。|

​				例如，代码如下：

```html
			<head>
			    <base target = "_blank" />
			</head>
			
			<body>
			<a href = "http://www.baidu.com">百度</a>
			<a href = "http://www.163.com">网易</a>
			</body>		
```

### `<meta>`

+ 元数据标签，不会显示在网页上
+ 用来定义字符集、关键字、描述、作者等 
           1) 字符集声明
                 `<meta charset = "utf-8">`
           2) 关键词声明
                 `<meta name = "keywords" content = "HTML5,CSS3,JQuery" />`
           3) 页面描述声明
                 `<meta name = "description" content = "This is a tutorial about HTML5,CSS3,jQuery" />`
               4）每30s刷新页面
                 `<meta http-equiv="refresh" content = "30" />`
           5) 定义页面作者
                 `<meta name="author" content = "Hege Refsnes" />`
+ 一般用于`<head>`与`</head>`之间
+ **<font color = "red" size = "3pt">【注意】：</font>**    3）中的name表示描述网页，content表示网页内容

### `<style>`

+ 样式标签，定义文档中指定区域的字体风格、背景颜色、对齐方式等各类样式信息

+ 出现在`<head>`与`</head>`之间，如：

  ```html
  <head>
      <style>
          p{color:purple}
      </style>
  </head>
  ```

### `<link>`

+ 用于连接外部资源和当前HTML5文档，也用于连接外部样式表
+ 出现在`<head>`与`</head>`之间
+ 其格式为：`<link rel = "stylesheet" type = "text/css" href = "css文件路径" />`
+ ***rel*** 的各个属性值配置：

|值|描述|
|:---|:---|
|alternate|文档的替代版本（比如打印页、翻译或镜像）|
|stylesheet|文档的外部样式表|
|start|集合的第一个文档|
|next|集合中的下一个文档|
|prev|集合中的上一个文档|
|contents|文档的目录|
|index|文档的索引|
|glossary|在文档中使用的词汇的术语表（解释）|
|copyright|包含版权信息的文档|
|chapter|文档的章|
|section|文档的节|
|subsection|文档的小节|
|appendlx|文档的附录|
|help|帮助文档|
|bookmark|相关文档|

### `<script>`

+ 可引入外部脚本，用于页面中，如JavaScript

### `<body>`

+ 主体部分，其内容显示在页面上
+ 有结束语`</body>`

###`<!--内容-->`

+ 用于注释方面
###`<p>`

+ 有结束语`</p>`
+ 段落标签，用于形成**段落**

### `<h1>~<h6>`

+ 标题标签，用于控制页面内容的大小
+ **从1到6依次增长，其字体逐渐变小**
+ 有结束语`</h1>~</h6>`

### `<hr>`

+ 水平线标签，用于**在页面上形成一条水平线**，没有结束语

### `<br>`

+ 换行标签，用于**一次换行**

### `<i>`

+ 斜体字标签
+ 有结束语`</i>`

### `<b>`

+ 有结束语`</b>`
+ 主要用于将文本内容**粗体化**

### `<strong>`

+ 有结束语`</strong>`
+ 主要同`<b>`一样，用于将文本内容**粗体化**

### `<sup>`

+ 上标标签，用于将与结束语`</sup>`之间的内容移至右上角，如2^10^。其中10为其内容

### `<sub>`

+ 下标标签，用于将与结束语`</sub>`之间的内容移至右下角，如H~2~O~2~。其中两个2都为其内容

### `<del>`

+ 修订标签，用于在被删除文本内容上画一条横线
+ 有结束语`</del>`

### `<ins>`

+ 修订标签，用于在文本内容上**加下划线**
+ 有结束语`</ins>`

### `<pre>`

+ 预格式化标签，其作用相当于多次换行和多次空格
+ 有结束语`</pre>`,可保留在与结束语之间排版格式（即在这区间内，内容排版的结果就是显示在页面的结果）

### `<ol>`

+ 有序列表标签，其作用在于将与结束语之间的内容有序排序；
+ 有结束语`</ol>`，需结合`<li>`一起使用

+ 默认为从1开始计数

+ 属性：

  |属性名称|实现语句|作用|
  |:---|:---|:---|
  |start|<**ol start = "n"**>|重新定义编号起始值，即实现语句中n为从哪里开始|
  |type|<**ol type = "类型值**">|类型值表示可以更换其他编号样式，默认为阿拉伯数字|
  
  type属性值与编号样式对应关系：
  
  |type属性值|标号样式示例|
  |:---:|:---:|
  |a|英文字母小写(a,b,c,d,···)|
  |A|英文字母大写(A,B,C,D,···)|
  |i|罗马数字小写(i,ii,iii,iv,···)|
  |I|罗马数字大写(I,II,III,IV,···)|
  |1|阿拉伯数字(1,2,3,4,···)|

###`<li>`

+ 列表项目标签，其作用在于将文本内容默认为缩进显示效果，类似于换行标签`<br>`和预格式化标签`<pre>`
+ 有结束语`</li>`
+ 可用在有序列表`<ol>`、无序列表`<ul>`和菜单列表`<menu>`中

### `<ul>`

+ 无序列表标签，其作用在于定义不带编号的列表
+ 有结束语`</ul>`，需结合`<li>`一起使用
+ 默认为实心圆形编号，以及在下一级（二级）列表中默认为空心圆形
+ 属性：

  |属性|实现语句|作用|
  |:---|:---|:---|
  |type|<**ul type = "类型值"** >|自定义编号样式|
  
  type属性值与编号样式的对应关系：
  
  |type属性值|编号样式实例|
  |:---:|:---:|
  |disc|实心圆形|
  |circle|空心圆形|
  |square|方形|
  

### `<dl>`

+ 有结束语`</dl>`，需结合`<dt>`和`<dd>`一起使用
+ 定义列表标签

### `<dt>`

+ 有结束语`</dt>`
+ 用于表示概括一段话的词条

### `<dd>`

+ 有结束语`</dd>`
+ 用于解释上面`<dt>`所标记的词条，同`<li>`一样，显示缩进效果



**`<dl>`,`<dt>`和`<dd>`的代码和页面显示：**

```html
<!DOCTYPE html>
<html>
	<html>
		<meta charset = "utf-8">
		<title>定义列表标签的应用</title>
	</head>
	<body>
		<h3>Ocford Dictionary</h3>
		<hr>
		<dl>
			<dt>HTML</dt>
			<dd>
				Hypert Markup Language, a standardized system for tagging text files to 
				achieve font, colour, graphic, and hyperlink effects on World Wide Web 
				pages: 'an HTML file'.
			</dd>
			
			<dt>World Wide Web</dt>
			<dd>
				An information system on the Internet which allows documents to be connected
				to other documents by hypertext links, enabling the user to search for information by moving from one document to another.
			</dd>
			
			<dt>browser</dt>
			<dd>
				A computer program with a graphical user interface for displaying HTML files,
				used to navigate the World Wide Web:
				'a web browser'.
			</dd>
		</dl>
	</body>
</html>
```

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E5%9F%BA%E7%A1%80%E5%9B%BE1.jpg)

### `<img>`

+ 图像标签，主要用途在于将一张图片放在页面上
+ 常用的四个属性：***src***，***alt***，***width***和 ***height***
+ 其语句写法为：***<img src = "图片路径"  alt="图片名字（自定义）" width = "宽度数字" height = “长度数字" >***

### `<a>`

+ 超链接标签，主要用于点击页面文字或图片时，跳转到某个网页上
+ 适用于制作网页的导航菜单或列表，也可用于发送邮件或下载文件等
+ 有结束语`</a>`
+ 两个重要属性：href（路径）和target（内容打开方式），可查看  “[base](# <base>)"  中target的用法
+ 访问与未访问的文本文字是两种不同的颜色
+ 其语句格式为：

  ```html
  <a href = "路径">链接的文本名字（自定义也行）</a>
  <a href = "路径"><img src = "图片路径" width = "宽度" height = "长度" /></a> 
  ```

+ 在内部链接中，其作用在于单击跳转到同一页面的指定区域
+ 其语句格式为：

   ```html
   <a href = "#指定区域名">链接文本或图像</a>
   <a name = "区域名">目标内容</a>
   ```
   

​     <font color = "red" size = "3pt">**【注意】：**</font>以上两个语句格式是同时存在的，含义为第一个语句用来标记跳转的区域，而第二个语句用来在跳转的部分标记对应的名称，例如：

    <a href = "#ch01">第一章</a>
    <a name = "ch01">第一章</a>

###`<table>`

+ 表格标签，定义一个表格
+ 有结束语`</table>`

### `<tr>`

+ 表格行标签，定义表格中的一行
+ 有结束语`</tr>`

### `<td>`

+ 单元格标签，定义表格行中的一个数据单元格，默认为左对齐
+ 有结束语`<td>`

###`<th>`

+ 有结束语`</th>`
+ 定义表格的第一行表头，默认为粗体字、居中对齐

### `<caption>`

+ 表格标签，默认居中对齐，并显示在表格的顶部
+ 有结束语`<caption>`

### `<iframe>`

+ 框架标签，通俗来说，就是在一个页面中还放着一个页面，如水杯中水在杯中一样
+ 有结束语`</iframe>`
+ 其格式为：`<iframe src = "相对/绝对路径/·····.html"></iframe>`

   代码与结果如下：

​         ***news.html***

   ```html
   <!DOCTYPE html>
   <html>
   	<head>
   		<meta charset = "utf-8">
   		<title>内联框架iframe的应用</title>
   	</head>
   	<body>
   		<p>	美国海军学会网站5日称，“里根”号航母打击群上周完成了“2017年以来美国航母首次访问韩国”的使命后，又在日本海与韩国和日本舰艇举行了大规模联合演习。10月3日，该航母已经南下到达日本东部海域。但在朝鲜4日发射中程弹道导弹飞过日本列岛上空后，“里根”号航母打击群接到命令重返朝鲜半岛附近海域。一名美国国防部官员5日证实，当天“里根”号航母打击群现在已位于日本海海域。报道称，“美国航母打击群在朝鲜半岛的重新部署是非常不寻常的，它表明了韩美联盟的坚定意愿，即加强韩美联盟对朝鲜历次挑衅的准备状态，并对朝鲜的任何挑衅和威胁作出果断回应。”不过，对于美韩双方炒作的朝鲜进行导弹发射，朝鲜方面没有进行回应。
   		</p>
   	</body>
   <html>
   ```

​	    ***Test1_1.html***		

     <!DOCTYPE html>
     <html>
     	<head>
     		<meta charset = "utf-8">
     		<title>内联框架iframe的应用</title>
     	</head>
     	<body>
     		<h3>内联框架iframe的应用</h3>
     		<hr>
     		<iframe src = "news.html"></iframe>
     	</body>
     </html>

​        结果如下：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E5%9F%BA%E7%A1%80%E5%9B%BE2.jpg" style="zoom: 67%;" />

### `<div>`

+ 有结束语`</div>`
+ 划分页面，分成块状，其默认状态下浏览器会在`<div>`和`</div>`前后放置一个换行符
+ <font color="blue" >每个标签都有独立的id号，意思是id号自拟，主要为了后期查看代码时方便阅读,其格式为**`<div id = "自拟名字">`**</font>

+ 其格式为：**`<div style = "color:字体颜色（英文单词）; background-color:背景颜色（英文单词）">`**

### `<span>`

+ 有结束语`</span>`
+ 只有与***CSS***同时使用时，才可以指定文本样式，属于内联元素
+ 默认内联元素（即指定的文本）同一行出现

### `<header>`

+ 有结束语`</header>`
+ 页眉标签，用来定义网页文档或节的标题

### `<nav>`

+ 有结束语`</nav>`
+ 导航标签，用来定义菜单栏

### `<section>`

+ 有结束语`</section>`
+ 节标签，定义节段落

### `<article>`

+ 有结束语`</article>`
+ 文章标签，定义文章的内容，同时包含文章的标题（页眉）和文章的注释（页脚）

### `<aside>`

+ 有结束语`</aside>`
+ 侧栏标签，定义网页正文两边的侧栏内容

### `<footer>`

+ 有结束语`</footer>`
+ 页脚标签，定义整个网页文档或其中的一节（文章）的标注（页脚）

以上六个标签的应用显示界面：

​                              

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E5%9F%BA%E7%A1%80%E5%9B%BE3.png" style="zoom: 50%;" />

 

### `<mark>`

+ 记号标签，有结束语`</mark>`
+ 用于为所指定的文字加上背景色

### `<progress>`

+ 进度标签，有结束语`</progress>`
+ 用于显示任务的进度情况，其两个属性为：`<value>`（当前进度）和`<max>`（进度最大值）

### `<meter>`

+ 度量标签，结束语`</meter>`
+ 显示磁盘使用量、投票数据统计等
+ 其所含属性：

  |属性名称|解释|
  |:---|:---|
  |value|用于显示实际值，可以是整数或小数，默认值为0|
  |min|用于规定范围内的最小值，默认为0|
  |max|用于规定范围内的最小值，默认为1|
  |low|用于规定范围内的较低值，当value<low，度量显示红色|
  |high|用于规定范围内的较高值，low<value<high，显示黄色;value>high,显示绿色|
  |optimum|规定范围内的最佳值|
  

## 二. HTML5文档规范

+ 字符实体（无法像平常一样正常输出的特殊字符，例“>"）可借助其对应的字符名称或数字代码进行输出：

```
  &实体名称
  &#实体数字
```

+ 特殊字符的实体名称和符号代码：

  |显示效果|字符实体|实体名称|实体数字|
  |:---:|:---:|:---:|:---:|
  | |空格|&nbsp|&#160|
  |>|大于号|&gt|&#62|
  |<|小于号|%lt|&#60|
  |×|乘法|&times|&#215|
  |÷|除号|&divide|&#247|
  |"|双引号|&quot|&#34|
  |'|单引号|&apos|&#39|
  |°|度数|&deg|&#176|
  |£|英镑|&pound|&#163|
  |€|欧元|&euro|&#8364|
  |©|版权|&copy|&#169|
  |®|注册商标|&reg|&#174|

​	

## 三. 内联元素与块级元素之间的区别

+ 内联元素不占一行，而块级元素占一行
+ 设置内联元素的长宽无效（由自身决定），而块级元素有效

