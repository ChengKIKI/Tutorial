# mongodb安装

 我的是mac，所以只介绍mac下的安装流程

 推荐使用brew（尝试过手动安装和使用brew安装，还是brew方便一点）

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

 ### 可能遇到的问题

 1.非正常关闭服务之后，mongodb无法正常启动

 找到data下的.lock文件，删除

 2.在这次安装mongodb之前，我曾在别的项目文件里启动过mongodb，所以出现了27017端口被占用情况

 ```
 sudo lsof -i :27017

 ```
 找到对应的PID,比如 657

 ```
 sudo kill -9 716

 ```
