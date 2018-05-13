# 集合\(Set\)

## 集合\(Set\)宣告

集合\(Set\)一個無序、不重複的序列，其宣告方式有兩種：

```text
>>> s1 = {1,2,3}
>>> print(type(s1))
<class 'set'>

>>> s2 = set([1,2,3,34,5])
>>> print(type(s1))
<class 'set'>
```

> Note：  
> 1. 以set\(\)函式創建集合時，要注意其僅能輸入一個值，你可傳入一個包含多個值的元組、字串或串列等等，創建出的集合對象會自動將重複的元素值去掉留下無序的不重複元素。  
> 2. 使用{ }宣告集合時，要注意當你想宣告一個空集合時，不能使用，因為會變成宣告字典。若你想要宣告空集合，需使用set\(\)

```text
>>> s3 = set((1,2,3,34,5))
>>> print(s3)
{1, 2, 3, 34, 5}

>>> s4 = {}
>>> print(type(s4))
<class 'dict'>
# 並非集合型態，而是字典型態。

>>> s5 = set()
>>> print(type(s5))
<class 'set'>
# 使用set()函式才可創建空集合。
```

## 集合\(Set\)操作

集合\(Set\)可進行集合運算，包括聯集、交集、差集等等。

```text
>>> s6 = set('abcdefg')
>>> s7 = {'c','d','e'}

>>> print(s6 - s7)
{'f', 'g', 'b', 'a'}
# 差集

>>> print(s6 | s7)
{'d', 'f', 'a', 'c', 'b', 'g', 'e'}
# 聯集

>>> print(s6 & s7)
{'d', 'e', 'c'}
# 交集

>>> print(s6 ^ s7)
{'f', 'a', 'b', 'g'}
# s6集合與s7集合中不同時存在的元素
```
