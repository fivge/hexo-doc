---
title: Github两步验证导致git push失败
date: 2018-04-22 16:20:56
tags:
- Github
categories:
- Git
---

## Creating a personal access token for the command line

<!--more-->

**Settings** ->  **Developer settings**,生成Personal access tokens,即为终端中待输入的密码

```bash
$ git clone https://github.com/username/repo.git
Username: your_username
Password: your_token
```



##### 参考链接

<https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/>