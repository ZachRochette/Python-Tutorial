### Solution:

```python
class Node:
    def __init__(self, data=None):
        self.left = None
        self.right = None
        self.data = data

    def insert(self, data):
        if not self.data:
            self.data = data
            return

        if self.data == data:
            return

        if data < self.data:
            if self.left:
                self.left.insert(data)
                return
            self.left = Node(data)
            return

        if self.right:
            self.right.insert(data)
            return
        self.right = Node(data)

    def min(self):
        current = self
        while current.left is not None:
            current = current.left
        return current.data

    def max(self):
        current = self
        while current.right is not None:
            current = current.right
        return current.data

    def delete(self, data):
        if self == None:
            return self
        if data < self.data:
            if self.left:
                self.left = self.left.delete(data)
            return self
        if data > self.data:
            if self.right:
                self.right = self.right.delete(data)
            return self
        if self.right == None:
            return self.left
        if self.left == None:
            return self.right
        min_value_node = self.right
        while min_value_node.left:
            min_value_node = min_value_node.left
        self.data = min_value_node.data
        self.right = self.right.delete(min_value_node.data)
        return self

    def exists(self, data):
        if data == self.data:
            return True

        if data < self.data:
            if self.left == None:
                return False
            return self.left.exists(data)

        if self.right == None:
            return False
        return self.right.exists(data)

    def order(self, values):
        if self.left is not None:
            self.left.order(values)
        if self.data is not None:
            values.append(self.data)
        if self.right is not None:
            self.right.order(values)
        return values

    
def main():
    nums = [5, 10, 3, 17, 4, 18, 29, 4, 2, 1, 50, 6, 9, 14]
    bst = Node()
    for num in nums:
        bst.insert(num)

    print("order:")
    print(bst.order([]))
    print("")

    nums = [1, 29, 50]
    print("deleting " + str(nums))
    for num in nums:
        bst.delete(num)
    print("")

    print("1 exists:")
    print(bst.exists(1))
    print("18 exists:")
    print(bst.exists(18))
    print("15 exists:")
    print(bst.exists(15))
    print("17 exists:")
    print(bst.exists(17))
    print("")
    
    print("The max value is: ")
    print(bst.max())
    print("The min value is: ")
    print(bst.min())
    
main()

# Output:
    # order:
    # [1, 2, 3, 4, 5, 6, 9, 10, 14, 17, 18, 29, 50]

    # deleting [1, 29, 50]

    # 1 exists:
    # False
    # 18 exists:
    # True
    # 15 exists:
    # False
    # 17 exists:
    # True

    # The max value is:
    # 18
    # The min value is:
    # 2
```
    
Back to Sets: [Trees](trees.md)