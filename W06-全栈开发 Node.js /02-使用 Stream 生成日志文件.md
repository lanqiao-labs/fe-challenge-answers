```js
// log.js
var fs = require('fs');
// 生成时间戳，每次程序启动都会生成新的日志文件
var timestemp = Date.now();
// 创建可写流
var stdout = fs.createWriteStream('./' + timestemp + '.log', {
  flags: 'w', // 打开文件进行写入。 创建（如果它不存在）或截断（如果它存在）该文件。
  encoding: 'utf8', // utf8编码
});

// 创建 logger 工具
var logger = new console.Console(stdout);

// 项目中调用下面即可记录日志
logger.log('[INFO] 日志信息');
logger.log('[INFO] 日志信息2');
logger.error('[ERROR] 这是一条错误日志');
```

