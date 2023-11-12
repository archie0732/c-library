# sort (長篇)

#### 作者: 神里綾華的狗
**題外話**  
建議先學習完以下後再進入  
函式:  
1. [array](https://github.com/archie0732/c-library/blob/main/array/array.md)
2. [vector](https://github.com/archie0732/c-library/blob/main/array/vector/README.md)

與以下演算法:
1. 二元搜尋法 binary sort
2. 泡沫搜尋法 Bubble Sort
3. 快速搜尋法 quick sort
***
* **overview**  
  2023/11/12 剛月中就沒錢了，~~該死的白朮專武~~   
  **sort是一種排序陣列的函式**(可以升列、降列或你喜歡的方式)   
  但老實說sort在現在寫題目基本用不到，因為會打亂`原來`陣列順序  
  不過在某些時後卻有奇效
***
## 基本用法1(升冪排序)
```cpp
sort (begin,end);
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
## 基本用法2(降冪排序)
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
## 排列字串(按照ASCII)
```cpp
sort(begin,end,less<char>());
```
同降冪，在第三個參數加上```less<char>()```  
範例:
排序a[a,c,d,f,b]  
```cpp
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main()
{
    char a[5] = {'a', 'c', 'd', 'f', 'b'};
    sort(a, a + 5, less<char>());

    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
    return 0;
}
```
輸出範例:
```
a b c d f
```

## sort struct
* 建議先學習
  1. [struct]()
  2. [bool](https://www.delftstack.com/zh-tw/howto/cpp/boolean-function-cpp/) 

***

條件:
1. 有 struct
2. 有 bool  回傳降序的方式

```cpp
sort(begin,end,bool 回傳降序的方式)
```

EX: 

```cpp
#include <iostream>
#include <algorithm>
#include <string>

using namespace std;

struct student { //建立struct(name: student)
    string name;
    int score;	
};

bool mycompare(student s1, student s2){ //bool 判斷條件
   return s1.score > s2.score;
}

int main() {
    student st[4]; // 建立資料
    st[0].name = "bob";
    st[0].score = 70;
    st[1].name = "cindy";
    st[1].score = 66;
    st[2].name = "archie";
    st[2].score = 80;
    st[3].name = "alice";
    st[3].score = 76;
    
    sort(st, st+4, mycompare);//排序(依照條件式)

    for (student s : st)  // 用指標輸出
        cout << s.name << " " << s.score << endl;

    return 0;
}
```
範例輸出:
```
archie 80
alice 76
bob 70
cindy 66
```
***
## 其他&補充
1. 排序陣列的某部份
   >例如只想排序陣列的前五項:  
   >```sort(arry,arry+5);```
***
2. 自動找長度
   覺得要算長度很麻煩，可以參考以下:
```cpp
int array[] = {4, 5, 8, 3, 7, 1, 2, 6, 10, 9};
int len = sizeof(array) / sizeof(int);
std::sort(array, array + len);
```
***
3. [X] 冷知識 c++ 的 `sort` 較 c 中的 `qsort` **速度更快**
