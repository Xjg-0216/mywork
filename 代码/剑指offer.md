### 剑指offer

#### 1、数组中重复的数字

[剑指 Offer 03. 数组中重复的数字 - 力扣（LeetCode）](https://leetcode.cn/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/?favorite=xb9nqhhg)

找出数组中重复的数字。

在一个长度为` n `的数组 `nums `里的所有数字都在 `0～n-1` 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。

```python
class Solution:
    def findRepeatNumber(self, nums):
        dict = collections.defaultdict(int)
        for i in nums:
            if dict[i]:
                return i
            dict[i] += 1
```

#### 2、二维数组中的查找

[剑指 Offer 04. 二维数组中的查找 - 力扣（LeetCode）](https://leetcode.cn/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/?favorite=xb9nqhhg)

在一个` n * m `的二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个高效的函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

```python
class Solution:
    def findNumberIn2DArray(self, matrix, target):
        for m in range(len(matrix)):
            if self.erfen(matrix[m], target):
                return True
        return False
    def erfen(self, nums, target):
        n = len(nums)
        left, right = 0, n - 1
        while left <= right:
            mid = left + (right - left) // 2
            if nums[mid] < target:
                left = mid + 1
            elif nums[mid] > target:
                right = mid - 1
            else:
                return True
        return False  
```

#### 3、替换空格

[剑指 Offer 05. 替换空格 - 力扣（LeetCode）](https://leetcode.cn/problems/ti-huan-kong-ge-lcof/?favorite=xb9nqhhg)

请实现一个函数，把字符串 `s` 中的每个空格替换成"%20"。

```python
class SOluiton:
    def replaceSpace(self, s):
        s = list(s)
        for i in range(len(s)-1, -1, -1):
            if s[i] == " ":
                s[i] = "%20"
        return ''.join(s)
```

#### 4、从尾到头打印链表

[剑指 Offer 06. 从尾到头打印链表 - 力扣（LeetCode）](https://leetcode.cn/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/?favorite=xb9nqhhg)

输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。

```python
class Solution:
    def reversePrint(self, head):
        result = []
        while head:
            result.insert(0, head.val)
            head = head.next
        return result
```

#### 5、重建二叉树

[剑指 Offer 07. 重建二叉树 - 力扣（LeetCode）](https://leetcode.cn/problems/zhong-jian-er-cha-shu-lcof/)

输入某二叉树的前序遍历和中序遍历的结果，请构建该二叉树并返回其根节点。

假设输入的前序遍历和中序遍历的结果中都不含重复的数字。

```python
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None
class SOlution:
    def buildTree(self, preorder, inorder):
        if not preprder:
            return None
        mid = preorder[0]
        inorder_index = inorder.index(mid)
        left_inorder = inorder[:inorder_index]
        right_inorder = inorder[inorder_index+1:]
        left_preorder = preorder[1:len(left_inorder)+1]
        right_preorder = preorder[len(left_inorder)+1:]
        root = TreeNode(mid)
        root.left = self.buildTree(left_preorder, left_inorder)
        root.right = self.buildTree(right_preorder, right_inorder)
        return root
```

#### 6、用两个栈实现队列

[剑指 Offer 09. 用两个栈实现队列 - 力扣（LeetCode）](https://leetcode.cn/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/?favorite=xb9nqhhg)

用两个栈实现一个队列。队列的声明如下，请实现它的两个函数`appendTail` 和 `deleteHead` ，分别完成在队列尾部插入整数和在队列头部删除整数的功能。(若队列中没有元素，`deleteHead` 操作返回 -1 )

```python
class CQueue:
    def __init__(self):
        self.stack1 = []
        self.stack2 = []
    def appendTail(self, value):
        self.stack1.append(value)
    def deletedHead(self):
        if self.stack2:
            return self.stack2.pop()
        elif not self.stack1:
            return -1
        else:
            while self.stack2:
                self.stack2.append(self.stack1.pop())
            return self.stack2.pop()
```

#### 7、[斐波那契数列](https://leetcode.cn/problems/fei-bo-na-qi-shu-lie-lcof/)

写一个函数，输入 `n` ，求斐波那契（Fibonacci）数列的第 `n` 项（即 `F(N)`）。斐波那契数列的定义如下：

```
F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), 其中 N > 1.
```

斐波那契数列由 0 和 1 开始，之后的斐波那契数就是由之前的两数相加而得出。

答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。

```python
class SOlution:
    def fib(self, n):
        if n < 2:
            return n 
        dp = [0] * (n + 1)
        dp[1] = 1
        for i in range(2, n+1):
            dp[i] = dp[i-1] + dp[i-2]
        return dp[n] % 1000000007
```

#### 8、青蛙跳台阶问题

[剑指 Offer 10- II. 青蛙跳台阶问题 - 力扣（LeetCode）](https://leetcode.cn/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/?favorite=xb9nqhhg)

一只青蛙一次可以跳上1级台阶，也可以跳上2级台阶。求该青蛙跳上一个`n` 级的台阶总共有多少种跳法。

答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。

```python
class Solution:
    def numWays(self, n):
        if n < 1:
            return 1
        dp = [0]  * (n + 1)
        dp[0] = dp[1] = 1
        for i in range(2, n+1):
            dp[i] = dp[i-1] +dp[i-2]
        return dp[n] % 1000000007
```

#### 9、旋转数组的最小数字

[剑指 Offer 11. 旋转数组的最小数字 - 力扣（LeetCode）](https://leetcode.cn/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/?favorite=xb9nqhhg)

把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。给你一个可能存在 **重复** 元素值的数组 `numbers` ，它原来是一个升序排列的数组，并按上述情形进行了一次旋转。请返回旋转数组的**最小元素**。例如，数组 `[3,4,5,1,2]` 为 `[1,2,3,4,5]` 的一次旋转，该数组的最小值为 1。 

注意，数组 `[a[0], a[1], a[2], ..., a[n-1]]` 旋转一次 的结果为数组`[a[n-1], a[0], a[1], a[2], ..., a[n-2]]` 。

```python
class Solution:
    def minArray(self, numbers):
        for i in range(1, len(numbers)):
            if numbers[i] < numbers[i-1]:
                return numbers[i]
        return numbers[0]
```

#### 10、矩阵中的路径

[剑指 Offer 12. 矩阵中的路径 - 力扣（LeetCode）](https://leetcode.cn/problems/ju-zhen-zhong-de-lu-jing-lcof/?favorite=xb9nqhhg)

给定一个 `m x n` 二维字符网格 `board` 和一个字符串单词 `word` 。如果 `word` 存在于网格中，返回 `true` ；否则，返回 `false` 。

单词必须按照字母顺序，通过相邻的单元格内的字母构成，其中“相邻”单元格是那些水平相邻或垂直相邻的单元格。同一个单元格内的字母不允许被重复使用。

例如，在下面的 3×4 的矩阵中包含单词 "ABCCED"（单词中的字母已标出）。

```python
class Solution:
    def exist(self, board, word):
        def dfs(i, j, k):
            if not 0 <= i < len(borad) or not 0 <= j < len(board[0]) or board[i][j] != word[k]:
                return False
            if k == len(word)-1:
                return True
            board[i][j] = ' '
            res = dfs(i+1, j, k+1) or dfs(i-1, j, k+1) or dfs(i, j+1, k+1) or dfs(i, j-1, k+1)
            board[i][j] = word[k]
            return res
        for i in range(len(board)):
            for j in range(len(board[0])):
                if dfs(i, j, 0):
                    return True
        return False
```

#### 11、剪绳子

[剑指 Offer 14- I. 剪绳子 - 力扣（LeetCode）](https://leetcode.cn/problems/jian-sheng-zi-lcof/?favorite=xb9nqhhg)

给你一根长度为 `n` 的绳子，请把绳子剪成整数长度的 `m` 段（m、n都是整数，n>1并且m>1），每段绳子的长度记为 `k[0],k[1]...k[m-1]` 。请问`k[0]*k[1]*...*k[m-1]` 可能的最大乘积是多少？例如，当绳子的长度是`8`时，我们把它剪成长度分别为`2、3、3`的三段，此时得到的最大乘积是`18`。

```python
class Solution:
    def cuttingRope(self, n):
        if n > 2:
            return 0
        dp = [0] * (n + 1)
        dp[2] = 1
        for i in range(3, n + 1):
            for j in range(1, i):
                dp[i] = max(dp[i], max(j * (i - j), j * dp[i - j]))
        return dp[n]
```

####  12、剪绳子II

[剑指 Offer 14- II. 剪绳子 II - 力扣（LeetCode）](https://leetcode.cn/problems/jian-sheng-zi-ii-lcof/?favorite=xb9nqhhg)

给你一根长度为 `n` 的绳子，请把绳子剪成整数长度的 `m` 段（m、n都是整数，n>1并且m>1），每段绳子的长度记为 `k[0],k[1]...k[m - 1]` 。请问 `k[0]*k[1]*...*k[m - 1]` 可能的最大乘积是多少？例如，当绳子的长度是8时，我们把它剪成长度分别为2、3、3的三段，此时得到的最大乘积是18。

答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。

```python
class Solution:
    def cuttingRope(self, n):
        if n < 2:
            return 0
        dp = [0] * (n + 1)
        dp[2] = 1
        for i in range(3, n+1):
            for j in range(1, i):
                dp[i] = max(dp[i], max(j * (i - j), j * dp[i - j]))
        return dp[n] % 1000000007
```

#### 13、二进制中1的个数

[剑指 Offer 15. 二进制中1的个数 - 力扣（LeetCode）](https://leetcode.cn/problems/er-jin-zhi-zhong-1de-ge-shu-lcof/)

python中的位运算

| 名称     | 符号 |
| -------- | ---- |
| 按位与   | &    |
| 按位或   | \|   |
| 按位异或 | ^    |
| 按位取反 | ~    |
| 左移运算 | <<   |
| 右移运算 | >>   |

**左移运算**
$$
x << n = x \times 2^n
$$
**右移运算**
$$
x >> n = x / 2^n
$$

```python
class Solution:
    def hammingWeight(self, n):
        result = 0
        while n:
            result += n & 1
            n = n >> 1
        return result
```

#### 14、数值的整数次方

[剑指 Offer 16. 数值的整数次方 - 力扣（LeetCode）](https://leetcode.cn/problems/shu-zhi-de-zheng-shu-ci-fang-lcof/?favorite=xb9nqhhg)

实现 [pow(*x*, *n*)](https://www.cplusplus.com/reference/valarray/pow/) ，即计算 x 的 n 次幂函数（即，xn）。不得使用库函数，同时不需要考虑大数问题。

```python
class Solution:
    def myPow(self, x, n):
        result = 1
        if n == 0:
            return 1
        elif n > 0:
            while n:
                result = x * result
                n -= 1
            return result
        else:
            n = abs(n)
            while n:
                result = 1 / x * result
                n -= 1
            return result
```



#### 15、打印从1 到最大的n位数

[剑指 Offer 17. 打印从1到最大的n位数 - 力扣（LeetCode）](https://leetcode.cn/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/?favorite=xb9nqhhg)

输入数字 `n`，按顺序打印出从 1 到最大的 n 位十进制数。比如输入 3，则打印出 1、2、3 一直到最大的 3 位数 999。

```python
class Solution:
    def printNumber(self, n):
        result = []
        num = 10 ** n
        for i in range(1, num):
            result.append(i)
        return result  
```

#### 16、删除链表的节点

[剑指 Offer 18. 删除链表的节点 - 力扣（LeetCode）](https://leetcode.cn/problems/shan-chu-lian-biao-de-jie-dian-lcof/?favorite=xb9nqhhg)

给定单向链表的头指针和一个要删除的节点的值，定义一个函数删除该节点。

返回删除后的链表的头节点。

```python
class Solution:
    def deleteNode(self, head, val):
        dummy = ListNode(0)
        dummy.next = head
        pre = dummy
        cur = head
        while cur:
            if cur.val == val:
                pre.next = cur.next
            pre = cur
            cur = cur.next
        return dummy.next
```

#### 