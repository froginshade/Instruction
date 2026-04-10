# 指定编码
放在直接执行脚本的最开头
```
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
```

# 字符串
str以Unicode编码
```
# 单字符的编号
ord('A')

# 编码对应的字符
chr(66)

# str编码为bytes
# 无法编码为ascii的字节在bytes中用\x##表示
'abc'.encode('ascii')

# 把bytes解码为str
# 设置error忽略错误无效的字节
b'abc'.decode('ascii', errors='ignore')
```

# 函数
```
x = 10
def func(a: int, b: float, c: str, *args, **kwargs) -> float:
    # 全局变量
    global x

    # 检查参数的类型
    if not isinstance(a, (int, float)):
        raise TypeError('bad type')

    # 元组形式传入
    print(args)

    # 字典形式传入
    print(kwargs)

    return 10*a, 10*b
```

## 匿名函数
```
square = lambda x: x**2
```

## 闭包
在函数内部定义一个内层函数
nonlocal在嵌套函数中向外层寻找匹配的（非全局）**变量**，直到达到全局作用域
```
def counter():
    n = 0
    def inc():
        # 修改外部变量必须使用nonlocal
        nonlocal n
        n += 1
        return n
    return inc

c = counter()
print(c())  # 1
print(c())  # 2
```

## 装饰器
接受一个函数并返回新函数
通常用闭包实现
```
import functools

def my_decorator(func):
    
    # 保留原始的元信息
    # 把原函数的关键信息复制到wrapper上
    @functools.wraps(func)   # 在这里加 wraps
    def wrapper(*args, **kwargs):   # 闭包
        print("Before call")
        return func(*args, **kwargs)
    return wrapper

@my_decorator
def hello():
    """这是原始函数的文档"""
    print("Hello!")

print(hello.__name__)   # hello ✅
print(hello.__doc__)    # 这是原始函数的文档 ✅
```

## 高阶函数
```
# 传入函数
def add(x, y, f):
    return f(x) + f(y)

print(add(-5, 6, abs))
```

### map/reduce函数
```
map(func, Iterable_element)
    return Iterator
```

```

```

## 偏函数
设定默认参数，返回新函数
```
import functools

int2 = functools.partial(int, base=2)
int2(10)
```

# 包调用
- 同级文件夹     from xxx import func
- 子文件夹       from xx.xx import func
- 上级文件夹     from ..xx import func
- 同级子文件夹   from ..xx.xx import func


# 类
## 抽象基类


