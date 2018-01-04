# vue-cli最新版所遇到的问题

 在使用最新的vue-cli 2.9.1构建项目时，其中自己mock数据配置访问时，之前版本时都是在dev-server文件中搭建虚拟服务器，请求json文件数据。具体配置方法不再赘述，现在最新版已不适用。现在介绍最新版的配置方法。

 在最新版本vue-cli的配置中浏览器服务都在webpack-dev-server 这个插件中，那我们就其在webpack.dev.conf.js进行修改。

 查看webpack文档有一个api其参数是 ```devServer.before```（https://doc.webpack-china.org/configuration/dev-server/#devserver-before）

 由此可知道改如何修改

 webpack.dev.conf.js中

 ```
 before(app) {
     app.get('/carlist' ,function(req, res){
         res.json({
             errno: 0,
             data: carlistdata.result
         })
     });
     app.get('/slideList' ,function(req, res){
         res.json({
             errno: 0,
             data: carlistdata.slideList
         })
     });
 }
 ```
 记得在头部require

 ```
 const carlistdata = require('../mock/carlist.json')
 ```

 这样，我们就可以直接发送API请求数据了

 ```
 this.axios.get("/carlist").then(function(res){
  // do something
 })
 ```
