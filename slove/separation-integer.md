# 分離數字

## 概述
給一串非字元字串數字(**未限制長度**)
我們想要分離他去做額外的計算  
(期中考題目)  
**例如:**  
分離:1234  
```
1 2 3 4
```

### 應先具備以下知識
1. [陣列]()
## 正題
將數字對10**取餘數**==>即得到該數之`個位數`  
例如```1234%10```得:  
```
4
```
**將直存入arry中**  

這時再將輸入值/10(因為系統所存為integer所以**剛求出的尾數會被拋棄**)  
即```1234/10```得:
```
123
```
再將其在次`取餘`求得尾數
```123%10```
```
3
```
**將直存入arry中**  


如此下來當除以得值==0時結束
```cpp
while(input!=0)
```
### 範例
```cpp

#include <iostream>

using namespace std;

int main()
{
    int input, i = 0;
    int a[500000];
    cin >> input; // 輸入值(同scanf("%d",&input))
    while (input != 0)//拆分數字
    {
        a[i] = input % 10;
        input = input / 10;
        i++;
    }
    for (int j = i; j > 0; j--)//輸出陣列
    {
        cout << a[j - 1] << " ";//輸出值(同printf("%d ",a[j])
    }
    return 0;
}
```
**輸入1234**得:
```
1 2 3 4
```
**輸入6589**得:
```
6 5 8 9
```
### 延伸用法
* [回文數列](https://github.com/archie0732/pu-computer-programming-G1-hw/tree/main/1103)
