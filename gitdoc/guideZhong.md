
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
1. 将本地环境切换到master分支，并将拉取远程master分支为最新版本  
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master011.png)   

2. 从本地master分支创建最新修补分支(分支名以1067为例)  
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master012.png)   

3. 修补分支修改后可推到远程，并进行测试
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master013.png)   
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master014.png)       

4. 代码发布后，在github网页端发起fix合并master分支的请求  
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master3.png)   
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master4.png)   
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master5.png)   
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master6.png)   
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/master7.png)   

5. 将修补分支代码合并到develop分支  
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/develop1.png)   
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/develop2.png)   
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/develop3.png) 

6. 删除修补分支    
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/10671.png) 
![git仓库基本流程](https://cdn.jsdelivr.net/gh/qjw1067/docsify/images/git/10672.png) 



*注：日常开发规范，以develop分支为例，个人分支以1067分支为例*
1. 每日开发前从develop拉取代码，保持1067分支代码版本与版本库一致
2. 每晚下班需进行代码合并，保持本地版本与开发版本基本一致，拉取develop分支
3. 合并无误后切换到develop分支合并1067分支代码
4. 推送develop分支到版本库

*注：develop为日常开发分支，推送代码无需发起合并请求*


https://www.jianshu.com/p/4883e95aa903

https://qjw1067.github.io/docsify/