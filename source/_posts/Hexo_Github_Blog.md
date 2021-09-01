---
title: "Hexo & Github 搭建个人博客"
date: 2021年9月1日 22:46:00
---

[Hexo](https://github.com/hexojs/hexo) 是开源博客工具，配合 GitHub，可以搭建个人免费博客

## 配置 Hexo

* 安装 ``` Node ```

```
npm uninstall -g npm
brew uninstall node

brew install node
```

* 安装 ``` git ```

```
brew install git
```

* 安装 ``` Hexo ```

```
 npm install -g hexo-cli
```

## 配置 Github

* 配置 Git 的 SSH Key

```
ssh-keygen -t rsa -C "email@gmail.com"

cat ~/.ssh/id_rsa.pub // 复制
```

登录 Github -- Setting -- SSH and GPS keys -- New SSH key -- Add SSH Key

* 创建仓库

创建命名为 ``` username.githug.io ``` 的创建

## 写作

* 创建项目

```
hexo init feelstart_blog
```

* 配置项目

```
cd feelstart_blog

npm install hexo-deployer-git --save
```

* 修改 ``` _config.yml ```

```
deploy:
	type: git
	repo: git@github.com:FeelStart/feelstart.github.io.git
	brance: main
```

* 生成和部署

```
// 清除以前静态文件
hexo cl 

// 生成静态文件
hexo g

// 部署到 Github
hexo d
```

## 主题

Hexo 默认 [landscape](https://github.com/hexojs/hexo-theme-landscape) 主题。下面安装 [Next](https://github.com/theme-next/hexo-theme-next) 主题

```
git clone https://github.com/iissnan/hexo-theme-next themes/next

// Hexo 5.0 之后要手动安装 swig
npm i hexo-renderer-swig
```

修改 ``` _config.yml ``` 中的 theme

```
theme: next 
```

## 访问

[feelstart-blog](https://feelstart.github.io/)

## 参考

[How to install NodeJS and NPM on Mac using Homebrew](https://medium.com/@hayasnc/how-to-install-nodejs-and-npm-on-mac-using-homebrew-b33780287d8f)

[Mac下使用GitHub+Hexo搭建个人博客](https://segmentfault.com/a/1190000038373795)

[npm在Mac上的卸载与安装](https://segmentfault.com/a/1190000021706685)

[同一客户端下使用多个git账号](https://www.jianshu.com/p/89cb26e5c3e8)

[使用git分支保存hexo博客源码到github](http://www.yangbing.club/2019/06/29/save-hexo-source-post-with-git-branch/)