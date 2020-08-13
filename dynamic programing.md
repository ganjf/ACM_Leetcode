## 动态规划 DP
ref:  
- 夜深人静写算法——动态规划 [[blog]](http://www.cppblog.com/menjitianya/archive/2015/10/23/212084.html)   

### 一、动态规划初探
#### 1、递推   

- [ ] 最长回文子串 [[problem]](https://leetcode-cn.com/problems/longest-palindromic-substring/)  

- [ ] 62.不同路径 [[problem]](https://leetcode-cn.com/problems/unique-paths/)  

- [ ] 63.不同路径 II [[problem]](https://leetcode-cn.com/problems/unique-paths-ii/)  


#### 2、记忆化搜索   
递推说白了就是在知道前i-1项的值的前提下，计算第i项的值，而记忆化搜索则是另外一种思路。它是直接计算第i项，需要用到第 j 项的值( j < i)时去查表，如果表里已经有第 j 项的话，则直接取出来用，否则递归计算第 j 项，并且在计算完毕后把值记录在表中。记忆化搜索在求解多维的情况下比递推更加方便。  

- [ ] 扰乱字符串 [[problem]](https://leetcode-cn.com/problems/scramble-string/)     



- [ ] Function Run Fun  [[problem]](http://poj.org/problem?id=1579)                              ★☆☆☆☆          【例题3】

- [ ] FatMouse and Cheese  [[problem]](http://acm.hdu.edu.cn/showproblem.php?pid=1078)                            ★☆☆☆☆          经典迷宫问题

- [ ] Cheapest Palindrome  [[problem]](http://poj.org/problem?id=3280)                           ★★☆☆☆ 

- [ ] A Mini Locomotive    [[problem]](http://poj.org/problem?id=1976)                           ★★☆☆☆

- [ ] Millenium Leapcow    [[problem]](http://poj.org/problem?id=2111)                           ★★☆☆☆

- [ ] Brackets Sequence   [[problem]](http://poj.org/problem?id=1141)                            ★★★☆☆          经典记忆化

- [ ] Chessboard Cutting  [[problem]](http://poj.org/problem?id=1191)                            ★★★☆☆          《算法艺术和信息学竞赛》例题

- [ ] Number Cutting Game  [[problem]](http://acm.hdu.edu.cn/showproblem.php?pid=2848)                         ★★★☆☆

#### 4、最优化原理和最优子结构
#### 5、决策和无后效性

### 二、动态规划的经典模型
#### 1、线性模型
#### 3、状态和状态转移  
#### 4、最优化原理和最优子结构   
#### 5、决策和无后效性   

### 二、动态规划的经典模型
#### 1、线性模型   
- [ ] 最大矩形 [[problem]](https://leetcode-cn.com/problems/maximal-rectangle/)  [[直方图O(N\*N\*M]]  [[DP O(N\*M)]]  

- [x] 解码方法 [[problem]](https://leetcode-cn.com/problems/decode-ways/)

#### 2、区间模型

- [x] 编辑距离  [[problem]](https://leetcode-cn.com/problems/edit-distance/)    

#### 3、背包模型

- 01背包模型

  - [x] [分割等和子集](https://leetcode-cn.com/problems/partition-equal-subset-sum/)

  - [x] [一和零](https://leetcode-cn.com/problems/ones-and-zeroes/)
  - [x] [目标和](https://leetcode-cn.com/problems/target-sum/)

- 完全背包模型
  - [x] [零钱兑换](https://leetcode-cn.com/problems/coin-change/)
  - [x] [零钱兑换II](https://leetcode-cn.com/problems/coin-change/)

#### 4. 状态压缩模型

- 一般处理的是数据规模较小的问题，将状态压缩成k进制的整数，k取2时最常见

#### 5、树状模型

### 三、动态规划的常用状态转移方程
#### 1、1D/1D
#### 2、2D/0D
#### 3、2D/1D
#### 4、2D/2D

### 四、动态规划和数据结构结合的常用优化
#### 1、滚动数组
#### 2、最长单调子序列的二分优化
#### 3、矩阵优化
#### 4、斜率优化
#### 5、树状数组优化
#### 6、线段树优化
#### 7、其他优化

### 五、动态规划题集整理