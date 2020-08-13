## 递归回溯

教程:  [[递归与回溯的理解]](https://cloud.tencent.com/developer/article/1434886)  [[手把手教怎么写递归和回溯]](https://leetcode-cn.com/circle/article/GV6eQ2/)   

递归回溯一般模板：
```cpp
'''
backtracking使用dfs的模板，基本跟dfs的模板一模一样
'''
class Backtracking(object):

    def backtracking(self, input):

        self.res = []

        def dfs(input, temp, [index]):
            # 边界
            if 非法数据：
                return

            # 终止条件
            if len(input) == len(temp)：
                self.res.append(temp[:])
                return

            # for循环
            for i range(len(input)):
                ##1. 修改path
                temp.append(input[i])
                ##2. backtracking
                dfs(input, temp, [index])
                ##3. 退回原来状态，恢复path
                temp.pop()
        # 执行
        dfs(input, [], 0)
        return self.res
```

- [ ] (中等)Leetcode 17 电话号码的字母组合[[problem]](https://leetcode-cn.com/problems/letter-combinations-of-a-phone-number/)

- [ ] (中等)Leetcode 22 括号生成[[problem]](https://leetcode-cn.com/problems/generate-parentheses/)

- [ ] (中等)Leetcode 46 全排列[[problem]](https://leetcode-cn.com/problems/permutations/)

- [ ] (中等)Leetcode 47 全排列II[[problem]](https://leetcode-cn.com/problems/permutations-ii/) 
