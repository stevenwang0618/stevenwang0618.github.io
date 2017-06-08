---
layout: post
title: Mac OSX 终端命令自动补全
description: 安装 Terminal 上的命令自动补全
category: blog
---

### 查看已安装列表

    brew list
    
### 安装 bash-completion

安装命令:

    brew install bash-completion
    
安装完成后:

    brew info bash-completion
    
将以下代码复制至 `~/.bash_profile` 中：

    if [ -f $(brew --prefix)/etc/bash_completion ]; then
    . $(brew --prefix)/etc/bash_completion
    fi
    
重启 bash.
 
### 安装其他的命令补全

1. git

        cd /usr/local/opt/bash-completion/etc/bash_completion.d
        curl -L -O https://raw.github.com/git/git/master/contrib/completion/git-completion.bash
        brew unlink bash-completion
        brew link bash-completion
