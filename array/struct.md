# struct (長篇)

#### 神里綾華的狗
***

* **overview**  
  ~~作者還在睡(混)~~  

***
## struct 初始化
如以下(**位置在主程式之上**):
想要在這存下兩種資料結構  
```cpp
struct struct名稱 {
  資料結構1  變數名稱;
  資料結構2  變數名稱;
};
```
理論上`資料結構`是可以1 個至數個  
***
EX:
```cpp
#include <iostream>

using namespace std;

struct student
{
    int age;
    int score;
    bool gender;
    char name[30];
};
```
## 基本使用
1. 宣告要放入值之容器
```cpp
    struct struct名稱 放入之容器名稱 ;


EX: struct student  s1 ;//s1才是"儲存資料"之容器名稱(不要搞混)
```
***
2. 將值放入容器:
```cpp
     容器名稱.資料結構1 = 值1 ;
     容器名稱.資料結構2 = 值2 ;


EX:　s1.age = 20;//不是 student.age　!!
```
***
3. 須注意要在struct 中放入資料結構`char`請使用`strcpy`

`strcpy`**須包含標頭檔`<string.h>`**  
```cpp
strcpy(容器名稱.資料結構 , "放入字串");
```
***

將上述組合
EX:
```cpp
#include <iostream>
#include <string.h>
#include <stdio.h>

using namespace std;

struct student
{
    int age;
    int score;
    bool gender;
    char name[30];
};

int main()
{
    struct student s1;
    s1.age = 19;
    s1.score = 80;
    s1.gender = 1;
    strcpy(s1.name, "Tom");

    struct student s2;
    s2.age = 18;
    s2.score = 60;
    s2.gender = 0;
    strcpy(s2.name, "lily");

    cout << "name:" << s1.name << " score:" << s1.score << " age:" << s1.age << endl;
    cout << "name:" << s2.name << " score:" << s2.score << " age:" << s2.age << endl;

    return 0;
}
```
輸出結果:
```
name:Tom score:80 age:19
name:lily score:60 age:18
```
