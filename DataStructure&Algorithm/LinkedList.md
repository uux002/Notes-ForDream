# 链表

> 链表是由一个一个节点组成的链式结构

#### 单向链表

>每一个节点都指向自己的下一个节点

#### 双向链表

> 每一个节点即指向自己的下一个节点，也指向自己的上一个节点

> 链表的查找复杂度为O(n)，插入和删除的复杂度为O(1)



> 删除或访问节点的时候，一定要记得检查节点是否为空



```python
# 单向链表
class Node:
  def __init__(self,val):
    self.val = val
    self.next = None
    
 # 双向链表
class Node:
  def __init__(self,val):
    self.val = val
    self.prev = None
    self.next = None
```



#### 快慢指针

> 访问链表的时候，定义两个指针fast, slow，slow 每次迭代一个节点，fast每次迭代两个节点（或多个节点）

1. 找到一个链表的中间节点，如果是偶数个节点，则会指向n/2个节点

   使用快慢指针，当fast指针指向末尾节点的时候，slow指针指向的一定是中间节点

2. 判断一个连表是否是有环 (尾部节点指向了头部节点，形成一个环路)

   使用快慢指针，如果fast指向了null，则说明不存在环，如果fast指针和slow指针指向了同一个节点，则说明有环，可以在纸上画一下，因为fast的速度是slow的2倍，所以fast一定会追上slow，如果存在环，fast和slow一定会在某一时刻指向同一节点



```python
# 找到一个链表的中间节点
def get_middle_node(self,head):
  fast = head
  slow = head
  while(fast and slow):
    fast = fast.next
    if (fast and fast.next):
      fast = fast.next
    else:
      break
    slow = slow.next
    
  return slow


# 判断链表是否有环
def has_circle(self,head):
  fast = head
  slow = head
  while(fast and slow):
    fast = fast.next
    if(fast):
      fast = fast.next
    slow = slow.next
    if(fast == slow):
      break
  if(fast and slow and (fast == slow)):
    return True
  else:
    retur False
```

