## <center><font color=#5C4033>Reverse Linked List</font></center>

### <font color=#FF7F00>题目</font>
```
反转一个单链表。
 
示例:
 
输入: 1->2->3->4->5->NULL
输出: 5->4->3->2->1->NULL
进阶:
你可以迭代或递归地反转链表。你能否用两种方法解决这道题？
```


### <font color=#FF7F00>Java代码</font>

```java
// 首先定义单链表
public class ListNode{
    int val;
    ListNode next;
    ListNode(int x) {val = x;}
}

```
#### <font color=#FAA400>非递归</font>

```java
class Solution{
    public ListNode reverseList(ListNode head){
        ListNode prev = null;
        ListNode curr = head;
        while(curr != null){
            ListNode nextTemp = curr.next;
            curr.next = prev;
            prev = curr;
            curr = nextTemp;
        }
        return prev;
    }
}
```

#### <font color=#FAA400>递归</font>
```java
class Solution{
    public ListNode reverseList(ListNode head){
        if(head == null || head.next == null){
            return head;
        }
        ListNode p = reverseList(head.next);
        head.next.next = head;
        head.next = null;
        return p;
    }
}
```


[Leetcode参考链接](https://leetcode-cn.com/problems/reverse-linked-list/solution/fan-zhuan-lian-biao-by-leetcode/)