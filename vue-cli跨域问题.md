# vue-cli跨域问题

  页面开发完毕之后，需要和后台接口进行联调，本地的服务启动起来之后实质上是127.0.0.1:8080，但是后台给的接口地址是 http://192.168.12.54:8088/renren-fast/sys/needs/bbc ，域名，端口都不同，所以需要进行跨域，跨域的方法有很多，通常都需要后台配置，不过 Vue-cli 创建的项目，可以直接利用 Node.js 代理服务器，通过修改vue proxyTable接口实现跨域请求

  ```
  dev: {

    // Paths
    assetsSubDirectory: 'static',
    assetsPublicPath: '/',
    proxyTable: {
        '/api': {
          target: 'http://192.168.12.54:8088/',
          changeOrigin: true,
          pathRewrite: {
            '^/api': '/'
          }
      }
    },
  }
  ```
  只要修改里面的proxyTable，然后重启项目npm run dev

  请求地址就可以换成如下了

  ```
  axios.get('/api/renren-fast/sys/needs/bbc').then((response)=>{
      console.log(response.data);
      self.randoms = response.data;
      //this.loading = true;
  })
  ```
