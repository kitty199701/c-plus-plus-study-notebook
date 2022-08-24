# hash表

**当我们遇到了要快速判断一个元素是否出现集合里的时候，就要考虑哈希法了。**

三种实现方法：

- unordered_set
- unordered_map
- 数组

只需要知道这个key是否出现时用unordered_set

需要知道这个key出现了多少次，即value为多少时，用unordered_map

以上两种情况在明确知道key有多少个，并且个数不多时用数组，因为**set和map不仅占用空间比数组大，而且速度要比数组慢**，set和map把数值映射到key上都要做hash计算的。不要小瞧这个耗时，在数据量大的情况，差距是很明显的。



## unordered_set

- 初始化1（空）：`unorder_set<string> uset;`

- 初始化2（直接赋值）：`unorder_set<string> uset={"one","two","three"};`

- 初始化3（用vector数组或普通数组赋值）：`unorder_set<string> uset(vec.begin(), vec.end());//vec为一个vector数组`

  `unorder_set<string> uset(array, array+sizeof(array)/sizeof(array[0]));//array为一个int或string或char数组`

- 初始化4（复制）：`unorder_set<string> usetCopy(uset);`

- `uset.insert(value)`将value插入到set中

- `uset.find(value)`返回value在set中的位置，如果返回值为uset.end()，说明没找到

- `uset.count(key)`返回key在set中的个数，因为是集合，所以只会返回0或者1

- `uset.clear()`

- `uset.begin()`

- `uset.end()`

- `uset.erase(key)`

- `uset.size()`

- `uset.empty()`

- 将set转换为vector：`vector<int>(result_set.begin(), result_set.end());`



## unordered_map

### 定义

```c++
unordered_map<char, int> umap;
```

- `umap.begin()`

- `umap.end()`

- `umap.size()`

- `umap.insert(pair<int, int>(a, b));` 

- `aotu iter = umap.find(value)`返回value在map中的位置，位置是一个迭代器，如果返回值为`umap.end()`，说明没找到

  找到之后可以使用iter->second

- 
# unordered_map排序

**必须转换成vector，才可以用sort函数排序。**

```
bool mycmp(const pair<string, int>& a, const pair<string, int>& b)
{
    if(a.second != b.second)  return a.second < b.second;
    return a.first<b.first;
}

vector<pair<char, int>> vec(umap.begin(), umap.end());//unordered_map转换为vector
sort(vec.begin(), vec.end(), mycmp);
```



### 遍历

可直接用for循环遍历，但只能输出value值

```c++
for(int i = 0; i < umap.size(); i++)  cout<<umap[i]<<endl;
```

也可用迭代器遍历，可以输出key和value

```c++
for(auto i = umap.begin(); i!=umap.end(); i++)  cout<<i->first<<i->second<<endl;
for(unordered_map<char, int>::iterator i = umap.begin(); i!=umap.end(); i++)  cout<<i->first<<i->second<<endl;
```

