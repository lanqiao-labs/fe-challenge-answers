
<details>
  <summary>jquery.color.js 参考答案</summary>

```html
;(function($) { $.fn.extend({ "color": function(value) { return
this.css("color", value); } }); })(jQuery);
```

</details>

<details>
  <summary>pluginTiaoZhan.html 参考答案</summary>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title></title>
    <script
      src="./js/jquery-2.1.4.js"
      type="text/javascript"
      charset="utf-8"
    ></script>
    <script
      src="./js/jquery.color.js"
      type="text/javascript"
      charset="utf-8"
    ></script>
    <script type="text/javascript">
      $(function () {
        $("#div1").color("red");
      });
    </script>
  </head>
  <body>
    <div id="div1">我是div1</div>
  </body>
</html>
```

</details>
