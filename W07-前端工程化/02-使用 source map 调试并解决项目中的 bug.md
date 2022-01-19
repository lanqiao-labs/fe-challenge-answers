```javascript
//引入path模块，nodejs中的系统模块
const path = require("path");

//引入 exports 模块
module.exports = {
  mode: "production", //设置打包模式为生产模式
  //入口
  entry: "./script.js",
  //出口
  output: {
    path: path.resolve(__dirname, "dist"), //__dirname是nodejs系统模块，用于表示当前文件的绝对路径
    filename: "bundle.js", //出口文件
  },
  devtool: "source-map",
};
```