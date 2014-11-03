---
layout: post
title: Built-in constraints in python 3.4
description: built-in constraints in python 3.4
category: ProgramThinking
---

1. built-in namespace:  
  + `False`: bool, SyntaxError
  + `True`: bool, SyntaxError
  + `None`: NoneType唯一的值，常表示值得缺失. SyntaxError
  + `NotImplemented`:
    - `NotImplemented`故名思议，就是“未实现”，一般是用在一些比较算法中的，如class的`__eq__`,`__lt__`等，注意`NotImplemented`并不是异常，所以不能使用raise，当没有实现时应该是`return NotImplemented`.
    - [NotImplemented小析](http://blog.csdn.net/yueguanghaidao/article/details/38641251)

  + `Ellipsis`:
    - [Ellipsis Slicing Syntax](http://stackoverflow.com/questions/101268/hidden-features-of-python/112316#112316)
    - [What does the Python Ellipsis object do?](http://stackoverflow.com/questions/772124/what-does-the-python-ellipsis-object-do#773472)
  + `__debug__`: 如果python启动时没有-O选项是默认为真. SyntaxError

2. 由 **site** 模块引入的常量: site启动时自动导入，除非使用-S选项. site自动添加许多常量到内置命名空间（built-in namespace）, 在交互解释shell中很有用，不应该在程序中使用.  
  + `quit(code=None)`: raise SystemExit
  + `exit(code=None)`: raise SystemExit
  + `copyright`, `license`, `credits`
