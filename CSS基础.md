# CSS基础

## <font color="red">一、常用CSS的属性和参考值</font>

  |CSS属性|含义|参考值|
  |:---|:---|:---|
  |background-color|背景色|字体背景颜色名，比如red|
  |color|前景色|字体颜色名，同上|
  |font-size|字体大小|数字为几，即为几像素的字体大小|
  |border|边框|数字为几，即为几像素的实现；例如:3px solid(实线)/dashed(虚线) blue:3像素的蓝色实线|
  |width|宽度|数字为几，即为几像素的宽度|
  |height|高度|数字为几，即为几像素的高度|

##<font color="red">二、样式表优先级</font>

  |CSS样式表类型|优先级别|
  |:---:|:---:|
  |内联样式表|最高|
  |内部样式表|次高|
  |外部样式表|最低|

##<font color="red">三、CSS数字取值类型</font>

  |数字类型|发布版本|解释|
  |:---:|:---:|:---:|
  |`<number>`|CSS2|浮点数值|
  |`<integer>`|CSS2|整数值|
  |`<percentage>`|CSS2|百分比，写法为n<number>%的形式。该数值必须有参照物才能换算出具体的数值，是一个相对值|

##<font color="red">四、CSS长度单位`<length>`</font>

  |文本相对长度|
  |:---|

|长度单位|发布版本|解释|
|:---:|:---:|:---:|
|em|CSS1|相对于当前对象内文本的字体尺寸|
|ex|CSS1|相对于字符x的高度。一般为字体正常高度的一半|
|ch|CSS3|数字0的宽度|
|rem|CSS3|相对于当前页面的根元素`<html>`规定的font-size字体大小属性值的倍数|

  |视口相对长度单位|
  |:---|

  |长度单位|发布版本|解释|
  |:---:|:---:|:---:|
  |vw|CSS3|相对于视口的宽度。视口为均分为100vw|
  |vh|CSS3|相对于视口的高度。视口为均分为100vh|
  |vmax|CSS3|相对于视口的宽度或高度中的较大值。视口均分100vmax|
  |vmin|CSS3|相对于视口的宽度或高度中的较小值。视口为均分100vmin|

  |绝对长度单位|
  |:---|

  |长度单位|发布版本|解释|
  |:---:|:---:|:---:|
  |cm|CSS1|厘米|
  |mm|CSS1|毫米|
  |q|CSS3|四分之一毫米|
  |in|CSS1|英寸，lin 相当于 2.54cm|
  |pt|CSS1|点，1 pt 相当于 1/72in|
  |pc|CSS1|派卡，1pc 相当于 12pt|
  |px|CSS1|像素，1 px 相当于 1/96in|

##<font color = "red">五、CSS角度单位`<angle>`</font>

  |角度单位|发布版本|解释|
  |:---:|:---:|:---:|
  |deg|CSS3|度，圆形环绕一周为360deg|
  |grad|CSS3|梯度，圆形环绕一周400grad|
  |rad|CSS3|弧度，圆形环绕一周2πrad|
  |turn|CSS3|转、圈，圆形环绕一圈1turn|

##<font color="red">六、CSS时间单位`<time>`</font>

  |时间单位|发布版本|解释|
  |:---:|:---:|:---:|
  |s|CSS3|秒|
  |ms|CSS3|毫秒，1000毫秒=1秒|

##<font color="red">七、CSS文本取值（三种）</font>

  |文本类型|发布版本|解释|
  |:---:|:---:|:---:|
  |`<string>`|CSS2|字符串|
  |`<url>`|CSS2|图像、文件或浏览器支持的任意资源的地址|
  |`<identifier>`|CSS2|用户自定义的标识名称，例如：为元素自定义id名称|

##<font color="red">八、CSS颜色规定的17种标椎色</font>

  |颜色名称|中文名|RGB十六进制|RGB十进制|
  |:---:|:---:|:---:|:---:|
  |aqua|cyan|青色|#00FFFF|0,255,255|
  |black|黑色|#000000|0,0,0|
  |blue|蓝色|#0000FF|0,0,255|
  |fuchsia|洋红色|#FF00FF|255,0,255|
  |gray|灰色|#808080|128,128,128|
  |green|调和绿|#008000|0,128,0|
  |lime|绿色|#00FF00|0,255,0|
  |maroon|栗色|#800000|128,0,0|
  |navy|藏青色|#000080|0,0,128|
  |olive|橄榄色|#808000|128,128,0|
  |orange|橘色|#FFA500|255,165,0|
  |purple|紫色|#800080|128,0,128|
  |red|红色|#FF0000|255,0,0|
  |silver|银色|#C0C0C0|192,192,192|
  |teal|鸭翅绿|#008080|0,128,128|
  |white|白色|#FFFFFF|255,255,255|
  |yellow|黄色|#FFFF00|255,255,0|


##九、CSS三种样式表

### 9.1   内联样式表

+ 又称行内样式表，其属性为style（用于定义字体大小、背景、颜色等）
+ 其格式为：***`<hn 元素名 style="属性名称1：属性值1;属性名称2,：属性值2；··········">`***
+ 仅适用与几行文字的定义，也因此每次定义相同的文字，但又相隔几行，所以要重新定义（**<font color = "red">缺点</font>**)
+ 举例：

     ```html
     <!DOCTYPE html>
     <html>
     	<head>
     		<meta charset = "utf-8">
     		<title>测试1</title>
     	</head>
     	<body>
     		<h3 style = "color:red">十年开拓，中国助力全球绿色发展</h3>
     		<hr style = "border:3px dashed blue">
     		<p style = "font-size:40px;background-color:yellow">
     			持续的绿色投资驱动下，过去十年，中国在可再生能源、电动车等领域的技术创新脚步不断迈向新高度。通过国际合作，中国还将所积累的技术和经验分享给不同国家，惠及更广大地区民众，在全球绿色发展中发挥重要作用。
     		</p>
     	</body>
     </html>
     ```

**[注释]:**第九行是对水平线的定义（设置线条宽度为3像素的蓝色虚线）

​       代码测试结果图：

​		        <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE1.png" style="zoom: 50%;" />

### 9.2   内部样式表

+ 一个属性style，定义在`<head>`和`</head>`之间

+ 其语法格式为：
  ```html
  <style>
      选择器{
          属性名称1：属性值1;
          属性名称2：属性值2；
          ....
          属性名称N：属性值N；
      }
  </style>

​       【注释】：选择器即为指定文字前的标签，例如`<h3>我</h3>`中的h3

+ 其作用范围扩大到整个正文中，改善了内联样式表的缺点

### 9.3   外部样式表

+ 在外定义一个.css文件，该文件里定义了所需文字的字体大小、背景色、字体颜色等
+ 但需在.html文件的首部`<head>`和`</head>`之间使用`<link>`标签来引用外部.css文件
+ `<link>`的具体格式，见我的上一篇文章“HTML5基础"

+ 举例：

  Test.html

      ```html
      <!DOCTYPE html>
      <html>
      	<head>
      		<meta charset = "utf-8">
      		<title>新闻</title>
      		<link rel = "stylesheet" href = "my.css">
      	</head>
      	<body>
      		<h3>跟着总书记看中国丨大江大河大时代</h3>
      		<pre>
      			水乃生命之源
      
      			长江、黄河、大运河
      			是中国人的母亲河
      
      			长江兴，四方盛
      			护一江清水
      			绵延后世，惠泽人民
      
      			黄河宁，天下平
      			退耕还林，退牧还林
      			绿进沙退，还大河安澜
      
      			运河通，国运升
      			自北向南，碧水清流
      			一步一景，国泰民安
      
      			大江大河，水润华夏
      			她们是中华民族的生存家园
      			也是精神家园
      			守护江河
      			创造属于每一个人的伟大时代
      		</pre>
      	</body>
      </html>
      ```

my.css

```css
h3{
	color:orange
}
pre{
	background-color:gray;
	color:white;
	width:500px;
	height:500px;
}
```

代码测试结果：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE2.png" style="zoom: 67%;" />

### 9.4   三种样式表同时应用的效果

+ 若同时引用，则按照三种样式表的优先级使用，有最高级别的先使用，好比占位。可参照最上方的样式表优先级表；

 Test.html

      ```html
      <!DOCTYPE html>
      <html>
      	<head>
      		<meta charset="utf-8">
      		<title>CSS样式表优先级测试</title>
      		<link rel = "stylesheet" href = "my.css">
      		<style>
      			p{
      				background-color: cyan
      			}
      		</style>
      	</head>
      	<body>
      		<h3>CSS样式表优先级测试</h3>
      		<P>
      			该段落字体颜色来自外部样式表；背景颜色来自内部样式表
      		</p>
      		
      		<p style = "background-color: yellow">
      			该段落字体颜色来自外部样式表；背景颜色来自内部样式表
      		</p>
      	</body>
      </html>
      ```

my.css

```html
h3{
	color:orange
}
p{
	background-color:gray;
	color:white;
	width:300px;
	height:50px;
}
```

代码测试结果：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE3.png"  />

## 十、CSS选择器

### 10.1   元素选择器

+ 又称类型选择器，用法为采用匹配HTML文档中的元素名称，例如：p{background:gray}中的p；

### 10.2   ID选择器

+ 利用自定义的id号进行匹配，来进行设置字体等
+ 其格式为：在正文中`<p id="id名称">正文内容</p>`，则在`<head>`和`</head>`中声明`#id名称{属性名称1：属性值1；········}`

+ 实例：

    ```html
    <!DOCTYPE html>
    <html>
    	<head>
    		<meta charset = "utf-8">
    		<title>ID选择器的简单应用</title>
    		<style>
    			#test{
    				background-color:cyan;
    				width: 100px;
    				height: 100px;
    			}
    		</style>
    	</head>
    	<body>
    		<h3>ID选择器的简单应用</h3>
    		<hr>
    		<p>
    			该段落没有定义id名称
    		</p>
    		
    		<p id="test">
    			该段落自定义了id名称为test
    		</p>
    	</body>
    </html>
    ```

代码测试结果：
                                                         <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE4.png" style="zoom: 50%;" />

### 10.3   类选择器

+ 其作用在于可以为不同的元素定义相同的样式，其做法类似于上方的[ID选择器](#4.2   ID选择器)
+ 若同一个元素可以设置多种样式，则格式为：

​         `.red{color:red}`

​		`.bgblue{background-color:blue}`

​    	`<p class = "red bgblue">本段落的字体颜色为红色，背景颜色为蓝色</p>`

+ 外说一点，通过不断验证，得出：

​       <font color="red">***就好比如上方的.bgblue改为.bgblue{color:blue}，***</font>

​       <font color="red">***当.red和.bgblue同时设置（不同的颜色）在同一元素上时，***</font>

​       <font color="red">***哪个（.red   or    .bgblue）在`<style>和</style>`之间的后声明，***</font>

​      <font color="red"> ***最后正文中的那个元素就显示后声明的颜色。***</font>

+ 实例：

    ```html
    <!DOCTYPE html>
    <html>
    	<head>
    		<meta charset="utf-8">
    		<title>类选择器的简单应用</title>
    		<style>
    			.set2{
    				color:blue
    			}
    			.set1{
    				color:red
    			}
    			
    		</style>
    	</head>
    	<body>
    		<h3 class = "set1">类选择器的简单应用</h3>
    		<hr>
    		<P class = "set2">
    			该段落字体将设置为蓝色
    		</p>
    		
    		<p class="set1">
    			该段落字体将设置为红色
    		</p>
    		
    		<p class="set1 set2">
    			该段落字体将设置为什么颜色呢？
    		</p>
    	</body>
    </html>
    ```

代码测试结果：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE5.png" style="zoom: 50%;" />

### 10.4   属性选择器

+ 其格式为：<font color="red">**`元素名称[元素属性]{属性名称1：属性值1；属性名称2：属性2；.......；属性名称N：属性值N}`**</font>

+ 其作用在于根据元素属性进行设置的匹配

+ 例如：

  ```html
  a[href]{
   	color:red;
  }
  对带有href属性的超链接元素<a>设置CSS样式；这里是设置字体颜色为红色；
  
  元素名称[attribute~="value"]{
  	color:red
  }
  对所有指定attribute的名字（比如href）属性【其中元素名称为a】中带有value关键字设置字体为红色；
  
  元素名称[attribute|=value]{
  	border:1px solid red;
  }
  对所有指定attribute的名字（比如alt）属性【其中元素名称为img】中以value关键字开头设置1像素宽的红色实线边框；
  ```

## 十一、一些语法语句

### 11.1   注释语句

+ 其格式为**`/*............*/`**
+ 支持单行或多行注释

### 11.2   @charset

+ 用于外部样式表CSS的第一行
+ 其格式为：<font color = "red">**`@charset = "utf-8";`**</font>
+ 【注意】格式末尾一定加上分号( ; )
+ 该格式表示的含义是指外部样式表的编码格式为UTF-8

### 11.3   !important

+ 其格式为<font color="red">**`选择器{样式规则 !important;}`**</font>
+ 其作用在于对待多种样式表设置时，哪种样式表后面声明了`<!important>`，哪种就先使用样式表中的样式规则
+ 比如：

  ```html
  p{
  	background-color:red !important;
  	background-color:blue;
  }
  优先使用background-color:red语句
  ```

## 十二、颜色

### 12.1   RGB色彩模式

+ 有红、绿、蓝三种颜色不断叠加而成
+ 通过三种颜色不同的配比形成很多中色彩

### 12.2   三种颜色表现格式

+ rgb(红色通道值，绿色通道值，蓝色通道值)【通道值是0—255之间的任意整数】
+ **`#RRGGBB`**【以“`#`为头的后面六位数是十六进制的意思，其中三种颜色各自占两个位】【最小值为0，最大值为FF】比如：`#FF0000`表示红色【大小写忽略】
+ 直接用英文单词表示，例如red

## 十三、CSS常用样式

### 13.1   CSS背景
+ CSS背景与颜色属性

|属性名称|解释|
|:---:|:---:|
|background-color|设置背景颜色(默认为透明的[transparent])|
|background-image|设置背景图像，其格式为<font color="red">`p{background-image:url(图片路径)}`</font>|
|background-repeat|设置背景图像是否重复平轴|
|background-attachment|背景图像是否随页面滚动|
|background-position|放置背景图像的位置，其格式为<font color="red">`background-position:水平方向值 垂直方向值`</font>|
|background|上述所有属性的综合简写方式|

+ 所有HTML元素的背景图片都会默认进行重复平铺（即重复多张放在页面上，无缝衔接）【水平和垂直两方面】

+ CSS属性background-repeat取值

|属性值|解释|
|:---:|:---:|
|repeat-x|水平方向平铺|
|repeat-y|垂直方向平铺|
|repeat|水平和垂直方向平铺|
|no-repeat|不平铺，只显示原图|

+ CSS属性background-attachment取值

|属性值|解释|
|:---:|:---:|
|scroll|背景图像随着页面滚动|
|fixed|背景图像固定在屏幕上|

+ 默认情况下，背景图片会放置在元素的左上角
+ CSS属性background-position关键字

|属性值|解释|
|:---:|:---:|
|center|水平居中或垂直居中|
|top|垂直方向置顶显示|
|bottom|垂直方向底部显示|
|left|水平方向左对齐显示|
|right|水平方式右对齐显示|

+ background背景简写用于概括以上五种背景属性，简写的声明顺序：[background-color] [background-image] [background-repeat] [background-attachment] [background-position]
+ 例如：

   ```html
   p{background:silver url(image/football.png) no-repeat}
   ```

### 13.2   针对12.1中的background-position属性的见解

+ 其代码如下：
  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset = "utf-8">
  		<title>图像处理</title>
  		<style>
  			div{
  				width:660px;
  			}
  			p{
  				width:200px;
  				heigth:200px;
  				background-color: blue;
  				background-image:url(C:/Users/清弦子之忆/Downloads/图2.jpeg);
  				background-repeat:no-repeat;
  				float:left;
  				margin:10px;
  				text-align:center;
  			}
  			#p1_1{
  				background-position:left top
  			}
  			#p1_2{
  				background-position:top
  			}
  			#p1_3{
  				background-position:right top
  			}
  			#p2_1{
  				background-position:0%
  			}
  			#p2_2{
  				background-position:50%
  			}
  			#p2_3{
  				background-position:100%
  			}
  			#p3_1{
  				background-position:0px 100px
  			}
  			#p3_2{
  				background-position:50px 100px
  			}
  			#p3_3{
  				background-position:100px 100px
  			}
  		</style>
  	</head>
  	<body>
  		<h3>图像处理</h3>
  		<hr>
  		<div>
  			<p id="p1_1">left top</p>
  			<p id="p1_2">top</p>
  			<p id="p1_3">right top</p>
  			
  			<p id="p2_1">0%</p>
  			<P id="p2_2">50%</p>
  			<p id="p2_3">100%</p>
  			
  			<p id="p3_1">0px 100px</p>
  			<p id="p3_2">50px 100px</p>
  			<p id="p3_3">100px 100px</p>
  		</div>
  	</body>
  </html>
  ```

  代码测试结果：

  ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE6.png)
  
  【见解】：若将代码中的16-18行的代码去除，则会出现以下结果：
  
  <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE7.png" style="zoom: 50%;" />
  
  因此得出定位背景图像background-position需与float、margin、text-align相结合；
  
  若只有float声明：
  
  ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE8.png)    

  若有float和margin声明：
  
  ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE9.png)

###13.3   百分比与等价关键词定位

|百分比定位|等价关键词定位|背景图像位置|
|:---:|:---:|:---:|
|0% 0%|left top或top left|元素的左上角|
|0% 50%或0%|left center或left|水平方向左对齐，垂直方向居中|
|0% 100%|left bottom或bottom left|元素的左上角|
|50% 0%|center top或top|水平方向居中，垂直方向置顶|
|50% 50%或50%|center center或center|元素的正中心|
|50% 100%|center bottom或bottom|水平方向居中，垂直方向底端|
|100% 0%|right top或top right|元素的右上角|
|100% 50%或100%|right center或right|水平方向右对齐，垂直方向居中|
|100% 100%|right bottom或bottom right|元素的右下角|

### 13.4   CSS框模型

​                            <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE10.png" style="zoom: 80%;" />  

+ <font color="red">CSS中宽度和高度表示的是元素内容的宽度和高度，而外面的内边距和外边距的宽度无法影响到元素内容的实际大小，但会增加元素占用的空间；</font>

#### 13.4.1   内边距padding

+ 该属性可使用 1 到 4 种值：
    + 如果规定一种值，比如：div {padding: 50px} - 所有四个内边距都是 50px。
      
    + 如果规定两种值，比如：div {padding: 50px 10px} - 上内边距和下内边距是 50px，左内边距和右内边距是 10px。
      
    + 如果规定三种值，比如：div {padding: 50px 10px 20px} - 上内边距是    50px，左内边距和右内边距是 10px，下内边距是 20px。
      
    - 如果规定四种值***（按上右下左顺序）***，比如：div {padding: 50px 10px 20px 30px} - 上内边距 是 50px，右内边距是 10px，下内边距是 20px，左内边距是 30px。

+ padding属性值不可为负数，但可为长度值和百分比值
+ 表示元素内容周边的填充物，用于增加元素内容与元素边框之间的距离
+ 比如：

    ```html
    <div style="width:100px">
    	<p style="padding:20%">段落</p>
    </div>
    
    20%表示上方width（100像素）的百分之20，即20像素;
    ```

+ 单边内边距：

|属性名称|解释|
|:---:|:---:|
|padding-top|元素的上边内边距|
|padding-bottom|元素的下边内边距|
|padding-left|元素的左边内边距|
|padding-right|元素的右边内边距|

​      例如：`p{padding-top:20px}`

+ 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>内边距</title>
		<style>
			p{
				width:200px;
				margin:10px;
				background-color:orange;
			}
			.style01{
				padding:20px
			}
			.style02{
				padding:10px 50px
			}
			.style03{
				padding-left:50px
			}
		</style>
	</head>
	<body>
		<h3>内边距</h3>
		<hr>
		<p>
			该段落没有使用内边距，默认值为0
		</p>
		<p class = "style01">
			该段落元素的各边内边距均为20像素
		</p>
		<p class = "style02">
			该段落元素的上下内边距均为10像素，左右内边距均为50像素
		</p>
		<p class = "style03">
			该段落元素的左边内边距为50像素
		</p>
	</body>
</html>
```

其运行结果如下：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE11.png" style="zoom: 67%;" />

#### 13.4.2   边框border

+ CSS边框属性一览表

|属性名称|解释|
|:---:|:---:|
|border-width|设置边框的宽度|
|border-style|设置边框的样式|
|border-color|设置边框的颜色|
|border|上述属性的简写|

+ CSS属性border-width取值

|属性值|解释|
|:---:|:---:|
|thin|较窄的边框|
|medium|中等宽度的边框|
|thick|较宽的边框|
|像素值|自定义像素值宽度的边框|

+ CSS属性border-style取值

|属性值|解释|
|:---:|:---:|
|none|定义无边框效果|
|dotted|定义点状边框效果|
|dashed|定义虚线边框效果|
|solid|定义实线边框效果|
|double|定义双线边框效果|
|groove|定义3D凹槽边框效果|
|ridge|定义3D脊状边框效果|
|inset|定义3D内嵌边框效果|
|outset|定义3D外凸边框效果|
|inherit|从父元素继承边框样式|

+ border-style的简写方式（即为每一边单独设置边框样式）：<font color="green">其用法类似于[内边距padding][#12.4.1 内边距padding]的第一点；</font>

​		例如：p{border-style:solid dashed dotted double}

+ border边框简写内无规定顺序，即p{border:1px solid red}，但三个属性之间要空格

+ border-width的应用效果：

   ​                                                                                ​<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE12.png" style="zoom:67%;" />  

+ border-style的应用效果：

​                                                                                               <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE13.png" style="zoom: 67%;" />

+ border-color的应用：

​                                                                                 ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE14.png)

#### 13.4.3   外边距margin

+ 可参考[内边距padding][#12.4.1 内边距padding] ，其属性用法以及有几个属性值表示的含义相同，但唯一不同的是***margin属性值可以是长度值或百分比值，也可以是负数***
+ CSS单边外边距属性

|   属性名称    |         解释         |
| :-----------: | :------------------: |
|  margin-top   | 设置元素的左边外边距 |
| margin-bottom | 设置元素的下边外边距 |
|  margin-left  | 设置元素的左边外边距 |
| margin-right  | 设置元素的右边外边距 |

+ 其代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>margin的应用</title>
		<style>
			.box{
				border:1px solid;
				width:300px;
				margin:10px;
			}
			.yellow{
				background-color:yellow
			}
			.style01{
				margin:20px
			}
			.style02{
				margin:10px 50px
			}
			.style03{
				margin-left:100px
			}
		</style>
	</head>
	<body>
		<h3>margin的应用</h3>
		<hr>
		<div class="box">
			<div class="yellow">
				该段落没有使用外边距，默认为0
			</div>
		</div>
		<div class="box">
			<div class="style01 yellow">
				该段落元素的各边外边距均为20像素
			</div>
		</div>
		<div class="box">
			<div class="style02 yellow">
				该段落上下边外边距均为10像素，左右边外边距均为50像素
			</div>
		</div>
		<div class="box">
			<div class="style03 yellow">
				该段落左边外边距为100像素
			</div>
		</div>
	</body>
</html>
```

其代码测试结果：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE15.png" style="zoom: 80%;" /> 

+ <font color="red">外边距合并主要指的就是上下外边距的合并，存在三种情况：</font>
    + <font color="red">当元素B出现在元素A下面时，元素A的下边距会与元素B的上边距发生重叠合并</font>
    + <font color="red">当元素B包含在元素A内部时，如果元素B的上下边距均为0，也会发生上下外边距合并现象</font>
    + <font color="red">当空元素没有边框和内边距时，上下外边距也会发生合并</font>
    
    <font color="red">【注意】：只有普通块级元素的垂直外边距才会发生合并，浮动框、行内框、绝对定位之间的外边距是不会发生合并的；</font>
    
###13.5   CSS文本

+ CSS文本属性

|属性名称|解释|
|:---:|:---:|
|text-indent|设置文本缩进|
|text-align|设置文本对齐方式（左对齐、居中、右对齐）|
|text-decoration|设置文本装饰（下画线、删除线、上画线）|
|text-transform|设置文本大小写的转换|
|letter-spacing|设置字符间距|

#### 13.5.1   文本缩进text-indent

+ 起到首行缩进效果;
+ 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>text-indent的应用</title>
		<style>
			p{
				text-indent:2em
				border:1px solid;
				width:200px;
				padding:10px;
			}
		</style>
	</head>
	<body>
		<h3>text-indent的应用</h3>
		<hr>
		<p>
			缩进了2个字符的距离
	    </p>
	</body>
</html>

【标注】：em表示原始字体大小的倍数
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE16.png) 

#### 13.5.2   文本对齐text-align

+ CSS属性text-align取值

|属性值|解释|
|:---:|:---:|
|left|文本内容对齐|
|right|右对齐|
|center|居中对齐|
|justify|两端对齐|

其实例：`text-align:left`

#### 13.5.3   文本装饰text-decoration

+ CSS属性text-decoration取值

|属性值|解释|
|:---:|:---:|
|underline|为文本添加下画线|
|line-through|删除线|
|overline|上画线（文字头顶上）|
|none|正常状态|

+ none适用于去掉超链接文本内容的下画线

#### 13.5.4   文本转换text-transform

+ CSS属性text-transform取值

|属性值|解释|
|:---:|:---:|
|uppercase|将文本中每个字母都转换为大写|
|lowercase|将文本中每个字母都转换为小写|
|capitalize|将文本中的首字母转换为大写|
|none|保持原状|

+ 其格式为  ` text-transform:属性值`

#### 12.5.5   字符间距letter-spacing

+ 其属性值为长度值（可以为负数，为负数时，文字重叠在一起），例如`h1{letter-spacing:1em}`、`h1{letter-spaceing:10px}`

###13.6   CSS字体

+ CSS字体属性

|属性名称|解释|
|:---:|:---:|
|font-family|设置字体系列|
|font-style|设置字体风格（正常、斜体、倾斜）|
|font-variant|设置字体变化（小型尺寸的大写字母等）|
|font-weight|设置字体的粗细|
|font-size|设置字体尺寸|
|font|对以上属性的简写|

#### 13.6.1   字体系列font-fanily

+ 分为两类：特定字体系列（指定，比如宋体），通用字体系列（相同外观特征的字体，五种：Serif字体、Sans-serif字体、Monospace字体、Cursive字体、Fantasy字体）
+ 由于有些字体名称有多个单词组成，所以要在属性值上加双引号；若为单个单词，则省略不写；
+ 例如：`font-family:"French Script MT"`

+ 若显示不出字体，可参考[解决：字体样式font-family不起作用](http://t.csdn.cn/0JxBl)

#### 13.6.2   字体风格font-style

+ CSS属性font-style取值

|属性值|解释|
|:---:|:---:|
|normal|正常字体|
|italic|斜体字|
|oblique|倾斜字体|

#### 13.6.3   字体变化font-variant

+ CSS属性font-variant取值

|属性值|解释|
|:---:|:---:|
|normal|正常字体|
|small-caps|小号的大写字母|

+ 当文本内容中存在大写字母，使用small-caps属性值将会将这些大写字母（原先就是大写字母）的字号显示为正常字体大小；
+ 当文本内容不存在大写字母，使用small-cpas属性值将会将其他小写字母转换为大写字母后，变成小一号的字体大小；

+ 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>font-variant</title>
		<style>
			.style01{font-variant:normal}
			.style02{font-variant:small-caps}
		</style>
	</head>
	<body>
		<h3>CSS属性font-variant的应用</h3>
		<hr>
		<p class="style01">
			Normal
		</p>
		<p class="style02">
			Small Caps
		</p>
		<p class="style02">
			small caps
		</p>
	</body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE17.png)

#### 13.6.4   字体粗细font-weight

+ CSS属性font-weight取值

|属性值|解释|
|:---:|:---:|
|normal|标准正常字体(默认)|
|bold|加粗字体|
|bolder|更粗的字体|
|lighter|更细的字体|
|100-900|[100,900]的整数，每个数字相差100。数字越大字体越粗。其中400等同于normal,700等同于bold|

#### 13.6.5   字体大小font-size

+ 可参考上方的[CSS长度单位<**length**>](#四、CSS长度单位`<length>`)
+ 属性值为长度值，可以使用绝对单位或相对单位
+ %------含义是相对于父元素的比例
+ em-----含义是相对于字体大小的尺寸，这里表示的是2em是2倍字体大小

#### 13.6.6   字体简写font

+ 简写顺序为：

​      [font-style]      [font-variant]      [font-weight]      [font-size]      [font-family]

+ 若中间没有属性值，则可省略不写
+ 其格式同上方[内边距padding](#13.4.1   内边距padding)类似

### 13.7   CSS超链接

+ 其元素为`<a>`
+ 超链接的四种状态

|状态名称|解释|
|:---:|:---:|
|a:link|未被访问的超链接|
|a:visited|已被访问的超链接|
|a:hover|鼠标悬浮在上面的超链接(必须在以上两种状态后声明)|
|a:active|正在被点击的超链接(必须在上一个状态后声明)|

+ 代码如下：

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title>超链接</title>
  		<style>
  			a:link,a:visited{
  				display:block;   /*块级元素，模拟按钮*/
  				text-decoration:none;  /*取消下画线*/
  				color:white;  /*字体为白色*/
  				font-weight:bold;   /*字体加粗*/
  				font-size:25px;   /*字体大小为25px*/
  				background-color:#7BF;   /*设置背景颜色*/
  				width:200px;    /*宽度为200像素*/
  				height:30px;   /*高度为30像素*/
  				text-align:center;    /*文本居中显示*/
  				line-height:30px;    /*行高30像素*/
  			}
  			a:hover,a:active{
  				background-color:#0074EB   /*设置背景颜色*/
  			}
  		</style>
  	</head>
  	<body>
  		<h3>超链接</h3>
  		<hr>
  		<a href="http://www.baidu.com">百度</a>
  	</body>
  </html>
  ```

  代码测试结果：

  未点击状态：

  ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE18.png)

  点击后状态：

  ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE19.png)

### 13.8   CSS列表

+ CSS列表属性

|属性名称|解释|
|:---:|:---:|
|list-style-type|设置列表标志类型|
|list-style-image|设置列表标志图标|
|list-style-position|设置列表标志位置|
|list-style-type|简写|

#### 13.8.1   样式类型list-style-type

+ CSS属性list-style-type常见取值

|属性值|解释|
|:---:|:---:|
|none|无标记符号|
|disc|默认值，实心圆点|
|circle|空心圆|
|square|实心方块|
|decimal|阿拉伯数字|
|decimal-leading-zero|01,02,03，····|
|upper-roman|I,II,III,IV，····|
|lower-roman|i,ii,iii,iv，····|
|upper-alpha|A,B,C,D,····|
|lower-alpha|a,b,c,d,····|
|upper-latin|A,B,C,D，···（IE浏览器不支持）|
|lower-latin|a,b,c,d，···（IE浏览器不支持）|
|lower-greek|alpha,beta,gamma，···（IE浏览器不支持）[希腊字母]|
|hebrew|传统的希伯来编号方式|
|armenian|亚美尼亚编号方式|
|georgian|乔治亚编号方式|
|cjk-ideographic|一，二，三，···|
|hiragana|日语平假名编号|
|katakana|日语片假名的编号|
|hiragana-iroha|日语平假名-伊吕波形的编号|
|katakana-iroha|日语片假名-伊吕波形的编号|

#### 13.8.2   样式图片list-style-image

+ 设置标志图标（可网络图像地址或本地图片）
+ 但谨记：声明了标志图片，便不可再声明标志类型
+ <font color="red">【注意】：这个样式图片不能修改图片大小，需自己在本地中改变像素大小（可以再系统自带的画图软件中修改）</font>

​        也可参考[关于html：CSS列表样式图像大小](https://www.codenong.com/7775594/)

#### 13.8.3   样式位置list-style-position

+ CSS属性list-style-position属性值

|属性值|解释|
|:---:|:---:|
|outside|默认值，表示列表标志放置在文本左侧|
|inside|表示列表标志放置在文本内部，多行文本根据标志对齐|
|inherit|继承父元素的list-style-position属性值<font color="red">***(有待考察)***</font>|

​                     <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE20.png" style="zoom: 80%;" />   

 

#### 13.8.4   样式简写list-style

+ 其简写顺序为：

​      [list-style-type]      [list-style-position]      [list-style-image]

+ 其余跟[字体简写font](#13.6.6   字体简写font)类似

### 13.9   CSS表格

+ CSS表格相关属性

|属性名称|解释|
|:---:|:---:|
|border-collapse|设置表格的边框样式为双线或单线|
|border-spacing|设置表格中双线边框的分割距离|
|caption-side|设置表格中的标题设置|
|empty-cells|定义表格中空单元格边框和背景的显示方式|
|table-layout|规定表格的布局方式，包括固定表格和根据内容调整布局|

#### 13.9.1   折叠边框border-collapse

+ 默认情况下，表格的边框如果设置为实线，那么线条为双层；
+ CSS属性border-collapse属性值

|属性名称|解释|
|:---:|:---:|
|separate|默认值，边框分开，双线|
|collapse|边框合并，一条|
|inherit|继承父元素border-collapse属性值|

+ 代码如下：

    ```html
    <!DOCTYPE html>
    <html>
    	<head>
    		<meta charset="utf-8">
    		<title>border-collapse</title>
    		<style>
    			.separate{
    				border-collapse:separate
    			}
    			.collapse{
    				border-collapse:collapse
    			}
    		</style>
    	</head>
    	<body>
    		<h3>border-collapse</h3>
    		<hr>
    		<table border="1" class="separate">
    			<caption>
    				双线边框
    			</caption>
    			<tr>
    				<td>年份</td>
    				<td>姓名</td>
    				<td>专业</td>
    			</tr>
    			<tr>
    				<td>2021</td>
    				<td>杨生</td>
    				<td>软件工程</td>
    			</tr>
    			<tr>
    				<td>2020</td>
    				<td>张飒</td>
    				<td>土木工程</td>
    			</tr>
    		</table>
    		<br>
    		
    		<table border="1" class="collapse">
    			<caption>
    				折叠边框
    			</caption>
    			<tr>
    				<td>年份</td>
    				<td>姓名</td>
    				<td>专业</td>
    			</tr>
    			<tr>
    				<td>2021</td>
    				<td>杨生</td>
    				<td>软件工程</td>
    			</tr>
    			<tr>
    				<td>2020</td>
    				<td>张飒</td>
    				<td>土木工程</td>
    			</tr>
    		</table>
    	</body>
    </html>
    ```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE21.png)

#### 13.9.2   边框距离border-spacing（双线边框两条线之间的距离）

+ CSS属性border-spacing属性值

|属性值|解释|
|:---:|:---:|
|长度值|表示水平和垂直方向上的距离|
|长度值1 长度值2|长度值1表示水平方向的距离，长度值2表示垂直方向的距离|
|inherit|继承父元素的border-spacing属性值|

+ 只有在双线边框，才能有效

#### 13.9.3   标题位置caption-side

+ CSS属性caption-side属性值

|属性值|解释|
|:---:|:---:|
|top|默认值，表示标题在表格上方|
|bottom|···········································下方|
|inherit|继承父元素的caption-side属性值|

#### 13.9.4   空单元格empty-cells

+ CSS属性empty-cells属性值

|属性值|解释|
|:---:|:---:|
|show|默认值，显示空白单元格的边框和背景|
|hide|隐藏空白单元格的边框和背景|
|inherit|继承父元素的empty-cells属性值|

#### 13.9.5   表格布局table-layout

+ CSS属性table-layout属性值

|属性值|解释|
|:---:|:---:|
|automatic|默认值，宽度由字体长度决定|
|fixed|由样式设置决定，一旦设定好宽度，则一行中每个单元格平均分配这个宽度（即使数据超出单元格，也不会变）|
|inherit|继承父元素的table-layout属性值|

+ 用于规定表格的布局方式，包括固定表格布局和根据内容调整布局

## 十四、CSS定位

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE22.png)

+ X轴越往右，数字越大；Y轴越往下，数字越大；

+ 可以将HTML元素放置在页面上指定的任意地方

### 14.1   绝对定位

+ 通过规定HTML元素在水平方向和垂直方向上的位置来固定元素，基于绝对定位的元素不占据空间
+ 使用时，需将position设置为absolution(绝对的)，再使用四种关于方位的关键词left(左边)、right(右边)、top(顶部)、bottom(底端)设置相关元素位置
+ 绝对定位的位置声明相对于已定位并且相较于最近的元素，若无，则相对于整个页面
+ 代码示例：

    ```html
    <!DOCTYPE html>
    <html>
    	<head>
    		<meta charset="utf-8">
    		<title>绝对定位</title>
    		<style>
    			p{
    				position:absolute;
    				width:120px;
    				height:120px;
    				top:100px;
    				left:0px;
    				background-color:#C8EDFF;
    			}
    			div{
    				position:absolute;
    				width:300px;
    				height:300px;
    				top:49px;
    				left:220px;
    				border:1px solid;
    			}
    		</style>
    	</head>
    	<body>
    		<h3>绝对定位</h3>
    		<hr>
    		<p>
    			该段落相对于页面定位的，距离页面的顶端100像素，距离左边0像素
    		</p>
    		<div>
    			我是相对于页面定位的div元素，距离页面的顶端49像素，距离左边220像素
    			<p>
    				该段落相对于页面定位的div元素，距离顶端100像素，距离左边0像素
    			</p>
    		</div>
    	</body>
    </html>
    ```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE23.png)

【提醒】：从以上示例可看出一个段落放置在一个已经定位的`<div>`内部，则声明的方位是相对于div而来的；  

+ <font color="red">***总结为一句话：搞清楚相对于谁，才定位的***</font>

### 14.2   相对定位

+ 相对定位的参照物为该元素最初的起点位置，并且即使该元素偏移到另一个位置上，也仍然从原始起点开始占据空间
+ 使用时，需将position设置为relative(相对的)，再使用四种关于方位的关键词left(左边)、right(右边)、top(顶部)、bottom(底端)设置相关元素位置
+ 代码示例

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>相对定位的应用</title>
		<style>
			div{
				width:200px;
				height:380px;
				border:1px solid;
				margin-left:50px;
			}
			p{
				width:150px;
				height:100px;
				background-color:#C8EDFF;
			}
			.left{
				position:relative;
				left:-50px;
			}
			.right{
				position:relative;
				left:130px;
			}
		</style>
	</head>
	<body>
		<h3>相对定位的应用</h3>
		<hr>
		<div> 	
			<p>
				正常状态的段落
			</p>
			<p class="left">
				相对自己正常位置向左偏移50像素
			</p>
			<p class="right">
				相对自己正常位置向右偏移130像素
			</p>
		</div>
	</body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE24.png)

### 14.3   叠层效果

+ 除了定义水平和垂直的位置，还可以定义多个元素叠层在一起
+ <font color="green">但有一点需注意：其有一个属性值z-index，这个属性值为整数，且数字越大，该元素越放在最上的位置上。还有声明完z-index后，还要使用四种关于方位的关键词left(左边)、right(右边)、top(顶部)、bottom(底端)设置相关元素位置</font>

### 14.4   浮动

#### 14.4.1   浮动效果float

+ CSS属性float属性值

|属性值|解释|
|:---:|:---:|
|left|元素向左浮动|
|right|元素向右浮动|
|none|默认值，表示元素不浮动|
|inherit|继承父元素的float属性值|

+ 在对元素声明浮动效果后，浮动元素会自动生成一个块级框，所以要声明元素的宽度
+ 元素进行浮动时，会朝着做指定的方向前进，直到碰触到页面边缘或上一个浮动框的边缘
+ 代码如下：

    ```html
    <!DOCTYPE html>
    <html>
    	<head>
    		<meta charset="utf-8">
    		<title>浮动</title>
    		<style>
    			div{
    				float:left;
    				width:230px;
    			}
    			p{
    				line-height:30px;
    				text-indent:2em;
    			}
    		</style>
    	</head>
    	<body>
    		<h3>浮动</h3>
    		<hr>
    		<div><img src="C:/Users/清弦子之忆/Downloads/背景1.jpg" alt="背景1" />
    		</div>
    		<p>
              一、10月22日（星期六）8时起，开展全域人员核酸检测。凡居住在我市的广大群众，采样前要在当时居住地保持原地静止，按照各区防控指挥部统一部署和街道（镇）、社区（村）组织安排，有序到指定地点进行核酸检测，不落一户、不漏一人。高中低风险区域和静态管理区域的居民要严格服从属地街道管理。静海区全域人员要在核酸检测阴性结果出来之前，继续保持相对静止。其他区居民采样后需持有本次核酸筛查采样证明和72小时核酸阴性证明可安排必要出行。
              　　	   二、凡是从津外来返津人员和我市有疫情地区旅居史的人员要主动向社区和单位报备，并第一时间主动进行核酸检测。
              　　   三、全市各级机关、各级各类企事业单位、各类公共场所要严格落实查验职责，要严格查验本次核酸筛查采样证明、72小时核酸阴性证明、场所码和健康码。对于未参加本次核酸筛查的，要及时提醒到就近核酸采样点进行核酸检测。各区、各行业部门、各单位要加强督促管理和查验。各区疫情防控指挥部要严格落实责任，完善保障措施，提高工作效率，确保“应检尽检”。
              　　 四、对于接种新冠病毒疫苗后48小时内人员，暂不安排参加此次核酸检测，各区提前做好备案统计，妥善安排后续检测。对于疫情防控、核酸采样检测和城市运行保障相关工作人员，各区统筹安排，保障工作出行。
            </p>
    	</body>
    </html>
    ```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureCSS%E5%9F%BA%E7%A1%80%E5%9B%BE25.png)

#### 14.4.2   清理浮动clear

+ 用于清理浮动效果
+ CSS属性clear属性值

|属性值|解释|
|:---:|:---:|
|left|元素的左侧不允许有浮动元素|
|right|元素的右侧不允许有浮动元素|
|both|左右两侧都不允许有浮动元素|
|none|默认值，允许|
|inherit|继承父元素的clear属性值|
