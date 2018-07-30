---
title: RubyGems镜像源
tags: 
- RubyGems
categories:
- Term
---

### RubyGems镜像源

<https://gems.ruby-china.org>

##### 更新

```bash
$ gem update --system # 这里请翻墙一下
$ gem -v
```

##### 替换镜像源

```bash
$ gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/
$ gem sources -l
https://gems.ruby-china.org
# 确保只有 gems.ruby-china.org
```

