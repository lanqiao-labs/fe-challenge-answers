```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>jqzoom的使用（图片放大镜）</title>
  </head>
  <script type="text/javascript" src="js/jquery.min.js"></script>
  <script type="text/javascript" src="js/jquery.jqzoom.js"></script>
  <!--<link rel="stylesheet" type="text/css" href="style/style.css" media="screen"/>-->
  <link
    rel="stylesheet"
    type="text/css"
    href="style/jqzoom.css"
    media="screen"
  />

  <script>
    $(function () {
      $(".jqzoom").jqueryzoom({
        xzoom: 300, //放大图片的宽度(默认值200)
        yzoom: 300, //放大图片的高度度(默认值200)
        offset: 10, //放大图片的偏移值(度(默认值10)
        position: "right", //放大图片的显示位置度(默认值“right”)
      });
    });
  </script>

  <body>
    <div>
      <div class="jqzoom">
        <img
          src="images/iphone12.jpg"
          alt="scarpa"
          jqimg="images/iphone12Big.jpg"
        />
      </div>
    </div>
  </body>
</html>
```