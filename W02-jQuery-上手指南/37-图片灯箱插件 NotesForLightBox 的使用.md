```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>NotesForLightBox 挑战</title>
    <link
      href="css/nf.lightbox.css"
      rel="stylesheet"
      type="text/css"
      media="screen"
    />
    <script src="js/jquery-1.3.2.min.js" type="text/javascript"></script>
    <script src="js/NFLightBox.js" type="text/javascript"></script>
    <script type="text/javascript">
      $(function () {
        $("#gallery a").lightBox({
          overlayBgColor: "#666", //浏览图片时的背景颜色
          overlayOpacity: 0.5, //背景颜色的透明度
          containerResizeSpeed: 600, //图片切换时的速度
        });
      });
    </script>

    <style type="text/css">
      #gallery {
        background-color: #444;
        padding: 10px;
        width: 420px;
      }
      #gallery ul {
        list-style: none;
      }
      #gallery ul li {
        display: inline;
      }
      #gallery ul img {
        border: 5px solid #3e3e3e;
        border-width: 5px 5px 20px;
      }
      #gallery ul a:hover img {
        border: 5px solid #fff;
        border-width: 5px 5px 20px;
        color: #fff;
      }
      #gallery ul a:hover {
        color: #fff;
      }
    </style>
  </head>
  <body>
    <div id="gallery">
      <ul>
        <li>
          <a
            href="photos/image1.jpg"
            title="Add title to show image name or description"
          >
            <img src="photos/thumb_image1.jpg" width="100" alt="" />
          </a>
        </li>
        <li>
          <a
            href="photos/image2.jpg"
            title="Add title to show image name or description"
          >
            <img src="photos/thumb_image2.jpg" width="100" alt="" />
          </a>
        </li>
        <li>
          <a
            href="photos/image3.jpg"
            title="Add title to show image name or description"
          >
            <img src="photos/thumb_image3.jpg" width="100" alt="" />
          </a>
        </li>
        <li>
          <a
            href="photos/image4.jpg"
            title="Add title to show image name or description"
          >
            <img src="photos/thumb_image4.jpg" width="100" alt="" />
          </a>
        </li>
        <li>
          <a
            href="photos/image5.jpg"
            title="Add title to show image name or description"
          >
            <img src="photos/thumb_image5.jpg" width="100" alt="" />
          </a>
        </li>
        <li>
          <a
            href="photos/image6.jpg"
            title="Add title to show image name or description"
          >
            <img src="photos/thumb_image6.jpg" width="100" alt="" />
          </a>
        </li>
      </ul>
    </div>
  </body>
</html>
```