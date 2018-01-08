# mongodb基本使用

  最近在坐前后端分离的项目，用到了mongodb，之前记录了mongodb的安装流程，现在记录下mongodb的基本使用

  启动
  ```
  mongod --config /usr/local/etc/mongod.conf
  ```

  另开端口
  ```
  mongo
  ```

  出现 ```>``` 代表启动成功

  查看所有数据库
  ```
  > show dbs

  admin  0.000GB
  local  0.000GB
  ```
  创建数据库
  ```
  > use test

  switched to db test
  ```
  插入数据
  ```
  > db.test.insert({"name":"kiki"})

  WriteResult({ "nInserted" : 1 })
  ```
