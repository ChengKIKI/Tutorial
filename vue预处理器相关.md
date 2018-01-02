# vue项目的预处理器

 最近和别人合作的vue项目用了很多预处理器，我用的vue-cli初始化项目，所以初始webpack并没有进行配置，vue-cli用起来比较方便

 ## sass

 首先说下sass配置，css的预处理器有很多，比如less,stylus,sass,能选择sass也是考虑了多方面的结果

 项目根目录下

 ```
 npm install sass-loader node-sass --save-dev
 ```
 安装命令有 ```--save-dev``` 和没有的区别在于是否写入package.js文件中的devDependencies中，具体可以自己实践下，一般项目的依赖都会加上 ```--save-dev```

 sass安装完毕后，打开build下的webpack.base.conf.js,在rules里加上sass

 ```
 {
     test: /\.scss$/,
     loader: 'style-loader!css-loader!sass-loader'
 }
 ```
 #### 在项目中的使用

 ```
 <style lang="sass">

  /* write sass here */

 </style>
 ```
 ## pug / jade

 html我们使用了pug模版引擎来开发，这样的开发效率有明显提升

 同样，项目根目录下

 ```
 npm install pug pug-loader pug-filters --save-dev
 ```

 webpack.base.conf.js中

 ```
 {
  test: /\.pug$/,
  loader: 'pug'
 }
 ```

 #### 在项目中的使用

 ```
 <template lang="pug">

  /* write pug here */

 </template>
 ```
 也可以使用jade，安装方法类似

 以上是css和html的预处理器安装，项目中的js用的es6，没有使用类似coffeescript的预处理器，感兴趣的话可以自行安装使用下
