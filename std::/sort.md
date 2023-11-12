# sort
**題外話**  
建議先學習完以下後再進入  
函式:  
1. [arry](https://github.com/archie0732/c-library/blob/main/array/array.md)
2. [vector](https://github.com/archie0732/c-library/blob/main/array/vector/README.md)

與以下演算法:
1. 二元搜尋法 binary sort
2. 泡沫搜尋法 Bubble Sort
3. 快速搜尋法 quick sort

***
## 用法1(升冪排序)
```cpp
sort (arry.begin,arry.end);
```
需要包含以下標頭檔
```cpp
#include<iostream>
```
與using namespace 
```cpp
using namespace std;
```
* 範例:  
將陣列a[10]={10, 9, 8, 7, 6, 5, 3, 1, 2,0}按順序`由小至大`排序
```cpp
#include <iostream>
#include <algorithm>

using namespace std;

int main()
{
    int a[10] = {10, 9, 8, 7, 6, 5, 3, 1, 2,0};
    sort(a, a + 10);

    for (int i = 0; i < 10; i++)
        cout << a[i] << " ";
    return 0;
}
```
輸出結果:
```
0 1 2 3 5 6 7 8 9 10
```
***
## 用法2(降冪排序)
```cpp
sort(begin, end, greater<Type>());
```
跟**升冪**一樣，只是最後再加上```greater<資料型態>()```  
範例:
將陣列a[10]={10, 9, 8, 7, 6, 5, 3, 1, 2,0}按順序`由大至小`排序  
```cpp
#include <iostream>
#include <algorithm>

using namespace std;

int main()
{
    int a[10] = {10, 9, 8, 7, 6, 5, 3, 1, 2,0};
    sort(a, a + 10, greater<int>());//陣列是以int 宣告，故用<int>

    for (int i = 0; i < 10; i++)
        cout << a[i] << " ";
    return 0;
}
```
輸出結果
```
10 9 8 7 6 5 3 2 1 0
```

***

# sort vector
```cpp
sort(v.begin(), v.end());
```
將arry的尾數改成**vector**的end即可  
跟上面一樣的範例:
```cpp
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main()
{
    vector<int> v = {10, 9, 8, 7, 6, 5, 3, 1, 2, 0};
    sort(v.begin(), v.end());

    for (int i = 0; i < 10; i++)
        cout << v[i] << " ";
    return 0;
}
```
輸出結果:
```
0 1 2 3 5 6 7 8 9 10
```
