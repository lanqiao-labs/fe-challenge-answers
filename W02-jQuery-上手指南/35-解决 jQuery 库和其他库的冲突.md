```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>挑战</title>
    <script src="js/jquery-3.6.0.min.js" type="text/javascript"></script>
    <script src="js/prototype-1.6.0.3.js" type="text/javascript"></script>
  </head>
  <body>
    <p id="pp">test---prototype</p>
    <p>test---jQuery</p>

    <script type="text/javascript">
      jQuery.noConflict();
      (function ($) {
        $("p").click(function () {
          alert($(this).text());
        });
      })(jQuery);

      $("pp").style.display = "none";
    </script>
  </body>
</html>
```