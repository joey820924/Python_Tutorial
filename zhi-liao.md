# 數值\(Number\)

## 資料型態

Python3中的數值型態有三種：  
1. 整數\(int\)  
2. 布林\(boolean\)  
2. 浮點數\(float\)  
3. 複數\(complex\)

#### 整數

在Python3中，整數並無分為整數與長整數，長度並無限制\(但在硬體限制內\)。整數的進位制整理如下

```
//十進位，為預設進位
10

//二進制，每位數值由0或1組成
0b1010 or bin(10)

//八進制，每位數值由0~7組成
0o12 or oct(10)

//十六進制，每位數值由0~7 A~F組成
oxa or hex(10)
```

其中無論是十進制、二進制亦或是十六進制，型態都是int。  
  
而若想將其他進制的數值\(須為字串型態\)轉換回十進位，僅需透過int\(\)方法，並指定要被轉換的進制，預設為十進位。

```text
//十進位
a = int('10')
print(a)
輸出結果：
10

//二進制
b = bin(a)
print(b) #字串型態
print(int(b,2))
輸出結果：
0b1010
10

//八進制
c = oct(a)
print(c) #字串型態
print(int(b,8))
輸出結果：
0o12
10

//十六進制
d = hex(a)
print(d) #字串型態
print(int(d,16))
輸出結果：
0xa
10
```

每種進位皆有其前輟符號，如二進位為0b, 八進位為0o, 十六進位為0x，但若不想有前面這些前輟符號該怎麼辦呢？  
  
這時僅需透過format\(\)函式：

```text
a = 10
format(10,'b') #二進位
format(10,'o') #八進位
format(10,'x') #十六進位
輸出結果：
'1010'
'12'
'a'
```

除此之外，透過print\(\)函式來顯示數字，會自動將其他進位轉換為十進位顯示。

```text
number_10 = 10
number_2 = 0b1010
number_8 = 0o12
number_16 = 0xa
print(number_10)
print(number_2)
print(number_8)
print(number_16)
輸出結果：
10
10
10
10
```

#### 布林

可用於表達True與False的數值，型態為bool，bool為int的子類別，0為False，1為True。在Python中，不是0就是True，所以空字串、空串列、None也都為False。

```text
//可用bool來指定型態
bool方法中傳入值只要非0或空資料，則都為True
bool(0) == False
bool({}) == False
bool('1') == True
```

#### 浮點數

可用於表達有小數位的數值，型態為float。  
另外，亦可使用科學表示法表示，如下。

```text
print(2.5e2)
輸出結果：
250.0
#e為十次方，因此e2代表100。
#e也可以用E表示

print(float(2))
輸出結果：
2.0
#可用float()方法來指定型態
```

而若想表達正負無限大等數值亦可做到喔，而想確認其是否為無限大或非數字也可透過isinf\(\)和isnan\(\)兩種方法進行判斷。

```text
float('inf') #無限大
float('infinity') #無限大
float('-inf') #負無限大
float('-infinity') #負無限大
float('nan') #Not a Number, 表明為非數字。
```

float類別也有提供一些內建函數，整理如下表。

| Function | Description |
| --- | --- | --- | --- |
| float.fromhex\(x\) | 將16進位的浮點數的字串表示x轉換為10進位的浮點數 |
| float.hex\(x\) or x.hex\(\) | 將10進位浮點數x轉換為16進位浮點數以字串型態回傳 |
| float.is\_integer\(\) | 判斷是否為整數 |

#### 分數

分數並不屬於數值型別但我們還是來談談要如何實現。  
答案就是透過fractions模組

```text
import fractions #導入模組
a = fractions.Fraction(12,18) #建立分子12分母18的分數
print(a)
print(a.numerator)
print(a.denominator)
b = fractions.Fraction(4,30)
print(a+b) #可以與其他分數進行運算
print(float(a+b)) #並可透過float()函式轉換為浮點數型態
輸出結果：
2/3
2
3
4/5
0.8
```

#### 複數

可用於表達複數，型態為complex。

```text
2+5j
#可用j來代表虛數
#可用complex(x,y)方法來建立複數，若未傳入y，則虛部則為0j

print(complex(2,3) == 2+3j)
輸出結果：
True

print(complex(2) == 2+0j)
輸出結果：
True

a = 2+3j #建立複數型態
print(a.real) #取得實數
print(a.imag) #取得虛數
print(a.conjugate()) #取得共軛複數
輸出結果：
2.0
3.0
(2-3j)
```

#### 隨機數

 隨機數的實現可透過導入random模組的以下方法：

| function | description |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| random.choice\(sequence\) | 從一個序列項目中隨機挑選其中元素 |
| random.randint\(a,b\) | 從a~b中的數值範圍隨機挑選其中一個整數 |
| random.random\(\) | 隨機選出從0~1的浮點數 |
| random.randrange\(start,end,step\) | 隨機從指定範圍中挑選一個隨機數 |
| random.sample\(seq,k\) | 從序列中隨機挑選k個元素 |
| random.shuffle\(seq,\[,random\]\) | 將序列隨機打亂 |
| random.seed\(a = None, version = 2\) | 初始化亂數種子，之後該亂數便會固定 |
| random.uniform\(a,b\) | 從指定範圍中挑選出隨機浮點數 |

```text
import random #導入模組

print(random.choice('Hello'))#從可迭代的字串序列中隨機挑選元素
輸出結果：
H

print(random.randint(0,100))#從0~100隨機挑選整數
輸出結果：
98

print(random.random()) #隨機選出0~1的浮點數
輸出結果：
0.821719218117871

print(random.randrange(10,30,2))
執行結果：
22

a = [1,2,3,4,5,6,7]
random.shuffle(a)
print(a)
執行結果：
[4, 5, 6, 1, 3, 2, 7]

a = [1,2,3,4]
print(random.sample(4))
print(random.sample(4))
執行結果：
[1, 3, 2]
[1, 4, 3]
# 在第二次sample時，尚未被選取的會有較高的優先度。

random.seed(1)
print(random.random())
random.seed(1)
print(random.random())
執行結果：
0.13436424411240122
0.13436424411240122
# 亂數被固定

print(random.uniform(1,10))
執行結果：
9.603368968242952
```

## 算數運算符

| 運算符號 | 功用 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| + | 加法 |
| - | 減法 |
| \* | 乘法 |
| / | 除法 |
| // | 整除 |
| \*\* | 次方運算 |
| % | 模運算\(取餘數\) |

> Note：若運算的數值有浮點數，則得出的結果亦會是浮點數。

而若在進行除法後同時取得商和餘數，則可使用divmod\(x,y\)方法。

```text
print(divmod(13,4))
輸出結果：
(3, 1) # 3為商數, 1為餘數
```

#### 浮點數精度問題

浮點數在計算的一個問題是其無法表達精確的數值，其原因是因底層的CPU和IEEE 754標準所導致的計算誤差。

```text
print(1.0-0.8)
輸出結果：
0.19999999999999996
```

若想顯示精確的數值\(但要容忍些微的性能降低\)，可使用decimal模塊：

```text
from decimal import Decimal
print(Decimal('1.0')-Decimal('0.8'))
輸出結果：
0.2
```

### 比較運算符

| 運算符號 | 功用 |
| --- | --- | --- | --- | --- | --- | --- |
| x == y | 比較x與y彼此是否相等 |
| x != y | 比較x與y彼此是否不相等 |
| x &gt; y | 比較x是否大於y |
| x &lt; y | 比較x是否小於y |
| x &gt;= y | 比較x是否大於等於y |
| x &lt;= y | 比較x是否小於等於y |

### 賦值運算符

| 運算符號 | 功用 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| x = y | 將y的值賦給x |
| x += y | 將x+y的值賦給x |
| x -= y | 將x-y的值賦給x |
| x \*= y | 將x\*y的值賦給x |
| x /= y | 將x/y的值賦給x |
| x //=y | 將x//y的值賦給x |
| x %= y | 將x%y的值賦給x |
| x \*\*= y | 將x\*\*y的值賦給x |

### 位元運算符

| 運算符號 | 功用 |
| --- | --- | --- | --- | --- | --- | --- |
| &  | 執行and位元運算。 |
| \| | 執行or位元運算。 |
| ^ | 執行xor位元運算。 |
| ~ | 執行not位元運算 |
| &lt;&lt; | 執行左移位元運算，所要移動的位元位數由符號的右邊值指定。 |
| &gt;&gt; | 執行右移位元運算，所要移動的位元位數由符號的右邊值指定。 |

### 邏輯運算符

| 運算符號 | 功用 |
| --- | --- | --- | --- |
| x and y | 布林運算的and運算。 |
| x or y | 布林運算的or運算。 |
| not x | 布林運算的not運算，回傳x的相反布林值。 |

> 邏輯運算符當面對非布林型態的值時，會直接回傳運算元。

```text
3 and 8  #輸出為8，原因需檢查每個運算元是否皆為True。
0 and 8  #輸出為0，因為檢查到第一個運算元時為False，所以會直接回傳。
3 or 8   #輸出為3，因為當檢查到第一個為True時，就可以判斷為True，所以會直接回傳。
0 or 8   #輸出為8，因為第一個運算元非True。
```

### 成員運算符

| 運算符號 | 功用 |
| --- | --- | --- |
| in | 若指定串列中有目標內容則回傳True，否則回傳False。 |
| not in  | 若指定串列中沒有目標內容則回傳True，否則回傳False。 |

### 身份運算符

| 運算符號 | 功用 |
| --- | --- | --- |
| x is y | 判斷x與y是否都是引用同個對象，若是則為True，否則為False。 |
| x is not y | 判斷x與y是否都是引用同個對象，若是則為False，否則為True。 |

> 身份運算符的is符號與比較運算符的==符號不同點在於，is是判斷兩個變量是否引用同一個Object，而==則是判斷兩個變量的值是否一樣。

### 運算優先級

| 優先級 | 運算符號 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | \*\* 算數運算符\(次方\) |
| 2 | ~ 位元運算符\(not\) |
| 3 | \*, / ,% , // 算數運算符\(乘法除法\) |
| 4 | +, - 算數運算符\(加法減法\) |
| 5 | &gt;&gt;, &lt;&lt; 位元運算符\(左移右移\) |
| 6 | & 位元運算符\(and\) |
| 7 | ^, \| 位元運算符\(xor, or\) |
| 8 | &lt;, &gt;, &lt;=, &gt;= 比較運算符\(大於小於\) |
| 9 | ==, != 比較運算符\(等於\) |
| 10 | =, +=, -=, =, \*\*==,/=, //= 賦值運算符 |
| 11 | is, is not 身份運算符 |
| 12 | in, not in 成員運算符 |
| 13 | not, or, and 邏輯運算符 |

## 數學運算

### 運算函數

| 函數 | 功用 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| abs\(x\) | x的絕對值 |
| math.ceil\(x\) | 無條件進位至整數 |
| math.exp\(x\) | x的指數 |
| math.fabs\(x\) | x的絕對值 |
| math.floor\(x\) | 無條件捨去至整數 |
| math.log\(x\) | x的對數，x須大於0 |
| math.log10\(x\) | x的對數，基底為10，x須大於0 |
| max\(x1,x2,...\) | 找出最大的數 |
| min\(x1,x2,...\) | 找出最小的數 |
| math.modf\(x\) | 回傳\(x的小數,x的整數\)，其中x的整數為浮點數型態。 |
| math.pow\(x,y\) | x的y次方 |
| round\(x,n\) | x四捨五入到n個小數位元，預設為取到整數。 |
| math.sqrt\(x\) | x的平方根，x須大於0 |

### 三角函數

| 函式 | 功用 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| math.acos\(x\) | x的反餘弦值，以弧度表示 |
| math.sin\(x\) | x的反正弦值，以弧度表示 |
| math.atan\(x\) | x的反正切值，以弧度表示 |
| math.atan2\(y,x\) | 反正切atan\(y/x\)值，以弧度表示 |
| math.cos\(x\) | x的餘弦值 |
| math.hypot\(x,y\) | x歐幾里德範數，sqrt\(x\*x+y\*y\) |
| math.sin\(x\) | x的正弦值 |
| math.tan\(x\) | x的正切值 |
| math.degrees\(x\) | 從弧度到角度的轉換 |
| math.radians\(x\) | 從角度到弧度的轉換 |

### 數學常數

| 常數變數 | 功用 |
| --- | --- | --- |
| math.pi | 數學常數pi |
| math.e | 數學常數e |

