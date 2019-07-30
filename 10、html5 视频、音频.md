---
title: 10、html5 视频、音频
date: 2018-06-15 16:55:51
tags: CSDN迁移
---
  视频播放语法：

 
     属性           | 值          | 说明                
     ------------ | ---------- | ------------------ 
     controls     | controls   | 向用户显示控件，比如播放按钮    
     autoplay     | autoplay   | 视频在就绪后马上播放        
     loop         | loop       | 视频结束后时重新开始播放      
     preload      | auto       | 视频在页面加载时进行加载，并预备播放
     muted        | muted      | 视频输出的音频为静音        
     width/height | length(px) | 设置视频播放器的宽度与高度     

 preload属性

 
     属性      | 值        | 说明            
     ------- | -------- | -------------- 
     preload | auto     | 一旦页面加载，开始加载视频 
     preload | metadata | 页面加载后仅加载视频的元数据
     preload | none     | 页面加载后不应加载视频   

 注意：如果使用autoplay属性 preload将被忽略

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <!-- video播放视频 -->
    <video src="movie.ogg" controls="controls"  preload="auto" width="800" height="700"></video>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180615150449207?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 音频的属性与音频属性一样

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <audio src="horse.ogg" controls autoplay loop muted></audio>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180615165513807?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 常见的视频、音频格式   
 视频格式：.ogg、.avi、.mp4、.rmvb   
 音频格式：.mp3、.ogg、.webm

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <!-- <audio src="horse.ogg" controls autoplay loop muted></audio> -->
    <video controls>
    <!-- source可以加载不同格式的视频、音频以适应不同的浏览器 -->
        <source src="movie.ogg"> </source>
        <source src="movie.mp4"> </source>
        <source src="movie.avi"> </source>
    </video>
</body>
</html>
```
   
  