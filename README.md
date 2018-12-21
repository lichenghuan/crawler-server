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

**什么是Puppeteer？**
简而言之，这货是一个提供高级API的node库，能够通过devtool控制headless模式的chrome或者chromium，它可以在headless模式下模拟任何的人为操作。
**和cheerio的区别** 
cherrio本质上只是一个使用类似jquery的语法操作HTML文档的库，使用cherrio爬取数据，只是请求到静态的HTML文档，如果网页内部的数据是通过ajax动态获取的，那么便爬去不到的相应的数据。而**Puppeteer**能够模拟一个浏览器的运行环境，能够请求网站信息，并运行网站内部的逻辑。然后再通过WS协议动态的获取页面内部的数据，并能够进行任何模拟的操作(点击、滑动、hover等),并且支持跳转页面，多页面管理。甚至能注入node上的脚本到浏览器内部环境运行，总之，你能对一个网页做的操作它都能做，你不能做的它也能做。
