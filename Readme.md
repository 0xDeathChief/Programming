# Data Structures & Algorithms Overview

### [1] Data Structure

<details>
<summary><strong>1. Array</strong></summary>

- Insert data  
- Delete data  
- Sorting data  
- Change array data  

</details>

<details>
<summary><strong>2. Linked List</strong></summary>

- Singly  
- Doubly  
- Circular  

</details>

<details>
<summary><strong>3. Stack</strong></summary>

- LIFO → <code>Last In First Out</code>  

</details>

<details>
<summary><strong>4. Queue</strong></summary>

- FIFO → <code>First In First Out</code>  
- Enqueue → Add Object  
- Dequeue → Remove Object  
- Priority Queue  

</details>

<details>
<summary><strong>5. Hash Table / Dictionary</strong></summary>

- Hashing Search  

</details>

<details>
<summary><strong>6. Tree</strong></summary>

- Binary Search Tree  

</details>

<details>
<summary><strong>7. Graph</strong></summary>

- Representation  
- Traversal  

</details>

---

### [2] Algorithm

<details>
<summary><strong>1. Search Algorithms</strong></summary>

- Linear Search  
- Binary Search  

</details>

<details>
<summary><strong>2. Sorting Algorithms</strong></summary>

- Bubble Sort  
- Selection Sort  
- Insertion Sort  
- Merge Sort  
- Quick Sort  

</details>

<details>
<summary><strong>3. Complexity</strong></summary>

- Big O Notation  
- Space Complexity  

</details>

<details>
<summary><strong>4. Divide & Conquer</strong></summary>
</details>

<details>
<summary><strong>5. Dynamic Programming</strong></summary>
</details>

<details>
<summary><strong>6. Tree Algorithms</strong></summary>

- BFS (Breadth-First Search)  
- DFS (Depth-First Search)  

</details>

<details>
<summary><strong>7. Graph Algorithms</strong></summary>

- Bellman-Ford Algorithm  

</details>

----
# Stack Data Stracture in C

- Stack কি ?
- Stack কেন লাগে?
- Stack কোডি করতে কি কি লাগবে?
- **Push()**, **pop()** & **peek()** কি?

<br>

- Push() => মানে একটা আইটেম যোগ করা।
- Pop() => মানে একটা আইটেম বিয়োগ করা।
- peek() => স্টেক এর উপরের মান রির্টান করে।

<br>

<details>
<summary><strong>Stack এর কোড কিভাবে করব।<strong></summary>
    
- একটা Array বা List নিবো, যেটাকে আমরা stack হিসেবে চিন্তা করব।

</details>

<br>

<details>
<summary><strong>Stack Rule: Last in first Out (LIFO).</strong></summary>

- push(item): put items on top of the stack
- pop(): Remove one item from top of the stack
- peek(): Returns the value of top item in the stack

</details>

<br>

### Let's See Example with Code:

```c
#include<stdio.h>
#define capacity 3

int stack[capacity];
int top = -1;

void push(int x)
{
    if(top < capacity - 1)
    {
        top = top + 1;
        stack[top] = x;
        printf("Successfully added item: %d\n",x);
    }

    else
        printf("\nException! No Spaces\n");
}

int pop()
{
    if(top >= 0)
    {
        int val = stack[top];
        top = top - 1;
        return val;
    }

    printf("Exception from pop! Empty Stack\n");
    return -1;
}


int peek()
{
    if(top >= 0)
    {
        return stack[top];
    }
    printf("Exception from peek! Empty Stack\n");
    return -1;
}

int main()
{
    printf("Implementing my stack in C.\n");
    //peek();
    push(10);
    push(20);
    push(40);
    //printf("pop item: %d.\n",pop());
    push(21);
    //printf("Top of Stack %d\n",peek());
    return 0;
}
```

<br>

<details>
<summary>Explanation:</summary>

<br>

### [1] Stack Setup

```c
#define MAX 3
int stack[MAX]; // Array to hold stack elements
int top = -1;   // Index of the top element (starts empty)
```

- `MAX`: The size of the stack.
- `stack[]`: Where we store our data.
- `top`: Tells us the position of the current top. Starts at -1 (empty stack).

<br>
<br>

### [2] push() -> Add Element to stack

```c
void push(int x)
{
    if(top == Max - 1)
    printf("Stack Overflow.\n");

    else{
        top = top + 1; // top++
        stack[top] = x;
        printf("%d pushed to stack.\n",x);
    }
}
```

- Check if the stack is full.
- If not full, moves `top` up and stroes `value` there.

<br>
<br>

### [3] pop() -> Remove element from stack

```c
int pop()
{
    if(top == -1)
    {
        printf("Stack overflow\n");
        return -1;
    }

    else{
        int val = stack[top];
        top = top - 1; // top --
        printf("%d popped from stack\n",val);
        return val;
    }
}
```

- Checks if the stack is empty.
- If not, gets the top value, decreases `top`, and returns the value.

<br>
<br>

### [4] peek() -> See the top value (without removing)

```c
int peek()
{
    if(top == -1)
    {
        printf("Stack is empty.\n");
        return -1;
    }

    else{
        return stack[top];
    }
}
```

- Shows the top value of the stack but does not remove it.


<br>
<br>

### [5] Main() -> Testing all functions

```c
int main() {
    push(10);
    push(20);
    push(30);
    
    printf("Top element is %d\n", peek()); // Should be 30
    
    pop(); // Removes 30
    pop(); // Removes 20
    
    printf("Top element is %d\n", peek()); // Should be 10
    
    return 0;
}
```

---

## [1] If we use `int stack[3];`. What issue will be happend?

- What This means:
    - `stack[3]` -> Creates an array that can hold 3 items.
    - `top = -1` -> Tell us the stack is currently empty.

<br>

- **What Issues Might Happen Late**
    - If you don't write `push()` & `pop()` functions properly, you might face these issues:

<br>
<br>

### [2] Stack Overflow

if you try to push more then 3 elements:

```c
push(4); // if top >= 9, stack[10] will overflow (array out of bounds)
```

- **Problem:** Writing to memory beyond the array (undefined behavior).

<br>

**solution:** Check this in your push function:

```c
if(top == 2)
{
    printf("Stack Overflow.\n");
}
```

<br>
<br>

### [4] Stack Underflow

- if you pop when the stack is empty (i.e., top == -1):

```c
pop(); // nothing to pop
```

- **Problem:** Reading from invalid memory.

<br>

- **Solution:** Add a Check

```c
if (top == -1)
{
    printf("Stack Underflow.\n");
}
```

<br>
<br>

### [5] Accessing uninitialized memory

- If you print or `stack[top]` without pushing any data first:

```c
printf("%d",stack[top]); // top = -1 -> invalid
```

- **Problem:** You are reading from a wrong memory index.

</details>