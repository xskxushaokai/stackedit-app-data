
## sort排序
```sort()```函数是排序函数，基于快速排序原理实现的，是不稳定的排序方法。

需要引用头文件```algorithm```。

```sort()```函数可以对任意数据类型的数组进行排序

格式：```sort（begin，end，cmp）```

```begin```是排序区间的开始指针，```end```是结尾指针，前闭后开(包括前面不包括后面)即 $[begin，end )$。

对于长度为 $n$ 数组```a```，我们要排序 $[0, n)$ 这个区间的数据，应该写成```sort(a，a+n)```。```cmp```可以缺省，默认为**从小到大排序**。

**例：输入一个整数n，接下来输入n个整数，将这n个数从小到大排序。**

分析：尝试用文件读写的方式完成。
```cpp
#include<cstdio>  //用到重定向文件函数
#include<algorithm>  //用到sort函数
#include<iostream>
using namespace std;

int main(){
  freopen("data.in","r",stdin);
  freopen("data.out","w",stdout);

  int n;
  cin>>n;
  int a[n];

  for(int i=0;i<n;i++)
    cin>>a[i];

  sort(a, a+n);

  for(int i=0;i<n;i++)
    cout<<a[i]<<" ";

  return 0;

}

```
sort函数默认是从小到大排序的，而且排序的类型必须支持操作符```<>```，比如整型、字符型、字符串型。

**想要从大到小排序怎么办呢？**

---

### 比较函数
```cpp
bool cmp(int a, int b){
  函数体;
}
```
1.函数的返回必须是bool型。

2.函数名```cmp```, 函数名可以自定义，符合C++命名规范即可。

3.形式参数，参数固定为两个，表示排序过程中遇到需要比较的两个数值。必须是待排序数组元素的类型。

4.函数体的返回值一般以表达式的方式返回。例如```return a>b;```（意思是说如果$a>b$就不交换，$a<b$交换，按从大到小排序）。想要按从大到小的顺序排序就```return a>b;```，想要按从小到大的顺序排序就```return a<b;```。

**例：** 输入一个整数 $n$，接下来输入 $n$ 个整数，将这 $n$ 个数从大到小排序。
分析：只需要将上题中的```sort(a, a+n)```改成```sort(a, a+n, cmp)```；增加一个```cmp```函数即可。
```cpp
bool cmp(int a, int b)
  {return a>b;}
```
自行尝试一下，不再赘述。

---

### 结构体排序

我们常常不仅对一个特征进行排序，而是对多个。例如学生的成绩进行排序，成绩相同时按姓名排序。这时就需要用到结构体排序。```sort```函数默认结构体中的第一个成员为第一关键字，第二成员为第二关键字。然后按从小到大的顺序排序。当我们无法采用默认规则进行排序的时候，就要自定义比较函数了。

**例题**：$n$个同学，按成绩从大到小排序，如果成绩相同就按姓名字典序排序

```cpp
struct stu{
  string name;
  int score;
}

bool cmp(stu a, stu b){
  if(a.score!=b.score)
    return a.score>b.score;
  return a.name<b.name;
}

int main(){
  int n;
  cin>>n;
  stu a[n];
  for(int i=0;i<n;i++)
    cin>>a[i].name>>a[i].score

  sort(a, a+n, cmp);

  for(int i=0;i<n;i++)
    cout<<a[i].name<<" "<<a[i].score<<endl;

  return 0;
}
```
程序说明：定义一个结构体```stu```，有两个成员变量```name```和```score```。```cmp```函数就是我们自定义的排序规则，当分数不同的时候按分数从大到小排序，当分数相同的时候按姓名从小到大排序。注意参数```a```，```b```为```stu```类型，才能对结构体```stu```排序。

**练习**：奖学金
问题描述：期末，每个学生都有3门课的成绩：语文、数学、英语。先按总分从高到低排序，如果两个同学总分相同，再按语文成绩从高到低排序，如果两个同学总分和语文成绩都相同，那么规定学号小的同学排在前面。

输入：第一行，一个整数$n$，表示学生数量 $6≤n≤300$, 
	  接下来的n行，每行3个整数，表示学号为i的学生语文、数学、英语成绩。

输出：5 行，每行两个正整数，依次表示前 5 名学生的学号和总成绩

分析：声明一个结构体，成员变量包括学号、语文成绩、数学成绩、英语成绩和总成绩。输入数据时把学号和总成绩也一并填入。用```sort```排序结构体，```cmp```函数按总分、语文成绩和学号的顺序依次比较。

**核心代码**
```cpp
#include<algorithm>  //用到sort函数
#include<iostream>
using namespace std;

struct stu{
  int xh, yw, sx, yy, total;
}

bool cmp(stu a, stu b){
  if(a.total!=b.total)
    return a.total>b.total;
  else{
    if(a.yw!=b.yw) return a.yw>b.yw;
    else return a.xh<b.xh;
  }
}

int main(){
  int n;
  cin>>n;
  stu a[n];
  for(int i=0;i<n;i++){
    a[i].xh=i;
    cin>>a[i].yw>>a[i].sx>>a[i].yy;
    a[i].total = a[i].yw+a[i].sx+a[i].yy;
  }

  sort(a, a+n, cmp);
  for(int i=0;i<n;i++){
    cout << a[i].xh << " " << a[i].total << endl;
  }

return 0;
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIyOTQ4ODAzN119
-->