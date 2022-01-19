```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta
      http-equiv="Content-Security-Policy"
      content="upgrade-insecure-requests"
    />
    <title>autocomplete</title>
    <!--1. 引入 autocomplete 的 css 和 js 文件-->
    <link
      rel="stylesheet"
      href="http://code.jquery.com/ui/1.11.4/themes/smoothness/jquery-ui.css"
    />
    <script src="http://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="http://code.jquery.com/ui/1.11.4/jquery-ui.js"></script>

    <script>
      var url =
        "https://www.fastmock.site/mock/8b633b200d85031741d679febbb4c6b6/autocomplete/search";

      $(function () {
        // 2. 调用 autocomplete 方法实现自动补全效果
        $("#search").autocomplete({
          source: url,
        });
      });
    </script>
  </head>
  <body>
    <div class="ui-widget">
      <label for="search">请输入搜索内容 </label>
      <input id="search" />
    </div>
  </body>
</html>
```