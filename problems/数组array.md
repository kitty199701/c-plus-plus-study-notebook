# string

## char和int类型转换为string类型

### 把char转换为string的最简单方法

新建一个string对象，该初始化将n个char c 拷贝到string s中。下面我们只拷贝1个char c。

```c++
char c = 'a';
string s(1, c);
```
最后结果s = "a"

### 把int, long long, double转换为string

**c++11标准增加了全局函数std::to_string:**

string to_string (int val);

string to_string (long val);

string to_string (long long val);

string to_string (unsigned val);

string to_string (unsigned long val);

string to_string (unsigned long long val);

string to_string (float val);

string to_string (double val);

string to_string (long double val);

```c++
int i = 10224;
string s = to_string(i); // i为int类型
```

最后结果s = "10224"



如果要把ascii码i转换成string，用上面把char转换为string的办法

```c++
int i = 3;
string s(1, 'a'+i); 
```
最后结果s="d"

