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
  插入数据（增）
  ```
  > db.test.insert({"name":"kiki","tag":"study"})

  WriteResult({ "nInserted" : 1 })
  ```
  use test后如果不插入数据就离开该数据库，mongodb会自动删除，show dbs是找不到新创建的数据库的

  更新数据（改）
  ```
  > db.test.update({"name":"kiki",{$set:{"tag":"work"}}})
  ```
  查找数据（查）接上条

  ```
  > db.test.find()
  ```
  根据上条的更改后的数据重新查询test数据库

  ```
  > db.test.find().pretty()
  ```
  把查询结果展开

  条件查找
  ```
  > db.test.find({"name":"kiki"}).pretty()
  ```
  通过条件查找

  删除数据（删）
  ```
  > db.test.remove({"name":"kiki"})
  ```
  删除之后可以find一下看看结果
