---
title: obj_func_arg_type.md
date: 2022-01-12 09:39:21
tags:

---

今天看博客的时候，看到一个有趣的问题。[原博客地址](https://juejin.cn/post/6844903635256623111)


###问题是什么

先看下面的代码。

```
[self performSelector:@selector(isOwner:) withObject:@YES];

- (void)isOwner:(BOOL)is {
    if (is) {
        NSLog(@"is owner");
    } else {
        NSLog(@"is not owner");
    }
}

```

```[NSObject performSelector: withObject:]``` 这个方法要传入的数据是 NSObject 类型，而函数参数是 BOOL 类型。而无论我们传入什么参数，is 都是为 NO。 

###查看源代码

查看源代码发现

```
+ (id)performSelector:(SEL)sel withObject:(id)obj {
    if (!sel) [self doesNotRecognizeSelector:sel];
    return ((id(*)(id, SEL, id))objc_msgSend)((id)self, sel, obj);
}

```

其最终会转换成为 C 函数调用。

C99 标准中有描述：如果调用函数是参数类型不对应，其行为是不确定的。

```
C99 standard, section 6.5.2.2, paragraph 9

If the function is defined with a type that is not compatible with the type (of the expression) pointed to by the expression that denotes the called function, the behavior is undefined.
```

###参考

[Why I always get NO when performSelector:withObject:@YES in iOS, which is different in macOS?](https://stackoverflow.com/questions/50019946/why-i-always-get-no-when-performselectorwithobjectyes-in-ios-which-is-differ)
 
 