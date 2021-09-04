---
title: ios_frame_bound_transfrom_qa
date: 2021-09-04 08:54:05
tags: iOS，爱思考

---

### 问题：改变 UIView 的 tranfrom 属性对 frame 和 bound 有什么影响？

```
import UIKit

class ViewController: UIViewController {

    let redView = UIView()

    override func viewDidLoad() {
        super.viewDidLoad()

        redView.backgroundColor = .red
        redView.frame = CGRect(x: 0, y: 100, width: 200, height: 50)
        view.addSubview(redView)

        print("before redView frame:", redView.frame) // 打印 (0.0, 100.0, 200.0, 50.0)
        print("before redView bound:", redView.bounds) // 打印 (0.0, 0.0, 200.0, 50.0)

        redView.transform = CGAffineTransform.init(scaleX: 0.5, y: 1)

        print("after redView frame:", redView.frame) // 打印 (50.0, 100.0, 100.0, 50.0)
        print("after redView bound:", redView.bounds) // 打印 (0.0, 0.0, 200.0, 50.0)
    }

}

``` 

可知：改变 tranfrom，影响 frame，不影响 bound。如果对 x 进行缩小 scaleX，其缩小后的 x = x + （1 - scaleX） * width / 2，width = width * scaleX。
