# Python学习笔记
### 数据类型
- 整数
- 浮点数
- 字符串
- 布尔值
- 空值（用None表示）

### 条件判断
```
if <条件判断1>:
    <执行1>
elif <条件判断2>:
    <执行2>
elif <条件判断3>:
    <执行3>
else:
    <执行4>
```

### 循环
1. 第一种是for...in循环，依次把list或tuple中的每个元素迭代出来

``` Python
names = ['leeper', 'lee', 'haha']
for name in names:
    print(name)
```
``` Python
>>> list(range(5))
# [0, 1, 2, 3, 4]
```
通过range()函数，生成一个整数序列，再通过list()函数可以转换为list。

2. 第二种循环是while循环，只要条件满足，就不断循环，条件不满足时退出循环。

### 字符串
Python 3版本中，字符串是以Unicode编码的。
- ord()：获取字符的整数表示
- chr()：函数把编码转换为对应的字符
- encode()：可以编码为指定的bytes
- decode()：把bytes变为str
- len()：计算str包含多少个字符

``` Python
>>> ord('A')
>>> chr(66)
>>> 'ABC'.encode('ascii')
>>> '中文'.encode('utf-8')
>>> b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
>>> len('ABC')
```

常见的占位符：（转义：用%%来表示一个%）
1. %d	整数
2. %f	浮点数
3. %s	字符串 （会把任何数据类型转换为字符串）
4. %x	十六进制整数
``` Python
>>> 'Age: %s. Name: %s' % (22, 'leeper')
# 'Age: 20. Name: leeper'
```

### 列表（list）
list是一种有序的集合，可以随时添加和删除其中的元素。list里面的元素的数据类型也可以是不同的。
- len()：可以获得list元素的个数
- append()：往list中追加元素到末尾
- insert()：把元素插入到指定的位置
- pop()：删除list末尾的元素
- pop(i)：删除指定位置的元素（i是索引位置）

``` Python
>>> name = ['leeper', 'lee', 'haha']
>>> len(name)  # -> 3
>>> name[-1] # 获取最后一个元素
>>> name.append('Sandman')
>>> name.insert(1, 'Jack') # 把元素插入到索引号为1的位置
>>> name.pop()
>>> name.pop(1) 
```

### 元组（tuple）
tuple和list非常类似，但是tuple一旦初始化就不能修改。
- 在定义的时候，tuple的元素就必须被确定下来
- 没有append()，insert()这样的方法
- tuple的不变是它的元素“指向不变”

``` Python
>>> t = (1) # 定义1为元组的元素
>>> t = (1, ) # 定义元组只有一个元素
```

### 字典（dict）
Python内置了字典：dict的支持，dict全称dictionary，使用键-值（key-value）存储，具有极快的查找速度。
- 通过in判断key是否存在
- dict的get方法，如果key不存在，返回None，或者自己指定的value

``` Python
>>> 'Thomas' in d
>>> d.get('Thomas')
>>> d.get('Thomas', -1) # -1
```

### set
set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。  
要创建一个set，需要提供一个list作为输入集合:
``` Python
>>> s = set([1, 2, 3])
>>> s # {1, 2, 3}
```

- add(key)：添加元素到set中，可以重复添加，但不会有效果
- remove(key)：删除元素