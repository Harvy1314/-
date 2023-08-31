## ajax

简称，异步的js和xml，无刷新与服务器通信，

xml可扩展标记语言

xml被设计用来存储和传输数据

xml和html，html是预定义标签，xml没有预定义

不过现在用json替代了

ajax的优点，无刷新页面与服务器通信、允许根据用户事件来更新部分页面内容

ajax缺点，没有浏览历史，跨域问题，seo不友好（无法爬虫哈哈哈）



## http协议

超文本传输协议

请求报文格式

行 get/post

头 host atgu.com

​	cookie: name=guigu

​	content-ty

空行

体 username=admin&



## 响应报文

行 http/1.1 200 ok

头 content-type text/html；charset=utf-8

​	content-length 2048

​	content-encoding: gzip

空行

体 html代码



## express框架

$ npm install express --save

```javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```

