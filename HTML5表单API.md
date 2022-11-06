# HTML5表单API

## 一、表单元素`<form>`属性一览表

|属性名称|属性值|解释|
|:---:|:---:|:---:|
|action|URL地址|规定表单提交数据的服务器地址|
|method|get(会将表单组件中的数据名称和值转换为文本形式的参数并直接加原URL地址后面，安全要求不高，且每次传输不超过2KB)或post(不会出现在地址栏中，安全要求高，传输量大且多种类型)|规定发送表单数据的HTTP方法，默认值为get|
|name|自定义表名称|规定表单的名称，具有唯一性|
|enctype|application/xxx-form-urlencoded(默认值，用于处理表单控件中所有的value属性值)、multipart/form-data(以二进制形式处理表单数据，用于表单上传文件中使用)、text/plain(通过表单发送邮件)|规定表单数据发送之前的编码要求|
|target|_blank、_self、_parent、_top、iframename|规定在何处打开action属性中的URL地址|

##二、`<input>`标签的常用属性

|属性名称|属性值|解释|
|:---:|:---:|:---:|
|accept|MIME文件类型|只能与`<input type = "file">`的文件上传控件配合使用，用于规定文件上传控件可选择的文件类型|
|alt|文本内容|只能与`<input type = "image">`的图像按钮控件配合使用，用于规定无法显示图像时的提示文本|
|checked|checked|只能与`<input type = "radio">`的单选按钮或`<input type = "checkbox">`的复选框配合使用，用于规定页面加载时默认为选中状态|
|disabled|disabled|用于加载时禁用此元素|
|maxlength|数值|用于规定输入框中字符的最大长度|
|name|自定义名称|用于定义`<input>`标签的名称，如果没有填写name属性值，则表单组件的内容无法被正确提交|
|readonly|readonly|用于定义`<input>`标签中的文本为不可编辑的只读状态|
|size|数值|用于定义输入框中可见字符的个数|
|type|text、password、radio、checkbox、submit、reset、button、image、file、hidden|用于规定`<input>`标签的类型|
|value|文本值|用于规定`<input>`标签的值|

##三、`<input>`标签的基本输入类型

|类型名称|解释|
|:---:|:---:|
|text|用于显示单行文本输入框|
|password|用于显示密码输入框，其中字符会被`*`遮挡|
|radio|用于显示单选按钮|
|checkbox|用于显示复选按钮|
|submit|用于显示提交按钮，该按钮可以将表单数据发送到服务器|
|reset|用于显示重置按钮，该按钮可以清除表单中的所有数据|
|button|用于显示无动作按钮，通常点击事件需要配合JavaScript使用|
|image|用于显示图像形式的提交按钮|
|file|用于显示文件上传控件，包含输入区域和浏览按钮|
|hidden|用于隐藏输入字段|

##四、选项元素`<option>`的属性

| **属性名称** | **属性值** |                         **解释**                         |
| :----------: | :--------: | :------------------------------------------------------: |
|   disabled   |  disabled  |                 首次加载时禁用当前选项。                 |
|    label     |  文本内容  | 规定选项的简写内容，该内容将取代原选项内容显示在列表中。 |
|   selected   |  selected  |            规定首次加载时当前选项为选中状态。            |
|    value     |  文本内容  |           规定提交表单时发送给服务器的选项值。           |

## 五、HTML表单基础

+ 用于收集用户输入或选择的数据，并将其作为参数提交到远程服务器

### 5.1   表单标签`<form>`

+ 定义一个完整的表单框架，有结束语`</form>`

+ 内部包含各式各样的表单组件
+ 其格式为：

     ```html
     <form>
     	内容及组件
     </form>
     ```

### 5.2   输入标签`<input>`

+ 可参考[`<input>`标签的常用属性](#二、`<input>`标签的常用属性)
+ 其格式为`<input type = "输入类型" name = "自定义名称" />`
+ 在上面的格式中输入类型可参考[`<input>`标签的基本输入类型](三、`<input>`标签的基本输入类型)

#### 5.2.1   单行文本框text

+ 其格式为`<input type = "text" name = "自定义名称" />`
+ 自定义名称默认字符长度为20个字符

#### 5.2.2   密码框password

+ 其格式为`<input type = "password" name = "自定义名称" />`
+ 输入的字符会被密码专用符号所遮挡
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>第一个表单页面</title>
    </head>
    <body>
        <h3>第一个表单页面</h3>
        <hr>
        <form method = "post" action = "URL">
            用户名：
            <input type = "text" name = "username" />
            <br/>
            密--码：
            <input type = "password" name = "pwd" />
        </form>
    </body>
</html>
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE1.png)

#### 5.2.3   单选按钮radio

+ 单选按钮，其样式为一个空心圆形区域
+ 其格式为`<input type = "radio" name = "自定义名称" value = "值" />自定义value的值（即显示在页面上的文字）`
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>单选按钮radio的简单应用</title>
    </head>
    <body>
        <h3>单选按钮radio的简单应用</h3>
        <hr>
        <form method = "post" action = "URL">
            <input type = "radio" name = "gender" value = "M" checked/> 
            男
            <br />
            <input type = "radio" name = "gender" value = "F" />
            女
        </form>
    </body>
</html>

//checked表示默认选中的选项
//name名字相同的为一组
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE2.png)

#### 5.2.4   复选框checkbox

+ 其样式为一个可勾选的空心方形区域，点击时，会出现打钩符号（√）
+ 其格式为：

  `<input type = "checkbox" name = "自定义名称" value = "值" />自定义value值`

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>复选框checkbox的简单应用</title>
    </head>
    <body>
        <h3>复选框checkbox的简单应用</h3>
        <hr>
        问卷调查：您是通过何种方式了解XX产品的？
        <form method = "post" action = "URL">
            <input type = "checkbox" name = "group1" value = "1" />
            朋友推荐
            <br />
            <input type = "checkbox" name = "group1" value = "2" checked />
            搜索引擎
            <br />
            <input type = "checkbox" name = "group1" value = "3" checked />
            媒体宣传
            <br />
            <input type = "checkbox" name = "group1" value = "4" checked />
            其他
        </form>
    </body>
</html>
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE3.png)

#### 5.2.5   提交按钮submit

+ 其格式为`<input type = "submit" value = "值" />`
+ 点击按钮时，当前表单中所有数据整理成名称和值的形式进行参数传递，提交到服务器处理
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>登陆界面</title>
    </head>
    <body>
        <h3>登陆界面</h3>
        <hr>
        <form method = "post" action = "URL">
            用户名：
            <input type = "text" name = "username" />
            <br>
            密&nbsp&nbsp&nbsp码：
            <input type = "password" name = "username" />
            <br>
            <input type = "submit" value = "登陆" />
        </form>
    </body>
</html>

//这里的URL是你的服务器地址，由于目前还没有，所以演示不出来
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE4.png)

#### 5.2.6   重置按钮reset

+ 其作用在与清空当前表单中的所有数据
+ 其格式为`<input type = "reset" value = "值" />`
+ value值如果不写，则默认文字内容为reset
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>登陆界面</title>
    </head>
    <body>
        <h3>登陆界面</h3>
        <hr>
        <form method = "post" action = "URL">
            用户名：
            <input type = "text" name = "username" />
            <br>
            密&nbsp&nbsp&nbsp码：
            <input type = "password" name="pwd" />
            <br>
            <input type = "reset" value = "重置" />
            <input type = "submit" value = "登陆" />
        </form>
    </body>
</html>
```

代码测试结果：

输入内容：



![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE5.png)

点击重置按钮：



![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE6.png)

#### 5.2.7   无动作按钮button

+ 其样式为一个按钮形状
+ 其格式为`<input type = "button" value = "值" />`【值为按钮上的文字】
+ 需与脚本配合使用

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>无动作按钮button的简单应用</title>
    </head>
    <body>
        <h3>无动作按钮button的简单应用</h3>
        <hr>
        <form method = "post" action = "URL">
            <input type = "button" value = "按钮1" />
            <input type = "button" value = "按钮2" onclick = "welcome()"/>
        </form>
        <script>
            function welcome(){
                alert("Hello Html5");
            }
        </script>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE7.png)

#### 5.2.8   图片提交按钮image

+ 样式为自定义图片，外观跟按钮一样
+ 其格式为`<input type = "image" src = "图片URL地址" alt = "替代文本内容" />`
+ 代码如下：

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>图片提交按钮image的简单应用</title>
        </head>
        <body>
            <h3>图片提交按钮image的简单应用</h3>
            <hr>
            <form method = "post" action = "URL">
                用户名：
                <input type = "text" name = "username" />
                <br>
                密&nbsp&nbsp&nbsp码：
                <input type = "password" name = "pwd" />
                <br>
                <input type = "image" src = "C:/Users/清弦子之忆/Downloads/背景1.jpg" alt = "登陆" />
            </form>
        </body>
    </html>
    ```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE8.png)

#### 5.2.9   文件上传域file

+ 其样式为一个可点击的浏览器按钮和一个文本输入框
+ 点击按钮时，会弹出对话框
+ 其格式为`<input type = "file" name = "自定义名称" />`与`<input type = "file" accept = "MIME文件类型"`
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>文件上传组件file的简单应用</title>
    </head>
    <body>
        <h3>文件上传组件file的简单应用</h3>
        <hr>
        <form method = "post" action = "URL">
            所有文件类型：
            <input type = "file" name = "file01" />
            <br>
            图片格式文件：
            <input type = "file" name = "file02" accept="image/*" />
            <br>
            WORD格式文件：
            <input type = "file" name = "file03" accept = "application/msword" />
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE9.png)

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE10.png)

#### 5.2.10   隐藏域hidden

+ 作用在于在页面中对用户不可见，移交表单时，隐藏域的数据名称和值一起发送到服务器端
+ 其格式为`<input type = "hidden" name = "自定义名称" value = "值" />`【这里的自定义名称和值应先设置正确的值】
+ 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset = "utf-8">
		<title>测试</title>
	</head>
	<body>
		<h3>测试</h3>
		<hr>
		<form method = "post" action = "URL">
			用户名：
			<input type = "text" name = "username" />
			<br>
			密码：
			<input type = "password" name = "pwd" />
			<br>
			<input type = "hidden" name = "country" value = "CHINA" />  
			<input type = "submit" value = "登陆" />
		</form>
	</body>
</html>
```

+ 由于没有服务器地址，所以无法操作

### 5.3   标记标签`<label>`

+ 有结束语`</label>`
+ 其格式为：

```html
使用for属性引用对应表单控件的id名称
<label for="name1">姓名：</label>
<input type="text" name="name1" id="name1" />

<label>姓名：<input type="text" name="name1" /></label>
```

+ 其作用在于可以在被点击时为对应的表单控件生成焦点（即点击“姓名：”，旁边的输入框会显示光标；
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>标记标签label的简单应用</title>
        <style>
            form{
                border:1px solid;
                text-align:center;
                width:250px;
            }
        </style>
    </head>
    <body>
        <h3>标记标签label的简单应用</h3>
        <hr>
        <form method="post" position="URL" name="form1">
            <label for="name1">用户名：</label>
            <input type="text" name="name1" id="name1" />
            <br>
            <label for="pwd1">密&nbsp&nbsp&nbsp码：</label>
            <input type = "password" name="pwd1" id="pwd1" />
            <br>
            <input type="submit" value="登陆" />
        </form>
        <br>
        
        <form method="post" action="URL" name="form2">
            <label>用户名：
                <input type="text" name="form2" />
            </label>
            <br>
            <label>密&nbsp&nbsp&nbsp码：
                <input type="password" name="pwd2" />
            </label>
            <br>
            <input type="submit" value="登陆" />
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE11.png)

如上图，点击用户名三字时，就会显示光标（输入框）

### 5.4   多行文本标签`<textarea>`

+ 可以实现多行文本区域，容纳许多文字
+ 与`<input>`标签的区别在于允许换行
+ 其所具有的属性：

|属性名称|属性值|解释|
|:---:|:---:|:---:|
|rows|数值|设置文本框的行数|
|cols|数值|设置文本框的宽度，默认20|
|wrap|soft或hard|规定文本框的换行方式，默认soft|
|readonly|readonly|将文本框改为只读模式|
|disabled|disabled|禁止使用该文本框|

+ 示例：

```html
<textarea cols="15" rows="20"></textarea>
//20行，每行15个字符
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>多行文本标签textarea的简单应用</title>
        <style>
            textarea{
                width:20em;
                height:5em;
                display:block;
                margin:10px;
            }
        </style>
    </head>
    <body>
        <h3>多行文本标签textarea的简单应用</h3>
        <hr>
        <textarea>这是可编辑状态的正常textarea元素</textarea>
        <textarea readonly>这是只读状态的textarea元素</textarea>
        <textarea disabled>这是禁用状态的textarea元素</textarea>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE12.png)

### 5.5   列表标签`<select>`

+ 有结束语`</select>`

+ 创建单选或多选菜单
+ 根据属性值的不同可显示为下拉菜单（select与option配合使用）或列表框【option的属性可参考[选项元素`<option>`的属性](#四、选项元素`<option>`的属性)】
+ 其具有的属性

| **属性名称** | **属性值** |                          **解释**                          |
| :----------: | :--------: | :--------------------------------------------------------: |
|   disabled   |  disabled  |                        禁用列表菜单                        |
|   multiple   |  multiple  | 规定允许同时选中多个选项，这个属性会使该列表标签变为列表框 |
|     name     | 自定义名称 |                     规定列表元素的名称                     |
|     size     |    数值    |                规定列表菜单中可见选项的个数                |

+ **<font color="red">如果是单选状态只能为其中一个选项添加selected属性。如果为多个选项同时添加了该属性，则默认也只显示最后一个带有selected属性的选项。*【注意：这里的selected不是上面的标签，是option的属性，主要用于默认选择的情况】*</font>**

+ 对上面红色第二句的解释：意思是在单选框中原本应显示第一个，然而所有选项都加上selected，就默认显示最后一个；
+ 若列表选项过多，可使用`<optgroup>`标签进行分类，其具有两个属性：

| **属性名称** | **属性值** |         **解释**         |
| :----------: | :--------: | :----------------------: |
|   disabled   |  disabled  | 禁用选项组中的所有选项。 |
|    label     |  文本内容  |    规定选项组的标题。    |

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>列表标签select的简单应用</title>
        <style>
            select{
                width:20em;
                display:block;
                margin:10px;
            }
        </style>
    </head>
    <body>
        <h3>列表标签select的简单应用</h3>
        <hr>
        <p>
            简单下拉菜单（单选）：
        </p>
        <select>
            <option value="apple" selected>苹果</option>
            <option value="cherry" selected>樱桃</option>
            <option value="grape" selected>葡萄</option>
        </select>

        <p>
            分组下拉菜单（单选）：
        </p>
        <select>
            <optgroup label="水果类">
                <option value="apple">苹果</option>
                <option value="cherry">樱桃</option>
                <option value="grape">葡萄</option>
            </optgroup>
            <optgroup label="蔬菜类">
                <option value="potato">土豆</option>
                <option value="tomato">番茄</option>
                <option value="eggplant">茄子</option>
            </optgroup>
        </select>

        <p>
            简单列表菜单（多选）：
        </p>
        <select multiple>
            <option value="apple">苹果</option>
            <option value="cherry">樱桃</option>
            <option value="grape">葡萄</option>
        </select>

        <p>
            分组列表菜单（多选）：
        </p>
        <select multiple size="8">
            <optgroup label="水果类">
                <option value="apple">苹果</option>
                <option value="cherry" label="鹦鹉">樱桃</option>
                <option value="grape">葡萄</option>
            </optgroup>
            <optgroup label="蔬菜类">
                <option value="potato">土豆</option>
                <option value="tomato">番茄</option>
                <option value="eggplant">茄子</option>
            </optgroup>
        </select>
    </body>
</html>

//在页面上的多选操作为Ctrl建+目标选项
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE13.png)

### 5.6   按钮标签`<button>`

+ 有结束语`</button>`

+ 在网页上生成自定义样式的按钮
+ `<button>`和`</button>`标签之间可包含普通纯文本内容、图像、文本格式化标签等内容

+ 其具有的属性为：

| **属性名称** |            **属性值**             |      **解释**      |
| :----------: | :-------------------------------: | :----------------: |
|   disabled   |             disabled              | 禁用当前按钮元素。 |
|     name     |            自定义名称             |  规定按钮的名称。  |
|     type     | button  reset(重置)  submit(提交) |  规定按钮的类型。  |
|    value     |             文本内容              | 规定按钮的初始值。 |

+ **如果将`<button>`按钮用于表单内，则必须为其规定type属性**
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>按钮标签button的简单应用</title>
        <style>
            #btn1{
                width:100px;
                height:30px;
                color:white;
                font-weight:bold;
                font-family: "微软雅黑Light";
                line-height: 30px;
                background-color:#3C9DFF;
                text-decoration:none;
                border:0px;
            }
            #btn1:hover{
                background-color:#0061C1;
            }
            #btn2{
                background:transparent;
                border:0;
            }
        </style>
    </head>
    <body>
        <h3>按钮标签button的简单应用</h3>
        <hr>
        <h4>文本按钮：</h4>
        <button id="btn1">
            按钮
        </button>
        <br>
        <h4>图片按钮：</h4>
        <button id="btn2"><img src="F:/古风/图3.jpeg" width="80" height="80" />
        </button>
    </body>
</html>

//text-decoration:文本样式，如下划线，这里是设置无
//transparent:无颜色，透明
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE14.png)

### 5.7   域标签`<fieldset>`和域标题标签`<legend>`

+ 域标签`<fieldset>`用于将同一个表单中的多个表单元素分组显示
+ 配合以域标题标签`<legend>`使用，可以为每个分组的区域显示独立的标题
+ 其代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>域标签fieldset的简单应用</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h3>域标签fieldset的简单应用</h3>
        <hr>
        <form method="post" action="server.html">
            <fieldset>
                <legend>账号信息</legend>
                <label>用户名：<input type="text" name="username" /></label><br>
                <label>密&nbsp&nbsp&nbsp码：<input type="text" name="pwd1" /></label><br>
                <label>确&nbsp&nbsp&nbsp认：<input type="text" name="pwd2" /></label><br>
            </fieldset>
            <br>
            <fieldset>
                <legend>个人信息</legend>
                <label>姓  名：<input type="text" name="name" /></label><br>
                <label>单  位：<input type="text" name="title" /></label><br>
                <label>职  位：<input type="text" name="position" /></label><br>
                <label>职  称：<input type="text" name="title" /></label><br>
                <label>手  机：<input type="text" name="tel" /></label><br>
                <label>邮  箱：<input type="text" name="email" /></label><br>
            </fieldset>
            <br>
            <div>
                <input type="reset" value="重置" />   <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE15.png)

## 六、HTML5表单新特性

+ HTML5表单新增输入类型

|  **输入类型**  |                   **含义**                    |
| :------------: | :-------------------------------------------: |
|      tel       |                   电话号码                    |
|     email      |                 电子邮箱地址                  |
|      url       |                    URL网址                    |
|     number     |                     数值                      |
|     range      |             包含数值范围的滚动条              |
|    datetime    | UTC日期（包含年、月、日）和时间（包含时、分） |
| datetime-local |                本地日期和时间                 |
|      time      |            选择时间（包含时、分）             |
|      date      |          选择日期（包含年、月、日）           |
|      week      |          选择星期（包含年、第几周）           |
|     month      |            选择月份（包含年、月）             |
|     search     |             搜索栏目的文本输入域              |
|     color      |                  颜色选择器                   |

### 6.1   电话号码类型tel

+ 代码：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5表单新增输入类型tel的简单应用</title>
        <style>
            form{
                width:200px;
                margin:20px;
            }
        </style>
    </head>
    <body>
        <h3>HTML5表单新增输入类型tel的简单应用</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    新增输入类型tel的简单应用
                </legend>
                <label>电话号码：
                    <input type="tel" name="tel" />
                </label>
            </fieldset>
            <br>
            <input type="submit" values="提交" />
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE16.png)

### 6.2   电子邮箱类型email

+ 只允许输入包含@的字样字符的邮箱，否则会提示错误
+ 当这个出现在`<form>`和`</form>`标签之中，浏览器会自动检查所输入的邮箱字符是否正确
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5表单新增输入类型email的简单应用</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>HTML5表单新增输入类型email的简单应用</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    新增输入类型tel的简单应用
                </legend>
                <label>电子邮箱：
                    <input type="email" name="email" />
                </label>
            </fieldset>
            <div>
                <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE17.png)

### 6.3   地址类型url

+ 提交表单时，会自动检查是否正确
+ 其格式为：

```html
网站地址：<input type="url" name="url" />
```

+ 代码：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5表单新增输入类型url的简单应用</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>HTML5表单新增输入类型email的简单应用</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    新增输入类型tel的简单应用
                </legend>
                <label>网站地址：
                    <input type="url" name="url" />
                </label>
            </fieldset>
            <div>
                <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE18.png)

### 6.4   数值类型number

+ 其具有三个属性：min（设置最小值）和max（设置最大值）和step（规定输入合法数字的间隔，即两个正确的数字之间的距离）
+ 其格式为：

```html
<input type="number" name="number1" min="0" max="100" step="20" />
//设置了一个只能输入0-100之间的数字，且满足间隔为20；
//满足的数字有0，20，40，60，80，100
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5表单新增输入类型number的简单应用</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align: center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>HTML5表单新增输入类型number的简单应用</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    新增输入类型number的简单应用
                </legend>
                <label>请输入20的整数倍：
                    <input type="number" name="number" min="0" max="100" step="20" />
                </label>
            </fieldset>
            <div>
                <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE19.png)

### 6.5   数值范围类型range

+ 其显示在页面上是一个滑动条，用户可拖动滑动条来选择自己需要的数字，类型window电脑右下角的调节声音
+ 其也具有三个属性：min（设置最小值）和max（设置最大值）和step（规定输入合法数字的间隔，即两个正确的数字之间的距离）
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>
            测试
        </title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    range应用
                </legend>
                <label>音量大小：
                    <input type="range" name="range" id="range" min="0" max="100"
                    step="1" value="0" onchange="change()" />
                </label><span id= "volume">0</span>
            </fieldset>
        </form>
        <script>
            function change(){
                var range = document.getElementById("range");
                var test = document.getElementById("volume");
                test.innerHTML = range.value;
            }
        </script>
    </body>
</html>

//补充一句：这里的<span></span>用于显示当前刻度值的文本内容，其特点为随文本内容的长度而变化
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE20.png)

### 6.6   日期选择器Date Pickers

+ 各种时间选择器的总称

+ 其各种时间选择器为：

  + datetime类型——选择包含年月日和时间的内容
  + datetime-local类型——选择包含年月日和时间的内容
  + time类型——选择包含小时和分钟
  + date类型——选择包含年月日
  + week类型——选择包含年份和第几周
  + month类型——选择包含年份和月份

+ 其格式为：

```html
<input type="时间类型" name="date" />
```

+ 代码：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5表单新增输入类型Date Pickers的应用</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    显示日期和时间
                </legend>
                <label>本地：
                    <input type="datetime-local" name="dete1" />
                </label>
            </fieldset>
            <br>
            <fieldset>
                <legend>
                    只显示时间
                </legend>
                <label>时间：
                    <input type="time" name="date2" />
                </label>
            </fieldset>
            <br>
            <fieldset>
                <legend>
                    只显示日期
                </legend>
                <label>日期：
                    <input type="date" name="date3" />
                </label>
            </fieldset>
            <br>
            <fieldset>
                <legend>
                    显示年份和月份
                </legend>
                <label>月份：
                    <input type="month" name="date4" />
                </label>
            </fieldset>
            <br>
            <fieldset>
                <legend>
                    显示年份和第几周
                </legend>
                <label>星期：
                    <input type="week" name="date5" />
                </label>
            </fieldset>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE21.png)

### 6.7   搜索框类型search

+ 其效果表面为普通文本框，但其不同之处在于在文本内容后面出现一个快捷符号“x”，为用于快速清空搜索框的文本内容
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>测试</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    search的应用
                </legend>
                <label>关键词：
                    <input type="search" name="search" />
                </label>
            </fieldset>
            <div>
                <input type="submit" value="搜索" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE22.png)

### 6.8   颜色类型color

+ 显示颜色的选择器
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>color的简单应用</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>   
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    color的简单应用
                </legend>
                <label>颜色选择：
                    <input type="color" name="color" id="color" onchange="change()" />
                </label> 
            </fieldset>
            <div>
                <input type="submit" value="提交" />
            </div>
        </form>
        <script>
            function change(){
                var color=document.getElementById("color").value;
                alert(color);
            }
        </script>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE23.png)





<img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE24.png" style="zoom: 80%;" />

### 6.9   数据列表标签`<datalist>`

+ 为普通单行文本输入框提供提示选项。提示选项初始为隐藏状态，当焦点位于对应的文本输入框时会在下方自动展开提示选项，用户可以通过点击提示选项自动生成文本内容
+ 其具有的属性：

| **属性名称** | **属性值** |            **解释**            |
| :----------: | :--------: | :----------------------------: |
|   disabled   |  disabled  |         禁用列表菜单。         |
|   multiple   |  multiple  |   规定允许同时选中多个选项。   |
|     name     | 自定义名称 |      规定列表元素的名称。      |
|     size     |    数值    | 规定列表菜单中可见选项的个数。 |

+ 与`<option>`和文本输入框配合使用
+ 示例：

```html
<input type="text" list="myList" />
<datalist id="myList">
    <option>选项一</option>
    <option>选项二</option>
    <option>选项三</option>
</datalist>
//自定义id名称被文本输入框调用
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>测试</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    detalist的应用
                </legend>
                <label>请选择：
                    <input type="text" list="mylist" />
                </label>
                <datalist id="mylist">
                    <option value="apple">苹果</option>
                    <option value="grape">葡萄</option>
                    <option value="banana">香蕉</option>
                </datalist>
            </fieldset>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE25.png)

### 6.10   输出标签`<output>`

+ 显示各类输出结果
+ 与oninput（其作用在于表单元素的数据发生变化时即时触发）【用于form中】事件配合使用，动态变化输出结果
+ 其具有的属性：

| **属性名称** | **属性值**   | **解释**                                                 |
| ------------ | ------------ | -------------------------------------------------------- |
| for          | 元素的id名称 | 定义**关联**的一个或多个元素。  若为多个元素，用逗号隔开 |
| form         | 表单的id名称 | 定义输出标签隶属于的一个或多个表单。                     |
| name         | 自定义名称   | 规定输出标签的名称。                                     |

+ 代码：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5的output的简单应用</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL" oninput="output1.innerHTML=range1.value">
            <fieldset>
                <legend>
                    新增元素标签output的简单应用
                </legend>
                音量大小：
                <input type="range" name="range1" id="range2" min="0" max="100" step="1" value="0" />
                <output name="output1" for="range2" >
                    0
                </output>
            </fieldset>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE26.png)

### 6.11   autofocus属性

+ 属性使得指定的输入框在页面加载时自动成为焦点，适用于所有`<input>`标签的类型
+ 其格式为：

```html
<input type="password" name="pwd" autofocus />
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>测试</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align: center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    autofocus的应用
                </legend>
                <label>用户名：
                    <input type="text" name="username" />
                </label>
                <br>
                <label>密码：
                    <input type="password" name="pwd" autofocus/>
                </label>
            </fieldset>
            <div>
                <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE27.png)

如上图，默认密码框获得光标

###6.12   form属性

+ 可以指定`<input>`元素从属于哪个表单，同一个`<input>`元素可以属于一个甚至多个表单。

+ 该属性适用于所有`<input>`标签的类型

+ 外部的`<input>`标签在使用时必须引用表单标签`<form>`的id名称

  示例：

```html
<form id="form1">
    <!--内容略-->
</form>
<input id="username" type="text" form="form1" />
```

+ 外部的`<input>`标签还允许同时从属多个表单，在使用form属性引用多个表单的id名称时需要使用逗号进行分割

​       示例：

```html
<form id="form1">
    <!--内容略-->
</form>
<form id="form2">
    <!--内容略-->
</form>
<input id="username" type="text" form="form1, form2" />
```

### 6.12   formaction系列属性

+ 以formaction为首的一系列属性被称为表单重写属性

+ 用于更改表单的一些属性设置，并且仅适用于类型为submit或image的`<input>`标签

+ 常用表单重写属性一览表

  | **属性名称**   | **解释**                       |
  | -------------- | ------------------------------ |
  | formaction     | 用于重写表单的action属性。     |
  | formenctype    | 用于重写表单的enctype属性。    |
  | formmethod     | 用于重写表单的method属性。     |
  | formnovalidate | 用于重写表单的novalidate属性。 |
  | formtarget     | 用于重写表单的target属性。     |

+ 方便为不同的按钮设置不同的服务器地址

### 6.13   placeholder属性

+ 其作用在于在输入框中显示所设置的文字提示（灰色字体，更改不了）【使用placeholder在input中设置文字提示】
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>测试</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    placeholder的应用
                </legend>
                <label>用户名：
                    <input type="text" name="username" placeholder="请输入用户名：" />
                </label>
                <br>
                <label>密码：
                    <input type="password" name="pwd" placeholder="请输入密码：" />
                </label>
            </fieldset>
            <div>
                <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE28.png)

### 6.14   required属性

+ 所设置的文本框提交时不能为空，否则提交失败
+ 其格式为：

```html
<label>用户名：
     <input type="text" name="username" required />
</label>
```

效果图如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE29.png)

### 6.15   max,min和step属性

+ 用于为数字或日期的input类型规定所允许的数值范围
+ 均适用于3种类型的`<input>`标签：date pickers（日期选择器）、number（数值）和range（数值范围）
+ 具体效果参考上文的代码

### 6.16   multiple属性

+ 允许`<input>`标签同时输入多个值。
+ 该属性只适用于2种类型的`<input>`标签：email（电子邮箱）和file（上传文件控件）

+ 其格式为：

```html
选择文件：<input type="file" name="file" multiple />
//这里为可以同时选择多个文件
```

### 6.17   width和height属性

+ 设置图像宽度和长度
+ 只能用于类型为image的`<input>`标签
+ 其格式为：

```html
<input type="image" src="image/btn.jpg" alt="登录" width="240" height="50" />
```

### 【重点】6.18   pattern属性

+ 用于约束输入域的内容，该属性以正则表达式的方式对输入内容进行规范
+ 适用于6种 `<input> `标签：text（单行文本框）、 search（搜索框）、 url（URL地址）、 tel（电话）、 email （电子邮箱）以及 password（密码框）
+ 其格式为：

```html
<input type="text" name="country_code" pattern="[A-z]{3}" title="Three letter country code" />
```

+ JavaScript常用正则表达式

|括号表达式|解释|
|:---|:---|
|[0-9]|查找0-9之间的数字|
|[a-z]|查找a-z之间的字符|
|[A-Z]|查找A-Z之间的字符|
|[A-z]|查找A-z之间的字符|
|[abc]|查找括号之间的任意一个字符|
|[^abc]|查找括号内字符以外的所有内容|
|（red|blue|green）|查找“|”符号间隔的任意选项内容|

|量词表达式|解释|
|:---|:---|
|n+|查找任何包含至少一个n的字符串|
|n*|查找任何包含至少一个n的字符串|
|n?|查找任何包含0~1个n的的字符串|
|n{X}|查找包含X个n的字符串|
|n{X,Y}|查找包含X或Y个n的字符串|
|n{X,}|查找至少包含X个n的字符串|
|n$|查找任何以n结束的字符串|
|^n|查找任何以n开头的字符串|
|? =n|查找任何后面紧跟字符n的字符串|
|?! n|查找任何后面没有紧跟字符n的字符串|

|元字符|解释|
|:---|:---|
|.|查找除了换行符与行结束符以外的单个字符|
|\w|查找单词字符|
|\W|查找非单词字符|
|\d|查找数字字符|
|\D|查找非数字字符|
|\s|查找空格字符|
|\S|查找非空格字符|
|\n|查找换行符|
|\f|查找换页符|
|\r|查找回车符|
|\t|查找制表符|
|\xxx|查找八进制数字xxx对应的字符，如果没有找到则返回null|
|\xdd|查找十六进制数字dd对应的字符，如果没有找到则返回null|
|\uxxxx|查找十六进制数字xxx对应的Unicode字符，如果没有找到则返回nulls|

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>测试</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    pattern的应用
                </legend>
                <label>邮政编码：
                    <input type="text" name="country_code" pattern="[0-9]{6}" title="请输入6位国内邮政编码" />
                </label>
            </fieldset>
            <div>
                <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>

//<input>里的title为提示语句
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE30.png)

### 6.19   list属性

+ 可以为输入框提供一系列选项提示，需要与数据列表标签`<datalist>`配合使用。数据列表标签`<datalist>`是输入域的提示选项列表，当输入域获得焦点时，提示选项列表会自动展开

### 6.20   autocomplete属性

+ 显示曾经填写过的内容选项，其属性值有on（开启）或off（关闭）
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>测试</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL">
            <fieldset>
                <legend>
                    autocomplete的应用
                </legend>
                <label>关键词：
                    <input type="search" name="search" autocomplete/>
                </label>
            </fieldset>
            <div>
                <input type="submit" value="搜索" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE31.png)

### 6.21   novalidate属性

+ 其作用在于表单提交时，不验证所输入的文本框内容是否符合，其属性值有true和false；【true为不验证】
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>测试</title>
        <style>
            form{
                width:280px;
                margin:20px;
            }
            div{
                text-align:center;
                margin-top:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <form method="post" action="URL" novalidate="true">
            <fieldset>
                <legend>
                    账号信息
                </legend>
                <label>用户名：
                    <input type="text" name="username" required/>
                </label>
                <br>
                <label>密码：
                    <input type="password" name="pwd1" />
                </label>
                <br>
                <label>确认：
                    <input type="password" name="pwd2" />
                </label>
                <br>
            </fieldset>
            <br>
            <fieldset>
                <legend>
                    个人信息
                </legend>
                <label>姓名：
                    <input type="text" name="username" required/>
                </label>
                <br>
                <label>单位：
                    <input type="text" name="title" />
                </label>
                <br>
                <label>职位：
                    <input type="text" name="position" />
                </label>
                <br>
                <label>邮箱：
                    <input type="email" name="email" />
                </label>
                <br>
            </fieldset>
            <br>
            <div>
                <input type="reset" value="重制" />    <input type="submit" value="提交" />
            </div>
        </form>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE32.png)

若不设置，则

s

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E8%A1%A8%E5%8D%95API%E5%9B%BE33.png)

