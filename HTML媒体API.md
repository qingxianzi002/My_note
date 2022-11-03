# HTML媒体API

+ 提供一些元素标签，就可以在页面上播放媒体文件

+ 支持的音频/视频文件格式有：
  + MP3(压缩率高，音频)
  + MPEG-4(MP4)【视频】格式
  + Wav
  + Ogg
  + WebM(在.mkv的基础上改造的)
##一、常用的音频格式：

  + MP3格式——媒体文件的后缀名为.mp3
  + Ogg格式——媒体文件的后缀名为.ogg
  + Wav格式——媒体文件的后缀名为.wav

##二、常用的视频格式：

  + MPEG4格式——后缀名为.mp4
  + Ogg格式——后缀名为.ogg
  + WebM格式——后缀名为.webm

##三、主流浏览器的支持情况

|音频格式|IE|Firefox|Chrome|Safari|Opera|
|:---:|:----:|:---:|:---:|:---:|:---:|
|**音频**||||||
|MP3|9.0及以上版本支持|不支持|3.0及以上版本支持|3.0及以上版本支持|不支持|
|Ogg|不支持|3.5及以上版本支持|3.0及以上版本支持|不支持|10.5及以上版本支持|
|Wav|不支持|3.5及以上版本支持|不支持|3.0及以上版本支持|10.5及以上版本支持|
|**视频**||||||
|MPEG4|9.0及以上版本支持|不支持|5.0及以上版本支持|3.0及以上版本支持|不支持|
|Ogg|不支持|3.5及以上版本支持|5.0及以上版本支持|不支持|10.5及以上版本支持|
|WebM|不支持|4.0及以上版本支持|6.0及以上版本支持|不支持|10.6及以上版本支持|

## 四、应用

### 4.1   音频

#### 4.1.1   格式

```html
<audio src="路径" controls>
</audio>
```

#### 4.1.2   常用属性

|属性名称|值|解释|
|:---:|:---:|:---:|
|autoplay|autoplay|音频准备就绪时自动播放|
|controls|controls|显示播放、暂停按钮和声音调节控件|
|loop|loop|音频结束时自动重复播放|
|muted|muted|静音状态|
|preload|preload|音频预加载，不与autoplay同时使用|
|src|url|播放的路径|

#### 4.1.3   检查浏览器支持情况

+ 可在`<audio>`与`</audio>`之间添加不支持的语句
+ 示例：

```html
<audio src="路径" controls>
	对不起，您的浏览器不支持
</audio>

这个表示当音频播放不了时，就会显示中间的那句话；如果播放的了，就不会执行中间的那句话
```

+ 可使用javaScript检查

+ 示例：

```javascript
<script>
	function test(){
		var supportAudio = !!document.createElement("audio").canPlayType;
		if(supportAudio){
			document.getElementById("support").innerHTML = "恭喜，您的浏览器支持HTML5音频";
		}else{
			document.getElementById("support").innerHTML = "对不起，您的浏览器不支持HTML5音频";
		}
	}
	test();
</script>

原理在于动态创建<audio>标签，然后检测<audio>元素包含的canPlayType函数是否存在，最后获取id为support的div标签内容，修改内容。
```

+ 若不支持，可使用以下进行多种情况考虑

```html
<audio controls>
	<source src="music/song.ogg">
	<source src="music/song.mp3">
	对不起，您的浏览器不支持HTML5音频API
</audio>

其目的在于先判断.ogg音频能否执行，不行则执行下一个.mp3，若还不行，则执行那句话
```

#### 4.1.4   自定义音频控制

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>自定义音频控制按钮</title>
    </head>
    <body>
        <h3>自定义音频控制按钮</h3>
        <hr>
        <audio id = "music01">
            <source src = "C:/Users/清弦子之忆/Music/真的不快乐.mp3">
        </audio>
        <button id = "btn" onclick = "toggleMusic()">
            播放
        </button>
        <script>
            var music = document.getElementById("music01");
            var toggleBtn = document.getElementById("btn");
            function toggleMusic(){
                if(music.paused){
                    music.play();
                    toggleBtn.innerHTML = "暂停";
                }
                else{
                    music.pause();
                    toggleBtn.innerHTML = "播放";
                }
            }
        </script>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML%E5%AA%92%E4%BD%93API%E5%9B%BE1.png)

### 4.2   视频

#### 4.2.1   格式

```
<video src="路径" controls>
</video>
```

#### 4.2.2   常用属性

|属性名称|值|解释|
|:---:|:---:|:---:|
|autoplay|autoplay|视频准备就绪后自动播放|
|controls|controls|显示播放、暂停按钮和声音调节控件|
|loop|loop|当视频结束后自动重新播放|
|preload|preload|视频预加载，并准备播放，不与autoplay同时使用|
|src|url|播放音频的url地址|
|width|（像素值）|设置视频播放器的宽度|
|height|（像素值）|设置视频播放器的高度|

#### 4.2.3   检查浏览器的支持情况

+ 在`<video>`和`</video>`之间添加不支持语句
+ 示例：

```html
<video src="路径" controls>
	对不起，您的浏览器不支持
</video>
```

+ 可使用javaScript来检查
+ 示例：

```javascript
<script>
    function test(){
        var supportVideo = !!document.createElement("video").canPlayType;
        if(supportVideo){
            document.getElementById("support").innerHTML = "恭喜，您的浏览器支持HTML5视频";
        }else{
            document.getElementById("support").innerHTML = "对不起，您的浏览器不支持HTML5视频";
        }
    }
    test();
</script>

其原理在于创建<video>标签，然后检测其包含的canPlayType函数是否存在；
(!!)表示判断<video>是否可以创建出来，若可以，则返回true；若不可以，则返回false；
```

+ 若不支持，可使用以下进行多种情况考虑

```
<video controls="controls">
	<source src="video/song.ogg">
	<source src="video/song.mo4">
	对不起，您的浏览器不支持
</video>
```

#### 4.2.4   自定义视频控制

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>自定义视频控制</title>
        <style>
            body{
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h3>自定义视频控制</h3>
        <hr>
        <video id = "video01" src = "C:/Users/清弦子之忆/Desktop/蔡徐坤 - Hug me (抱我).mp4" width = "400">
            对不起，您的浏览器不支持HTML5视频API。
        </video>

        <div>
            <button id = "toggleBtn" onclick = "toggleVideo()">
                播放
            </button>
            <button onclick = "bigVideo()">
                画面放大
            </button>
            <button onclick = "smallVideo()">
                画面缩小
            </button>
        </div>

        <script>
            var video01 = document.getElementById("video01");
            var toggleBtn = document.getElementById("toggleBtn");
            function toggleVideo(){
                if(video01.paused){
                    video01.play();
                    toggleBtn.innerHTML = "暂停";
                }
                else{
                    video01.pause();
                    toggleBtn.innerHTML = "播放";
                }
            }
            function bigVideo(){
                video01.width = "600";
            }
            function smallVideo(){
                video01.width = "200";
            }
        </script>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML%E5%AA%92%E4%BD%93API%E5%9B%BE2.png)

## 五、其他通用功能

### 5.1   标记媒体播放时间范围

+ 使用格式为`src="音频或视频的URL地址"#t=[starttime][,endtime]"`
+ 示例：

```html
src = "video/art.mp4#t=4,25";
```

### 5.2   跳转媒体播放时间点

+ 利用以下格式：

```html
var mediaFile = document.getElement("media");  //获取媒体元素对象
mediaFile.currentTime=200;   //设置需要跳转到第200秒
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <title>HTML5视频标签video的简单应用</title>
    </head>
    <body>
        <h3>HTML5视频标签video的简单应用</h3>
        <hr>
        <video id = "media" src = "C:/Users/清弦子之忆/Desktop/蔡徐坤 - Hug me (抱我).mp4" controls></video>
        <div>
            <button onclick = "changeTime()">
                跳转至1分钟
            </button>
        </div>
        <script>
            var media = document.getElementById("media");
            function changeTime(){
                media.currentTime = 60;
                media.play();
            }
        </script>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML%E5%AA%92%E4%BD%93API%E5%9B%BE3.png)

### 5.3   获取媒体播放时间

+ 其格式为：

```html
//获取媒体元素对象
var mediaFile = document.getElementById("media");
//获取媒体播放的开始时间(秒)
mediaFile.seekable.start(0);
//获取媒体播放的结束时间(秒)
mediaFile.seekable.end(0);
//获取媒体当前播放的秒数(当前的播放的时间点)
mediaFile.played.end(0);
```

+ 代码如下：

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>获取媒体的播放时间</title>
    </head>
    <body>
        <h3>获取媒体的播放时间</h3>
        <hr>
        <video id = "media" src = "C:/Users/清弦子之忆/Desktop/蔡徐坤 - Hug me (抱我).mp4" controls autoplay></video>
        <br>
        <button onclick = "getTime()">
            点击此处获取视频详细信息
        </button>
        <div id="status"></div>
        <Script>
            function getTime(){
                var media = document.getElementById("media");
                var starttime = media.seekable.start(0);
                var endtime = media.seekable.end(0);
                var play_end = media.played.end(0);
                var status = document.getElementById("status");
                status.innerHTML = "视频开始时间："+starttime+"<br>视频结束时间："+endtime+"<br>视频已播放时间："+play_end;
            }
        </Script>
    </body>
</html>
```

代码测试结果：

![](https://raw.githubusercontent.com/qingxianzi002/My_note/main/pictureHTML%E5%AA%92%E4%BD%93API%E5%9B%BE4.png)

### 5.4   终止媒体文件的下载

+ 其格式为

```html
//获取媒体元素对象
var mediaFile = document.getElementById("ID名称");
//暂停当前媒体文件的播放
mediaFile.pause();
//去除src属性
mediaFile.removeAttribute("src");
或
mediaFile.src = "";
```

### 5.5   使用Flash播放器

+ 其格式为

```html
<video src = "C:/Users/清弦子之忆/Desktop/蔡徐坤 - Hug me (抱我).mp4" controls>
	<object data="player.swf" type="application/x-shockwave-flash" width="640" height = "480">
    	<param value = "player.swf" name = "movie" />
        <param name = 'flashvars' value = 'file=C:/Users/清弦子之忆/Desktop/蔡徐坤 - Hug me (抱我).mp4' />
    </object>
</video>
```

