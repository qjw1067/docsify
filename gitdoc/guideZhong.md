
# Git基础操作

> ##### 现有分支介绍
- master 主干分支  
主要负责管理正在运行的生产环境代码。永远保持与正在运行的生产环境完全一致。

<!-- ![](https://cdn.jsdelivr.net/gh/itwanger/toBeBetterJavaer/images/overview/one-01.png) -->
<!-- ![](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/gitall.png) -->
<!-- ![](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/123.jpg) -->


- develop 开发分支  
主要负责管理正在开发过程中的代码。一般情况下应该是最新的代码。

- release 准生产分支（预发布分支） -- 预计2022年可能会投入使用 
较大的版本上线前，会从开发分支中分出准生产分支，进行最后阶段的集成测试。该版本上线后，会合并到主干分支。生产环境运行一段阶段较稳定后可视情况删除。

*注：生产环境下出现的紧急修复的代码。需从master分支建立自定义分支，修改完毕并测试上线后，并回主干分支，具体操作如下：*

> SourceTree操作介绍  
1. 从master上拉取生产环境代码，进行生产环境的bug修复
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master1.png)   
2. 代码修改并经测试无问题后，拉取master代码更新本地代码库，如有冲突，切勿使用"以我版本为主"进行处理，建议手动处理
3. 将本地修改的分支推到远程，例如：从master分离出fix分支进行bug修复，测试无误后将本地fix分支推向远程fix分支
4. 代码发布后，在github网页端发起fix合并master分支的请求


*注：日常开发规范，以develop分支为例，个人分支以1067分支为例*
1. 每日开发前从develop拉取代码，保持1067分支代码版本与版本库一致
2. 每晚下班需进行代码合并，保持本地版本与开发版本基本一致，拉取develop分支
3. 合并无误后切换到develop分支合并1067分支代码
4. 推送develop分支到版本库

*注：develop为日常开发分支，推送代码无需发起合并请求*


https://www.jianshu.com/p/4883e95aa903

https://qjw1067.github.io/docsify/