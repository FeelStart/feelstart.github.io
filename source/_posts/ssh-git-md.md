---
title: ssh_git.md
date: 2021-12-20 14:57:10
tags: Other

---

#### 生产 ssk key

```
cd ~/.ssh
ssh-keygen -t rsa -C "email"
```

#### 复制 ssk pub

```
pbcopy < ~/.ssh/id_rsa.pub

// 打印并复制
cat ~/.ssh/id_rsa.pub
```

#### 多用户

```
open ~/.ssh/config

# Default GitHub. ssh -T github.com
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ras
  
# user. ssh -T github.com-user
Host github.com-user
  HostName github.com
  User git
  IdentityFile ~/.ssh/github.com-user
```

#### 拉取仓库

```
git clone git@github.com-user:user/user.git
cd user
git config user.name user
git config user.email user.email
```