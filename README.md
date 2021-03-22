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
- [代码随想录](https://github.com/youngyangyang04/leetcode-master)
    - 数组 二分法、双指针法、滑动窗口、模拟行为 https://mp.weixin.qq.com/s/LIfQFRJBH5ENTZpvixHEmg
      - [x] 35 搜索插入位置 二分搜索 注意数组区间
      - [x] 27 移除元素/数组去重 双指针
        - 一个快指针不停取非重复数，非重复数swap到慢指针，
        - 慢指针最终位置即新不重复数组
      - [x] 209 长度最小的子数组 双指针滑窗法
      - [x] 59 螺旋矩阵II 模拟顺时针画矩阵、循环不变式、注意数组区间
    - 链表 
      - [x] 203 移除链表元素 使用虚拟头节点（在单链表中移除头结点 和 移除其他节点的操作方式是不一样）
      - [x] 707 设计链表 使用虚拟头节点 size struct
      - [x] 206 反转链表 （相邻）双指针/重新创建/递归
      - [x] 141 环形链表 快慢双指针 
      - [x] 142 环形链表2 找环形链表入口 双指针、解方程、归纳
    - 哈希表/散列表 hash table（数组 集合set 映射map） 底层实现：哈希表O(1)/红黑树O(logn)
      虽然map是万能的，但也要知道什么时候用数组，什么时候用set
      数组的大小是受限制的，而且如果元素很少，而哈希值太大会造成内存空间的浪费。
      set是一个集合，里面放的元素只能是一个key，而两数之和这道题目，不仅要判断y是否存在而且还要记录y的下表位置，因为要返回x 和 y的下表。所以set 也不能用。
      https://mp.weixin.qq.com/s/g8N6WmoQmsCUw3_BaWxHZA
      https://mp.weixin.qq.com/s/1s91yXtarL-PkX07BfnwLg
      - [x] 242 有效的字母异位词 排序比较/数组哈希表/哈希表
      - [x] 349 两个数组的交集 unordered_set
      - [x] 202 快乐数 不停计算，结果存到unordered_set，有重复即是快乐数
      - [x] 1 两数之和 unordered_map 存储每一次的数字，target-curr查是否存在与map中。O(n)        
      - [x] 454 四数相加II 分组 + 哈希表  o(n^2)
      - [x] 383. 赎金信 (只有小写字母)数组/哈希表 O(n)
      - [ ] 15 三数之和 排序+双指针  o(n^2) / ~~哈希表法~~
      - [ ] 18 四数之和 排序+双指针  o(n^3) / ~~哈希表法~~
    - 字符串
      char-code计算 `s - 'a'`
      - [x] 344 反转字符串 （首尾）双指针
      - [x] 541 反转字符串2  每隔2k个反转一次，注意区间/（首尾）双指针
      - [x] 剑指offer05 替换空格 双指针/从后往前填充 s.resize(s.size()+count*2)
        - 先把s resize到对应的长度（每有一个空格长度加2）
        - 再从后开始填充字符串（从前往后需要O(n^2)因为从前往后需要把每个字符串往后挪动）
      - [x] 151 翻转字符串里的单词
        - 移除多余空格 移除首尾空格+移除字间空格+双指针移动+resize
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
          - PMT中的值是字符串的**前缀集合**与**后缀集合**的交集中最长元素的长度
        - 
      - [ ] 28 实现strStr kmp算法解决/已学习
      - [ ] 458 重复的字符串 
      - [ ] 239 滑动窗口最大值
      - [ ] 347 前 K 个高频元素      
    -  双指针法
        - [x] 27 移除元素
        - [x] 344 反转字符串
        - [x] 剑指Offer 05.替换空格
        - [x] 151 翻转字符串里的单词
        - [x] 206 反转链表
        - [x] 142 环形链表II
        - [x] 15 三数之和
        - [x] 18 四数之和
    - 栈与队列       
      - [x] 232 用栈实现队列 
        - 两个栈负负得正
      - [x] 225 用队列实现栈 
        - 一个队列操作、另一个队列用于备份，pop到剩一个即是后进先出，再从备份队列拷贝回来      
      - [x] 20 有效的括号 
        - map存储左右括号匹配，三种情况：左括号多了、右括号多了、左右括号不一致
      - [x] 1047 删除字符串中的所有相邻重复项
        - 栈，空栈或当前字符不等于栈顶字符即入栈，否则出栈，最后输出栈内字符的逆序（先进后出，所以需要reverse一下）
      - [ ] 150 逆波兰表达式求值
      - [ ] 239 滑动窗口最大值
- 练习
    - 数组
      - [x] 两数之和 哈希表  o(n)
      - [x] 三数之和 排序+双指针  o(n^2)
      - [x] 四数之和 排序+双指针  o(n^3)
      - [x] js数组扁平化 简单递归/迭代      
      - [x] 384 打乱数组
        - 伪随机数生成器，数组中每个数字与当前idx到末尾的一个随机idx进行swap
        - **排列的相同机会**
        - [knuth-shuffle算法](https://yjk94.wordpress.com/2017/03/17/%E6%B4%97%E7%89%8C%E7%9A%84%E6%AD%A3%E7%A1%AE%E5%A7%BF%E5%8A%BF-knuth-shuffle%E7%AE%97%E6%B3%95/)
        - 标准库有shuffle实现(c++、js都有)
        - seed不能设置为时间，不然无法通过用例..
      - [ ] 旋转数组
    - 树 
      - [x] 129 求根到叶子节点数字之和 DFS 带参prev递归，非尾调用和尾调用版本
      - [x] 589 N叉树的前序遍历
      - [x] 590 N叉树的后序遍历
      - [ ] 找扁平N叉树的所有路径
      - [ ] 1490 克隆N叉树 N叉树的遍历/ 尾递归和非尾递归