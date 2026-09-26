# 6.linked_list_palindrome.py-
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class LinkedList:
    def __init__(self):
        self.head = None

    def insert_end(self, data):
        new_node = Node(data)

        if self.head is None:
            self.head = new_node
            return

        current = self.head

        while current.next:
            current = current.next

        current.next = new_node

    def is_palindrome(self):
        values = []

        current = self.head

        while current:
            values.append(current.data)
            current = current.next

        return values == values[::-1]

    def display(self):
        current = self.head

        while current:
            print(current.data, end=" -> ")
            current = current.next

        print("None")


ll = LinkedList()

ll.insert_end(1)
ll.insert_end(2)
ll.insert_end(2)
ll.insert_end(1)

ll.display()

if ll.is_palindrome():
    print("Palindrome")
else:
    print("Not Palindrome")

Output:

1 -> 2 -> 2 -> 1 -> None
Palindrome
