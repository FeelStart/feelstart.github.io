---
title: ios_drawRect_qa
date: 2021-09-04 09:11:11
tags: iOS，爱思考

---

## 问题：iOS 中 UIView 的 drawRect: 方法什么时候调用？

官方文档

```
这个方法默认不实现任何东西。子类可以重写该方法，并利用如 Core Graphics 和 UIKit 技术进行绘制。UIKit 提供 UIGraphicsGetCurrentContext() 来获取 context 方法，并对其坐标进入了转换。

可以用 setNeedsDisplay() 或 r setNeedsDisplay(_:) 方法标记 View 需要重新绘制。
```
