package CCE105;

import java.util.Scanner;

public class ActLab {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);

        while (true) {
            System.out.println("Choose Data Structure:");
            System.out.println("1. Stack");
            System.out.println("2. Queue");
            System.out.println("3. Linked List");
            System.out.println("4. Circular Linked List");
            System.out.println("5. Exit");
            System.out.print("Enter choice: ");
            int Choice = s.nextInt();

            switch (Choice) {
                case 1:
                    stackOperations(s);
                    break;
                case 2:
                    queueOperations(s);
                    break;
                case 3:
                    linkedListOperations(s);
                    break;
                case 4:
                    circularLinkedListOperations(s);
                    break;
                case 5:
                    System.out.println("Exiting program.");
                    s.close();
                    return;
                default:
                    System.out.println("Invalid choice! Try again.");
            }
        }
    }

    // Stack Implementation
    static class Stack {
        private int[] arr;
        private int top;

        public Stack(int size) {
            arr = new int[size];
            top = -1;
        }

        public void push(int val) {
            if (top == arr.length - 1) {
                System.out.println("Stack overflow");
            } else {
                arr[++top] = val;
                System.out.println("Pushed " + val + " into stack.");
            }
        }

        public void pop() {
            if (top == -1) {
                System.out.println("Stack underflow");
            } else {
                System.out.println("Popped: " + arr[top--]);
            }
        }

        public void display() {
            if (top == -1) {
                System.out.println("Stack is empty.");
                return;
            }
            System.out.print("Stack contents: ");
            for (int i = top; i >= 0; i--) {
                System.out.print(arr[i] + " ");
            }
            System.out.println();
        }
    }

    // Queue Implementation
    static class Queue {
        private int[] arr;
        private int front, rear, size;

        public Queue(int capacity) {
            arr = new int[capacity];
            front = 0;
            rear = -1;
            size = 0;
        }

        public void enqueue(int val) {
            if (size == arr.length) {
                System.out.println("Queue overflow");
            } else {
                rear = (rear + 1) % arr.length;
                arr[rear] = val;
                size++;
                System.out.println("Enqueued " + val + " into queue.");
            }
        }

        public void dequeue() {
            if (size == 0) {
                System.out.println("Queue underflow");
            } else {
                System.out.println("Dequeued: " + arr[front]);
                front = (front + 1) % arr.length;
                size--;
            }
        }

        public void display() {
            if (size == 0) {
                System.out.println("Queue is empty.");
                return;
            }
            System.out.print("Queue contents: ");
            for (int i = 0; i < size; i++) {
                int index = (front + i) % arr.length;
                System.out.print(arr[index] + " ");
            }
            System.out.println();
        }
    }

    // Linked List Implementation
    static class LinkedList {
        static class Node {
            int data;
            Node next;

            Node(int data) {
                this.data = data;
                next = null;
            }
        }

        private Node head;

        // Insert at end
        public void insert(int val) {
            Node newNode = new Node(val);
            if (head == null) {
                head = newNode;
            } else {
                Node curr = head;
                while (curr.next != null) {
                    curr = curr.next;
                }
                curr.next = newNode;
            }
            System.out.println("Inserted " + val + " at the end.");
        }

        // Delete at beginning
        public void deleteAtBeginning() {
            if (head == null) {
                System.out.println("List is empty, nothing to delete.");
            } else {
                System.out.println("Deleted: " + head.data);
                head = head.next;
            }
        }

        // Display
        public void display() {
            if (head == null) {
                System.out.println("Linked List is empty.");
                return;
            }
            System.out.print("Linked List contents: ");
            Node curr = head;
            while (curr != null) {
                System.out.print(curr.data + " ");
                curr = curr.next;
            }
            System.out.println();
        }
    }

    // Circular Linked List Implementation
    static class CircularLinkedList {
        static class Node {
            int data;
            Node next;

            Node(int data) {
                this.data = data;
                next = null;
            }
        }

        private Node tail = null;

        // Insert at end
        public void insert(int val) {
            Node newNode = new Node(val);
            if (tail == null) {
                tail = newNode;
                tail.next = tail;
            } else {
                newNode.next = tail.next;
                tail.next = newNode;
                tail = newNode;
            }
            System.out.println("Inserted " + val + " into circular linked list.");
        }

        // Delete at beginning
        public void delete() {
            if (tail == null) {
                System.out.println("Circular Linked List is empty, nothing to delete.");
            } else if (tail.next == tail) {
                System.out.println("Deleted: " + tail.data);
                tail = null;
            } else {
                Node head = tail.next;
                System.out.println("Deleted: " + head.data);
                tail.next = head.next;
            }
        }

        // Display
        public void display() {
            if (tail == null) {
                System.out.println("Circular Linked List is empty.");
                return;
            }
            System.out.print("Circular Linked List contents: ");
            Node curr = tail.next;
            do {
                System.out.print(curr.data + " ");
                curr = curr.next;
            } while (curr != tail.next);
            System.out.println();
        }
    }

    // Methods to handle user interaction with each data structure

    static void stackOperations(Scanner sc) {
        Stack stack = new Stack(100);
        System.out.println("\n--- Stack Operations ---");
        while (true) {
            System.out.println("Choose operation:");
            System.out.println("1. Push");
            System.out.println("2. Pop");
            System.out.println("3. Display");
            System.out.println("4. Back to main menu");
            System.out.print("Enter choice: ");
            int op = sc.nextInt();
            switch (op) {
                case 1:
                    System.out.print("Enter value to push: ");
                    int pushVal = sc.nextInt();
                    stack.push(pushVal);
                    break;
                case 2:
                    stack.pop();
                    break;
                case 3:
                    stack.display();
                    break;
                case 4:
                    return;
                default:
                    System.out.println("Invalid operation! Try again.");
            }
            System.out.println();
        }
    }

    static void queueOperations(Scanner sc) {
        Queue queue = new Queue(100);
        System.out.println("\n--- Queue Operations ---");
        while (true) {
            System.out.println("Choose operation:");
            System.out.println("1. Enqueue");
            System.out.println("2. Dequeue");
            System.out.println("3. Display");
            System.out.println("4. Back to main menu");
            System.out.print("Enter choice: ");
            int op = sc.nextInt();
            switch (op) {
                case 1:
                    System.out.print("Enter value to enqueue: ");
                    int val = sc.nextInt();
                    queue.enqueue(val);
                    break;
                case 2:
                    queue.dequeue();
                    break;
                case 3:
                    queue.display();
                    break;
                case 4:
                    return;
                default:
                    System.out.println("Invalid operation! Try again.");
            }
            System.out.println();
        }
    }

    static void linkedListOperations(Scanner sc) {
        LinkedList list = new LinkedList();
        System.out.println("\n--- Linked List Operations ---");
        while (true) {
            System.out.println("Choose operation:");
            System.out.println("1. Insert at end");
            System.out.println("2. Delete at beginning");
            System.out.println("3. Display");
            System.out.println("4. Back to main menu");
            System.out.print("Enter choice: ");
            int op = sc.nextInt();
            switch (op) {
                case 1:
                    System.out.print("Enter value to insert: ");
                    int val = sc.nextInt();
                    list.insert(val);
                    break;
                case 2:
                    list.deleteAtBeginning();
                    break;
                case 3:
                    list.display();
                    break;
                case 4:
                    return;
                default:
                    System.out.println("Invalid operation! Try again.");
            }
            System.out.println();
        }
    }

    static void circularLinkedListOperations(Scanner sc) {
        CircularLinkedList clist = new CircularLinkedList();
        System.out.println("\n--- Circular Linked List Operations ---");
        while (true) {
            System.out.println("Choose operation:");
            System.out.println("1. Insert");
            System.out.println("2. Delete");
            System.out.println("3. Display");
            System.out.println("4. Back to main menu");
            System.out.print("Enter choice: ");
            int op = sc.nextInt();
            switch (op) {
                case 1:
                    System.out.print("Enter value to insert: ");
                    int val = sc.nextInt();
                    clist.insert(val);
                    break;
                case 2:
                    clist.delete();
                    break;
                case 3:
                    clist.display();
                    break;
                case 4:
                    return;
                default:
                    System.out.println("Invalid operation! Try again.");
            }
            System.out.println();
        }
    }
}
