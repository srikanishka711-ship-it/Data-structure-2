# Data-structure-2
# Queue ADT using Singly Linked List

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Queue:
    def __init__(self):
        self.front = None
        self.rear = None

    def enqueue(self, data):
        new_node = Node(data)
        if self.rear is None:
            self.front = self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = new_node
        print("Element enqueued successfully.")

    def dequeue(self):
        if self.front is None:
            print("Queue is empty. Cannot dequeue.")
        else:
            removed = self.front.data
            self.front = self.front.next
            if self.front is None:
                self.rear = None
            print("Dequeued element is:", removed)

    def display(self):
        if self.front is None:
            print("Queue is empty.")
        else:
            temp = self.front
            print("Queue elements are:")
            while temp:
                print(temp.data)
                temp = temp.next

queue = Queue()

while True:
    print("\n--- Queue ADT using Singly Linked List ---")
    print("1. Enqueue")
    print("2. Dequeue")
    print("3. Display")
    print("4. Exit")

    choice = int(input("Enter your choice: "))

    if choice == 1:
        element = int(input("Enter element to enqueue: "))
        queue.enqueue(element)
    elif choice == 2:
        queue.dequeue()
    elif choice == 3:
        queue.display()
    elif choice == 4:
        print("Exiting program.")
        break
    else:
        print("Invalid choice.")
        --- Queue ADT using Singly Linked List ---
1. Enqueue
2. Dequeue
3. Display
4. Exit
Enter your choice: 1
Enter element to enqueue: 10
Element enqueued successfully.

Enter your choice: 1
Enter element to enqueue: 20
Element enqueued successfully.

Enter your choice: 3
Queue elements are:
10
20

Enter your choice: 2
Dequeued element is: 10
