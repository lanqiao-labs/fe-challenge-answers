```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>文本效果</title>
    <style>
      p.test1 {
        width: 9em;
        border: 1px solid #000000;
        word-break: keep-all;
        background-color: aquamarine;
      }
      p.test2 {
        width: 9em;
        border: 1px solid #000000;
        word-break: break-all;
        background-color: darkgreen;
      }
    </style>
  </head>
  <body>
    <p class="test1">
      This paragraph contains some text. This line will-break-at-hyphenates.
    </p>
    <p class="test2">
      This paragraph contains some text. This line will-break-at-hyphenates.
    </p>
  </body>
</html>
```