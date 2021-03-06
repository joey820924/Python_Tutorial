# 變數

## 變數宣告

很多時候，我們不可能單用數值來做複雜的運算，但透過變數我們可以很方便地在程式碼的各處傳遞與運算數值。  
在Python中，變數的宣告方式非常簡單，如下。毋須像其他程式語言如Java一樣必須宣告變數的型態，在Python中可以直接建立並賦予值。

```text
a = 1
# 如此我們就成功將1這個值賦予給名為a的這個變數囉～

a = a+1
print(a)
輸出結果：
2
#由這個例子可以看到，我們可以隨意在其他地方使用a這個變數。

x,y = 1,2
print(x,y)
輸出結果：
1,2

q=w=e=1
print(q,w,e)
輸出結果：
1,1,1
#由這個例子可以看到，我們亦可同時宣告好幾個變數並賦予他們值。
```

## 變數名稱

變數名稱的命名規則如下：  
1. 變數名稱僅能由\[a-z\], \[A-Z\], \[0-9\]以及底線\(\_\)所結合而成。  
2. 大小寫有別。  
3. 命稱開頭不能以數字開頭。  
4. 不得使用Python的保留字

```text
import keyword
print(keyword.kwlist)
輸出結果：
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del',
 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 
 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 
 'yield']
# 以上為Python的保留字。
```

## 刪除變數

當我們認為不會再使用該變數時，我們亦可透過del\(\)函式將其刪除。

```text
x = 1
del(x)
print(x)
輸出結果：
Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
NameError: name 'x' is not defined
#當刪除後，就無法再使用該變數，因為已不存在了。
```



