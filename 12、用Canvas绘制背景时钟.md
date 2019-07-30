---
title: 12、用Canvas绘制背景时钟
date: 2018-06-18 21:11:37
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <canvas id="clock" width="500px" height="500px" style="background: #000"></canvas>
    <script>
        var canvas=document.getElementById("clock");
        var cxt=canvas.getContext("2d");
        function drawClock(){ 
            // 获取系统时间   
            var date=new Date();
            var hour=date.getHours();
            var min=date.getMinutes();
            var sec=date.getSeconds();
            // alert(hour);
            hour>12?hour-12:hour;
            // 清空画布
            cxt.clearRect(0,0,canvas.width,canvas.height);
            //绘制时刻度                    
            cxt.strokeStyle="blue";
            cxt.lineWidth=10;
            cxt.beginPath(); //起始一条路径  
            cxt.arc(250,250,200,0,Math.PI*2);
            cxt.stroke();            
            cxt.closePath();//结束路径   
            cxt.clip();//按圆框裁剪时钟背景图

            // 绘制表盘背景
            var img =new Image();
            img.src="clock.jpg";
            cxt.drawImage(img,40,40,420,420);


            for(var i=0;i<12;i++){
            cxt.save();
            cxt.strokeStyle="yellow";
            cxt.lineWidth=7;
            cxt.translate(250,250);//设置原点
            cxt.rotate(30*i*Math.PI/180);//设置旋转角度,隔30度画一个分刻度
            cxt.beginPath();
            cxt.moveTo(0,-197);
            cxt.lineTo(0,-175);
            cxt.stroke();
            cxt.closePath();
            cxt.restore();
            }
            //绘制分刻度
            for(var i=0;i<60;i++){
            cxt.save();
            cxt.strokeStyle="yellow";
            cxt.lineWidth=5;
            cxt.translate(250,250);//设置原点
            cxt.rotate(6*i*Math.PI/180);//设置旋转角度,隔30度画一个分刻度
            cxt.beginPath();
            cxt.moveTo(0,-195);
            cxt.lineTo(0,-185);
            cxt.stroke();
            cxt.closePath();
            cxt.restore();
            }
            // 绘制时针
            cxt.save();
            cxt.strokeStyle="blue";
            cxt.lineWidth=7;
            cxt.translate(250,250);
            cxt.rotate(hour*30*Math.PI/180);            
            cxt.beginPath();
            cxt.moveTo(0,-130);
            cxt.lineTo(0,0);
            cxt.stroke();
            cxt.closePath();
            cxt.restore();

            //绘制分针
            cxt.save();
            cxt.strokeStyle="yellow";
            cxt.lineWidth=4;
            cxt.translate(250,250);
            cxt.rotate(min*6*Math.PI/180);
            cxt.beginPath();
            cxt.moveTo(0,-150);
            cxt.lineTo(0,0);
            cxt.stroke();
            cxt.closePath();
            cxt.restore();

            // 绘制秒针
            cxt.save();
            cxt.strokeStyle="red";
            cxt.lineWidth=3;
            cxt.translate(250,250);
            cxt.rotate(sec*6*Math.PI/180);
            cxt.beginPath();
            cxt.moveTo(0,-170);
            cxt.lineTo(0,0);
            cxt.stroke();
            cxt.closePath();
           // cxt.restore();

            // 美化表盘,中间小圆
            cxt.beginPath();
            cxt.arc(0,0,7,0,Math.PI*2);
            cxt.fillStyle="yellow";
            cxt.fill();
            cxt.strokeStyle="red";
            cxt.stroke();
            cxt.closePath();

            // 秒针上的小圆
            cxt.beginPath();
            cxt.arc(0,-140,7,0,Math.PI*2);
            cxt.fillStyle="yellow";
            cxt.fill();
            cxt.strokeStyle="red";
            cxt.stroke();
            cxt.closePath();
            cxt.restore();
        }
        drawClock();
        setInterval(drawClock,1000);//设置定时器

    </script>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180618211057407?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

   
  