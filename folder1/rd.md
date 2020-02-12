
# Chapter 3 Strings, Vectors, and Arrays
## 3.2 Library string Type
>本章節範例皆假設已有以下程式碼:
``` c++
#include <strung>
using std::string
```

### 3.2.2 Operations on strings
>**Table 3.2 String Operations**  
![image](https://user-images.githubusercontent.com/55428505/66101454-7d0e4400-e5e1-11e9-9c33-b47d3f1dc919.png)
>#### Reading and Writing strings
可用`iostream`函式庫來讀或寫`string`:
``` c++
// Note: #include and using declarations must be added to compile this code
int main()
{
    string s;          // empty string
    cin >> s;          // read a whitespace-separated string into s
    cout << s << endl; // write s to the output
    return 0;
}
```
`string`輸入運算子(`is>>s`)會*忽略任何前方的whitespace*(e.g.空白、換行、tabs)並且開始讀取字元*直到遇見下一個whitespace*，例如如果我們輸入  *Hello World!* (前方及後方都有space)，則輸出會是*Hello*(沒有其他space)。就跟內建型別的輸入與輸出一樣，string operators回傳它左側的運算元作為結果，因此可以連續的讀或寫:
``` c++
string s1, s2;
cin >> s1 >> s2; // read first input into s1, second into s2
cout << s1 << s2 << endl; // write both strings
```
如果我們的輸入還是   *Hello World!*   ，則輸出會是”*HelloWorld!*”。
