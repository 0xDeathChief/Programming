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

# ডাটা স্ট্রাকচার ২ ধরনের হয়ে থাকেঃ

1. primitive Data Structure 
    - Interger
    - Float
    - Character
    - Pointer

<br>

2. Non Primitive Data Structure
    - linear List
        - Array
        - Link List
        - Stack
        - Queue
    
    - Non-Linear List
        - Graph
        - Trees

<br>

--- 

## ডাটা স্ট্রাকচার এর অ্যারেতে সাধারনত ৬ ধরনের অপারেশন হয়ে থাকে।

1. Traversing
2. Searching
3. Inserting
4. Deleting
5. Sorting
6. Merging

<br>

- **=> Traversing:** মানে হচ্ছে ভ্রমন করা। যেমন আমার ক্লাসে ৪০ টি চেয়ার আছে, আমি প্রত্যেকটি চেয়ার ঘুরে ঘুরে দেখলাম এইটাকে আমরা ট্রাভারসিং (Traversing) বলতে পারি। এখন এইটা আমরা কিভাবে কোডে প্রয়োগ করতে পারি।

<br>

- **Static type in travarsing.**

```c
#include<stdio.h>
int main()
{
    int arr[5]={1,2,3,4,5};

    for(int i = 0; i < 5; i++)
        printf("arr [%d] = %d\n",i, arr[i]);


    return 0;
}
```
<br>

ব্যাখ্যাঃ 

<details><summary><strong>#include<stdio.h></strong></summary><br>

- এটি একটি header file
- `stdio.h` মানে Standard Input Output Header
- এখানে printf() ফাংশনটি ব্যবহারের জন্য এই লাইব্রেরি দরকার হয়।

<br>

</details>

<details><summary><strong>int main()</strong></summary><br>

- প্রতিটি C প্রোগ্রামের প্রধান ফাংশন হলো main()।
- প্রোগ্রাম এখান থেকেই শুরু হয়।

<br>

</details>

<details><summary><strong>int arr[5] = {1, 2, 3, 4, 5};</strong></summary><br>

- এখানে একটি পুরো সংখ্যা টাইপের অ্যারে ডিক্লিয়ার করা হয়েছে যার সাইজ ৫।
- অ্যারেটিতে শুরুতেই মান দেওয়া হয়েছে: ১, ২, ৩, ৪, ৫
- অ্যারেটির ইনডেক্স ০ থেকে ৪ পর্যন্ত যাবে:

```c
arr[0] = 1
arr[1] = 2
arr[2] = 3
arr[3] = 4
arr[4] = 5
```

<br>

</details>

<details><summary><strong>for (int i = 0; i < 5; i++)</strong></summary><br>

- এটি একটি for loop, যেখানে:
    - `int i = 0;` → লুপ শুরু হচ্ছে ০ থেকে
    - `i < 5;` → যতক্ষণ i পাঁচের চেয়ে ছোট, লুপ চলবে
    - `i++` → প্রতিবার লুপ চলার পর i এক করে বাড়বে

<br>

</details>

<details><summary><strong>printf("arr [%d] = %d\n", i, arr[i]);</strong></summary><br>

- এটি printf() ফাংশন, যা স্ক্রিনে তথ্য দেখায়।
- এখানে i মানে ইনডেক্স এবং arr[i] মানে সেই ইনডেক্সে থাকা মান।
- উদাহরণস্বরূপ, প্রথমবার:

```c
arr [0] = 1
```

```c
return 0;
```

- main() ফাংশনের শেষে return 0; মানে হচ্ছে প্রোগ্রাম সফলভাবে শেষ হয়েছে।

<br>

</details>

### **নিজে করোঃ রিভার্স ট্রার্ভাসিং করো।**

---

## ডায়নামিক ট্রার্ভাসিং

- এইখানে আমরা সব কিছু ইউজার থেকে ইনপুট নিয়ে করবাে।

```c
#include<stdio.h>

int main()
{
    int i,k;

    printf("Enter the array size:");
    scanf("%d",&i);

    int arr[i];

    printf("\n\nEnter the array Element:");

    for(int j=0; j < i; j++)
    {
        scanf("%d",&arr[j]);
    }

    printf("\n\n");

    for(int j=0; j < i; j++)
    {
        printf("arr[%d]=%d\n",j,arr[j]);
    }

    return 0;
}
```

<br>

ব্যাখ্যাঃ 

<details><summary><strong>#include<stdio.h></strong></summary><br>

- ইনপুট-আউটপুটের জন্য `stdio.h` লাইব্রেরি যুক্ত করা হয়েছে।

<br>

</details>

<details><summary><strong>int i, k;</strong></summary><br>

- `i` হবে অ্যারের সাইজ, `k` আপাতত ব্যবহার হয়নি (মুছে ফেললেও চলে)।

<br>

</details>

<details><summary><strong>scanf("%d", &i);</strong></summary><br>

- ইউজার কতগুলো সংখ্যা ইনপুট দেবে, সেটা নিচ্ছো।

<br>

</details>

<details><summary><strong>int arr[i];</strong></summary><br>

- এখানে C99 এর ফিচার ব্যবহার করে Variable Length Array (VLA) বানানো হয়েছে।

<br>

</details>

<details><summary><strong>for (int j = 0; j < i; j++) { scanf("%d", &arr[j]); }</strong></summary><br>

- ইউজার যত সংখ্যক ইনপুট দেবে, প্রতিটা `arr[j]` তে সেভ হচ্ছে।

<br>

</details>

<details><summary><strong>for (int j = 0; j < i; j++) { printf("arr[%d]=%d\n", j, arr[j]); }</strong></summary><br>

- অ্যারে থেকে সব ভ্যালু ইনডেক্স সহ প্রিন্ট হচ্ছে।

<br>

</detail>

### **নিজে করোঃ রিভার্স ডায়নামিক ট্রার্ভাসিং করো।**