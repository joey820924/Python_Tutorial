# 元組\(Tuple\)

## 元組宣告

元組為可迭代對象，宣告方式有兩種，如下。

```text
t1 = tuple('Joey')
print(type(t1))
print(t1)
輸出結果：
<class 'tuple'>
('J','o','e','y')

t2 = ('a',123,tuple('a'))
print(type(t2))
輸出結果：
<class 'tuple'>
```

> 但tuple\(\)方法所能轉換的僅能為可迭代者。

由上述例子可以看到元組可以容納好幾個元素，且每個元素的類型可不同。

> 當使用\( \)來宣告元組時，當僅宣告空元組或一個元組時需注意：

```text
t3 = ()
print(type(t3))
輸出結果：
<class 'tuple'>
#宣告空元組

t4 = (20,)
print(type(t4))
輸出結果：
<class 'tuple'>
#當要宣告一個元組時，需在元素後加上逗點，否則會變為宣告數值，如下例

t5 = (20)
print(type(t5))
輸出結果：
<class 'int'>
```

## 操作元組

### Slice\(切片\)

與字串一樣，元組亦可透過Slice\(切片\)來取得其中的值。

```text
t6 = (1,'Joey',3,4,5,'XDXD',7,8,9)
print(t6[2:5])
輸出結果：
(3,4,5)
```

同時，元組亦為不可變\(Immutable\)的資料型態，所以也沒有append\(\)、insert\(\)等方法。

```text
t7 = (1,'Joey',3,4,5,'XDXD',7,8,9)
t7[3] = 2
輸出結果：
Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment

# 由上例即可發現，元組是不容許被變更其內元素值的。
```

### 元組增添

雖然元組內容是不可變更的\(Immutable\)，但我們可以透過+來拼接其他元組，或是用\*複製元素。

```text
t8 = (1,'Joey',3,4,5,'XDXD',7,8,9)
print(t8+(10,11,12))
輸出結果：
(1,'Joey',3,4,5,'XDXD',7,8,9,10,11,12)

print(t8*2)
輸出結果：
(1,'Joey',3,4,5,'XDXD',7,8,9,10,11,12,1,'Joey',3,4,5,'XDXD',7,8,9,10,11,12)
```

### 內建方法

雖然元組沒有append\(\)、insert\(\)等會改變內部值的方法，但還是有一些好用的方法，如count\(\)、index\(\)。

```text
a = (1,2,3,4,2,'Joey',1,2,3,1,1)
print(a.count(1))
print(a.index('Joey'))
輸出結果：
4
5
```

