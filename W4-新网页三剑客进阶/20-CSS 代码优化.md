
```css
/*******************************************************************************
*  Name: style.css
*  Author: wcy
*
*  Description: stylesheet for main theme
*
*******************************************************************************/

body {
  color: #666;
  /* 修改第一处：简写font */
  /* font-family: sans-serif;
  font-size: 13px; */
  font: 13px sans-serif;
  line-height: 1.7;
  margin: 0;
}

h1,
h2,
h3,
h4 {
  /* 修改第二处：将h2 h3 h4 相同样式进行合并 */
  font-size: 22px;
  font-weight: 700;
  color: #666;
  margin: 0;
}

h1 {
  font-size: 40px;
  font-weight: 700;
  margin: 10px;
  padding: 10px 0;
}

/* 修改第三处：删除下面注释内容，避免使用 !importants */

/* h2 {
  font-size: 22px;
  font-weight: 700 !important;
}

h3 {
  font-size: 22px;
  font-weight: 700 !important;
}

h4 {
  font-size: 22px;
  font-weight: 700 !important;
} */

p,
ul,
ol {
  line-height: 140%;
  text-align: inherit;
}

a {
  color: #0078ff;
  text-decoration: none;
}

/* 修改第四处：补充相应注释 */

/* header start */

header {
  width: 1000px;
  height: 120px;
  font-size: 12px;
  text-align: left;
  border-bottom: 2px solid gray;
}

.headl {
  float: left;
}

.headr {
  float: right;
  margin-top: 55px;
}

.nav {
  margin-bottom: 15px;
  float: right;
  display: inline;
  height: 44px;
  width: 500px;
  padding: 0;
}

.nav ul {
  list-style: none;
  list-style-position: outside;
  position: absolute;
}

.nav ul li {
  float: left;
  font-family: Open sans, sans-serif;
  font-size: 20px;
  font-weight: 500;
  padding: 0 5px;
}

.nav ul li:first-child {
  padding-left: 0;
}

.nav ul li a {
  color: #4a4a4a;
  display: block;
  height: 40px;
  line-height: 40px;
  border: 2px solid transparent;
  padding: 0 7px;
}

.nav ul li.active a,
.nav ul li a:hover {
  border: 2px solid #029cdb;
  background: url(../images/nav-btn.png) repeat-x 0 0;
  color: #fff;
  text-decoration: none;
}

/* header end */

/* content start */

.page {
  width: 1000px;
  margin: 0 auto;
}

.content {
  float: left;
  width: 970px;
  margin: 0;
  padding: 10px;
}

div.one-col,
div.two-col,
div.three-col {
  overflow: hidden;
}

div.separator {
  border-bottom: 1px solid gray;
  margin-bottom: 18px;
}

div.one-col div.col {
  width: 100%;
}

div.two-col div.col {
  width: 465px;
  float: left;
  margin-right: 30px;
}

div.three-col div.col {
  width: 300px;
  float: left;
  margin-right: 30px;
}

div.col p {
  font-size: 14px;
  line-height: 1.5em;
  margin-bottom: 1.5em;
}

/* content end */

/* footer start */

footer {
  width: 1000px;
  margin: 1px auto;
  padding: 10px;
}

.footer p {
  text-align: left;
  font-size: 14px;
  border: 0;
  margin: 10px;
  padding: 0;
}

.footerleft {
  float: left;
  width: 600px;
  margin-left: 2px;
  display: inline;
  padding: 0 10px 30px 0;
}

.footerright {
  float: right;
  width: 200px;
  margin-left: 2px;
  display: inline;
  padding: 0 10px 10px 0;
}

div.two-col div.last,
div.three-col div.last {
  margin-right: 0;
}

/* footer end */
```
