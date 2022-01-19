```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<html lang="en">
  <head>
    <title>Nivo Slider Demo</title>
    <!--
        1. 在这里引入 nivo slider 插件需要的 css 和 js 文件
        themes 都是不同的 css 主题, 例如 default、dark、light等，只需要引入其中一个
        其他的 css 都是必须引入的 css文件
    -->
    <link
      rel="stylesheet"
      href="../themes/light/light.css"
      type="text/css"
      media="screen"
    />
    <link
      rel="stylesheet"
      href="../nivo-slider.css"
      type="text/css"
      media="screen"
    />
    <link rel="stylesheet" href="style.css" type="text/css" media="screen" />

    <script type="text/javascript" src="scripts/jquery-1.9.0.min.js"></script>
    <script type="text/javascript" src="../jquery.nivo.slider.js"></script>

    <script type="text/javascript">
      // 2. 在这里调用 nivoSlider 方法实现轮播图功能
      $(window).load(function () {
        $("#slider").nivoSlider();
      });
    </script>
  </head>
  <body>
    <div id="wrapper">
      <a href="http://dev7studios.com" id="dev7link" title="Go to dev7studios"
        >dev7studios</a
      >

      <div class="slider-wrapper theme-light">
        <div id="slider" class="nivoSlider">
          <img
            src="images/toystory.jpg"
            data-thumb="images/toystory.jpg"
            alt=""
          />
          <a href="http://dev7studios.com"
            ><img
              src="images/up.jpg"
              data-thumb="images/up.jpg"
              alt=""
              title="This is an example of a caption"
          /></a>
          <img
            src="images/walle.jpg"
            data-thumb="images/walle.jpg"
            alt=""
            data-transition="slideInLeft"
          />
          <img
            src="images/nemo.jpg"
            data-thumb="images/nemo.jpg"
            alt=""
            title="#htmlcaption"
          />
        </div>
        <div id="htmlcaption" class="nivo-html-caption">
          <strong>This</strong> is an example of a <em>HTML</em> caption with
          <a href="#">a link</a>.
        </div>
      </div>
    </div>
  </body>
</html>
```