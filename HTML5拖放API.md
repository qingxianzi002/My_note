# HTML5拖放API

+ 用于拖拽网页中的元素并放置到页面上的指定区域或直接将本地文件拖放在网页中

## 一、DragEvent事件

+ 继承于事件MouseEvent
+ DragEvent的常用事件

|事件名称|存储模式|时间目标|解释|
|:---:|:----:|:---:|:---:|
|ondragstart|读写模式|该事件由被拖拽的元素触发|当用户刚开始拖动元素时触发该事件|
|ondrag|保护模式|该事件由被拖拽的元素触发|当元素处于被拖动状态时触发该事件|
|ondragenter|保护模式|该事件由被拖拽的元素触发|当被拖动的元素进入到可以被放置下来的有效区域的瞬间触发该事件|
|ondragleave|保护模式|该事件由被拖拽的元素触发|当被拖动的元素离开了可以被放置下来的有效区域的瞬间触发该事件|
|ondragover|保护模式|该事件由目标区域元素触发|当被拖动的元素处于可以被放置下来的有效区域内时，该事件会不停地被触发。该事状态在dragenter之后，在dragleave之前|
|ondrop|只读模式|该事件由目标区域元素触发|当被拖动的元素被放置在有效的区域时触发该事件|
|ondragend|保护模式|该事件由被拖拽的元素触发|当拖动操作结束时激发该事件。例如，在拖动元素的过程中释放鼠标左键或按下键盘上的Esc键均可触发该事件。该事件状态在drop之后。|

+ 在整个拖放生命周期触发的事件按照顺序如下：

​    dragstart  ——  drag  ——  dragenter  ——  dragover  ——  dragleave  ——  drop  ——  dragend

## 二、DataTransfer对象

+ HTML5拖放API允许在拖放过程中携带一项或多项自定义数据内容
+ 数据内容可以使用拖放事件DragEvent中的datatransfer属性（来源于HTML5的DataTransfer对象）进行添加和处理
+ DataTransfer对象的属性

|   属性名称   |                            属性值                            |                             解释                             |
| :----------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|  dopEffect   | **none**【不允许任何操作】、**copy**【该状态下被拖拽的元素将复制一个副本放到指定的放置区域】、**move**【该状态下被拖拽的元素将移动到指定的放置区域，该属性值为默认值】、**link**【该状态下被拖拽的元素与被放置区域之间将创建连接】 |              改属性用于获取或重置当前的拖放类型              |
| effetAllowed | **none**【不允许任何操作】、**copy**【只允许复制操作】、**copyLink**【允许复制或者链接】、**copyMove**【允许复制或者移动】、**link**【只允许链接操作】、**linkMove**【允许链接或移动】、**move**【只允许移动操作】、**all**【允许所有（复制、移动或链接）操作】、**uninitialized**【尚未设置，等同于all】 |                    提供所有允许的拖放类型                    |
|    types     |                         DOMString[]                          | 该属性为只读属性。返回值为字符串数组。包含了所有存入数据的类型 |
|    items     |                   DataTransferItemList对象                   | 该属性为只读模式。返回值为DataTransferItemList对象，该对象是以列表的形式保存所有的存入数据 |
|    files     |                         FileList对象                         | 该属性为只读模式。如果拖放的是一个或多个本地文件，则该属性返回值为文件列表对象。如果拖放过程中没有涉及本地文件，则本地列表为空 |

+ DataTransfer对象的常用方法

|        方法名称         |                             解释                             |
| :---------------------: | :----------------------------------------------------------: |
|     getData(format)     | 获取DataTransfer对象中的format格式的数据。一般在ondrop事件中使用，获取传递的数据内容。其中format替换成某种数据类型，例如，纯文本类型为text/plain |
|  setData(format,data)   | 将数据设置为format格式，并保存在DataTransfer对象中进行传递。一般在ondragstart事件中使用，设置需要传递的数据内容【可以添加不同类型的数据，如纯文本类型（text/plain），超链接类型（text/uri-list），HTML代码类型（text/html）】 |
|   clearData([format])   | 清除DataTransfer对象中format格式的数据。如果省略参数，则表示清除全部数据 |
| setDragImage(image,x,y) | 设置拖拽元素时所显示的自定义图标。其中image为图片对象，x和y分别指的是图标与鼠标在水平和垂直方向上的距离 |

## 三、拖放元素过程

+ 实现拖放的主要过程：

  + 为需要被拖放的元素添加draggable属性（设置为true，表示为可拖放状态；设置为false，表示为不可拖放状态），使其允许被拖放；

  ​       示例：

  ```html
  <p draggable = "true">
  	内容
  </p>
  ```

  具体代码示例：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>HTML5拖放API之设置可拖放元素</title>
          <style>
              p{
                  width:100px;
                  height:100px;
                  background-color:yellow;
              }
          </style>
      </head>
      <body>
          <h3>HTML5拖放API之设置可拖放元素</h3>
          <hr>
          <p draggable = "true">这是一个可拖放的段落元素.</p>
      </body>
  </html>
  ```

  代码测试结果：

  ​                           <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE1.png" style="zoom: 67%;" />

  ​                          ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE2.png)       

  + 在被拖拽元素的ondragstart事件中初始化需要传递的数据信息（监听元素刚被拖动的状态，同时也可以为ondragstart事件设置自定义名称的回调函数）

  ​      示例：

  ```javascript
  <p draggable = "true" ondragstart = "drag(event)">
      内容
  </p>
  
  当用户开始拖动元素时，元素的ondragstart事件会被触发并调用drag（）函数来传递参数event对象，其中event.datatransfer属性用于在拖放过程中传递数据
  
  function drag(ev){
      ev.dataTransfer.setData("text/plain","Hello HTML5");
  }
  ```

    在event事件中的target属性表示被拖拽的元素对象，所以可以用纯文本类型传递元素对象的id名称

  ```javascript
  function drag(ev){
  	ev.dataTransfer.setData("text/plain",ev.target.id);  //传递元素id名称
  }
  有利于使用getData()方法获取id名称，并且使用document.getElementById()方法获得并处理被拖拽元素的对象
  ```

  + 为作为放置区域的元素设置ondragover事件，取消默认操作【可放置区域的元素（该元素指就在要放置的区域内）必须带有ondragover事件，用于监听是否可有可拖放的元素进入目标区域】

  ​       示例：

  ```javascript
  <p ondragover = "allowDrop(event)">
      内容
  </p>
  
  //回调函数allowDrop()和drop()名称自定义，表示当前事件触发时的处理操作
  
  function allowDrop(ev){
      ev.preventDefault();  //阻止默认处理方式（无法将元素放置到可放置的区域内）
  }
  ```

  + 为作为放置区域的元素设置ondrop事件（不是被拖拽的元素，而是一直在该放置区域的元素触发的），接受并处理传递过来的数据内容（前提是通过datatransfer.getData()方法获取传递的数据内容）

  ​     示例：

  ```javascript
  <p ondragover = "allowDrop(event)" ondrop = "drop(event)">
  	内容
  </p>
  
  //回调函数drop()名称自定义
  
  function drop(ev){
  	ev.preventDefault();   //先阻止默认行为（ondrop事件默认是以超链接的形式打开数据）
  	var data = ev.datatransfer.getData("text");  //获取数据，另这里的括号可以简写为text或url，如果没有找到指定数据内容，返回空字符串
  }
  ```

  具体代码如下：
  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset = "utf-8">
          <title>测试</title>
          <style>
              p{
                  width:100px;
                  height:100px;
                  background-color:yellow;
              }
              #container{
                  border:1px solid;
                  width:200px;
                  height:200px;
              }
          </style>
      </head>
      <body>
          <h3>测试</h3>
          <hr>
          <p id="test" draggable = "true" ondragstart = "drag(event)">
              这是一个可以被拖放的段落元素。
          </p>
          <div id="container" ondragover = "allowDrop(event)" ondrop = "drop(event)">
              这是一个可以用于放置被拖放元素的区域
          </div>
          <script>
              function drag(ev){
                  ev.dataTransfer.setData("text/plain",ev.target.id);
              }
  
              function allowDrop(ev){
                  ev.preventDefault();
              }
  
              function drop(ev){
                  ev.preventDefault();
                  var id = ev.dataTransfer.getData("text");
                  var p = document.getElementById(id);
                  ev.target.appendChild(p);
              }
          </script>
      </body>
  </html>
  ```

  代码测试结果：

  初始状态：

  

  ​                                              ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE3.png)

  拖动状态：

  

  ​                                                ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE4.png)
  
  放置状态：
  
  
  
  ​                                              ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE5.png)

## 四、自定义拖放图标

+ `setDragImage(image,x,y);`自定义拖拽时显示的图标；一般用于ondragstart事件的回调函数中，表示从拖动动作开始时更改拖放图标；

​       示例：

```html
function drag(ev){
    var img = new Image();
    img.src = "image/star.jpg";
    ev.dataTransfer.setDragImage(img,10,10);  //鼠标箭头（在图里）离图标左上角水平和垂直的距离
}
```

+ 一句话就是：原本拖拽文字时会鼠标会携带着相应的文字，而定义上述图标后，就会由携带的文字变成定义的图片；

## 五、自定义拖放行为

+ DataTransfer对象具有effectAllowed和dropEffect属性用于规定拖放行为

+ 拖放时，三种常见效果：

  + copy------表示被拖拽的数据从它的初始位置复制到可放置区域
  + move------表示被拖拽的数据将从它的初始位置移动到可放置区域
  + link--------表示被拖拽的数据将从它的初始位置链接一个快捷方式到可放置区域

+ 一般在**ondragstart**事件被触发时通过设置**effectAllowed**属性值来规定允许进行哪种操作。

+ 一般在**dragenter**或**dragover**事件被触发时通过设置**dropEffect**属性值来规定允许进行哪种操作。

​       示例：

```html
ev.dataTransfer.effectAllowed = "move";
```

+ 具体操作行为，可参考[DataTransfer对象](#二、DataTransfer对象)

+ effectAllowed与dropEffect属性取值对照表

|effectAllowed设置的取值|dropEffect允许的取值|
|:---:|:---:|
|none|none|
|copy|copy|
|copyLink|copy或link|
|copyMove|copy或move|
|link|link|
|linkMove|link或move|
|move|move|
|all|copy、link或move任意其一|
|uninitialized并且被拖拽的元素为文本内容|move或copy|
|uninitialized并且被拖拽的元素为普通元素|cpy或link|
|uninitialized并且被拖拽的元素为带href属性的超链接元素`<a>`|link或copy|

+ 代码如下：

     ```html
     <!DOCTYPE html>
     <html>
         <head>
             <meta charset="utf-8">
             <title>HTML5拖放API之自定义拖放行为</title>
             <style>
                 p{
                     width:100px;
                     height:100px;
                     background-color:lightblue;
                     float:left;
                     margin:10px;
                     text-align:center;
                 }
                 div#container{
                     border:1px solid;
                     width:340px;
                     height:100px;
                     clear:both;
                     margin:10px;
                     text-align:center;
                 }
             </style>
         </head>
         <body>
             <h3>测试</h3>
             <hr>
             <p id="test1" draggable="true" ondragstart = "drag1(event)">
                 拖拽效果<br>move
             </p>
             <p id = "test2" draggable = "true" ondragstart = "drag2(event)">
                 拖拽效果<br>copy
             </p>
             <p id = "test3" draggable="true" ondragstart = "drag3(event)">
                 拖拽效果<br>link
             </p>
             <div id="container" ondragover = "allowDrop(event)" ondrop = "drop(event)">
                 可放置区域
             </div>
             <script>
                 function drag1(ev){
                     var dataTrans = ev.dataTransfer;
                     dataTrans.effectAllowed = "move";
                     dataTrans.setData("text/plain",ev.target.id);
                 }
                 function drag2(ev){
                     var dataTrans = ev.dataTransfer;
                     dataTrans.effectAllowed = "copy";
                     dataTrans.setData("text/plain",ev.target.id);
                 }
                 function drag3(ev){
                     var dataTrans = ev.dataTransfer;
                     dataTrans.effectAllowed = "link";
                     dataTrans.setData("text/plain",ev.target.id);
                 }
                 function allowDrop(ev){
                     ev.preventDefault();
                 }
                 function drop(ev){
                     ev.preventDefault();
                 }
             </script>
         </body>
     </html>
     ```

代码测试结果:



​                                               ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE6.png)      

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE7.png)

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE8.png)

**从上方三幅结果图中可看出不同的拖放行为导致鼠标指针呈现不同的样式**

## 六、本地文件的拖放

+ 就是通过DataTransfer对象的files属性获取文件列表，而无须设置传递数据内容
+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>HTML5拖放API之本地文件拖放</title>
        <style>
            #fileCheck{
                width:300px;
                height:100px;
                border:1px dashed;  /*宽度为1像素的虚线框*/
                margin:20px;
            }
            li{
                margin:10px;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <div id="fileCheck" ondragover = "allowDrop(event)" ondrop="drop(event)">   
            请将文件拖放至此处。
        </div>
        <div id="status"></div>
        <script>
            function allowDrop(ev){
                //解除当前元素为可放置被拖拽元素的区域
                ev.preventDefault();
            }
            function drop(ev){
                //解除当前元素为可放置被拖拽元素的区域
                ev.preventDefault();
                //获取拖拽的文件列表
                var files = ev.dataTransfer.files;
                //记录文件的状态信息等
                var fileStatus;
                //获取单个文件对象
                var f;
                for(var i=0;i<files.length;i++){
                    f = files[i];
                    var lastModified = f.lastModifiedDate;  //把最近的一次修改时间给它
                    var lastModifiedStr = lastModified.toLocaleString();   //将日期时间显示为纯文本形式
                    //组合文件相关信息
                    fileStatus += '<li>文件名称：'+f.name+'<br>文件类型：'+f.type+'<br>文件大小：'+f.size+'字节<br>修改时间：'+lastModifiedStr+'</li>';
                }
                var status = document.getElementById("status");
                status.innerHTML = '<ul>'+fileStatus+'</ul>';
            }
        </script>
    </body>
</html>
```

代码测试结果：

​                              <img src="https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE9.png" style="zoom:150%;" />

​                            ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE10.png)   

## 七、关于target在事件中指的是什么的探究

通过不断查证，得出一条结论：**target的指向与定义它的事件有关，谁触发了事件，target就指代谁；**

## 八、关于#container与div#container之间的区别或联系的探究

代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>测试</title>
        <style>
            div#container{
                background-color:blue;
            }
        </style>
    </head>
    <body>
        <h3>测试</h3>
        <hr>
        <div id="container">
            我是一个小宝贝
        </div>
        <p id="container">
            阿呆撒大所大大所多所多撒大所大多;
        </p>
    </body>
</html>
```

测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%E6%8B%96%E6%94%BEAPI%E5%9B%BE11.png)

<font color="red">【分析】:综上所述，div#container意思是只有在div的标签且id为container中有用，除此之外，其他id为container的标签无法对其产生影响。而#container是对所有id为container的标签起作用</font>

