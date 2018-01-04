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

 补充：我本地自己模拟的数据，仅供参考，方便理解

 ```
 {
   "status":"0",
   "result":[
     {
         "productId":"10001",
         "productName":"丰田-卡罗拉2017款 改款双擎",
         "productTit":"1.8L CVT先锋版",
         "prodcutPrice":"12.78",
         "prodcutTwo":"13.98",
         "prodcutImg":"car1.png"
     },
     {
         "productId":"10002",
         "productName":"本田-思域2016款",
         "productTit":"220TURBO 自动豪华版",
         "prodcutPrice":"13.99",
         "prodcutTwo":"13.99",
         "prodcutImg":"car2.png"
     },
     {
       "productId":"10003",
       "productName":"大众速腾2017款",
       "productTit":"1.6L 自动舒适型",
       "prodcutPrice":"9.8",
       "prodcutTwo":"15.08",
       "prodcutImg":"car3.png"
     },
     {
       "productId":"10004",
       "productName":"别克英朗2017款",
       "productTit":"15N 自动精英型",
       "prodcutPrice":"9.29",
       "prodcutTwo":"12.69",
       "prodcutImg":"car4.png"
     },
     {
       "productId":"10005",
       "productName":"荣威i62017款",
       "productTit":"16T 自动互联智享版",
       "prodcutPrice":"11.38",
       "prodcutTwo":"11.38",
       "prodcutImg":"car5.png"
     },
     {
       "productId":"10006",
       "productName":"奇瑞-艾瑞泽5",
       "productTit":"2017款 1.5L CVT领潮版",
       "prodcutPrice":"6.49",
       "prodcutTwo":"7.19",
       "prodcutImg":"car6.png"
     }
 ],
 "slideList":[
     {
         "clickUrl":"#",
         "bannerimg":"banner1.png"
     },
     {
         "clickUrl":"#",
         "bannerimg":"banner3.png"
     },
     {
         "clickUrl":"#",
         "bannerimg":"banner4.png"
     }
 ]
 }

 ```
