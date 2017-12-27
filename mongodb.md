# mongodb安装

 我的是mac，所以只介绍mac下的安装流程

 一，推荐使用brew

 首先更新Homebrew的package数据库（这个时间有点长）
 ```
 brew update

 ```

 更新完成之后，安装mongodb（brew和npm不同，这行命令意味全局安装，路径：/usr/local/Cellar/mongodb）,这里说下mac上怎么找隐藏路径，右键Finder-前往文件夹
 ```
 brew install mongodb

 ```
 #### 等待安装完成后，接下来运行mongodb

 首先我们创建一个数据库存储目录 /data/db（管理员权限下运行该命令）

 ```
 sudo mkdir -p /data/db

 ```
 启动mongodb

 ```
 sudo mongod

 ```
 当前这个终端不要关掉，此时另开一个终端，依次运行以下命令

 ```
 cd /usr/local/Cellar/mongodb/bin

 ```

 ```
 ./mongo

 ```
 出现 ```>```就代表启动成功

 二，手动下载安装

 1.可以在mongodb的官网下载对应的安装包，下载完成后更改压缩包名为：mongodb

 2.在Finder中进入/usr/local/目录下

 3.把压缩包解压放到该目录下

 未结束，待续...
