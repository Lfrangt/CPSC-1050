# Chapter 8: Abstract Data Types and Subprograms
# 第八章：抽象数据类型与子程序

---

# 📖 Slide 1–2: Chapter Goals | 本章目标

**中文：** 学完本章，你将能够：

**English:** After completing this chapter, you will be able to:

1. **区分数组与列表**  
   Distinguish between an array and a list

2. **区分无序列表与有序列表**  
   Distinguish between an unsorted list and a sorted list

3. **区分栈与队列的行为**  
   Distinguish between the behavior of a stack and a queue

4. **区分二叉树与二叉搜索树**  
   Distinguish between the binary tree and a binary search tree

5. **画出由一系列插入操作构建的二叉搜索树**  
   Draw the binary search tree that is built from inserting a series of items

6. **理解树与图的区别**  
   Understand the difference between a tree and a graph

7. **解释子程序与参数的概念，区分值参数与引用参数**  
   Explain the concept of subprograms and parameters and distinguish between value and reference parameters

---

# 📖 Slide 3–4: Abstract & Abstract Data Types | 抽象与抽象数据类型

**中文：**

- **抽象 (Abstraction)**：不关心实现细节，关注**简洁**与**直观理解**。  
  例：把“爱”理解为一种感受 vs 理解为神经元的放电。

- **数据结构 (Data Structure)**：用来**组织数据**的方式。

- **抽象数据类型 (ADT, Abstract Data Type)**：  
  只定义数据的**逻辑操作**与**行为**，不规定具体如何存储或实现。

**English:**

- **Abstraction**: Does not worry about implementation details; focuses on **simplicity** and **intuitive understandability**.  
  E.g., love as a feeling vs. firing of neurons.

- **Data structure**: A way of **organizing your data**.

- **Abstract Data Type (ADT)**:  
  Defines only the **logical operations** and **behavior** of the data, not how it is stored or implemented.

**关键概念：**
- **ADT** - 抽象数据类型：逻辑视图，与实现分离
- **Data structure** - 数据结构：组织数据的方式

---

# 📖 Slide 5–7: Stacks | 栈

**中文：**

- **栈 (Stack)** 是一种只在**一端**进行存取操作的抽象数据类型。
- **LIFO** = **Last In First Out**（后进先出）。
- **Push**：插入元素（入栈）。
- **Pop**：删除/取出元素（出栈）。
- 日常例子：一摞盘子、摞起来的书、浏览器后退按钮用的历史记录。

**English:**

- A **stack** is an ADT in which accesses are made at **only one end**.
- **LIFO** = **Last In, First Out**.
- **Push**: Insert an item.
- **Pop**: Remove/delete an item.
- Everyday examples: stack of plates, stack of books, browser back-button history.

**伪代码示例（带行末中文注释）：**

```
WHILE (more data)                    // 当还有数据时
    Read value                       // 读入一个值
    Push(myStack, value)             // 将该值压入栈
WHILE (NOT IsEmpty(myStack))         // 当栈非空时
    Pop(myStack, value)              // 弹出栈顶到 value
    Write value                      // 输出 value
```

**📝 Class Activity 答案（Slide 8）：**  
Push 5, 4, 4 → 栈顶到栈底：4, 4, 5。  
Pop → item=4；再 Pop → item=4；Push(item) → 又压入 4；栈中剩 5, 4。  
WHILE 依次 Pop 输出：先 4，再 5。  
**输出：4 5**

---

# 📖 Slide 9–11: Queues | 队列

**中文：**

- **队列 (Queue)**：在一端**入队**、在另一端**出队**的抽象数据类型。
- **FIFO** = **First In First Out**（先进先出）。
- 入队操作常见叫法：Enqueue, Enque, Enq, Enter, Insert。
- 出队操作常见叫法：Dequeue, Deque, Deq, Delete, Remove。

**English:**

- A **queue** is an ADT in which items are **entered at one end** and **removed from the other end**.
- **FIFO** = **First In, First Out**.
- Insert: Enqueue, Enque, Enq, Enter, Insert.
- Delete: Dequeue, Deque, Deq, Delete, Remove.

**伪代码示例：**

```
WHILE (more data)                    // 当还有数据时
    Read value                       // 读入值
    Enque(myQueue, value)           // 从队尾入队
WHILE (NOT IsEmpty(myQueue))         // 当队列非空时
    Deque(myQueue, value)            // 从队头出队
    Write value                      // 输出
```

**📝 Class Activity 答案（Slide 11）：**  
Enqueue 5, 4, 4 → 队列：5, 4, 4（Front 到 Back）。  
Dequeue → item=5；Dequeue → item=4；Enqueue(item) → 把 4 再入队；队列变为 4, 4。  
WHILE 依次 Dequeue 输出：4, 4。  
**输出：4 4**

---

# 📖 Slide 12–14: Lists | 列表

**中文：**

- **列表 (List)**：可视为**项的容器**，与“数组”不同——列表强调**逻辑操作**，不规定物理存储。
- 常见逻辑操作：
  - **Add item**：把一项放入列表
  - **Remove item**：从列表中移除一项
  - **Get next item**：获取（查看）下一项
  - **more items**：是否还有更多项？

**English:**

- A **list** is a container of items. It is an abstraction; implementation may be array or linked.
- Logical operations: **Add item**, **Remove item**, **Get next item**, **more items?**

**伪代码：创建列表并打印（行末中文注释）：**

```
WHILE (more data)                    // 当还有数据时
    Read value                       // 读入值
    Insert(myList, value)            // 将值插入列表
Reset(myList)                        // 将“当前指针”重置到开头
Write "Items in the list are "       // 输出提示
WHILE (moreItems(myList))            // 当还有更多项时
    GetNext(myList, nextItem)        // 取下一项
    Write nextItem, ' '              // 输出该项和空格
```

---

# 📖 Slide 15–17: Trees | 树

**中文：**

- 列表、栈、队列是**线性**的，只表示一种前后关系。
- **树 (Tree)** 是**非线性、层次化**的结构，用于表示更复杂的关系。
- **二叉树 (Binary tree)**：  
  一种链式容器，有唯一**根节点 (root)**，每个节点最多有**两个子节点**，从根到任意节点存在**唯一路径**。
- 术语：根节点、叶节点 (leaf)、左子/右子 (left child / right child)。

**English:**

- Lists, stacks, queues are **linear**—only one relationship is modeled.
- A **tree** is a **nonlinear, hierarchical** structure.
- **Binary tree**: A linked container with a unique **root**, each node capable of having **two child nodes**, and a **unique path** from the root to every other node.

**关键概念：**
- **Root** - 根节点：树的唯一起点
- **Leaf node** - 叶节点：没有子节点的节点
- **Path** - 路径：从根到某节点经过的节点序列

---

# 📖 Slide 18–20: Binary Search Trees (BST) | 二叉搜索树

**中文：**

- **二叉搜索树 (Binary Search Tree, BST)** = 二叉树的**形状** + **语义性质**：  
  任意节点的值 **大于** 其**左子树**中所有节点的值，**小于** 其**右子树**中所有节点的值。
- 因此中序遍历 (左→根→右) 会得到**有序序列**。

**English:**

- **Binary search tree (BST)**: A binary tree (shape) with the property:  
  The value in any node is **greater than** all values in its **left subtree** and **less than** all values in its **right subtree**.

---

# 📖 Slide 21–23: Searching a BST | 在二叉搜索树中查找

**中文：**  
从根开始：若当前节点为空则未找到；若等于目标则找到；若目标小于当前值则进左子树，否则进右子树。

**English:**  
Start at root; if null return false; if item equals current node return true; if item < current go left, else go right.

**伪代码（行末中文注释）：**

```
IsThere(tree, item)
    IF (tree is null)                    // 树为空
        RETURN FALSE                     // 未找到
    ELSE
        IF (item equals info(tree))      // 当前节点值等于目标
            RETURN TRUE                  // 找到
        ELSE
            IF (item < info(tree))       // 目标小于当前节点
                IsThere(left(tree), item)   // 在左子树中递归查找
            ELSE
                IsThere(right(tree), item)  // 在右子树中递归查找
```

---

# 📖 Slide 24–26: Building a BST & In-Order Print | 构建二叉搜索树与中序打印

**中文：**  
按给定顺序依次 **Insert**：若树为空则放根；否则与根比较，小则插入左子树，大则插入右子树（递归）。  
**Print(tree)**：若树非空，先 Print 左子树，再 Write 当前节点，再 Print 右子树 → **中序遍历**，输出有序。

**English:**  
Insert: if tree null put item there; else if item < root insert in left subtree, else insert in right subtree.  
Print: if not null, print left, write current, print right → in-order → sorted output.

**伪代码：**

```
Insert(tree, item)
    IF (tree is null)                // 当前位置为空
        Put item in tree             // 将 item 放在此处
    ELSE
        IF (item < info(tree))       // item 小于当前节点
            Insert(left(tree), item) // 插入到左子树
        ELSE
            Insert(right(tree), item)// 插入到右子树

Print(tree)
    IF (tree is not null)             // 树非空
        Print(left(tree))            // 先打印左子树
        Write info(tree)             // 再打印当前节点
        Print(right(tree))           // 再打印右子树
```

**📝 例题：** 用 john, phil, lila, kate, becca, judy, june, mari, jim, sue 建 BST：  
按字符串比较建树，中序遍历得到字母序排列的名字序列。

---

# 📖 Slide 27–33: Graphs | 图

**中文：**

- **图 (Graph)**：由**顶点 (vertices)** 集合和**边 (edges)** 集合组成，边表示顶点之间的关系。  
  例：城市与道路。
- **无向图 (Undirected graph)**：边没有方向。
- **有向图 (Directed graph / Digraph)**：每条边从一个顶点指向另一个（或同一）顶点。

**English:**

- **Graph**: A set of **nodes (vertices)** and a set of **edges** that relate the nodes. E.g., cities and roads.
- **Undirected graph**: Edges have no direction.
- **Directed graph (Digraph)**: Each edge is directed from one vertex to another.

**关键概念：**
- **Vertex (vertices)** - 顶点：图中的节点
- **Edge** - 边：连接两顶点的关系
- **Depth-First Search (DFS)** - 深度优先搜索：沿一条路走到底再回溯
- **Breadth-First Search (BFS)** - 广度优先搜索：先访问完当前层所有相邻顶点，再往下一层；可求**最少步数/最少停靠**

---

# 📖 Slide 34–43: Graph Algorithms | 图算法

**中文：**

- **深度优先 (DFS)**：从起点沿一条分支尽量往深处走，再回溯尝试其他分支；可判断“从 A 能否到 B”并找一条路径。
- **广度优先 (BFS)**：先访问起点所有相邻顶点，再访问这些顶点的相邻顶点，依此类推；适合求**从 A 到 B 的最少边数/最少停靠**（如最少航班中转）。

**English:**

- **Depth-first**: Go as far down one path as possible, then backtrack; find a path from start to end.
- **Breadth-first**: Visit all vertices at distance 1, then distance 2, …; answers “how to get from X to Y in the **fewest** number of stops?”

---

# 📖 例题：Austin 到 Washington | Example: Can We Get from Austin to Washington?

**问题 / Question：** Can we get from Austin to Washington?（能否从 Austin 到 Washington？）

**设定 / Setup：**

- **顶点 (Vertices)** = 城市：Austin, Dallas, Denver, Chicago, Houston, Atlanta, Washington。
- **边 (Edges)** = 直飞航线（有向），边上的数字表示**距离/成本**（如 200, 600, 800 等）。  
  例：Austin→Dallas 200，Dallas→Atlanta 800，Atlanta→Washington 600。

**用栈存路径 / Using a Stack to Store the Routes (FIGURE 8.11)：**

- 用**栈**配合 **DFS**：探索路径时，每到一个城市就 **push**，回溯时 **pop**；栈里存的是**当前路径上的城市**（或待访问城市），旁边的数字（如 800, 200, 600）表示**沿该路径的累计距离/成本**。
- **(a)** 栈里只有 Austin → 从起点开始。
- **(b)** 栈顶 Houston，下面 Dallas → 沿一条分支走到 Houston（深度优先）。
- **(c)** 栈顶 Atlanta (800)，下面 Dallas (200) → 路径上有 Dallas → Atlanta，数字为累计成本。
- **(d)** 栈顶 Washington (600)，下面 Dallas → 已到达 Washington，说明**存在从 Austin 到 Washington 的路径**。

**结论 / Conclusion：**  
**Yes, we can get from Austin to Washington.** 例如一条路径：Austin → Dallas (200) → Atlanta (800) → Washington (600)。

**与本章联系：** 栈 (LIFO) 存路径/待访问顶点；图 = 顶点 + 有向边；DFS 沿一条路走到底再回溯，可回答“从 A 能否到 B”并找出一条路径；求**最少停靠**则用 BFS。

---

# 📖 Slide 44–48: Subprograms and Parameters | 子程序与参数

**中文：**

- **子程序 (Subprogram)**：给一段代码起名，在其他地方通过名字调用；执行到调用处时，主流程暂停，转去执行子程序，执行完再返回。
- **参数 (Parameters)**：子程序需要调用方传入的数据。
  - **形参 (Formal parameters)**：子程序声明时括号里的标识符。
  - **实参 (Arguments / Actual parameters)**：调用时括号里传入的标识符或表达式。
- **值参数 (Value parameter)**：调用方传入的是**副本**；子程序内修改不影响调用方的变量。
- **引用参数 (Reference parameter)**：调用方传入的是**地址**；子程序内修改会改变调用方的变量。

**English:**

- **Subprogram**: A named section of code; when the name is encountered, the calling code halts while the named code runs, then returns.
- **Parameters**: Data the subprogram needs from the caller.
  - **Formal parameters**: Identifiers in the subprogram declaration.
  - **Arguments (actual parameters)**: Identifiers/expressions in the subprogram call.
- **Value parameter**: A **copy** of the argument is passed; changes inside the subprogram do not affect the caller’s variable.
- **Reference parameter**: The **address** of the argument is passed; changes inside the subprogram **do** affect the caller’s variable.

**例子（Slide 48）：**  
`Insert(list, item)` 定义里会修改 `list.values` 和 `list.length`，所以 `list` 通常用**引用参数**；若传的是副本，主程序里的 `myList` 不会被更新。

---

# 📋 术语表 | Terminology

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Abstract Data Type (ADT) | 抽象数据类型 | 只定义逻辑操作与行为，不规定实现的数据类型 |
| Stack | 栈 | LIFO，一端 Push/Pop |
| Queue | 队列 | FIFO，一端 Enqueue、另一端 Dequeue |
| List | 列表 | 项的容器；Add, Remove, GetNext, moreItems |
| Binary tree | 二叉树 | 有根，每节点最多两子，根到每节点唯一路径 |
| Binary Search Tree (BST) | 二叉搜索树 | 左子树 < 根 < 右子树 |
| Graph | 图 | 顶点 + 边；可无向或有向 |
| Vertex (vertices) | 顶点 | 图中的节点 |
| Edge | 边 | 顶点之间的关系 |
| Depth-First Search (DFS) | 深度优先搜索 | 沿一条路走到底再回溯 |
| Breadth-First Search (BFS) | 广度优先搜索 | 按“层”扩展，可求最少步数 |
| Subprogram | 子程序 | 有名字、可被调用的代码块 |
| Parameter | 参数 | 子程序声明中的占位符 |
| Argument | 实参 | 调用时传入的值或变量 |
| Value parameter | 值参数 | 传副本，子程序内修改不影响调用方 |
| Reference parameter | 引用参数 | 传地址，子程序内修改会影响调用方 |

---

# 📝 学习建议 | Study Tips

1. **栈 vs 队列**：记 LIFO vs FIFO，各记一个日常例子（盘子栈 vs 排队）。
2. **BST**：插入、查找、中序打印的伪代码要能手写；会根据一串插入顺序画出 BST 并写出中序序列。
3. **树 vs 图**：树是“无环、有根、分层”；图可有环、可多对多，DFS/BFS 用于路径与最少步数。
4. **值参 vs 引用参**：要改调用方变量用引用，只读或不想被改用值参。
5. **Quiz 重点**：区分 array/list、stack/queue、BST 性质、子程序形参/实参、值参/引用参。

---

*笔记来源：Chapter 8_Post.pdf (48 slides) | 与 Ch7 算法、Ch6 伪代码衔接*
