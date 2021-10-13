
<details>
  <summary>jquery.table.js 参考答案</summary>

```js
(function () {
  $.fn.extend({
    changeTableColor: function () {
      console.log($(this).find("tr:odd"));
      $(this).find("tr:odd").addClass("odd"); //先排除第一行,然后给奇数行添加样式
      $(this).find("tr:even").addClass("even"); //先排除第一行,然后给偶数行添加样式

      $(this).find("tr").eq(0).css("background-color", "#fff");
    },
  });
})(jQuery);
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
    <link href="css/style.css" rel="stylesheet" type="text/css" />
    <script src="./js/jquery-3.6.0.min.js"></script>
    <script src="./js/jquery.table.js"></script>
    <script type="text/javascript">
      $(function () {
        // 调用插件的指定方法
        $("#myTable").changeTableColor();
      });
    </script>
  </head>
  <body>
    <table id="myTable">
      <thead>
        <tr>
          <th>姓名</th>
          <th>性别</th>
          <th>暂住地</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>张山</td>
          <td>男</td>
          <td>浙江宁波</td>
        </tr>
        <tr>
          <td>李四</td>
          <td>女</td>
          <td>浙江杭州</td>
        </tr>
        <tr>
          <td>王五</td>
          <td>男</td>
          <td>湖南长沙</td>
        </tr>
        <tr>
          <td>找六</td>
          <td>男</td>
          <td>浙江温州</td>
        </tr>
        <tr>
          <td>Rain</td>
          <td>男</td>
          <td>浙江杭州</td>
        </tr>
        <tr>
          <td>MAXMAN</td>
          <td>女</td>
          <td>浙江杭州</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

</details>
