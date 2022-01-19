<details>
  <summary>5-4-index.html 参考答案</summary>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>制作图片滑块验证码</title>
    <style>
      * {
        touch-action: pan-y;
      }

      .container {
        width: 312px;
        margin: 0 auto;
      }

      .box {
        width: 312px;
        position: relative;
      }

      #imgfront {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: auto;
      }

      .buttonarea {
        margin-top: 10px;
        background: #f7f9fa;
        height: 40px;
        line-height: 40px;
        text-align: center;
        position: relative;
        font-weight: 300;
        font-size: 5px;
        cursor: default;
        user-select: none;
        text-shadow: none;
        border: 1px solid #e3e7eb;
        border-radius: 2px;
      }

      .buttonarea .trajectory {
        height: inherit;
        position: absolute;
        top: 0;
        left: 0;
        background-color: rgb(135 191 154);
      }

      .buttonarea .tip {
        white-space: nowrap;
        overflow: hidden;
        padding-left: 20px;
        color: #88949d;
      }

      .buttonarea .button {
        height: inherit;
        width: 40px;
        position: absolute;
        top: 0;
        background-color: #ffffff;
        border: 0px solid #e3e7eb;
        box-sizing: border-box;
        cursor: move;
        border-radius: 2px;
        font-weight: bold;
        box-shadow: 0 0 3px rgb(0 0 0 / 30%);
      }

      .buttonarea .buttonsign {
        width: auto;
        display: block;
        position: relative;
        top: -1px;
        pointer-events: none;
      }
    </style>
  </head>

  <body>
    <div class="container">
      <div class="box">
        <img
          src="https://labfile.oss.aliyuncs.com/courses/3944/2-3-verify-1.jpg"
          style="width: 312px; height: 156px; background-color: rgb(199, 199, 199);"
        />
        <img
          id="imgfront"
          src="https://labfile.oss.aliyuncs.com/courses/3944/2-3-verify-2.png"
          style="left: 0px;"
        />
      </div>
      <div class="buttonarea" style="height: 39.52px; line-height: 39.52px;">
        <div
          class="trajectory"
          id="process"
          style="width: 0px; margin-left: 0px;"
        ></div>
        <div class="tip" style="padding-left: 59.28px; font-size: 14.82px;">
          向右拖动滑块填充拼图
        </div>
        <div class="button" id="bar" style="width: 59.28px; left: 0px;">
          <span class="buttonsign">&gt;&nbsp;&gt;</span>
        </div>
      </div>
    </div>
  </body>
  <script type="text/javascript" src="index.js"></script>
</html>
```

</details>

<details>
  <summary>index.js 参考答案</summary>

```js
window.onload = function () {
  let bar = document.getElementById("bar"); //拖动按钮
  let process = document.getElementById("process"); //拖动按钮进度条
  let imgfront = document.getElementById("imgfront"); //缺口图片
  //限制最大宽度，不让滑块出去
  var maxW = 250;
  bar.addEventListener("touchstart", function (e) {
    var ev = e || window.event;
    var touch = ev.targetTouches[0];
    oL = touch.clientX - bar.offsetLeft;
  });
  //触摸中的，位置记录
  bar.addEventListener("touchmove", function (e) {
    var ev = e || window.event;
    var touch = ev.targetTouches[0];
    var oLeft = touch.clientX - oL;
    if (oLeft < 0) {
      oLeft = 0;
    } else if (oLeft >= maxW) {
      oLeft = maxW;
    }
    //设置拖动按钮进度
    process.style.width = oLeft + "px";
    //设置缺口图片位置
    imgfront.style.left = oLeft + "px";
    //设置拖动按钮位置
    bar.style.left = oLeft + "px";
  });
  //触摸结束时的处理
  bar.addEventListener("touchend", function () {
    //判断是否重合
    // 误差在2px以内则算做成功
    if (Math.abs(parseInt(imgfront.style.left) - 153) > 2) {
      alert("验证失败！");
      //重置
      imgfront.style.left = "0px";
      bar.style.left = "0px";
      process.style.width = "0px";
    } else {
      //改变样式
      process.style.backgroundColor = "#009933";
      bar.innerText = "√";
      alert("验证成功！");
    }
  });
};
```

</details>
