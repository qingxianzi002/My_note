# HTML5 Web 存储API

+ HTML5存储 API 包含了本地存储（localStorage）与会话存储（sessionStorage）两种方式，其中 localStorage 可以实现客户端数据的永久存储，而 sessionStorage 只能在浏览器打开的时间段中存储数据；若浏览器关闭，则数据全部消失；

## 一、HTTP cookie存储

+ HTTP cookie由服务器端生成，将数据以“键-值”对的形式发送给客户端浏览器，浏览器将这些数据保存至指定目录下的文本文件中，这样在下一次访问相同的网站时可以直接使用该cookie数据
+ 最早设计出来是用于处理单个事务，不太适用于存储大量数据
  + cookie的存储数据量小：一个cookie最多只能存放4096B左右的数据，并且部分浏览器对cookie有数量限制
  + cookie请求限制：每次浏览器与服务器进行请求时，cookie都会存放在请求头部传输到服务器端。如果请求头部的大小过大，就会导致服务器无法处理

## 二、HTML5 Web 存储

+ 适用于存储大量数据
+ HTML5提供了两种客户端存储数据的方法：本地存储（localStorage）与会话存储（sessionStorage）。localStorage方法存储的数据没有时间限制，永久保存，并且数据可以被不同的网页页面共享使用。sessionStorage主要是针对一个session会话的数据存储，只能在创建session的网页中使用，当用户关闭浏览器窗口时，该数据将被删除

## 三、检查浏览器支持情况

+ 由于存储的数据库可以直接被 HTML DOM中的window对象访问，故最简单的检测方法是使用 JavaScript 代码分别检查 window.localStorage 或 windows.sessionStorage 是否存在
+ 主要相关代码：

```javascript
if(window.localStorage){
  //浏览器支持Web存储中的localStorage
}else{
  //浏览器不支持Web存储中的localStorage
}

if(window.sessionStorage){
  //浏览器支持Web存储中的sessionStorage
}else{
  //浏览器不支持Web存储中的sessionStorage
}
```

## 四、Storage 接口

+ 使用Storage接口实现本地存储（localStorage）或会话存储（sessionStorage）数据的添加、修改、查询或删除
+ 包含了只读属性length，该属性返回值为整数形式，表示当前存储对象中“键-值”对的总数量

### 4.1   Storage接口的常用方法一览

| **方法名称**        | **解释**                                                     |
| ------------------- | ------------------------------------------------------------ |
| key(n)              | 用于返回数据中第n个值的名称。如果n大于所有键值对的总数，则返回null值。 |
| getItem(key)        | 用于返回指定键名称的值，如果该名称不存在，则返回null值。     |
| setItem(key, value) | 用于设置一条自定义的“键-值”对数据，如果该数据原先不存在，则会在存储对象的键值对列表中新增该数据；如果该数据的键名称原先存在，则看数据值是否有变化，如有变化则更新成最新值，否则不做任何操作。 |
| removeItem(key)     | 用于删除存储对象中指定key名称的数据，如果没有则不做任何操作。 |
| clear()             | 用于清空存储对象中的键值对列表，如果原先就无任何数据则不做任何操作。 |

### 4.2   localStorage 和 sessionStorage  

+ localStorage方法用于在客户端永久存储数据，该方法存储的数据没有过期时间，即使关闭了浏览器重新打开，数据也仍然保存在设备中可继续使用。
+ sessionStorage方法和localStorage方法的语法结构均类似，只不过sessionStorage方法有时间限制，只能用于在浏览器打开的时间段（又称为一个session）中存储数据，若浏览器关闭则数据全部消失

### 4.3   存储数据

+ 在Storage接口中提供的setItem()方法可以用于存储数据

  + 其格式为：

  ```javascript
  localStorage.setItem('key', 'value');
  或
  sessionStorage.setItem('key', 'value');
  
  数据是以“键-值”对的方式进行存储的，每个数据值对应一个指定的键名称进行索引。其中key换成需要存储的键名称（可自定义），value换成需要存储的数据值。这里的引号可以是单引号或双引号的任意一种
  
  localStorage['key']= 'value';
  或
  localStorage.key = 'value';
  
  localStorage.setItem('name', 'His name is " Wallace".');
  或
  localStorage.setItem("name", "His name is 'Wallace'.");
  ```

  代码如下：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <title>分别使用localStorage和sessionStorage存储数据</title>
          <style>
              form{
                  width:200px;
              }
              select,button{
                  margin:10px;
                  width:180px;
              }
          </style>
      </head>
      <body>
          <h3>分别使用localStorage和sessionStorage存储数据</h3>
          <hr>
          <p>
              请在下列列表中选择颜色并点击保存按钮。
          </p>
          <form>
              <fieldset>
                  <legend>
                      颜色信息
                  </legend>
                  <select id="color">
                      <option value = "red">red</option>
                      <option value = "green">green</option>
                      <option value = "blue">blue</option>
                  </select>
                  <br>
                  <button onclick = "saveLocal()">
                      localStorage存储
                  </button>
                  <br>
                  <button onclick = "saveSession()">
                      sessionStorage存储
                  </button>
              </fieldset>
          </form>
          <script>
              function saveLocal(){
                  var color = document.getElementById("color").value;
                  alert("数据已保存到localStorage中！当前颜色为："+color);
                  localStorage.setItem('color',color);
              }
  
              function saveSession(){
                  var color = document.getElementById("color").value;
                  alert("数据已保存到sessionStorage中！当前颜色为："+color);
                  sessionStorage.setItem('color',color);
              }
          </script>
      </body>
  </html>
  ```

  代码测试结果：

  ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%20Web%E5%AD%98%E5%82%A8API%E5%9B%BE1.png)

​          ![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%20Web%E5%AD%98%E5%82%A8API%E5%9B%BE2.png)

### 4.4   读取指定数据

+ 在Storage接口中提供的getItem()方法可以用于获取指定了键名称的数据值
+ 其格式为：

```javascript
localStorage.getItem('name')
或
sessionStorage.getItem('name')

//这里的name需要替换成指定的键名称
//如果该名称name并不存在，则直接返回null值

以上格式可改为：
var 变量名称 = localStorage.name;
或
var x = 'name';
var studentID = localStorage.x;
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>记录用户页面访问次数</title>
    </head>
    <body>
        <h3>记录用户页面访问次数</h3>
        <hr>
        localStorage存储：您曾经访问了当前页面<span id="time1">0</span>次。
        <br>
        sessionStorage存储：您曾经访问了当前页面<span id="time2">0</span>次。
        <script>
            var count1 = localStorage.getItem('count1');
            var count2 = sessionStorage.getItem('count2');
            console.log("最初："+count1);
            if(count1 == null){
                count1 = 0;
            }
            if(count2 == null){
                count2 = 0;
            }

            document.getElementById("time1").innerHTML = count1;
            document.getElementById("time2").innerHTML = count2;

            localStorage.setItem('count1',parseInt(count1)+1);
            console.log("最后："+localStorage.getItem('count1'));
            sessionStorage.setItem('count2',parseInt(count2)+1);
        </script>
    </body>
</html>
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%20Web%E5%AD%98%E5%82%A8API%E5%9B%BE3.png)

### 4.5   数据遍历

+ 如果需要读取所有的数据，可以先使用Storage接口中length属性获取数据的数目
+ 使用key(n)方法依次获取每一条数据的键名称
+ 其格式为：

```javascript
//获取使用localStorage存储的数据总数
var num = localStorage.length; 
//进行存储数据的遍历
for(var i=0;i<num;i++){
	//获取键名称
	var name = localStorage.key(i);
	//获取键值
	var value = localStorage.getItem(name);
}
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5 Web存储API之数据遍历</title>
    </head>
    <body>
        <h3>HTML5 Web存储API之数据遍历</h3>
        <hr>
        <h4>我的留言板</h4>
        <!--留言框-->
        <textarea id = "comment"></textarea>
        <br />
        <!--保存按钮-->
        <button onclick = "saveComment()">
            提交留言
        </button>
        <!--全部留言记录-->
        <ol id="all"></ol>
        <script>
            var allComments = document.getElementById("all");
            getAll();
            //读取历史留言
            function getAll(){
                //获取历史留言个数
                var num = localStorage.length;
                if(num == 0){
                    allComments.innerHTML = "暂无留言.";
                }else{
                    allComments.innerHTML = "";
                    for(var i=0;i<num;i++){
                        var x = document.createElement("li");
                        var name = localStorage.key(i);
                        x.innerHTML = localStorage.getItem(name);
                        allComments.appendChild(x);
                    }
                }
            }
            //保存当前留言内容
            function saveComment(){
                var comment = document.getElementById("comment");
                var now = new Date();
                var key = now.getTime();
                
                localStorage.setItem(key,comment.value);
                //清空留言板
                comment.value = "";
                //刷新留言历史记录
                getAll();
            }
        </script>
    </body>
</html>
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%20Web%E5%AD%98%E5%82%A8API%E5%9B%BE4.png)

### 4.6   删除指定数据

+ 在Storage接口中提供的removeItem()方法可以用于删除指定了键名称的数据
+ 其格式为：

```javascript
localStorage.removeItem('name')
或
sessionStorage.removeItem('name')
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5 Web存储API之删除指定数据</title>
    </head>
    <body>
        <h3>HTML5 Web存储API之删除指定数据</h3>
        <hr>
        <form>
            <fieldset>
                <legend>添加测试数据</legend>
                <input id="testData" type="text" />
                <input type="button" value="添加" onclick="addData()">
            </fieldset>
        </form>
        <p>当前在sessionStorage中保存的数据如下：</p>
        <table id="allData" border="1"></table>
        <script>
            var allData = document.getElementById("allData");
            refreshData();
            //刷新数据显示
            function refreshData(){
                var length = sessionStorage.length;
                //如果session数据总数为0
                if(length==0){
                    allData.innerHTML = "目前暂无数据.";
                }
                else{
                    //清空列表
                    allData.innerHTML = "<tr><th>键名称</th><th>键值</th><th>操作</th></tr>";
                    //遍历所有数据并显示出来
                    for(var i = 0;i<length;i++){
                        var tr = document.createElement("tr");
                        var name = sessionStorage.key(i);
                        tr.innerHTML = '<td>'+name+'</td><td>'+sessionStorage.getItem(name)+'</td><td><button onclick="delData('+i+')">删除</button></td>';
                        allData.appendChild(tr);
                    }
                }
            }
            //添加新数据
            function addData(){
                var length = sessionStorage.length;
                var n = length+1;
                var test = document.getElementById("testData");
                //获取测试数据内容
                var value = test.value;
                //保存当前测试数据
                sessionStorage.setItem(n,value);
                //清空测试数据
                test.value = "";
                refreshData();
            }
            //删除第n个数据
            function delData(n){
                var name = sessionStorage.key(n);
                sessionStorage.removeItem(name);
                refreshData();
            }
        </script>
    </body>
</html>
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%20Web%E5%AD%98%E5%82%A8API%E5%9B%BE5.png)

### 4.7   清空所有数据

+ 在Storage接口中提供的clear()方法可以用于清空所有Web存储数据
+ 其格式为：

```javascript
localStorage.clear();
或
sessionStorage.clear();
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>HTML5 Web存储API之删除全部数据</title>
        <style>
            td{
                text-align:center;
            }
            img.goods{
                width:200px;
                height:200px;
                display:block;
            }
            img.cart{
                width:80px;
                height:80px;
            }
        </style>
    </head>
    <body>
        <h3>HTML5 Web存储API之删除全部数据</h3>
        <hr>
        <table>
            <tr>
                <td><img class="goods" src="F:/古风/充电宝1.jpg" />
                <button onclick = "updateNum(1)">
                    加入购物车
                </button></td>
                <td><img class="goods" src="F:/古风/充电宝2.jpg" />
                <button onclick = "updateNum(2)">
                    加入购物车
                </button></td>
                <td><img class="goods" src="F:/古风/充电宝3.jpg" />
                <button onclick = "updateNum(3)">
                    加入购物车
                </button></td>
            </tr>
        </table>
        <h4>我的购物车</h4>
        <button onclick = "clearAll()">
            清空购物车
        </button>
        <ol id="myCart">购物车中尚无商品.</ol>
        <script>
            var myCart = document.getElementById("myCart");
            //从localStorage中获取保存的商品数据
            var item01 = localStorage.item01;
            var item02 = localStorage.item02;
            var item03 = localStorage.item03;
            //如果没有获取到，则从0开始计数
            if(item01 == null){
                item01 = 0;
            }
            if(item02 == null){
                item02 = 0;
            }
            if(item03 == null){
                item03 = 0;
            }

            //更新购物车中的商品个数
            function updateNum(n){
                if(n == 1){
                    item01++;
                }
                else if(n==2){
                    item02++;
                }
                else if(n==3){
                    item03++;
                }
                showGoods();
            }

            //在购物车中显示商品列表
            function showGoods(){
                //清空购物车显示内容
                myCart.innerHTML = "";

                //判断商品不为空时显示
                if(item01 != 0){
                    localStorage.item01 = item01;
                    addGood(1,item01);
                }
                if(item02 != 0){
                    localStorage.item02 = item02;
                    addGood(2,item02);
                }
                if(item03 != 0){
                    localStorage.item03 = item03;
                    addGood(3,item03);
                }
            }

            //添加第n件商品，共num个
            function addGood(n,num){
                var good = document.createElement("li");
                good.innerHTML = '<img src = "F:/古风/充电宝'+n+'.jpg" class="cart" />共'+num+'件.';
                myCart.appendChild(good);
            }

            //清空购物车
            function clearAll(){
                //清空购物车显示内容
                myCart.innerHTML = "购物车中尚无商品.";
                //清空商品个数
                item01 = 0;
                item02 = 0;
                item03 = 0;
                //清空存储数据
                localStorage.clear();
            }
        </script>
    </body>
</html>
```

代码测试结果如下：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%20Web%E5%AD%98%E5%82%A8API%E5%9B%BE6.png)

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML5%20Web%E5%AD%98%E5%82%A8API%E5%9B%BE7.png)
