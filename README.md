# node-crawler1

> 爬虫demo1



#### 前端：

crawler-views文件夹中的是前端页面代码

技术栈：

- vue
- axios

运行后台代码后，到crawler-views文件夹中 执行 npm install   然后运行 npm run dev 便可打开本地浏览器浏览爬取的页面。



#### 后台：

crawler-server文件夹放置的是Node服务器代码；

技术栈：

- node
- express
- cheerio  （Cheerio是一个服务器端基本实现Jquery核心功能的一个库）
- superagent （nodejs里一个非常方便的客户端请求代理模块）
- cors  （允许客户端跨域请求）

进入 crawler-server文件夹  首先执行 npm install    再执行 node app.js。



跟传统爬虫一样，缺点就是爬取不到js动态渲染的元素（单页面应用是其中之一）；那单页面应用应该如何爬？不慌，我最近发现了一个Chrome官方团队进行维护node库--**puppeteer**。  [中文翻译API传送门](https://zhaoqize.github.io/puppeteer-api-zh_CN/) 

（by the way：PhantomJS和puppeteer差不多，但是前者好像GG了）