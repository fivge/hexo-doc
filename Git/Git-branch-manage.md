---
title: Git branch manage
date: 2018-09-11 22:12:24
tags:
- Git
categories:
- Git
---



<!--more-->

### 0x01 基本

> 创建分支

```bash
➜  gitTest git:(master) git checkout -b dev
Switched to a new branch 'dev'
➜  gitTest git:(dev)
```

#### `=>`

```shell
git branch dev
git checkout dev
```

> 查看分支

```bash
➜  gitTest git:(dev) git branch
* dev
  master
```

> 切换分支

```bash
### 切换到 master
➜  gitTest git:(dev) git checkout master 
Switched to branch 'master'
### 切换到 dev
➜  gitTest git:(master) git checkout dev
Switched to branch 'dev'
```

> 合并分支

```bash
### 合并 dev 分支到当前分支
➜ git merge dev
Updating 4008c54..64cfdd3
Fast-forward
 init.md | 2 ++
 1 file changed, 2 insertions(+)
### 禁用 Fast forward
➜ git merge --no-ff -m "merge with no-ff" dev
```

`Fast-forward`，“快进模式”，也就是直接把`master`指向`dev`的当前提交，合并速度非常快

> 删除分支

```bash
➜ git branch -d dev 
Deleted branch dev (was 64cfdd3).
➜ git branch
* master
```

## 0x02 解决冲突

当 dev 分支和 master 分支都修改时,此时合并分支,出现冲突

```bash
### 新建分支 feature
### 尝试合并分支 feature 到 master
➜  gitTest git:(master) git merge feature 
Auto-merging init.md
CONFLICT (content): Merge conflict in init.md
Automatic merge failed; fix conflicts and then commit the result.
##### 合并分支失败,但将不同的部分都同步并标识出来

### 查看详情
➜  gitTest git:(master) ✗ gst
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

	both modified:   init.md

no changes added to commit (use "git add" and/or "git commit -a")
### 查看文件
➜  gitTest git:(master) ✗ cat init.md 
This is a init file

>  branch
<<<<<<< HEAD
This is master branch
=======
This is feature branch.
>>>>>>> feature
```

**Git用`<<<<<<<`，`=======`，`>>>>>>>`标记出不同分支的内容，修改后保存**

查看分支合并情况

```bash
git log --graph --pretty=oneline --abbrev-commit

*   8ade83a (HEAD -> master) feat(init.md): master not feature
|\  
| * 1105478 (feature) feat(init.md): feature
* | ef30346 feat(init.md): master
|/  
* 64cfdd3 😢 update init.md
* 4008c54 ❤ init
(END)
```

>  远程协助

```bash
git checkout -b dev origin/dev

git push origin dev
```

1. 首先，可以试图用`git push origin <branch-name>`推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图合并；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

如果`git pull`提示`no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`。

这就是多人协作的工作模式，一旦熟悉了，就非常简单。

> ```bash
> git rebase
> ```

