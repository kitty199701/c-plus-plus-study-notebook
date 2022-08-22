# 顺序容器适配器（stack,queue,priority_queue）

## 通用操作

- 初始化：`A a;`
- `A a(c);` c为一个顺序容器
- `a.empty()`
- `a.size()`
- `swap(a,b)`
- 关系运算符`==, !=, <, >, >=, <=`





# queue

- `que.front()`返回queue的首元素，但不删除此元素

- `que.pop()`删除queue的首元素，但返回void

所以**在queue中取值加删除得两步**

  ```
  TreeNode* node = que.front();
  que.pop();
  ```

- `que.push(item)` 在queue的末尾添加一个元素
- `que.back()`返回queue的尾元素，但不删除此元素