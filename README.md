# python--
## 程序设计思路

我是要使用scrapy对接selenium完成我的关注用户博文的爬取。


- 问题1：如何对接selenium？通过编写scrapy的下载器中间件，截胡spider的请求并将其改成使用selenium发起request，然后将渲染后的page_source加载到response的body中返回到spider进行解析。。
- 问题2：如何登录？通过在spider中重写start_request函数，在这个函数中再次调用selenium完成登录并获取cookie。并将cookie定义为一个属性实例，因为selenium是阻塞的，所以完成多个任务会有些麻烦。
