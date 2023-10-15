# vector 

**作者:綾華的狗**  


*請先學會array後再進入此文*  
~~用過vector後就會覺得array難用死了~~
## vector 的好處
* [x] 用法與array差不多
* [X] 能隨意增加、縮短陣列長度
* [X] 能在一個陣列中包含各種屬性的值(int,string)
### 初始化
1. 須包含`include<vector>`標頭檔或`std::vector`
```cpp
#include<vector>
int main(){
  vector<int>v //建立一個名為v的陣列(裝著`整數`值)
  return 0;
}
```
```vector<int>```裡的值<int>帶表裡面裝的是整數(int)。也能改成string、char、pair等  
**也能像陣列一樣**`vector v(n)={1,2,3}` 
**須注意!!**
```cpp
#include<vector>
using namespace std;
int main(){
  int n;
  std::cin>>n;
  int array[n]={1,2,3};//在vscode裡會報錯
  vector <int>v(n)={1,2.3};//與array不同，是用()來宣告容器大小。不會像array一樣報錯
  return 0;
}
```


## 輸入
**在vector `v`中放入值1**  
1. 最基本的輸入`v[0]=1;`
2. `v.push_back(1);`把值放入最後面

**cin進入v**  
* `cin>>v[0];`
* 跟一般的陣列差不多只是多了很多新功能

## 刪除值
1.`v.pop_back();`直接刪除在最後面的值
可以做以下測試:
```cpp
#include<vector>
using namespace std;
int main(){
  int a;
  cin>>a;
  vector <int>v({1,2.3});//結果同上面的一樣{1,2,3}
  v.push_back(a);//v={1,2,3,a}
  v.push_back(1);//v={1,2,3,a,1}

  v.pop_back();//刪除最後面的(1)==>v={1,2,3,a}
  cout<<v[0]<<endl;//print 1;
  cout<<v[3]<<endl;//print a;
  return 0;
}
```
```
輸出結果:
 1
 a
```
## 插入值
**版主尚未撰寫**
## 用for迴圈輸入所有值
```cpp
#include<vector>
using namespace std;
int main(){
  int a;
  cin>>a;
  vector <int>v({1,2.3});//結果同上面的一樣{1,2,3}
  v.push_back(a);//v={1,2,3,a}
  v.push_back(1);//v={1,2,3,a,1}

  v.pop_back();//刪除最後面的(1)==>v={1,2,3,a}
  for(int i=0;i<v.size();i++){
    cout<<v[i]<<" ";//print 1 2 3 a
 }
}
```
```
輸出結果:
1 2 3 a
```
## 使用auto來更快印出所有值

**版主尚未撰寫**  
## 關於vector pair
**版主尚未撰寫**
