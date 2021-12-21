---
title: fdk_aac_codec_ios
date: 2021-12-21 14:15:23
tags: 音视频，iOS

---

# AAC 编码器 iOS 配置

## 环境

Mac M1 pro

## 下载

[fdk-aac](https://sourceforge.net/p/opencore-amr/fdk-aac/ci/v0.1.4/tree/)

[dk-aac-build-script-for-iOS](https://github.com/kewlbear/fdk-aac-build-script-for-iOS)

## 编译

```
brew install automake libtool 

// 修改 build-fdk-aac.sh 的目标目录

cd fdk-aac... 
arch -arch x86_64 ./autogen.sh

cd ..
arch -arch x86_64 ./build-fdk-aac.sh
```

## 集成 Xcode

``` fdk-aac-ios```  改名 ``` fdk-aac ```，并拖动到项目中。

修改 buiild setting -> Search Header Path: ``` $SRCROOT/fdk-aac/include ```

build setting -> excluded archiectures -> debug -> arm64

## 参考

[编译fdk-aac的ios版本](https://www.jianshu.com/p/129de9d6b21d)
