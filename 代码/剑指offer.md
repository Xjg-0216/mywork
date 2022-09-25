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

#### 17、调整数组顺序使奇数位于偶数前面

[剑指 Offer 21. 调整数组顺序使奇数位于偶数前面 - 力扣（LeetCode）](https://leetcode.cn/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)

```python
class Solution:
    def exchange(self, nums):
        left = []
        right = []
        for i in range(len(nums)):
            if nums[i] % 2 != 0:
                left.append(nums[i])
            else:
                right.append(nums[i])
        return left + right
```

#### 18、 链表中倒数第K个节点

[剑指 Offer 22. 链表中倒数第k个节点 - 力扣（LeetCode）](https://leetcode.cn/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/?favorite=xb9nqhhg)

输入一个链表，输出该链表中倒数第k个节点。为了符合大多数人的习惯，本题从1开始计数，即链表的尾节点是倒数第1个节点。

```python
class Solution:
    def getKthFromEnd(self, head, k):
        fast, slow = head, head
        while k:
            fast = fast.next
            k -= 1
        while fast:
            fast = fast.next
            slow = slow.next
        return slow
```

#### 19、反转链表

[剑指 Offer 24. 反转链表 - 力扣（LeetCode）](https://leetcode.cn/problems/fan-zhuan-lian-biao-lcof/)

定义一个函数，输入一个链表的头节点，反转该链表并输出反转后链表的头节点。

```python
class Solution:
    def reverseList(self, head):
        pre = None
        cur = head
        while cur:
            post = cur.next
            cur.next = pre
            pre = cur
            cur = post
        return pre
```

#### 20、合并两个排序的链表

[剑指 Offer 25. 合并两个排序的链表 - 力扣（LeetCode）](https://leetcode.cn/problems/he-bing-liang-ge-pai-xu-de-lian-biao-lcof/?favorite=xb9nqhhg)

输入两个递增排序的链表，合并这两个链表并使新链表中的节点仍然是递增排序的。

```python
class Solution:
    def mergeTwoLists(self, l1, l2):
        dummy = ListNode(0)
        cur = dummy
        while l1 and l2:
            if l1.val < l2.val:
                cur.next = ListNode(l1.val)
                l1 = l1.next
            else:
                cur.next = ListNode(l2.val)
                l2 = l2.next
            cur = cur.next
        if not l1 and l2:
            cur.next = l2
        elif not l2 and l1:
            cur.next = l1
        return dummy.next
```

#### 21、树的子结构

[剑指 Offer 26. 树的子结构 - 力扣（LeetCode）](https://leetcode.cn/problems/shu-de-zi-jie-gou-lcof/?favorite=xb9nqhhg)

输入两棵二叉树A和B，判断B是不是A的子结构。(约定空树不是任意一个树的子结构)

B是A的子结构， 即 A中有出现和B相同的结构和节点值。

```python
class Solution:
    def isSubStructure(self, A, B):
        if not A or not B:
            return False
        que = collections.deque()
        que.append(A)
        while que:
            size = len(que)
            for _ in range(size):
                node = que.popleft()
                if self.recur(node, B):
                    return True
                if node.left:
                    que.append(node.left)
                if node.right:
                    que.append(node.right)
         return False
     def recur(self, A, B):
            if not B:
                return True
            if not A:
                return False
            if A.val == B.val:
                return self.recur(A.left, B.left) and self.recur(A.right, B.right)
            else:
                return False
```

#### 22、二叉树的镜像

[剑指 Offer 27. 二叉树的镜像 - 力扣（LeetCode）](https://leetcode.cn/problems/er-cha-shu-de-jing-xiang-lcof/)

请完成一个函数，输入一个二叉树，该函数输出它的镜像。

```python
class Solution:
    def mirrorTree(self, root):
        if not root:
            return root
        que = collections.deque()
        cur = root
        que.append(cur)
        while que:
            size = len(que)
            for _ in range(size):
                node = que.popleft()
                if node.left or node.right:
                    node.left, node.right = node.right, node.left
                	if node.left:
                        que.append(node.left)
                    if node.right:
                        que.append(node.right)
         return root
```

#### 23、对称的二叉树

[剑指 Offer 28. 对称的二叉树 - 力扣（LeetCode）](https://leetcode.cn/problems/dui-cheng-de-er-cha-shu-lcof/)

请实现一个函数，用来判断一棵二叉树是不是对称的。如果一棵二叉树和它的镜像一样，那么它是对称的。

```python
class Solution:
    def isSymmetric(self, root):
        if not root:
            return True
        return self.recur(root.left, root.right)
    def recur(self, A, B):
        if not A and not B:
            return True
        if not A or not B or A.val != B.val:
            return False
        return self.recur(A.left, B.right) and self.recur(A.right, B.left)
```

#### 24、顺时针打印矩阵

[剑指 Offer 29. 顺时针打印矩阵 - 力扣（LeetCode）](https://leetcode.cn/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/?favorite=xb9nqhhg)

输入一个矩阵，按照从外向里以顺时针的顺序依次打印出每一个数字。

```python
class Solution:
    def spiralOrder(self, matrix):
        result = []
        if not matrix:
            return result
        l, r, t, b = 0, len(matrix[0])-1, 0, len(matrix)-1
        while True:
            for i in range(l, r+1):
                result.append(matrix[t][i])
            t += 1
            if t > b:
                break
            for j in range(t, b+1):
                result.append(matrix[j][r])
            r -= 1
            if r < l:
                break
            for i in range(r, l-1, -1):
                result.append(matrix[b][i])
            b -= 1
            if b < t:
                break
            for j in range(b, t-1, -1):
                result.append(matrix[j][l])
            l += 1
            if l < r:
                break
        return result
```

#### 25、包含min函数的栈

[剑指 Offer 30. 包含min函数的栈 - 力扣（LeetCode）](https://leetcode.cn/problems/bao-han-minhan-shu-de-zhan-lcof/?favorite=xb9nqhhg)

定义栈的数据结构，请在该类型中实现一个能够得到栈的最小元素的 min函数在该栈中，调用 min、push 及 pop 的时间复杂度都是 O(1)。

```python
class Solution:
    def __init__(self):
        self.stack1 = []
        self.stack2 = []
    def push(self, x):
        self.stack1.append(x)
        if not self.stack2 or self.stack2[-1] >= x:
            self.stack2.append(x)
    def pop(self):
        x = self.stack1.pop()
        if x == self.stack2[-1]:
            self.stack2.pop()
    def top(self):
        return self.stack1[-1]
    def min(self):
        return self.stack2[-1]
```

#### 26、栈的压入、弹出序列

[剑指 Offer 31. 栈的压入、弹出序列 - 力扣（LeetCode）](https://leetcode.cn/problems/zhan-de-ya-ru-dan-chu-xu-lie-lcof/?favorite=xb9nqhhg)

输入两个整数序列，第一个序列表示栈的压入顺序，请判断第二个序列是否为该栈的弹出顺序。假设压入栈的所有数字均不相等。例如，序列{1,2,3,4,5} 是某栈的压栈序列，序列 {4,5,3,2,1} 是该压栈序列对应的一个弹出序列，但 {4,3,5,1,2} 就不可能是该压栈序列的弹出序列。

```python
class Solution:
    def validateStackSequence(self, pushed, popped):
        stack = []
        i = 0
        for num in pushed:
            stack.append(num)
            while stack and stack[-1] == popped[i]:
                stack.pop()
                i += 1
        return len(stack) == 0
```

#### 27、从上到下打印二叉树

[剑指 Offer 32 - I. 从上到下打印二叉树 - 力扣（LeetCode）](https://leetcode.cn/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/?favorite=xb9nqhhg)

从上到下打印出二叉树的每个节点，同一层的节点按照从左到右的顺序打印。

```python
class Solution:
    def levelorder(self, root):
        res = []
        if not root:
            return res
        que = collections.deuqe()
        que.append(root)
        while que:
            size = len(que)
            for _ in range(size):
                node = que.popleft()
                res.append(node.val)
                if node.left:
                    que.append(node.left)
                if node.right:
                    que.append(node.right)
         return res       
```

#### 28、从上到下打印二叉树II

[剑指 Offer 32 - II. 从上到下打印二叉树 II - 力扣（LeetCode）](https://leetcode.cn/problems/cong-shang-dao-xia-da-yin-er-cha-shu-ii-lcof/?favorite=xb9nqhhg)

从上到下按层打印二叉树，同一层的节点按从左到右的顺序打印，每一层打印到一行。

```python
class Solution:
    def levelOrder(self, root):
        res = []
        if not root:
            return res
        que = collections.deque()
        que.append(root)
        while que:
            size = len(que)
            tmp = []
            for _ in range(size):
                node = que.popleft()
                tmp.append(node.val)
                if node.left:
                    que.append(node.left)
                if node.right:
                    que.append(node.right)
            res.append(tmp)
        return res        
```

#### 29、从上到下打印二叉树III

[剑指 Offer 32 - III. 从上到下打印二叉树 III - 力扣（LeetCode）](https://leetcode.cn/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/?favorite=xb9nqhhg)

请实现一个函数按照之字形顺序打印二叉树，即第一行按照从左到右的顺序打印，第二层按照从右到左的顺序打印，第三行再按照从左到右的顺序打印，其他行以此类推。

```python
class Solution:
    def levelOrder(self, root: TreeNode) -> List[List[int]]:
        res = []
        if not root:
            return res
        que = collections.deque()
        que.append(root)
        b = 0
        while que:
            size = len(que)
            tmp = []
            for _ in range(size):
                node = que.popleft()
                tmp.append(node.val)
                if node.left:
                    que.append(node.left)
                if node.right:
                    que.append(node.right)
            if b % 2 != 0 : tmp = tmp[::-1]
            res.append(tmp)
            b += 1
        return res
```

#### 30、二叉搜索树的后序遍历序列

[剑指 Offer 33. 二叉搜索树的后序遍历序列 - 力扣（LeetCode）](https://leetcode.cn/problems/er-cha-sou-suo-shu-de-hou-xu-bian-li-xu-lie-lcof/?favorite=xb9nqhhg)

输入一个整数数组，判断该数组是不是某二叉搜索树的后序遍历结果。如果是则返回 `true`，否则返回 `false`。假设输入的数组的任意两个数字都互不相同。

```python
class Solution:
    def verifyPostorder(self, postorder):
        def recur(i, j):
            if i >= j:
                return True
            p = i
            while postorder[p] < postorder[j]:
                p += 1
            m = p
            while postorder[p] > postorder[j]:
                p += 1
            return p == j and recur(i, m-1) and recur(m, j-1)
        return recur(0, len(postorder)-1)       
```

#### 31、二叉树中和为某一值的路径

[剑指 Offer 34. 二叉树中和为某一值的路径 - 力扣（LeetCode）](https://leetcode.cn/problems/er-cha-shu-zhong-he-wei-mou-yi-zhi-de-lu-jing-lcof/?favorite=xb9nqhhg)

给你二叉树的根节点 `root` 和一个整数目标和 `targetSum` ，找出所有 **从**

```python
class Solution:
    def pathSum(self, root, target):
        def traversal(root, tmp, target, result):
            tmp.append(root.val)
            if not root.left and not root.right:
                if sum(tmp) == target:
                    result.append(tmp[:])
                return 
            if root.left:
                traversal(root.left, tmp, target, result)
                tmp.pop()
            if root.right:
                traversal(root.right, tmp, target, result)
                tmp.pop()
            result = []
            if not root:
                return result
            traversal(root, [], target, result)
            return result
```

#### 32、复杂链表的赋值

[剑指 Offer 35. 复杂链表的复制 - 力扣（LeetCode）](https://leetcode.cn/problems/fu-za-lian-biao-de-fu-zhi-lcof/)

请实现 `copyRandomList` 函数，复制一个复杂链表。在复杂链表中，每个节点除了有一个 `next` 指针指向下一个节点，还有一个 `random` 指针指向链表中的任意节点或者 `null`。

```python
class Solution:
    def copyRandomList(self, head):
        if not head:
            return head
        dict = {}
        cur = head
        while cur:
            dict[cur] = Node(cur.val)
            cur = cur.next
        cur = head
        while cur:
            dict[cur].next = dict.get(cur.next)
            dict[cur].random = dict.get(cur.random)
            cur = cur.next
        return dict[head]
```

#### 33、二叉搜索树与双向链表

[剑指 Offer 36. 二叉搜索树与双向链表 - 力扣（LeetCode）](https://leetcode.cn/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/?favorite=xb9nqhhg)

输入一棵二叉搜索树，将该二叉搜索树转换成一个排序的循环双向链表。要求不能创建任何新的节点，只能调整树中节点指针的指向。

```python
class Solution:
    def treeToDoublyList(self, root):
        def traversal(root):
            if not root:
                return
            traversal(root.left)
            if self.pre:
                self.pre.right, root.left = root, self.pre
            else:
                self.head = root
            self.pre = root
            traversal(root.right)
        if not root:
            return
        self.pre = None
        traversal(root)
        self.pre.right, self.head.left = self.head, self.pre
        return self.head
```

#### 34、字符串的排列

[剑指 Offer 38. 字符串的排列 - 力扣（LeetCode）](https://leetcode.cn/problems/zi-fu-chuan-de-pai-lie-lcof/?favorite=xb9nqhhg)

输入一个字符串，打印出该字符串中字符的所有排列。你可以以任意顺序返回这个字符串数组，但里面不能有重复元素。

```python
class Solutiom:
    def __init__(self):
        self.path = []
        self.result = []
    def backtracking(self, nums, used):
        if len(self.path) == len(nums):
            self.result.append("".join(self.path))
            return 
        for i in range(len(nums)):
            if used[i] or (i > 0 and nums[i] == nums[i-1] and not used[i-1]):
                continue
            used[i] = True
            self.path.append(nums[i])
            self.backtracking(nums, used)
            self.path.pop()
            used[i] = False
     def permutation(self, s):
        s = list(s)
        s.sort()
        used = [False] * len(s)
        self.backtracking(s, used)
        return self.result
```

#### 35、数组中出现次数超过一半的数字

[剑指 Offer 39. 数组中出现次数超过一半的数字 - 力扣（LeetCode）](https://leetcode.cn/problems/shu-zu-zhong-chu-xian-ci-shu-chao-guo-yi-ban-de-shu-zi-lcof/?favorite=xb9nqhhg)

数组中有一个数字出现的次数超过数组长度的一半，请找出这个数字。你可以假设数组是非空的，并且给定的数组总是存在多数元素。

```python
class Solution:
    def majorityElement(self, nums):
        n = len(nums)
        dict = collections.defaultdict(int)
        for i in range(n):
            dict[nums[i]] += 1
            if dict[nums[i]] > n // 2:
                return nums[i]
```

#### 36、最小的k个数

[剑指 Offer 40. 最小的k个数 - 力扣（LeetCode）](https://leetcode.cn/problems/zui-xiao-de-kge-shu-lcof/)

输入整数数组 `arr` ，找出其中最小的 `k` 个数。例如，输入4、5、1、6、2、7、3、8这8个数字，则最小的4个数字是1、2、3、4。

```python
class Solution:
    def quickSort(self, nums):
        if not nums:
            return []
        a = nums[0]
        list_left = self.quickSort([i for i in nums[1:] if i < a])
        list_right = self.quickSort([i for i in nums[1:] if i >= a])
        return list_left + [a] + list_right
    def getLeastNumber(self, arr, k):
        return self.quickSort(arr)[:k]
```

