```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      html {
        font-size: 20px;
      }

      h1 {
        font-size: 2rem;
      }

      p {
        font-size: 1rem;
      }
    </style>
  </head>

  <body>
    <div>
      试一试改变文字大小：
      <select id="selectfont">
        <option value="20">大</option>
        <option value="16">中</option>
        <option value="14">小</option>
      </select>
    </div>
    <br />
    <h1>这是一个巨大的标题</h1>
    <p>Hey，我是一段有意思的文字！</p>
  </body>
  <script>
    var obj = document.getElementById("selectfont");
    obj.onchange = function () {
      //设置HTML根元素的 font-size属性
      document.documentElement.style.fontSize =
        obj.options[obj.selectedIndex].value + "px";
    };
  </script>
</html>
```