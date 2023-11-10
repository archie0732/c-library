# #define 定義

## 用途
1. 簡化程式
2. 定義常數
## 使用方式
**#define `取代名字` ` `   `要取代函式或數字`**  
EX:
```cpp
#include <iostream>
#define ll long long // 定義(替代) long long 為 ll
#define SIZE 100     // 定義SIZE為常數100

using namespace std;

int main()
{
    ll a;     // 等同於long long a;
    a = SIZE; //(等於a=100)
    cout << a << endl;

    return 0;
}
```
在上面的程式碼中使用`ll`替代較複雜的宣告方式`long long`但效力是相同的  

進階用法1.(vector 宣告)
```cpp
#include<iostream>
#define
```
