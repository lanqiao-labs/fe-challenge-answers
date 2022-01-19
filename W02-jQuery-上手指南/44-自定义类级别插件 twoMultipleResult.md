
<details>
  <summary>jquery.twoMultipleResult.js 参考答案</summary>

```html
;(function($) { // 自定义类级别插件 $.extend({ "multiple": function(a,b) {
return a * b; } }); })(jQuery);
```

</details>

<details>
  <summary>usePlugin2.html 参考答案</summary>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>自定义类级别插件的挑战</title>
    <!-- 1. 引入 liFocusColor 插件的 js 文件 -->
    <script src="js/jquery-2.1.4.js"></script>
    <script src="js/jquery.twoMultipleResult.js"></script>
    <style ref="text/css">
      li {
        list-style-type: none;
      }
    </style>
  </head>
  <body>
    <div class="content">
      两数相乘：
      <input id="text1" type="text" class="txt" />
      *
      <input id="text2" type="text" class="txt" />
      =
      <input id="text3" type="text" class="txt" />
    </div>
    <div>
      <input id="btn1" type="button" value="计算" />
    </div>

    <script type="text/javascript">
      $(function () {
        $("#btn1").bind("click", function () {
          var a = parseInt($("#text1").val());
          var b = parseInt($("#text2").val());
          // 2. 调用 twoAddResult 插件的 sum 方法
          var result = $.multiple(a, b);
          $("#text3").val(result);
        });
      });
    </script>
  </body>
</html>
```

</details>
