---
title: git
date: 2021-12-22 10:37:56
tags: Git

---

# Git

### 指定分支 tag 代码

```
git clone --branch [tags标签] [git地址] 
git clone --b [tags标签] [git地址]

git checkout tag_name
```

### 多用户

```
// 配置 ssh
cd ~/.ssh
touch config 

Host github.com-user
  HostName github.com
  User git
  IdentityFile ~/.ssh/isa
  
git clone git@github.com-user:user/user.git
```

### 用户信息

```
git config user.name user
git config user.email user.email
```



### 拉取子模块

```
ls -a


git clone --recurse-submodules ..
```