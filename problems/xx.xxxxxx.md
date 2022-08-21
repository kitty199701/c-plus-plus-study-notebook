# xx. xxxxxx

## 题目

leetcode链接：

## 参考思路 - 



- 时间复杂度：O(n)
- 空间复杂度：O(1)

## 参考代码

```c++

```



## 我的思路 - 



- 时间复杂度：O(n)
- 空间复杂度：O(1)

## 我的代码

```
class Solution {
public:
    int jump(vector<int>& nums) {
        int cover = 0;
        int singleCover = 0;
        int step = 0;
        int curPos=0;
        if (nums.size() == 1) return 0;
        for (int i = 0; i <= cover; i++)
        {
            cover = max(i+nums[i],cover);
            if(i==curPos ||  cover>=nums.size()-1)
            {
                curPos = cover;
                step++;
            }
            if(cover>=nums.size()-1)  return step;
        }
        return step;
    }
};
```

