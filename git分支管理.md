# git分支管理

  新的合作团队使用的是git代码管理，但是发现没有进行分支规范的话开发过程中会出很多问题，所以想写一篇来总结，方便以后的使用

  之前项目经理让我整理了一份git使用的相关说明，传到了teambition上方便团队合作的人随时浏览，我就把那份拷到这边来吧。

  ### 约束目的

  为了使得版本库的演进保持简洁，主干清晰，各个分支各司其职、井井有条。

  ### 规范内容

  ##### 主分支Master（代码库有且只有一个主分支，只用来发布版本）

  每次版本发布都应打一个tag标签来标明版本或简要说明

  ![master](https://github.com/ChengKIKI/Tutorial/blob/master/images/master.png)

  ##### 开发分支Develop（日常开发分支）

  日常的开发工作都在develop分支上进行，一阶段的开发完毕后，想正式对外发布，就合并到master主分支上进行发布

  ![develop](https://github.com/ChengKIKI/Tutorial/blob/master/images/dev.png)

  ##### 功能分支Feature（功能分支）

  开发某种功能分支，从develop上分出来的，开发完成后，合并到develop上，功能分支属于临时性分支的一种，功能开发完毕后可以删除。他的命名可以以feature-* 的形式。

  ![feature](https://github.com/ChengKIKI/Tutorial/blob/master/images/feature.png)

  ##### 预发布分支Release（预发布分支）

  发布正式版本之前（即合并到Master分支之前），我们可能需要一个预发布的版本进行测试，该分支是从develop分支上分出来的，测试完毕之后必须合并进develop和master分支，他的命名可以以 release-* 的形式。Release属于临时性分支中的一种，用完之后可以删除。

  ##### 修补bug分支

  版本正式发布后，难免会出现bug，这时就需要创建一个分支进行bug修补，修补bug分支是从master分支上分出来的，修补完毕之后再合并到develop和master分支上，可以采用fixbug-* 的形式来命名。Fixbug属于临时性分支的一种，用完可以删除掉。

  ![bug](https://github.com/ChengKIKI/Tutorial/blob/master/images/bug.png)
