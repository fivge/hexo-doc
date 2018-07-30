---
title: oh my zsh
date: 2017-04-14 17:41:30
tags:
- zsh
- Term
categories:
- Term
---

### oh-my-zsh

> 安装

```bash
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```

或者

```bash
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

<!--more-->

> 配置

```bash
vim ~/.zshrc
```

> 插件

oh-my-zsh 项目提供了完善的插件体系，相关的文件在~/.oh-my-zsh/plugins目录下，默认提供了100多种，大家可以根据自己的实际学习和工作环境采用，想了解每个插件的功能，只要打开相关目录下的 zsh 文件看一下就知道了。插件也是在.zshrc里配置，找到plugins关键字，你就可以加载自己的插件了，系统默认加载 git ，你可以在后面追加内容，如下：



```bash
plugins=(git textmate ruby autojump osx mvn gradle)
```

###### 1.autojump

> > mac

```bash
brew install autojump
```

> > linux

```bash
git clone git://github.com/joelthelion/autojump.git
```

~~最后把以下代码加入.zshrc~~

~~[[ -s ~/.autojump/etc/profile.d/autojump.sh ]] && . ~/.autojump/etc/profile.d/autojump.sh~~

智能跳转，安装了autojump之后，zsh 会自动记录你访问过的目录，通过` j + `目录名 可以直接进行目录跳转，而且目录名支持模糊匹配和自动补全，例如你访问过`hadoop-1.0.0`目录，输入`j hado` 即可正确跳转。`j –stat `可以看你的历史路径库。

###### 2.git

当你处于一个 git 受控的目录下时，Shell 会明确显示 「git」和 branch，另外对 git 很多命令进行了简化，例如 gco=’git checkout’、gd=’git diff’、gst=’git status’、g=’git’等等，熟练使用可以大大减少 git 的命令长度，命令内容可以参考~/.oh-my-zsh/plugins/git/git.plugin.zsh

###### 3.textmate

mr可以创建 ruby 的框架项目，tm finename 可以用 textmate 打开指定文件。

###### 4.osx

tab 增强，quick-look filename 可以直接预览文件，man-preview grep 可以生成 grep手册 的pdf 版本等。

> 常用技巧

###### 1.目录浏览和跳转

输入 d，即可列出你在这个会话里访问的目录列表，输入列表前的序号，即可直接跳转。

在当前目录下输入 .. 或 … ，或直接输入当前目录名都可以跳转，你甚至不再需要输入 cd 命令了。

###### 2.通配符搜索

```shell
ls -l */.sh
```

可以递归显示当前目录下的 shell 文件，文件少时可以代替 find，文件太多就歇菜了。