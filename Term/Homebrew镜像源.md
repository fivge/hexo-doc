---
title: Homebrew镜像源
date: 2018-04-21 23:11:03
tags:
- Homebrew
categories:
- Term
---

### Homebrew镜像源

[ 清华大学镜像源](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/)

[科大镜像源](http://mirrors.ustc.edu.cn/help/brew.git.html)

```bash
### 替换现有上游
cd "$(brew --repo)"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git

brew update
```

