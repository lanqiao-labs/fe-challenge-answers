```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>移动端事件封装</title>
    <style type="text/css">
      div {
        width: 200px;
        height: 200px;
        background-color: red;
      }
    </style>
  </head>

  <body>
    <div id="box"></div>
  </body>
  <script>
    // 定义一个大的事件对象，用于存放封装的移动端事件
    var touchEvent = {
      /*
      swipe：封装的事件名称
      element ：dom元素
      fn：fn 事件触发函数
       */
      /*滑屏 事件封装*/
      swipe: function (element, fn) {
        var startTx, startTy;
        element.addEventListener(
          "touchstart",
          function (e) {
            var touches = e.touches[0];
            startTx = touches.clientX;
            startTy = touches.clientY;
          },
          false
        );
        element.addEventListener(
          "touchmove",
          function (e) {
           
          },
          false
        );
        element.addEventListener(
          "touchend",
          function (e) {
            var touches = e.changedTouches[0],
              endTx = touches.clientX,
              endTy = touches.clientY,
              distanceX = startTx - endTx,
              distanceY = startTy - endTy;
            // 滑动举例 大于 30 才被认为是 滑动操作
            if (Math.abs(distanceX) > 10 || Math.abs(distanceY) > 10) {
              fn();
            }
          },
          false
        );
      },
    };

    window.onload = function () {
      var box = document.getElementById("box");
      //调用封装的 swipe 事件
      touchEvent.swipe(box, function () {
        box.style.background = "green";
      });
    };
  </script>
</html>
```