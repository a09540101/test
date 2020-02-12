# Chapter 2 Variables and Basic Types
## 2.2 Variables
#### Default Initialization
當我們在定義變數的時候沒有提供initializer，則它會被default initialized，default value取決於該變數的型別以及被定義的地方，內建型別物件的值取決於他被定義的地方:

(1)  如果定義於所有函式之外，則會被初始化為0。
(2)  如果定義於函數之內，則這些變數為**uninitialized**(例外:static變數，見6.1.1)，並且他們 
的值為未定義的(undefined)，複製或access這種變數是錯誤的。
大部分的class可以默認初始化，例如如果我們不給string明確的initializer時，會獲得一個空字串，有些class不允許默認初始化，當我們沒在創建它的物件時提供initializer的話編譯器會complain。

### 2.2.2 Variable Declarations and Definitions
為了支援separate compilation，C++將聲明(declaration)與定義(definition)做了區別:
(1)	**聲明(declaration)**
使得一個名稱(name)被程式所知道(makes a name known to the program)。
(2)	**定義(definition)**
創建該名稱的實體(creates the associated entity)。
一個變數的聲明標示了該變數的(1)型別(2)名稱，而一個變數的定義就是一種聲明，除了標示型別及名稱外，定義還在記憶體中配置了空間(allocates storage)且可能為該變數提供了初始值。
如果要獲得一個不是定義的聲明，我們加入關鍵字extern並且不提供一個explicit initializer:
``` C++
extern int i;     // declares but does not define i
int j;          // declares and defines j
```
任何包含explicit initializer的聲明即為一個定義:
```C++
extern double pi = 3.1416; // definition
```

上面的語法可行，但是這麼做就蓋掉extern的作用了。但是在函數中這麼做會發生錯誤。
注意:變數*只能被定義一次*，但是可以被聲明很多次!

## 2.3 Compound Types
廣義上來說，一個宣告的結構為**base type**加上一串**declarator**，每個declarator都為一個變數命名並且給予該變數與base type相關的型別。  
e.g.
``` C++
int &reval;
```
根據以上的程式碼

base type: ```int```
declarator: ```&reval```

