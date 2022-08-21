# hash表

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



## unordered_map

### 定义

```
unordered_map<char, int> umap;
```

- `umap.begin()`
- `umap.end()`
- `umap.size()`
- 

### 遍历

可直接用for循环遍历

```
for(int i = 0; i < umap.size(); i++)  cout<<umap[i]<<endl;
```

也可用迭代器遍历(代码不太对，待调整)

```
for(auto i = umap.begin(); i!=umap.end(); i++)  cout<<i.first<<i.second<<endl;
```

- 
