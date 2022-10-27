# JavaScript基础

##一、JavaScript的内外部

###1.1   内部JavaScript

+ 其格式为：

       ```html
       <script>
          //代码
       </script>
       ```

+ 【JavaScript的alert()方法】：弹窗提醒；其格式为：`alert("语句");`
+ 实例：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>内部JavaScript的简单应用</title>
	</head>
	<body>
		<h3>内部JavaScript的简单应用</h3>
		<hr>
		<!--JavaScript的代码部分-->
		<script>
			alert("Hello JavaScript!");
		</script>
	</body>
</html>
```

代码测试结果如下：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE1.png" style="zoom: 67%;" />

+ <font color="red">【注意】：</font>内部JavaScript可以在页面上的任何位置，而页面也允许在不同位置上放入多段javaScript代码

###1.2   外部JavaScript

+ 用法在于将原本应写到`<script>`和`</script>`的内容变为在外面另建一个.js文件，并存放在里面
+ 建好.js文件后，如果要用，则必须在HTML代码中，声明如下：

​      `<script src="JavaScript 文件地址"></script>`

+ 代码如下：

​    myFireScript.js

    ```javascript
    alert("数据库代向HTML致敬");
    ```

Test1_1.html

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>外部JavaScript的应用</title>
		<!--外部JavaScript的引用-->
		<script src="myFirseScript.js"></script>
	</head>
</html>
```

代码测试结果如下：

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE2.png" style="zoom: 80%;" />

## 二、JavaScript语法

+ 有大小写之分
+ 其语法类似于java
+ 每一段语句可以有分号（;），也可以没有分号（;）
+ 注释可以这样表示：

​       //     或     /* */

​       【注意】：注释只能在`<script>`和`</script>`之间的标签或外部js文件使用

## 三、JavaScript变量

### 3.1   变量声明

+ 无论是什么类型内容，都统一使用关键字var加上变量名称进行声明，例如：var a = 2
+ 在声明变量的同时可以对其进行初始化，也可以先声明变量，再另行赋值
+ 允许一个关键字var同时声明多个变量，同时多个变量也可以是相互不同的类型，也可以是全部相同的类型
+ 变量声明var不是必须存在的，也可以直接使用变量名称进行赋值使用，例如：list = "String"
+ 当程序遇到未声明的变量时，就像上方的list，会自动使用该名称创建一个变量并继续使用
+ 如果声明的变量没有赋值，则alert(变量名称)显示为underfined

### 3.2   变量的命名规范

+ 首位字符必须是字母、下画线、美元符号
+ 其他位置可以为下画线、美元符号、数字、字母
+ 变量命名方式有Camel标记法（变量为多个单词时，第一个单纯的首字母为小写，其他单词的首字母为大写，如，var myFirseScript）、Pascal标记法（所有单词的首字母大写）、匈牙利类型标记法（在Pascal标记法的基础上，加上一个前缀【i表示整数，s表示字符串】，如，varsMyFirstScript）

### 3.3   关键字和保留字

+ 关键字

|break|case|catch|continue|default|
|:---:|:---:|:---:|:---:|:---:|
|delete|do|else|finally|for|
|function|if|in|instanceof|new|
|return|switch|this|throw|try|
|typeof|var|void|while|with|

+ 保留字

|abstract|boolean|byte|char|class|
|:---:|:---:|:---:|:---:|:---:|
|const|debugger|double|enum|export|
|extends|final|float|goto|implements|
|import|int|interface|long|native|
|package|privaste|protected|public|short|
|static|super|synchronized|throws|transient|
|volatite|||||

+ 都不能作为变量或函数名称

## 四、JavaScript基本数据类型

+ 五种原始类型：Number（数字）、Boolean（布尔值）、String（字符串）、Null（空值）和Undefined（未定义）
+ typeof 变量名称：返回该变量名称的类型
+ typeof方法的常见返回值

|返回值|示例|解释|
|:---:|:---:|:---:|
|underfined|var x; alert(x);|该变量为赋值|
|boolean|var x = true; alert(x);|该变量为布尔值|
|string|var x = "Hello"; alert(x);|该变量为字符串|
|number|var x = 3.14; alert(x);|该变量为数值|
|object|var x = null; alert(x);|该变量为空值null或对象|

### 4.1   Undefined类型

+ 当输出的变量从<font color="red">未声明过</font>，或<font color="red">使用关键字var声明过后但并未赋值</font>，alert(变量名称)会显示undefined字样

+ 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>undefined类型</title>
	</head>
	<body>
		<h3>undefined类型</h3>
		<hr>
		<script>
			//声明变量msg
			var msg;
			//在alert()方法中使用变量msg
			alert(msg);
		</script>
	</body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE3.png)

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE4.png)

### 4.2   Null类型

+ null值表示变量的内容为空，可用于初始化变量或者清空已经赋值的变量
+ 示例：

    ```javascript
    <script>
    	var msg = 99;
    	msg = null;
    	alert(msg);   //显示null
    </script>
    ```

### 4.3   String类型

+ 用于存储文本内容，赋值时，可以用单引号或双引号
+ 这里的单引号不是指只能一个字符，它与字符串是相同的意思
+ 当文本内容里有双引号，则外面字符串用单引号表示，反之亦然
+ 示例:

```javascript
var msg = 'he said:"now is lighting"'
```

+ JavaScript String对象常见方法

|方法名|解释|
|:---:|:---:|
|charAt()|返回指定位置上的字符|
|charCodeAt()|返回指定位置上的字符Unicode编码|
|concat()|连接字符串|
|indexOf()|正序检索字符串中指定内容的位置|
|lastIndexOf()|倒序检索字符串中指定内容的位置|
|match()|返回匹配正则表达式的所有字符串|
|replace()|替换字符串中匹配正则表达式的指定内容|
|search()|返回匹配正则表达式的索引值|
|slice()|根据指定位置节选字符串片段|
|split()|把字符串分割成字符串数组|
|substring()|根据指定位置节选字符串片段|
|toLowerCase()|将字符串中所有字母都转换为小写|
|toUpperCase()|将字符串中所有字母都转换为大写|

#### 4.3.1   字符串长度

+ 可以使用    变量名称.length   获取其长度（与java相同）

#### 4.3.2   获取字符串中的单个字符

+ 使用charAt()方法获取字符串中的单个字符，使用charCodeAt()方法获取字符串中的单个字符的Unicode编码
+ 示例：

```javascript
var msg = "Hello Java";
var x = msg.charAt(0);

//charAt(index)

var msg = "Hello java";
var x = msg.charCodeAt(0);

//charCodeAt(index)

//alert("Hello Java在第4位的字符："+letter+"\n编码为："+code);
//其中/n表示换行
```

#### 4.3.3   连接字符串

+ 使用concat()方法将新的字符串内容连接到原始字符串上

+ 其格式为：`concat(String s1,String s2,String s3,········,String sn);`

+ 示例：

```javascript
var msg = "hello";
var new = msg.concat("Java");
alert(new);

//使用加号（+）进行字符串连接
```

#### 4.3.4   查找字符串是否存在

+ 使用indexOf()和lastIndexOf()方法来查找原始字符串中是否包含指定的字符串
+ 其格式为：【正序】`indexOf(指定的字符串，指定开始索引的位置)`，【倒序】`lastIndexOf(指定的字符串，指定开始索引的位置)

### 4.4   Number类型

+ Number类型表示数字，其数字可以是32位以内的整数或64位以内的浮点数

#### 4.4.1   科学计数法

+ 其格式为：数值e倍数    （倍数可以为负数，其格式含义为数值【整数或浮点数】乘以10的倍数次方）
+ 示例：

```javascript
var msg = 3e6;
```

#### 4.4.2   八进制与十六进制数

+ 要运用到八进制、十六进制以及相互转换之间的知识
+ Number类型也可以是八进制（以0开头，后面跟的数字只能是0—7中的一个）或十六进制（以0x开头，后面跟的字符只能是0—9或A-F之间的一个）
+ 示例：

```javascript
var x = 0xA;   //十六进制
var x = 010;   //八进制
```

+ 在代码中虽然以八/十六进制赋值，最后输出是以十进制输出

#### 4.4.3   浮点数

+ 使用toFixed（）方法规定小数点后保留几位数，其格式为：

   ```javascript
   var x = 3.1415926;
   var result = x.toFixed(2);   //返回值3.14
   //遵守四舍五入
   ```

+ 若使用浮点数计算，有时会产生误差

```javascript
var x = 0.7+0.1;
alert(x);    //返回值变为0.799999999999999999，而不是0.8

则需要如此做，才能避免误差
var x = (0.7*10+0.1*10)/10;
alert(x);    //返回值变为0.8
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>JavaScript浮点数类型的简单应用</title>
	</head>
	<body>
		<h3>JavaScript浮点数类型的简单应用</h3>
		<hr>
		<p>
			浮点数的加法运算
		</p>
		<script>
			var result1 = 0.7+0.1;
			var result2 = (0.7*10+0.1*10)/10;
			document.write("0.7+0.1="+result1+"<br>(0.7*10+0.1*10)/10="+result2);
		</script>
	</body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE5.png)

#### 4.4.4   特殊Number值

+ JavaScript中Number类型的特殊值

|特殊值|解释|
|:---:|:---:|
|Infinity|正无穷大，在JavaScript使用Number.POSITIVE_INFINITY表示|
|-Infinity|负无穷大，在JavaScript使用Number.NEGATIVE_INFINITY表示|
|NaN|非数字，在JavaScript使用Number.NaN表示|
|Number.MAX_VALUE|数值范围允许的最大值，大约等于1.8e308|
|Number.MIN_VALUE|数值范围允许的最小值，大于等于5e-324|

+ Infinity有正负之分，但如果Number数值超出他的上限或下限，就会返回Infinity
+ 示例：

```javascript
var x = 9e3000000;
alert(x);    //超出上限，返回值为Infinity
```

+ 当两个变量数值都超出数值范围的大小，但他们各自的实际长度不相同；而由于都超出范围限制，都变为Infinity,所以判定两者是相等的，返回true；
+ 示例：

```javascript
var x1 = 3e30000000;
var x2 = 8e30000000;
alert(x1==x2);    //返回true
```

+ 使用数字0作为除数不会报错，则分为几种情况：
    + 正数 / 0 = Infinity
    + 负数 / 0 = -Infinity
    + 0 / 0 = NaN(非数字)
    
+ Infinity不可以与其他正常的数字进行计算，返回结果仍是Infinity

+ Infinity - Infinity = NaN

#### 4.4.5   NaN

+ 表示的是非数字，用于表示数据转换成Number类型失败的情况，从而抛出异常
+ isNaN（变量名称）：判断数据类型是否为数值的方法，返回值为布尔值

​     【true时，为无法转换；false，可以转换】

#### 4.4.6   关于Infinity 、-Infinity 、NaN三者的讨论

+ Infinity 运算法则
    + 正数除以 0 得 Infinity。
    + Infinity 加或减任何有限数字都得 Infinity 。Infinity + Infinity 或 Infinity - -Infinity 也得 Infinity 。
    + Infinity 乘或除以任何有限正数得 Infinity 。Infinity 乘或除以任何有限负数得 -Infinity 。 Infinity * Infinity 或 Infinity / 0 也得 Infinity 。Infinity * -Infinity 得 -Infinity。
    + Infinity - Infinity 得 NaN 。 Infinity / Infinity 得 NaN 。 Infinity * 0 得 NaN 。
    + Infinity == Infinity 为真。 Infinity.isNaN() 为假。
    + Infinity.isFinite() 为假。 Boolean(Infinity) 为真。
+ -Infinity 运算法则
    + 负数除以 0 得 -Infinity。
    + -Infinity 加或减任何有限数字都得 -Infinity 。-Infinity + -Infinity 或 -Infinity - Infinity 也得 -Infinity
    + -Infinity 乘或除以任何有限正数得 -Infinity 。-Infinity 乘或除以任何有限负数得 Infinity 。 -Infinity * Infinity 或 -Infinity / 0 也得 -  Infinity 。-Infinity * -Infinity 得 Infinity。
    + -Infinity - -Infinity 得 NaN 。 -Infinity / -Infinity 得 NaN 。 -Infinity * 0 得 NaN 。
    + -Infinity == -Infinity 为真。 -Infinity.isNaN() 为假。
    + -Infinity.isFinite() 为假。 Boolean(-Infinity) 为真。

+ NaN 运算法则
    + 0 / 0 得 NaN 。上面也有一些得 NaN 的情况。
    + NaN 加、减、乘或除以任何数（包括 Infinity 、 -Infinity 和 NaN 本身）得 NaN 。
    + 无论变量 x 取何值（包括 undefined 、 null 、 true 、 false 、 Infinity 、 -Infinity 和 NaN 本身），NaN == x 恒为假。NaN.isNaN() 为真。 NaN.isFinite() 为假。 Boolean(NaN) 为假。
   
+ 本段来源于[关于 Infinity， -Infinity 和 NaN](http://t.csdn.cn/dZ5Qs)

### 4.5   Boolean类型

+ 多用于条件判断，返回为布尔值（true或false）

+ ```javascript
  alert(Boolean('')); //outpt false  
  alert(Boolean(0)); //output false
  alert(Boolean(NaN)); //output false
  alert(Boolean(null)); //output false  
  alert(Boolean(undefined)); //output false  
  
  总之：
  1.特殊值undefined和null变成false.
  2.数字0和NaN变成false.
  3.空字符串变成false.
  4.所有其他值都变成true.
  
  另：凡是关于Boolean()、Number()等都是将括号里的元素强制转换为外面声明的类型
  ```

## 五、涉及八进制和十六进制的知识补充

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE6.png" style="zoom:150%;" />

<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE7.png" style="zoom:150%;" />

## 六、JavaScript运算符

+ 赋值运算符：=

  示例：`var x1 = 9;`

+ 算数运算符的常见用法：

|运算符|解释|
|:---:|:---:|
|+|加号，求和，连接字符串|
|-|减号，求差|
|*|乘号,求积|
|/|除号，求商|
|%|求余符号|
|++|自增加1|
|--|自减减1|

+ 运算符组合：

|运算符组合|格式|解释|
|:---:|:---:|:---:|
|+=|x+=y|x=x+y|
|-=|x-=y|x=x-y|
|*=|x*=y|x=x*y|
|/=|x/=y|x=x/y|
|%=|x%=y|x=x%y|

+ 逻辑运算符有三种类型：NOT（逻辑非）、AND（逻辑与）、OR（逻辑或）

+ 逻辑运算符分为：！（逻辑非，表示对结果的对立面）、&&（逻辑与，表示并列关系）、||（逻辑或，表示二选一）
+ <font color="red">【注意：】</font>这里与Java不同的是，JavaScript自带有一个抽象方法ToBoolean，可以提前将运算条件转换为布尔值，之后在进行逻辑运算符判断；
+ **ToBoolean的具体转换规则如下：**

|值|示例|转换结果|
|:---:|:---:|:---:|
|布尔值true|var x = true;|true|
|布尔值false|var x = false;|false|
|null|var x = null;|false|
|underfined|var x = underfined;|false|
|非空字符串|var x = "Hello";|true|
|空字符串|var x = "";|false|
|数字0|var x = 0;|false|
|NaN|var x = NaN;|false|
|除0和NaN以外的其他数字|var x = 99;|true|
|对象|var student = new Object();|true|

+ 逻辑与特殊情况：

|运算数类型|示例|返回值|
|:---:|:---:|:---:|
|一个是对象，一个是布尔值|var student = new Object(); var result = student && true;|返回对象类型，即student|
|两个都是对象|var student1 = new Object(); var student2 = new Object(); var result = student1 && student2;|返回第二个对象，即student2|
|一个是空值null,一个是布尔值|var x = null; var result = x && true;|null|
|存在NaN|var x = NaN; var result = x && true;|NaN|
|存在未赋值undefined|var x; var result = x && true;|underfined|

但有一点：若条件1为假，返回值都是假的；【逻辑或（||）亦是如此，只要条件1为真，返回值都为真的】

+ 逻辑或特殊情况：

|运算数类型|示例|返回值|
|:---:|:---:|:---:|
|条件1位false,条件2为对象|var student = new Object(); var result = flase`||`student;|返回对象类型，即student|
|两个都是对象|var student1 = new Object(); var student2 = new Object(); var result = student1`||`student2;|返回第一个对象，即student1|
|条件1是false，条件2为空值null|var x = null; var result = flase`||`x;|null|
|条件1是false,条件2为NaN|var x = NaN; var result = false`||`x;|NaN|
|条件1为false,条件2为underfined|var x;var result = false`||`x;|underfined|

+ 关系运算符分为**三种比较方式**：

​     **数字之间的比较**（和正常做数学题差不多）、**字符串之间的比较**（根据位数，判断该位数上的字母那个unicode的数字大或小；另，再讲个较为特殊一点的：一个是“9”，另一个是“10”，则按位数进行比较，切勿当做数学题做，这里9和1是同一位数的，所以按照数学正常比大小顺序，9>1，则“9”>10）、**字符串与数字之间的比较**（先将字符串转为数字，再进行比较；若无法转为数字，则返回false）

​     另：附加两个方法：toLowerCase()【将所有字母转换为小写形式】、toUpperCase()【将所有字母转换为大写形式】

+ 相等性运算符是先将其他非数字类型的转换为数字类型，在进行相等判断；
+ 数据类型转换规则表

|数据类型|示例|转换结果|
|:---:|:---:|:---:|
|布尔值（真）|true|1|
|布尔值（假）|false|0|
|字符串（纯数字类型）|“99”|99|
|字符串（非纯数字类型）|“99hello123”|NaN|
|空值|null|null|
|未定义的值|undefined|undefined|

+ 相等性特殊情况规则（数据类型转换后仍不是数字类型的特殊情况）

|运算数类型|示例|返回值|
|:---:|:---:|:---:|
|其中一个为null，另一个为undefined|var x1 = null; var x2; var result = (x1==x2);|true|
|两个值均为null|var x1 = null; var x2 = null; var result = (x1==x2)|true|
|两个值均为undefined|var x1; var x2; var result = (x1==x2);|true|
|其中一个为数字，另一个为NaN|var x1 = 5; vae x2 = parseInt("a"); var result = (x1==x2);|false|
|两个值均为NaN|var x1 = parseInt("a"); var x2 = parseInt("b"); var result = (x1==x2);|false|

<font color="red">**那为什么两个值为NaN时，返回为false？**</font>

因为NaN是不可预测的数字，所以当两个值为NaN时，不知道哪个是大，哪个是小，因此返回false；

## 七、JavaScript条件语句

+ **if-else if-else语句**与java用法相同，这里不阐述；
+ **switch-case-default语句**与java用法相同，这里也不阐述；

## 八、JavaScript函数

+ 函数的格式如下：
  ```javascript
  function 函数名称(参数1，参数2，参数3，······){
  	函数方法中的内容
  }
  ```

+ javascript的函数返回形式与java不同，它不需要在函数名前特别声明该返回什么类型，也不要加什么void，只需要按正常的在函数内部内容**直接返回return加需要返回的内容**就行了，没有返回值就不用写吧return；

## 九、文档对象模型

###9.1   含义

+ HTML的应用程序接口
+ 简称DOM
+ 将整个HTML页面看作由各种节点层级构成的结构

###9.2   在javascript中查找HTML元素有三种方法

+ HTML元素的id名称查找
  + 其格式为`document.getElementById("id名称");`

  + 如果未找到id名称，则会返回null；如果找到，则以对象形式返回；
  
  + ```javascript
    //根据id名称获取元素（id为test）对象
    var test = document.getElementId("test");
    //获取元素内容
    var result = test.innerHTML;
    ```
  
+ HTML元素的标签名称查找

  + 其格式为`document.getElementsByTagName("标签名称");`

  + 注意这里的Elements是复数形式，其原因在于可能存在多个元素符合要求；这时若找到标签名称，则会以数组的形式返回；而找不到，则返回null；

  + ```javascript
    var test = document.getElementsByTagName("p");
    var result = p[0].innerHTML;
    ```

+ HTML元素的类名称查找

  + 其格式为`document.getElementsByClassName("类名称");`

  + 注意这里的Elements是复数形式，其原因在于可能存在多个元素符合要求；这时若找到标签名称，则会以数组的形式返回；而找不到，则返回null；

  + ```javascript
    var test = document.getElementsByClassName("coral");
    var result = test[0].innerHTML;
    ```



###9.3   DOM HTML

####9.3.1   使用document.write（）方法可以想页面动态输出内容

​       示例：

       ```javascript
       <body>
       	<script>
       		document.write("Hello");   //若想要在write括号里实现换行操作，需跟平时的HTML的标签一样；使用<br>标签进行换行；例如：document.write("asdjkaj<br>adhad");
       	</script>
       </body>
       ```

####9.3.2   innerHTML的用法

+ innerHTML可以实现用于获取元素内容，也可用于修改元素内容。

+ 其格式为:

  + 获取：

         ```javascript
         var 变量名 = 元素对象.innerHTML;
         示例：
         var p = document.getElementById("test");  //获取id为test的元素
         var msg = p.innerHTML;
         ```

  + 修改内容：

  ```javascript
  元素对象.innerHTML = 新的内容;
  //元素对象可以通过document对象的getElementById("id名称")方法获取
  示例：
  var p = document.getElementById("test");  //获取id为test的元素
  p.innerHTML = "<strong>三大飒飒</strong>";
  ```

  + 修改元素属性：

  ```javascript
  元素对象.属性名称(attribute) = 新的属性值;
  示例：
  var img = document.getElementById("image");   //更改id为image的图片地址src属性
  img.src = "img/newpix.jpg";
  img.alt = "百合";
  
  元素对象.setAttribute("属性名称","新的属性值");
  示例：
  var img = document.getElementById("image");   //同上
  img.setAttribute("src","img/newpic.jpg");
  ```

###9.4   DOM CSS

+ 其格式为：

      ```javascript
      元素对象.style.属性 = 新的值；
      示例：
      var test = document.getElementById("test");
      test.style.backgroundColor = "blue";   //属性名称（例如，backgroundColor)需修改为骆驼命名法；
      
      var test = document.getElementById("test").style.backgroundColor = "blue";
      ```

### 9.5   DOM事件

+ 含义：可以再HTML页面状态发生变化时执行代码
+ 示例：

​    `<button onclick = "alert('hi')">点我会弹出对话框</button>button>`

+ HTML常用事件属性

|事件属性|解释|
|:---:|:---:|
|onabort|图像加载过程被中断|
|onblur|元素失去焦点|
|onchange|域的内容被改变|
|onclick|元素被鼠标左键点击|
|ondbclick|元素被鼠标左键双击|
|onerror|加载文档或图像时发送错误|
|onfocus|元素获得焦点|
|onkeydown|键盘按键被按下|
|onkeypress|键盘按键被按下并松开|
|onkeyup|键盘按键被松开|
|onload|页面或图像被加载完成|
|onmousedown|鼠标按钮被按下|
|onmousemove|鼠标被移动|
|onmouseout|鼠标从当前元素上移动|
|onmouseover|鼠标移动到当前元素上|
|onmouseup|鼠标按键被松开|
|onreset|重置按钮被点开|
|onresize|窗口或框架的大小被更改|
|onselect|文本被选中|
|onsubmit|提交按钮被点击|
|onunload|退出页面|

### 9.6   DOM节点                           

#### 9.6.1   添加HTML元素

+ 两个步骤：

  + 创建新的元素，其格式为：`document.createElement("元素标签名");`
  + 将其追加到一个已存在的元素中，其格式为：`已存在的元素对象.appendChild(需要添加的新元素对象);`【已存在的元素对象可由document对象的getElementById("id名称")获取】
  + 其总的格式为：

    ```javascript
    var p = document.createElement("p");   //创建段落标签<p>
    var test = document.getElementById("test");
    test.appendChild(p); //追加
    ```

####9.6.2   删除HTML元素

+ 两个步骤：

  + 使用document对象的getElementById("id名称")方法获取该元素；

  + 使用removeChild()方法将其从父元素中删除

  + 另：若父元素有明确的的id名称，可以使用getElementById()方法获取

    示例：

    ```javascript
    var test = document.getElementById("test");    //获取父元素
    var p = document.getElementById("p01");   //获取子元素
    test.removeChild(p);   //删除子元素
    ```

  + 另：若父元素没有明确的id名称，则可以使用子元素的parentNode属性获取其父元素对象

  ​       示例：

  ```javascript
  var p = document.getElementById("p01");  //获取子元素
  var test = p.parentNode;    //获取父元素
  test.removeChild(p);    //删除子元素
  ```

+ 代码如下：
  
  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>测试</title>
          <style>
              div{
                  width:200px;
                  height:400px;
                  border:1px solid;
                  padding:10px;
                  margin:10px;
                  float:left;
              }
              p{
                  background-color:pink;
                  width:100px;
              }
          </style>
      </head>
      <body>
          <h3>测试</h3>
          <hr>
          <div>
              习近平总书记关于科技伦理治理的重要论述和重要指示批示，
              深刻阐明了科技伦理对保障科技安全、国家安全的重要意义，
              对科技伦理治理提出了明确要求，为保证我国科技创新活动的
              正确方向和加强科技伦理治理提供了根本遵循。
              <p>深入学习领会习近平总书记关于科技伦理治理的重要论述
              精神，增强科技伦理治理的责任感紧迫感</p>
          </div>
          <div id = "container">
              加强科技伦理治理是实现高水平科技自立自强的有力支撑。
              党的十九届四中、五中全会对完善国家科技治理体系、提升科技
              治理能力和水平作出具体部署。
              <p id = "box">有力支撑</p>
          </div>
          <script>
              var container = document.getElementById("container");
              var box = document.getElementById("box");
              container.removeChild(box);
          </script>
      </body>
  </html>
  ```
  
  代码测试结果：
  
  ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureJavaScript%E5%9F%BA%E7%A1%80%E5%9B%BE8.png)
  
  
  
  
