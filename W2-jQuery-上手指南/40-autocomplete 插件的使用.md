
<details>
  <summary>search.html 参考答案</summary>

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
      var path = "SearchServlet";

      $(function () {
        // 2. 调用 autocomplete 方法实现自动补全效果
        $("#search").autocomplete({
          source: path,
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

</details>

<details>
  <summary>SearchServlet 参考答案</summary>

```java
package com.servlet;

import com.google.gson.Gson;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.io.PrintWriter;
import java.util.ArrayList;
import java.util.List;


@WebServlet("/SearchServlet")
public class SearchServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        this.doGet(request, response);
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        //1. 获取客户要查询的关键字
        String keyWord = request.getParameter("term");
        System.out.println(keyWord);

        //2. 去目标数组中找所有包含关键字的字符串，加入到集合中
        String[] arr = {"ActionScript","AppleScript","Asp","BASIC","C","C++","Clojure","COBOL","ColdFusion","Erlang","Fortran","Groovy", "Haskell", "Java", "JavaScript", "Lisp", "Perl", "PHP", "Python", "Ruby", "Scala", "Scheme"};

        List<String> resultList = new ArrayList<String>();


        for(String str: arr) {

            int place = str.toLowerCase().indexOf(keyWord.toLowerCase());
            if(place!=-1) { // 找到了
                resultList.add(str);
            }
        }

        System.out.println(resultList);


        //3. 把查询结果输出给用户
        Gson gson = new Gson();
        String searchResultJson = gson.toJson(resultList); // 把查询结果集合转换为 json格式

        response.setContentType("application/json");
        PrintWriter out = response.getWriter();
        out.println(searchResultJson);
        out.flush();
        out.close();
    }


}
```

</details>
