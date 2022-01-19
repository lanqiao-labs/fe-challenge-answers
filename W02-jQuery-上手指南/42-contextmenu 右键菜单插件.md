```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="css/style.css" rel="stylesheet" type="text/css" />
  <script src="js/contextmenu/jquery-2.1.4.min.js"></script>
  <script
  src="js/contextmenu/jquery.contextMenu.js"
  type="text/javascript"
></script>
<link
  href="js/contextmenu/jquery.contextMenu.css"
  rel="stylesheet"
  type="text/css"
/>
  <title>Document</title>
  <script type="text/javascript">
    $(function(){
      $.contextMenu({
            selector: '.context-menu-one', // 指定对应 div 的 class 样式
            // key为items中的键 , options为items的数据对象。
            callback: function(key, options) {
              alert('点击了' + key);
              switch(key) {
                case 'new': alert('新建文件');break;
                case 'edit': alert('编辑文件 ');break;
                case 'delete': alert('删除文件');break;
                case 'about': alert('关于');break;
              }

            },
            items: {
                "new": {name: "新建", icon: "add"},
                "edit": {name: "编辑", icon: "edit"},
                "delete": {name: "删除", icon: "delete"},
                "sep1": "---------",
                "about": {name: "关于", icon: "quit"}
            }
        });

      $("tbody>tr:odd").addClass("odd"); //先排除第一行,然后给奇数行添加样式
      $("tbody>tr:even").addClass("even"); //先排除第一行,然后给偶数行添加样式

      var bgColor = '';
      $("table tr").on("mouseover",function() {
        bgColor = $(this).css('background-color');
        $(this).css('background-color','yellowgreen');
      }).on("mouseout",function() {
        $(this).css('background-color',bgColor);
      })
    })
  </script>
</head>
<body>
  <div class="context-menu-one">
    <table>
      <thead>
        <tr><th>姓名</th><th>性别</th><th>暂住地</th></tr>
      </thead>
      <tbody>
        <tr><td>张山</td><td>男</td><td>浙江宁波</td></tr>
        <tr><td>李四</td><td>女</td><td>浙江杭州</td></tr>
        <tr><td>王五</td><td>男</td><td>湖南长沙</td></tr>
        <tr><td>找六</td><td>男</td><td>浙江温州</td></tr>
        <tr><td>Rain</td><td>男</td><td>浙江杭州</td></tr>
        <tr><td>MAXMAN</td><td>女</td><td>浙江杭州</td></tr>
      </tbody>
    </table>
  </div>

</html>
```