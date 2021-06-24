# cppStart

### Start
* Install complier

``` 
sudo apt install g++;
```

* Create a cpp file

``` 
#include <iostream>

int main(){
    using namespace std;
    cout << "Hello Wolrd\n";
    return 0;
}

```

* Compile and debug

press `F5` to compile and debug. (config files are in `/.vscode/` )

### Complie single source file and multi single files

Edit `.vscode/tasks.json`

``` js
 {
     ...

     "args": [

         "-Wall",
         "-g",
         // "${file}",      // 单个源文件编译
         "${fileDirname}/*.cpp", // 当前路径下所有源文件编译
         "-o",
         // "${fileDirname}/${fileBasenameNoExtension}.out",  // 单个源文件编译输出: 文件名.out
         "${fileDirname}/main.out" // 多个源文件编译输出: main.out
     ],

     ...
 }
```

- 初级算法
    - [ ] 数组
      - [ ] 买股票的最佳时机-2    
### [代码随想录](https://github.com/youngyangyang04/leetcode-master)


- **数组** 二分法、双指针法、滑动窗口、模拟行为 
https://mp.weixin.qq.com/s/LIfQFRJBH5ENTZpvixHEmg
  - [x] 35 搜索插入位置 二分搜索 注意数组区间
  - [x] 27 移除元素/数组去重 双指针
      - 一个快指针不停取非重复数，非重复数swap到慢指针，
      - 慢指针最终位置即新不重复数组
  - [x] 209 长度最小的子数组 双指针滑窗法
  - [x] 59 螺旋矩阵II 模拟顺时针画矩阵、循环不变式、注意数组区间
- **链表** 
  - [x] 203 移除链表元素 使用虚拟头节点（在单链表中移除头结和 移除其他节点的操作方式是不一样）
  - [x] 707 设计链表 使用虚拟头节点 size struct
  - [x] 206 反转链表 （相邻）双指针/重新创建/递归
  - [x] 141 环形链表 快慢双指针 
  - [x] 142 环形链表2 找环形链表入口 双指针、解方程、归纳
- **哈希表/散列表** hash table（数组 集合set 映射map） 底层实现：哈希表O(1)/红黑树O(logn)
      虽然map是万能的，但也要知道什么时候用数组，什么时候用set
      数组的大小是受限制的，而且如果元素很少，而哈希值太大会造成内存空间的浪费。
      set是一个集合，里面放的元素只能是一个key，而两数之和这道题目，不仅要判断y是否存在而且还要记录y的下表位置，因为要返回x 和 y的下表。所以set 也不能用。
      https://mp.weixin.qq.com/s/g8N6WmoQmsCUw3_BaWxHZA
      https://mp.weixin.qq.com/s/1s91yXtarL-PkX07BfnwLg
  - [x] 242 有效的字母异位词 排序比较/数组哈希表/哈希表
  - [x] 349 两个数组的交集 unordered_set
  - [x] 202 快乐数 不停计算，结果存到unordered_set，有即是快乐数
  - [x] 1 两数之和 unordered_map 存储每一次的数target-curr查是否存在与map中。O(n)        
  - [x] 454 四数相加II 分组 + 哈希表  o(n^2)
  - [x] 383. 赎金信 (只有小写字母)数组/哈希表 O(n)
  - [ ] 15 三数之和 排序+双指针  o(n^2) / ~~哈希表法~~
  - [ ] 18 四数之和 排序+双指针  o(n^3) / ~~哈希表法~~
- **字符串**
    char-code计算 `s - 'a'`
    - [x] 344 反转字符串 （首尾）双指针
    - [x] 541 反转字符串2  每隔2k个反转一次，注意区间/（首尾双指针
    - [x] 剑指offer05 替换空格 双指针/从后往前填充 s.resiz(s.size()+count*2)
      - 先把s resize到对应的长度（每有一个空格长度加2）
      - 再从后开始填充字符串（从前往后需要O(n^2)因为从前往后需把每个字符串往后挪动）
    - [x] 151 翻转字符串里的单词
      - 移除多余空格 移除首尾空格+移除字间空格+双指针移+resize
      - 反转字符串 首尾双指针反转字符串
      - 反转单词 遍历+每个单词块中首尾双指针反转字符串
    - [ ] 剑指Offer58-II.左旋转字符串
      ```
      例如 ：示例1中 输入：字符串abcdefg，n=2
      反转区间为前n的子串 ：bacdefg
      反转区间为n到末尾的子串：bagfedc
      反转整个字符串：cdefgab
      ```
      - 反转0到n个字符串
      - 反转n到末尾的字符串
      - 反转整个字符串即是答案
    - [ ] KMP算法：解决字符串匹配的问题
      https://leetcode-cn.com/problems/implement-strstr/solution/bang-ni-ba-kmpsuan-fa-xue-ge-tong-tou-ming-ming-ba/
      - **最长相等前后缀**
      - 前缀表、后缀表：
        - 前缀：包含首字母不包含尾字母的所有字符串
        - 后缀：包含尾字母不包含首字母的所有字符串
        - 一个字符没有前缀也没有后缀
        - PMT中的值是字符串的**前缀集合**与**后缀集合**的交集最长元素的长度
      - 
    - [ ] 28 实现strStr kmp算法解决/已学习
    - [ ] 458 重复的字符串       
-  **双指针法**
    - [x] 27 移除元素
    - [x] 344 反转字符串
    - [x] 剑指Offer 05.替换空格
    - [x] 151 翻转字符串里的单词
    - [x] 206 反转链表
    - [x] 142 环形链表II
    - [x] 15 三数之和
    - [x] 18 四数之和
- **栈与队列**       
  - [x] 232 用栈实现队列 
    - 两个栈负负得正
  - [x] 225 用队列实现栈 
    - 一个队列操作、另一个队列用于备份，pop到剩一个即是后出，再从备份队列拷贝回来      
  - [x] 20 有效的括号 
    - map存储左右括号匹配，三种情况：左括号多了、右括号多了右括号不一致
  - [x] 1047 删除字符串中的所有相邻重复项
    - 栈，空栈或当前字符不等于栈顶字符即入栈，否则出栈，最出栈内字符的逆序（先进后出，所以需要reverse一下）
  - [ ] 150 逆波兰表达式求值 - 已学习
  - [ ] 239 滑动窗口最大值 - 实现单调队列 - 已学习
  - [ ] 347 前 K 个高频元素 - 已学习
    - [ ] 建堆 堆排序
- **二叉树**
二叉树解题的大忌就是自己稀里糊涂的过了，但是也不知道自己是怎么遍历的。
  - [x] 知识点 leetcode-learn/tree/二叉树知识点.md
  - [x] 如何写好递归 leetcode-learn/tree/递归方法论.md  
    - [x] 递归前中后序遍历 leetcode-learn/tree/Travels A Tree
  - [x] 迭代法前中后序遍历二叉树 
    - [x] 栈来模拟递归的函数调用栈
       - [x] 递归前序&迭代前序 中左右
       - [x] 递归后序 & 迭代后序 左右中 （（前序）中左右 -> （临时）中右左 -> （后序）左右中）
       - [x] 递归中序 & 迭代中序 左 中 右
    - [ ] 统一迭代写法
  - [x] 层序遍历    
    - [x] 102. 二叉树的层序遍历 
      - 方法1.队列queue进行层序，pair记录每个节点对应的层级
      - 方法2（更优、效率高、能解决更多问题）.每层用queue的固定size做改层节点的遍历
    - [x] 107.二叉树的层次遍历 II
      - 正常的层序遍历，完了之后reverse结果数组
    - [x] 199.二叉树的右视图 
      - 层序时，判断节点是该层最后一个节点即推入结果数组
    - [x] 637.二叉树的层平均值
      - 层序时，将该层节点累加出一个sum，除以该层size，推入结果数组
    - [x] 429.N叉树的层序遍历
      - 层序时，推左右子树改为遍历推入children数组
  - [x] 226 翻转二叉树
    - [x] 递归法 （前序或后序都可以）操作交换左右子树
    - [x] 迭代法 深度优先遍历(栈模拟递归)和广度优先遍历（队列层序遍历）
  - [x] 小结 https://mp.weixin.qq.com/s/JWmTeC7aKbBfGx4TY6uwuQ
  - [x] 101 对称二叉树
    - [x] 递归法：1、左右节点都不存在 2、左右节点只有一个存在 3、左右节点都存在,且不等 4、左右节点都存在,且相等
    - [ ] 迭代法： dfs bfs
  - [x] 104 二叉树的最大深度/559.N叉树的最大深度
    - [x] 递归法1： dfs,(自顶向下)递归传递层级参数，每向下一层+1，后序遍历操作与max比较取最大，返回max
    - [x] 递归法2: 自底向上,从叶子节点开始，回溯到根节点，每次层级加1，后序比较左右子树的max
    - [x] 迭代法：层序遍历，每一层深度加1
  - [x] 111 二叉树的最小深度
    - 和最大深度的区别在于，最小深度需要判断最小的是否为空，如果为空则不是最小深度
     比如：当一个左子树为空，右不为空，这时左子树并不是最低点
  - [x] 222.完全二叉树的节点个数
    - [x] 递归法1: 自底向上
    - [x] 递归法2: 自顶向下
    - [x] 迭代法：队列层序
  - [x] 110.平衡二叉树
    - 自底向上，比较左右子树的高度差
  - [x] 257.二叉树的所有路径
    - [x] 递归法
      - 1 前序：方便处理，
      - 2 找叶子节点：左右子树都为空，在叶子节点处进行result插入
    - [ ] 迭代法
  - [x] 小结
    - [x] 二叉树对称相似题 100.相同的树
    - 二叉树最大深度 前序自顶向下 后序自底向上 层序队列bfs
    - 二叉树最小深度 后序自底向上 处理左右孩子为空的逻辑（都为空、某一个为空、都不为空）
    - 二叉树节点数量 复习二叉树的4种遍历方式 前中后 层序
    - 二叉树平衡问题 后序自底向上 比较左右子树高度差
    - 二叉树所有路径 前序自顶向下 在叶子节点出进行操作
    （**!root->left &&!root->right**）
  - [x] 二叉树中的回溯 
    - 递归中隐藏着回溯https://mp.weixin.qq.com/s/ivLkHzWdhjQQD1rQWe6zWA
  - [x] 404.左叶子节点之和
    - 深度优先DFS 判断叶子节点 判断左节点
    - 难点在于判断左节点，有两种思路：
    1.通过递归函数额外参数isLeft区分 2.通过root->left root->left->left root->left->right去隔层判断
  - [x] 17: 513.找树左下角的值
    （与本题不太相关的）小技巧: 如果需要遍历整颗树，递归函数就不能有返回值。如果需要遍历某一条固定路线，递归函数就一定要有返回值！
    - [x] bfs 层序遍历 取每层第一个节点为result
    - [x] 迭代法 dfs 找最深的第一个叶子节点
  - [x] 18 递归函数究竟什么时候需要返回值，什么时候不要返回值？
    - [x] 112 路径总和 
      如果需要**遍历整颗树**，那么**递归函数就不要返回值**，如果要**搜索其中一条符合条件的路径**，**递归函数就需要返回值，因为遇到符合条件的路径就要及时返回**
      - [x] (可以遍历，但不必要)遍历有路径无返回值的递归，叶子节点+隐含的回溯 
      - [x] 不遍历 有返回值的递归
    - [x] 113 路径总和2
      - [x] 找所有路径，需要遍历，无返回值的递归
  - [x] 106.从中序与后序遍历序列构造二叉树
    关键点：（前提是树中没有重复的元素，才可以通过比较值相等来查找节点）1 后序的最后一个节点为当前层根节点 2 通过根节点在中序数组中进行切割，左边为左子树节点，右边为右子树节点 3 根据中序的左右节点树切割后序数组 左（左子树数量个节点为新的左子树的后序数组） 右（右子树数量个节点新的右子树的后序数组） 中，再将新的中序和后序数组递归传递下去
    - 实现方式1：每次递归重新创建inorder、postorder数组
    - 实现方式2: 传参idx,原地操作
  - [x] 654 最大二叉树
    **构造树一般采用的是前序遍历，因为先构造中间节点，然后递归构造左子树和右子树。**
    什么时候递归函数前面加if，什么时候不加if?**一般情况来说：如果让空节点（空指针）进入递归，就不加if，如果不让空节点进入递归，就加if限制一下， 终止条件也会相应的调整。**
    - [x] 每次找数组最大值为root，以每层root位置进行切割，root左侧数组为左子树数组，root右侧数组为右子树数组
  - [x] 21 小结
    递归中如何隐藏着回溯
    如何通过三层关系确定左叶子
    如何通过二叉树深度来判断左下角的值
    递归函数究竟什么时候需要返回值，什么时候不要返回值？
    前序和中序，后序和中序构造唯一二叉树
    使用数组构造某一特性的二叉树
  - [x] 617.合并二叉树
    - 两棵树都不存在返回nullptr，其中一颗树不存在返回存在的一颗树，两颗树都存在值为两颗树的值之和，并分别递归处理左右子树
  - [x] 700.二叉搜索树中的搜索
    - 二叉搜索树是一个有序树：
      若它的左子树不空，则左子树上所有结点的值均小于它的根结点的值；
      若它的右子树不空， 则右子树上所有结点的值均大于它的根结点的值；
      它的左、右子树也分别为二叉搜索树
    - root为空返回nullptr，root不为空：
    1 节点值等于target，返回root 2 节点值小于target，递归右子树 3 节点值大于target，递归左子树
  - [x] 98.验证二叉搜索树
   - 中序遍历，（通过一个全局值存储上一节点值）判断节点值是否有序递增，（注意return值是左右都为true才是返回true）
  - [x] 530.二叉树的最小绝对差
    - 中序遍历，用一个全局变量记录前一个节点的指针（注意这里与记录parent指针的区别，二叉搜索树中序遍历为有序，并不能通过递归的第二个参数来记录有序数组的前一个节点）
  - [x] 501.二叉搜索树的众数
    - [x] 中序遍历，注意是在每轮更新完cnt就做比较和相应操作，而不是等下个节点才比较（这样会写冗余的逻辑）
  - [x] 236 二叉树的最近公共祖先
    - [x] 1 返回当root等于p或者root等于q时，应该返回root，否则返回nullptr  2 后序遍历处理，自底向上，当左右子树都不为nullptr则说明当前为lca，某一个子树为空则返回另外一颗子树，都为空说明两个节点都不在当前节点的子树返回nullptr
  - [ ] 28 小结
    - 合并二叉树 
    - 二叉搜索树 是否是二叉搜索树 （中序）有序遍历二叉搜索树 二叉搜索树众数
    - 二叉树公共祖先
  - [ ] 235 二叉搜索树的公共祖先
  - [x]  450 删除二叉搜索树中的节点
    - 根等于target
      - 左右子树都存在
        - 方案1： 将左子树放到右子树的最左侧节点的left，并把右子树作为新的root return
        - 方案2： 将右子树放到左子树的最右侧子树的right，并把左子树作为新的root return
      - 左右子只存在一个或都不存在，返回存在的子树或nullptr
    - 根大于target，遍历左子树
    - 根小于target，遍历右子树
  - [x] 669 修剪二叉搜索树
    - 注意需要当前节点小于low，或者大于high的时候还需要对其子树进行修剪操作
      - 当前节点小于low，递归操作右子树
      - 当前节点大于high，递归操作左子树
  - [x] 108 将有序数组转换为二叉搜索树
    - 取数组中间位置的数创建treenode，此数左边比它小、右边比它大
      将左右数组递归进行此操作
    - 相似题 654 最大二叉树 106 从中序与后序序列构造二叉树
  - [x] 538 把二叉搜索树转换为累加树
    - 顺序 右 中 左，额外一个值做累加
  - [ ] 二叉树总结 
        https://mp.weixin.qq.com/s/-ZJn3jJVdF683ap90yIj4Q
    - 遍历顺序的大致总结：
      - 二叉树的构造，无论普通二叉树还是二叉搜索树一定前序，都是先构造中节点
      - 普通二叉树的属性，一般是后序，一般要通过递归函数的返回值做计算。求普通二叉树的属性还是要具体问题具体分析，例如单纯求深度就用前序，二叉树：找所有路径也用了前序
      - 二叉搜索树的属性，一定是中序了，要不白瞎了有序性了
- **回溯算法**
  - [x] 1.关于回溯
    - 什么是回溯法
    - 回溯法的效率
    **虽然回溯法很难，很不好理解，但是回溯法并不是什么高效的算法。**
    **因为回溯的本质是穷举，穷举所有可能，然后选出我们想要的答案**，如果想让回溯法高效一些，可以加一些剪枝的操作，但也改不了回溯法就是穷举的本质。
    - 回溯法解决的问题
      - **组合问题**：N个数里面按一定规则找出k个数的集合
      - 切割问题：一个字符串按一定规则有几种切割方式
      - 子集问题：一个N个数的集合里有多少符合条件的子集
      - 排列问题：N个数按一定规则全排列，有几种排列方式
      - 棋盘问题：N皇后，解数独等等
    - 如何理解回溯法
      - **回溯法解决的问题都可以抽象为树形结构（N叉树）**，是的，我指的是所有回溯法的问题都可以抽象为树形结构！
      - 因为回溯法解决的都是在集合中递归查找子集，**集合的大小就构成了树的宽度，递归的深度，都构成的树的深度。**
      ```
        void backtracking(参数) {
          if (终止条件) {
              存放结果;
              return;
          }

          for (选择：本层集合中元素（树中节点孩子的数量就是集合的大小）) {
              处理节点;
              backtracking(路径，选择列表); // 递归
              回溯，撤销处理结果
          }
      }
      ```
  - [x] 2. 77 组合问题 
    - 回溯
  - [x] 3. 77 组合问题 剪枝优化
    -  **剪枝优化** 可以剪枝的地方就在递归中**每一层的for循环所选择的起始位置**（或者直接避免后序for循环）。如果for循环选择的起始位置之后的元素个数 已经不足 我们需要的元素个数了，那么就没有必要搜索了
    -  剪枝操作可以在for循环中做break、continue，也可以在递归函数中return实现
  - [x] 4. 216.组合总和III
    - int cnt-组合数量 int target-目标值, int curr-当前值, int currSum-当前sum
    - 注意sum值要在backtrack路径传递中才做累加，不然会影响当前层的currSum
    - 回溯法中递归函数参数很难一次性确定下来，一般先写逻辑，需要啥参数了，填什么参数。
  - [x] 5. 17.电话号码的字母组合
    - **回溯三部曲**
      - （辅助）画回溯N叉树梳理思路
      - **确定回溯函数参数**
      - **确定终止条件**
      - **确定单层遍历逻辑**
  - [x] 6. 小结
  - [x] 7. 39.组合总和 
  - [ ] 8. 40.组合总和II 已练习
    -  判断重复需要对candidates候选数组进行排序
    -  区分树层重复和树枝重复
    -  used数组记录，used[i - 1] == true树枝重复 used[i - 1] == false树层重复
  - [ ] 9. 131.分割回文串
    - 回文串判断：首位双指针O(n)判断是否相等
    - C++ string操作 substr
  - [x] 10 93.复原 IP 地址
    - 注意符合条件的ip的判断
    - 注意边界条件：1、ip地址前导0 2、不超过255，字符串转int
    - string转int
  - [x] 11. 78.求子集问题    
    - 1、每一个path都是result 2、每个子集不同通过startIdx+1区分下层树的选择
  - [x] 12. 本周小结二
    -  对于组合问题，什么时候需要startIndex呢？
       - 如果是**一个集合**来求**组合**的话，就需要startIndex 
       - 如果是**多个集合**取**组合**，各个集合之间**相互不影响**，那么就不用startIndex
    - 剪枝
    - 去重
      - 树层去重，同一树层上“使用过”
      - 树枝去重，同一树枝上“使用过”
    - 切割问题，如何截取子串
    - 收集所有节点、收集叶子节点
  - [x] 13. 90.子集II
    - 1、收集N叉树所有节点 2、树层去重
  - [x] 14. 491.递增子序列
    - 树层去重逻辑不能再使用排序后的used[i-1]去做判断，
      - 在每一层for时使用unordered_set记录当层已经使用过的数字
      - 使用size为200的数字做哈希更加方便 used.resize(200,false) used[nums[i]+100]
  - [ ] 15. 
### 练习

- 数组
  - [x] 两数之和 哈希表  o(n)
  - [x] 三数之和 排序+双指针  o(n^2)
  - [x] 四数之和 排序+双指针  o(n^3)
  - [x] js数组扁平化 简单递归/迭代      
  - [x] 384 打乱数组
    - 伪随机数生成器，数组中每个数字与当前idx到末尾的一个idx进行swap
    - **排列的相同机会**
    - [knuth-shuffle算法](https://yjk94.wordpress.com/2017/03/17/%E6%B4%97%E7%89%8C%E7%9A%84%E6%AD%A3%E7%A1%AE%E5%A7%BF%E5%8A%BF-knuth-shuffle%E7%AE%97%E6%B3%95/)
    - 标准库有shuffle实现(c++、js都有)
    - seed不能设置为时间，不然无法通过用例..    
  - [ ] 旋转数组
  - [x] 80. 删除有序数组中的重复项 II 
    - 双指针、cnt、区间
- 树 
  - [x] 129 求根到叶子节点数字之和 DFS 带参prev递归，非用和尾调用版本
  - [x] 589 N叉树的前序遍历 
    - 递归法 children遍历之前push 根节点优先，兄弟节点顺序按遍历顺序
    - 迭代法 即N叉树的层序
  - [x] 590 N叉树的后序遍历 
    - children遍历之后push 根节点最后，兄弟节点顺序按遍历顺序
  - [x] 429 N叉树的层序遍历 
    - 队列 push节点记录层级
  - [ ] 找扁平N叉树的所有路径
  - [ ] 1490 克隆N叉树 
    - N叉树的先序遍历/ 尾递归和非尾递归
  - [x] 102 二叉树的层序遍历: 
    - 队列实现、且push节点时需要记录层级
  - [x] 107 二叉树的层序遍历2
    - 队列实现、且push节点时需要记录层级
    - 自底向上顺序，需要把结果数组reverse
  - [ ] 剑指 Offer 33. 二叉搜索树的后序遍历序列
- 二分查找
    - [ ] 69 x的平方根 
      - 1 二分查找/需要注意ans更新的时机
      - 2 牛顿迭代法
      - 3 袖珍计算器算法 https://leetcode-cn.com/problems/sqrtx/solution/x-de-ping-fang-gen-by-leetcode-solution/
    - [ ] 153.寻找旋转排序数组中的最小值