```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <canvas
      id="myCanvas"
      width="400"
      height="200"
      style="border:1px solid #000;"
    >
      您的浏览器不支持 HTML5 canvas 标签。
    </canvas>
  </body>
  <script>
    //1. 得到Canvas对象
    var mycanvas = document.getElementById("myCanvas");
    //2. 得到一个CanvasRenderingContext2D对象
    var ctx = mycanvas.getContext("2d");
    //3. 随机一张图片
    var arr = ["./images/1-1-guaguale01.png", "./images/1-1-guaguale02.png"];
    var number = Math.floor(Math.random() * arr.length);
    mycanvas.style.background = "url(" + arr[number] + ")";
    mycanvas.style.backgroundSize = "100%";
    //4. 绘制一个填充的矩形，填充的颜色是灰色
    ctx.fillStyle = "#ccc";
    ctx.fillRect(0, 0, 400, 200);
    //5. 绑定鼠标事件
    var status = "false";
    mycanvas.onmousedown = function () {
      status = "true";
    };
    mycanvas.onmouseup = function () {
      status = "false";
    };
    mycanvas.onmousemove = function (e) {
      if (status == "true") {
        //重叠变透明
        ctx.globalCompositeOperation = "destination-out";
        ctx.beginPath();
        //6. 绘制圆
        ctx.arc(e.pageX, e.pageY, 20, 0, 2 * Math.PI);
        ctx.closePath();
        ctx.fill();
      }
    };
  </script>
</html>
```
