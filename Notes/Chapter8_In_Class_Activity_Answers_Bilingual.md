# CPSC 1050 Chapter 8 ADT – 课堂练习答案（中英双语）
# Chapter 8 ADT In-Class Activity – Bilingual Answers

---

## Question 1 | 第 1 题

**题目 (Full question):**  
What is the difference between the logical level and the implementation level when discussing abstract data types?

**题目（中文）：**  
在讨论抽象数据类型时，逻辑层（logical level）和实现层（implementation level）有什么区别？

---

**答案 / Answer**

**中文：**  
- **逻辑层 (Logical level)**：只关心 ADT **能做什么**——有哪些操作、行为是什么（如栈的 Push/Pop、LIFO），不关心数据在内存里怎么存。  
- **实现层 (Implementation level)**：关心**具体怎么做到**——用数组还是链表、指针怎么指、下标怎么算等。

**English:**  
- **Logical level**: What the ADT *does*—operations and behavior (e.g., stack: Push, Pop, LIFO). No storage details.  
- **Implementation level**: *How* it is done—array vs linked list, pointers, indices, etc.

---

## Question 2 | 第 2 题

**题目 (Full question):**  
Why are data structures like stacks and queues referred to as Abstract Data Types (ADT)? What makes them "abstract" compared to other data structures?

**题目（中文）：**  
为什么像栈和队列这样的数据结构被称为抽象数据类型（ADT）？与其他数据结构相比，它们的“抽象”体现在哪里？

---

**答案 / Answer**

**中文：**  
因为它们只定义**操作语义**（栈：一端进出一端、LIFO；队列：一端进另一端出、FIFO），不规定用数组还是链表等**具体实现**。使用者只依赖“栈/队列”的抽象行为，所以是 ADT。

**English:**  
They define only the *semantics* of operations (stack: one end, LIFO; queue: enqueue at one end, dequeue at the other, FIFO), not the *implementation* (array, linked list, etc.). Users rely on the abstract behavior, so they are ADTs.

---

## Question 3 | 第 3 题

**题目 (Full question):**  
Imagine you're building an undo feature for a text editor. How would you use a stack to implement this feature? Describe how the push and pop operations would work in this context.

**题目（中文）：**  
假设你正在为文本编辑器实现“撤销”功能。你会如何用栈来实现？请描述在该场景下 push（入栈）和 pop（出栈）操作是如何工作的。

---

**答案 / Answer**

**中文：**  
- 用户每次编辑（输入、删除等）后，把**当前状态**（或“操作/命令”）**Push** 入栈。  
- 用户点 Undo 时，**Pop** 栈顶，得到上一个状态（或撤销上一步操作），并恢复到该状态。  
- 多次 Undo = 多次 Pop，按“后进先出”依次回到更早的状态。

**English:**  
- After each edit, **Push** the current state (or the operation) onto the stack.  
- On Undo, **Pop** the top to get the previous state and restore it.  
- Multiple Undos = multiple Pops (LIFO).

---

## Question 4 | 第 4 题

**题目 (Full question):**  
This question asks to determine the final content of a stack after a given sequence of operations, starting with an initially empty stack. The elements should be listed from top to bottom.  
Operations: (1) Push(5) (2) Push(10) (3) Push(15) (4) Pop() (5) Push(20) (6) Pop()

**题目（中文）：**  
从空栈开始，按下列顺序执行操作后，栈的最终内容是什么？请按从栈顶到栈底的顺序列出元素。  
操作序列：(1) Push(5) (2) Push(10) (3) Push(15) (4) Pop() (5) Push(20) (6) Pop()

---

**答案 / Answer**

| Step | Operation   | Stack (top → bottom) |
|------|-------------|----------------------|
| 1    | Push(5)     | 5                    |
| 2    | Push(10)    | 10, 5                |
| 3    | Push(15)    | 15, 10, 5            |
| 4    | Pop()       | 10, 5                |
| 5    | Push(20)    | 20, 10, 5            |
| 6    | Pop()       | 10, 5                |

**Answer / 答案：** From top to bottom: **10, 5**（栈内只剩 10 和 5，栈顶是 10）

---

## Question 5 | 第 5 题

**题目 (Full question):**  
This question asks to determine the final content of a queue after a given sequence of operations, starting with an initially empty queue. The elements should be listed from front to back.  
Operations: (1) Enqueue(10) (2) Enqueue(20) (3) Enqueue(30) (4) Dequeue() (5) Enqueue(40) (6) Dequeue()

**题目（中文）：**  
从空队列开始，按下列顺序执行操作后，队列的最终内容是什么？请按从队头到队尾的顺序列出元素。  
操作序列：(1) Enqueue(10) (2) Enqueue(20) (3) Enqueue(30) (4) Dequeue() (5) Enqueue(40) (6) Dequeue()

---

**答案 / Answer**

| Step | Operation   | Queue (front → back) |
|------|-------------|----------------------|
| 1    | Enqueue(10) | 10                   |
| 2    | Enqueue(20) | 10, 20               |
| 3    | Enqueue(30) | 10, 20, 30          |
| 4    | Dequeue()   | 20, 30               |
| 5    | Enqueue(40) | 20, 30, 40           |
| 6    | Dequeue()   | 30, 40               |

**Answer / 答案：** From front to back: **30, 40**

---

## Question 6 | 第 6 题

**题目 (Full question):**  
This question describes a "shopping list" that supports add, remove, and view operations.  
- **Initial state:** The list contains [Milk, Eggs, Bread].  
- **Operations:** Add "Butter" to the list; Remove "Eggs" from the list; View: Get the next item in the list.  
What is the final state of the shopping list after these operations? List the items in order.

**题目（中文）：**  
某“购物清单”支持添加、删除和查看下一项操作。  
- **初始状态：** 列表中为 [Milk, Eggs, Bread]（牛奶、鸡蛋、面包）。  
- **操作：** 添加 "Butter"（黄油）；删除 "Eggs"（鸡蛋）；查看：取列表中的下一项。  
完成以上操作后，购物清单的最终状态是什么？请按顺序列出各项。

---

**答案 / Answer**

**中文：**  
Add Butter → [Milk, Eggs, Bread, Butter]。Remove Eggs → [Milk, Bread, Butter]。View next 表示“取下一项”（通常从当前指针取并可能前移）。若从表头开始取下一项，取到 Milk 后列表内容不变。  
**Final list (order): Milk, Bread, Butter.**

**English:**  
After Add and Remove, list is Milk, Bread, Butter. “Get next item” returns the next item (e.g. Milk if we’re at the start); the list content remains **Milk, Bread, Butter**.

---

## Question 7 | 第 7 题

**题目 (Full question):**  
Consider a sequence of operations performed on a linked list:  
(1) Insert(10) (2) Insert(20) (3) Insert(30) (4) Remove(20) (5) Insert(40)  
What is the final state of the linked list after these operations? List the elements in order from head to tail.

**题目（中文）：**  
对链表依次执行以下操作：(1) Insert(10) (2) Insert(20) (3) Insert(30) (4) Remove(20) (5) Insert(40)。  
这些操作完成后，链表的最终状态是什么？请按从表头到表尾的顺序列出各元素。

---

**答案 / Answer**

**中文：**  
Insert 10,20,30 → 头到尾 10 → 20 → 30。Remove(20) 后为 10 → 30。Insert(40) 若在尾部插入则 10 → 30 → 40。  
**Answer / 答案：** **10, 30, 40** (head to tail)

---

## Question 8 | 第 8 题

**题目 (Full question):**  
What is the difference between a binary tree and a binary search tree (BST)? Provide an example of how the values are organized in each type of tree.

**题目（中文）：**  
二叉树（binary tree）和二叉搜索树（BST）有什么区别？请分别举例说明两种树中数值是如何组织的。

---

**答案 / Answer**

**中文：**  
- **二叉树 (Binary tree)**：只有“形状”约束——每个节点最多两个子节点，无大小顺序。  
- **二叉搜索树 (BST)**：在二叉树基础上增加**有序性**——任意节点值 &gt; 左子树所有值，&lt; 右子树所有值。  
- **Example:**  
  - Binary tree: 根 10，左子 20，右子 5 也可以。  
  - BST: 根 10，左子必须 &lt; 10（如 5），右子必须 &gt; 10（如 20）。

**English:**  
- **Binary tree**: Only shape—at most two children per node; no ordering.  
- **BST**: Same shape + **ordering**—value at any node &gt; all in left subtree, &lt; all in right subtree.  
- Example: In a BST, root 10 → left subtree all &lt; 10, right subtree all &gt; 10.

---

## Question 9 | 第 9 题

**题目 (Full question):**  
Given the following sequence of values: 15, 10, 20, 8, 12, 18, 25, insert them into an empty binary search tree in the given order. What is the final structure of the tree?

**题目（中文）：**  
将数值 15, 10, 20, 8, 12, 18, 25 按给定顺序依次插入一棵空的二叉搜索树。树的最终结构是什么？

---

**答案 / Answer**

- 15 → root  
- 10 &lt; 15 → left of 15  
- 20 &gt; 15 → right of 15  
- 8 &lt; 15, 8 &lt; 10 → left of 10  
- 12 &lt; 15, 12 &gt; 10 → right of 10  
- 18 &gt; 15, 18 &lt; 20 → left of 20  
- 25 &gt; 15, 25 &gt; 20 → right of 20  

**结构（文字描述）：**  
根 15；左子树根 10（左子 8，右子 12）；右子树根 20（左子 18，右子 25）。

```
        15
       /  \
     10    20
    / \   /  \
   8  12 18  25
```

**Answer / 答案：** 上述树结构；中序遍历 (In-order) 结果为：8, 10, 12, 15, 18, 20, 25。

---

## Question 10 | 第 10 题

**题目 (Full question):**  
What is the difference between a directed graph (digraph) and an undirected graph? Provide an example of when each would be used in real-world applications.

**题目（中文）：**  
有向图（directed graph / digraph）和无向图（undirected graph）有什么区别？请分别举一个在实际应用中会使用它们的例子。

---

**答案 / Answer**

**中文：**  
- **有向图 (Directed graph)**：边有方向，A→B 不代表 B→A。例：网页链接、航班单方向、依赖关系。  
- **无向图 (Undirected graph)**：边无方向，A-B 即双向。例：社交好友关系、城市之间的道路（若可双向行驶）。

**English:**  
- **Directed**: Edges have direction (A→B ≠ B→A). E.g. hyperlinks, one-way flights, dependencies.  
- **Undirected**: Edges have no direction (A-B = B-A). E.g. friend connections, two-way roads.

---

## Question 11 | 第 11 题

**题目 (Full question):**  
Imagine you are tasked with implementing a graph traversal algorithm for a network of cities connected by roads. The goal is to find all possible routes from a given city to others, using a Depth-First Search (DFS) approach.  
**(a)** Which ADT would you use to represent the network of cities and the connections between them?  
**(b)** What ADT would you use to track the cities visited during the DFS traversal, and why?

**题目（中文）：**  
假设你需要为“由道路连接的城市网络”实现图遍历算法，目标是使用深度优先搜索（DFS）找出从某一城市到其他城市的所有可能路线。  
**(a)** 你会用哪种抽象数据类型（ADT）来表示城市网络以及城市之间的连接？  
**(b)** 在 DFS 遍历过程中，你会用哪种 ADT 来记录已访问的城市？为什么？

---

**答案 / Answer**

**(a) ADT to represent the network of cities and connections? / 用哪种 ADT 表示城市网络与连接？**  
**中文：** **图 (Graph)**——顶点 = 城市，边 = 道路/连接。  
**English:** **Graph** (vertices = cities, edges = roads/connections).

**(b) ADT to track cities visited during DFS, and why? / 用哪种 ADT 记录 DFS 中已访问城市？为什么？**  
**中文：** 用**栈 (Stack)** 保存“当前路径”或“待访问节点”——DFS 沿一条路走到底再回溯，与 LIFO 一致。也可用集合/布尔数组专门记录“已访问”，但“下一步要访问谁”用栈实现 DFS。  
**English:** **Stack** to hold the current path or “to-visit” nodes—DFS goes deep then backtracks (LIFO). (A separate “visited” set or array is often used as well.)

---

## Question 12 | 第 12 题

**题目 (Full question):**  
Consider the given graph. Perform Depth-First Search (DFS) starting from node A. Fill in the table to show the state of the stack and the nodes visited at each step.  
Graph structure: A is connected to B and C; B is connected to A, D, and E; C is connected to A, E, and F; D is connected to B; E is connected to B and C; F is connected to C.

**题目（中文）：**  
对给定的图从节点 A 开始进行深度优先搜索（DFS）。请填写表格，写出每一步的栈状态和已访问的节点。  
图的结构：A 与 B、C 相连；B 与 A、D、E 相连；C 与 A、E、F 相连；D 与 B 相连；E 与 B、C 相连；F 与 C 相连。

---

**答案 / Answer**

假设邻接按字母序访问（如 A 的邻居先 B 后 C）：

| Step | Stack (top on left) | Node Visited | Explain |
|------|---------------------|--------------|---------|
| 1    | A                   | A            | 访问 A，将 A 的未访问邻居 B,C 入栈（如 C 先入则 B 在顶）。 |
| 2    | B, C                | B            | 弹出 B 并访问，B 的未访问邻居 D,E 入栈。 |
| 3    | D, E, C             | D            | 弹出 D 并访问，D 无未访问邻居。 |
| 4    | E, C                | E            | 弹出 E 并访问，E 的未访问邻居（若 C 未访问则 C）入栈。 |
| 5    | C                   | C            | 弹出 C 并访问，C 的未访问邻居 F 入栈。 |
| 6    | F                  | F            | 弹出 F 并访问，栈空，结束。 |

**访问顺序 (DFS order):** A, B, D, E, C, F（具体顺序取决于邻接顺序约定）。

---

## Question 13 | 第 13 题

**题目 (Full question):**  
Consider the given graph. Perform a Breadth-First Search (BFS) starting from node A. Fill in the table to show the state of the queue and the nodes visited at each step.  
Graph structure (tree-like): Level 1: A; Level 2: B and C (children of A); Level 3: D and E (children of B), F (child of C).

**题目（中文）：**  
对给定的图从节点 A 开始进行广度优先搜索（BFS）。请填写表格，写出每一步的队列状态和已访问的节点。  
图的结构（类似树）：第一层 A；第二层 B、C（A 的子节点）；第三层 D、E（B 的子节点），F（C 的子节点）。

---

**答案 / Answer**

| Step | Queue (front → back) | Node Visited | Notes |
|------|----------------------|--------------|-------|
| 1    | A                    | A            | 入队 A 并访问。 |
| 2    | B, C                 | B            | 出队 A，A 的邻居 B,C 入队；出队 B 并访问。 |
| 3    | C, D, E              | C            | 出队 B 后 B 的邻居 D,E 入队；出队 C 并访问。 |
| 4    | D, E, F              | D            | 出队 C 后 C 的邻居 F 入队；出队 D 并访问。 |
| 5    | E, F                 | E            | 出队 E 并访问。 |
| 6    | F                   | F            | 出队 F 并访问，队列空，结束。 |

**BFS 访问顺序：** A, B, C, D, E, F（层序）。

---

## Question 14 | 第 14 题

**题目 (Full question):**  
Explain the concept of "parameter passing" in subprograms. What are the differences between "pass-by-value" and "pass-by-reference"?

**题目（中文）：**  
解释子程序中“参数传递”（parameter passing）的概念。传值（pass-by-value）与传引用（pass-by-reference）有什么区别？

---

**答案 / Answer**

**中文：**  
- **参数传递 (Parameter passing)**：调用子程序时把**实参**交给**形参**的方式。  
- **传值 (Pass-by-value)**：传的是实参的**副本**；子程序内修改形参不影响调用方的变量。  
- **传引用 (Pass-by-reference)**：传的是实参的**地址**；子程序内修改形参会改变调用方对应变量的值。  
- 若子程序需要把结果写回调用方（如修改 list、数组），应使用引用参数。

**English:**  
- **Parameter passing**: How arguments are given to the subprogram’s parameters.  
- **Pass-by-value**: A **copy** is passed; changes inside the subprogram do **not** affect the caller’s variable.  
- **Pass-by-reference**: The **address** is passed; changes inside the subprogram **do** affect the caller’s variable.  
- Use reference when the subprogram must update the caller’s data (e.g. list, array).

---

*来源：Chapter 8 ADT In-Class Activity（课堂练习 1–14 题）*
