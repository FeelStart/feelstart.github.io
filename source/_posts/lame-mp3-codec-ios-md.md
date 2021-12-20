---
title: lame_mp3_codec_ios.md
date: 2021-12-20 15:06:18
tags: 音视频, iOS

---

# iOS 的 lame 环境配置

lame 是 mp3 编码库。

#### 1，环境

Mac M1 Pro

#### 2，下载 [lame](https://github.com/zlargon/lame)

```
mkdir lame_codec
cd lame_codec 
git clone https://github.com/zlargon/lame
```

#### 3，下载编译脚本 [build-lame-for-ios](https://github.com/kewlbear/lame-ios-build)

```
git clone https://github.com/kewlbear/lame-ios-build

mv ./lame-ios-build/build-lame.sh ./build-lame.sh
```

#### 编译

```
./build-lame.sh

// M1 要加上
arch -arch x86_64 ./build-lame.sh
```

#### 合并到 xcode 项目

* 将编译好 ``` flat-lame ``` 拖到 xcode 项目，并改名 ``` lame ```

* 修改 ``` search header path ```

  ``` build settings ``` -> ``` search header ``` -> ``` $SRCROOT/lame/include ```
  
* ``` Excluded Architectures ``` 添加 ``` arm64 ```