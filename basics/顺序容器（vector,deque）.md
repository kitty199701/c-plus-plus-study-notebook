# 顺序容器（vector,deque）

如果要return vector 可以这样写：

`return {1,2,3};`

`return {};`



## deque - 双端队列（two-ended queue）

```
deque<int> dq;
dq.push_back();//压入尾元素
dq.push_front();//压入首元素
dq.back();//返回尾元素
dq.front();//返回首元素
dq.pop_back();//删除尾元素，返回void
dq.pop_front();//删除首元素，返回void
```

