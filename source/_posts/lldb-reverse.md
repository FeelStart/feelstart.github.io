---
title: ios_reverse
date: 2021-12-24 08:21:24
tags: iOS, LLDB 

---

# LLDB 逆向

```
#include <stdio.h>

int main() 
{
  printf("Hello\n");
  return 0;
}
```

```
arch -arch x86_64 clang hello.c
arch -arch x86_64 clang -glldb a.out // -glldb 标志会显示源代码

file a.out

lldb a.out

(lldb)r // 运行

nm a.out // 显示符合表
(lldb) image dump symtab a.out // 显示符合表

// 查看镜像的帮助
(lldb)help image 
(lldb)help target modules

(lldb)b main // 断点

(lldb)register read // 读寄存器
(lldb)register read rsp

(lldb)x/10w -l 1 $rsp // 打印内存

(lldb)ni // 执行下一条指令

(lldb)di // 反汇编
```


## 参考资料

[Using LLDB for reverse engineering
](https://rderik.com/blog/using-lldb-for-reverse-engineering/)