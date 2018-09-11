---
title: Git-分支管理
date: 2018-08-22 17:21:14
tags:
categories:
---

### 查看远程分支

```bash
$ git branch -a
* master
  remotes/origin/Develop
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
```

### 查看本地分支

```bash
$ git branch
* master
```

### 切换分支

```bash
# 切换远程分支到本地
$ git checkout -b Develop origin/Develop
Switched to a new branch 'Develop'
Branch 'Develop' set up to track remote branch 'Develop' from 'origin'.
# 查看
$ git branch -a
### 查看全部分支
* Develop
  master
  remotes/origin/Develop
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
### 查看本地分支
$ git branch
* Develop
  master
# 切换本地分支
### 切换到 master
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
#### 切换到 Develop
$ git checkout Develop
Switched to branch 'Develop'
Your branch is up to date with 'origin/Develop'.
```

### 版本回退

```bash
$ git log
commit 8862dda9655dd36881bc1ee09625a3e93850cf77 (HEAD -> Develop, origin/Develop)
Author: luanxingtong <luanxingtong@inspur.com>
Date:   Mon Aug 6 19:14:43 2018 +0800

    suppliersInfo.jsp(服务商管理-修改页面): 修改页面逻辑

commit eebe0aea263860f7ba54bfc8ab84a5c25671b433
Author: luanxingtong <luanxingtong@inspur.com>
Date:   Mon Aug 6 19:13:28 2018 +0800

    suppliersAdd.jsp(服务商管理-添加页面): 页面结构优化

commit 680e76fa1e7b2ac4656a9f6a7c605c074772b5c9
Author: luanxingtong <luanxingtong@inspur.com>
Date:   Mon Aug 6 19:12:24 2018 +0800

    suppliersQuery.jsp(服务商管理): 删除供应商简介，优化化代码

commit 2a93f50ea94daedf751b67b09b1db15678d3a1d3
Author: luanxingtong <luanxingtong@inspur.com>
Date:   Mon Aug 6 19:10:42 2018 +0800

    indexs.jsp(首页): 删除无用图表

$ git reset --hard 680e76fa1e7b2ac4656a9f6a7c605c074772b5c9
HEAD is now at 680e76f suppliersQuery.jsp(服务商管理): 删除供应商简介，优化化代码
```



<!--more-->