### Linked List
* two pointer technique to find middle or n - x

```python
def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if head.next == None: 
            return head
        
        i = head
        j = head
        
        while i != None and i.next != None:
            i = i.next.next
            j = j.next
            
        return j
        
```

* reverse list: via recursive call
```python
def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        if head == None or head.next == None:
            return head
        
        p = self.reverseList(head.next)
        head.next.next = head
        head.next = None
        return p
        
```
