# c++ tips

## tips

1. 函数默认参数设置可只在声明时写，函数定义时不用写 

2. typedef 可以定一个类型 

   ```
   Typedef int arr[10]; 
   Arr a; //相当于定义int a[10]; 
   a[0]=0;
   a[9]=9;
   ```
3. 

## 虚函数

假设我们有两个类，一个是Base父类，另一个是Derived子类。



```c++
class Base //父类
{
public:
    int print() ; // 非虚函数
};

int Base::fun()  // virtual 字段不用在函数体时定义
{
    std::cout << "Base::fun()" << std::endl;
}

class Derived: public Base  //子类
{
public:
    int fun();
    int derived_fun();
    int derived_fun_fun();
private:
    int dummy = 1;
};
// 继承父类的函数
int Derived::fun()  {
    std::cout << "Derived::fun()" << std::endl;
}
// 子类独有函数
int Derived::derived_fun() {
    std::cout << "Derived::derived_fun()" << std::endl;
    std::cout << this->dummy << std::endl;
}
// 子类独有函数 且调用父类继承的函数
int Derived::derived_fun_fun() {
    std::cout << "Derived::derived_fun_fun()" << std::endl;
    fun();
}
```



## dynamic_cast

假设我们有两个类，一个是Base父类，另一个是Derived子类。

https://zhuanlan.zhihu.com/p/268427828

```c++
class Base //父类
{
public:
    virtual int fun() ; // 虚函数
};

int Base::fun()  // virtual 字段不用在函数体时定义
{
    std::cout << "Base::fun()" << std::endl;
}

class Derived: public Base  //子类
{
public:
    int fun();
    int derived_fun();
    int derived_fun_fun();
private:
    int dummy = 1;
};
// 继承父类的函数
int Derived::fun()  {
    std::cout << "Derived::fun()" << std::endl;
}
// 子类独有函数
int Derived::derived_fun() {
    std::cout << "Derived::derived_fun()" << std::endl;
    std::cout << this->dummy << std::endl;
}
// 子类独有函数 且调用父类继承的函数
int Derived::derived_fun_fun() {
    std::cout << "Derived::derived_fun_fun()" << std::endl;
    fun();
}
```



## 计算一段程序运行的时间

```
#include <ctime>
using namespace std;
int main()
{
    clock_t startTime, endTime;
    startTime = clock();
    //---------------------计时开始---------------------
    int x = 0;
    for (int i = 0 ; i < 1000000; i++)
    {
        x++;
    }
    //---------------------计时结束---------------------
    endTime = clock();
    cout << "The run time is: " << (double)(endTime-startTime)/CLOCK_PER_SEC << "s" << endl;
}
```

