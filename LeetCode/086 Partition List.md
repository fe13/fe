# Partition List
`中等`

💡 将小于 x 的节点和大于等于 x 的节点组成两个链表，在连接起来。
```javascript
function partition(head, x) {
  if (!head) return null;
  
  let ldummy = new ListNode();
  let rdumpy = new ListNode();
  let left = ldummy;
  let right = rdumpy;
  
  let curr = head;

  while (curr) {
    if (curr.val < x) {
      left.next = curr;
      left = curr;
    } else {
      right.next = curr;
      right = curr;
    }

    curr = curr.next;
  }

  right.next = null;
  left.next = rdummy.next;

  return ldummy.next;
}
```

💡 将大于等于 x 的(连续)节点向右移。
```javascript
function partition(head, x) {
  let curr = head;
  let left = null;
  let lprev = null;
  let cprev = null;
  
  while (curr) {
    if (!left && curr.val >= x) {
      left = curr;
      lprev = cprev;
    }
    if (left && curr.val < x) {
      cprev.next = curr.next;
      curr.next = left;
      if (lprev) lprev.next = curr;
      else head = curr;

      left = null;
      lprev = null;
    }
    cprev = curr;
    curr = curr.next;
  }
  
  return head;
}
```

## 参考答案
* http://www.cnblogs.com/grandyang/p/4321292.html
* http://www.jiuzhang.com/solution/partition-list

## 题目链接
* https://lintcode.com/zh-cn/problem/partition-list
* https://leetcode.com/problems/partition-list/description
