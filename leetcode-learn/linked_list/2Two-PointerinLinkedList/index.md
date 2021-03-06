[Two-Pointer in Linked List](https://leetcode.com/explore/learn/card/linked-list/214/two-pointer-technique/1211/)

Let's start with a classic problem:
> Given a linked list, determine if it has a cycle in it.
判断一个链表内是否存在循环链表。

You might have come up with the solution using the `hash table`.
你可能想到的解法是用哈希表。

But there is a more efficient solution using the `two-pointer technique`.
但更高效的解法是使用双指针。


Imagine there are two runners with different speed. If they are running on a straight path, the fast runner will first arrive at the destination. However, if they are running on a circular track, the fast runner will catch up with the slow runner if they keep running.
想象两个跑步的人，以不同的速度跑步。如果两人在直道跑步，跑的快的人会先到达终点。然而如果它们在一个环形的跑道跑步，一直跑，跑的快的人最终会与跑的慢的人相遇。

That's exactly what we will come across using two pointers with different speed in a linked list:
- If there is no cycle, the fast pointer will stop at the end of the linked list.
    如果没有循环链表，快的指针会先到达链表的尾部
- If there is a cycle, the fast pointer will eventually meet with the slow pointer.
    如果有循环链表，快的指针最终会与慢的指针相遇



So the only remaining problem is:
> What should be the proper speed for the two pointers?

It is a safe choice to move the slow pointer `one step` at a time while moving the fast pointer `two steps` at a time. For each iteration, the fast pointer will move one extra step. If the length of the cycle is M, after M iterations, the fast pointer will definitely move one more cycle and catch up with the slow pointer.

> What about other choices? Do they work? Would they be more efficient?


Here we provide a template for you to solve the two-pointer problem in the linked list.
**双指针解法框架：**
``` cpp
// Initialize slow & fast pointers
ListNode* slow = head;
ListNode* fast = head;
/**
 * Change this condition to fit specific problem.
 * Attention: remember to avoid null-pointer error
 **/
while (slow && fast && fast->next) {
    slow = slow->next;          // move slow pointer one step each time
    fast = fast->next->next;    // move fast pointer two steps each time
    if (slow == fast) {         // change this condition to fit specific problem
        return true;
    }
}
return false;   // change return value to fit specific problem
```


Tips:
- 1. Always examine if the node is null before you call the next field.
```
Getting the next node of a null node will cause the null-pointer error. For example, before we run fast = fast.next.next, we need to examine both fast and fast.next is not null.
```
- 2. Carefully define the end conditions of your loop.
```
Run several examples to make sure your end conditions will not result in an endless loop. And you have to take our first tip into consideration when you define your end conditions.
```

we will run the loop up to N times
空间复杂度O(1) 时间复杂度O(N)