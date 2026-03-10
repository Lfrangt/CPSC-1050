# Chapter 7: Problem Solving and Algorithms
# 第七章：问题求解与算法

---

# 📖 Slide 1–2: Chapter Goals | 本章目标

**中文：** 学完本章，你将能够：

**English:** After completing this chapter, you will be able to:

1. **描述计算机问题求解过程**  
   Describe the computer problem-solving process

2. **区分简单类型与复合类型**  
   Distinguish between a simple type and a composite type

3. **区分无序数组与有序数组**  
   Distinguish between an unsorted array and a sorted array

4. **应用二分查找算法**  
   Apply the binary search algorithm

5. **能手写应用选择排序、冒泡排序、插入排序和快速排序**  
   Apply selection sort, bubble sort, insertion sort, and Quicksort to an array of items by hand

6. **识别递归问题并写出递归算法**  
   Recognize a recursive problem and write a recursive algorithm to solve it

---

# 📖 Slide 3: Problem Solving | 问题求解

## How do you solve problems? | 如何解决问题？

**中文：**  
四步法：

1. **理解问题** (Understand the problem)  
2. **制定计划** (Devise a plan)  
3. **执行计划** (Carry out the plan)  
4. **回顾检查** (Look back)

**English:**  
Four steps:

1. **Understand the problem**  
2. **Devise a plan**  
3. **Carry out the plan**  
4. **Look back**

**关键概念：**
- **Problem-solving process** - 问题求解过程：理解 → 计划 → 执行 → 回顾

---

# 📖 Slide 4: Algorithms | 算法

## 核心定义 | Core Definitions

**中文：**  

- **Algorithm（算法）**  
  一组**无歧义的**指令，在**有限时间**内用**有限数据**解决问题或子问题。

- **Abstract Step（抽象步骤）**  
  含有未指定细节的算法步骤。

- **Concrete Step（具体步骤）**  
  所有细节都已指定的算法步骤。

**English:**  

- **Algorithm**  
  A set of **unambiguous** instructions for solving a problem or subproblem in a **finite** amount of time using a **finite** amount of data.

- **Abstract Step**  
  An algorithmic step containing unspecified details.

- **Concrete Step**  
  An algorithm step in which all details are specified.

**关键概念：**
- **Unambiguous** - 无歧义：每一步只有一种理解  
- **Finite** - 有限：时间与数据量都要有限

---

# 📖 Slide 5: Developing an Algorithm | 算法开发

**中文：**  
两种设计方法论：

1. **Top-down design（自顶向下设计）**  
   关注**要完成的任务**。

2. **Object-oriented design（面向对象设计）**  
   关注**所涉及的数据**。（第 9 章会讲）

**English:**  
Two methodologies:

1. **Top-down design** — focuses on the **tasks** to be done  
2. **Object-oriented design** — focuses on the **data** involved (Ch. 9)

---

# 📖 Slide 6: Top-Down Design | 自顶向下设计

**中文：**  

- 逐层细化，直到**每一步都变成具体步骤**。
- 某一层的（子）问题名称，在下一层变成**模块 (module)**。

**English:**  

- Process continues until **every step is concrete**.
- The name of a (sub)problem at one level becomes a **module** at the next lower level.

**关键概念：**
- **Module** - 模块：可独立命名、调用的子任务  
- **Refinement** - 细化：把抽象步骤拆成更具体的步骤

---

# 📖 Slide 7: Composite Data Types | 复合数据类型

## Records and Arrays | 记录与数组

**中文：**  

- **Record（记录）**  
  **异质**集合，有名字，通过**名字**访问各项。  
  例：把 name、age、hourlyWage 打成一条记录 `Employee`。

- **Array（数组）**  
  **同质**集合，有名字，通过**位置（下标）**访问各项。

**English:**  

- **Records** — A named **heterogeneous** collection; items accessed **by name** (e.g. Employee: name, age, hourlyWage).
- **Arrays** — A named **homogeneous** collection; items accessed **by position (index)**.

**关键概念：**
- **Heterogeneous** - 异质：元素类型可以不同  
- **Homogeneous** - 同质：元素类型相同  
- **Index** - 下标：数组中的位置，通常从 0 开始

---

# 📖 Slide 8: Composite Data Types – Example | 复合类型示例

**中文：**  
按算法给记录的各个字段赋值：

**English:**  
Following algorithm, store values into the fields of a record:

```
Employee employee                    // 声明一个 Employee 变量 | Declare an Employee variable
Set employee.name to "Frank Jones"   // 设置姓名 | Set name
Set employee.age to 32               // 设置年龄 | Set age
Set employee.hourlyWage to 27.50     // 设置时薪 | Set hourly wage
```

---

# 📖 Slide 9: Unsorted Array | 无序数组

**中文：**  

- 关心范围：`data[0]` … `data[length-1]`。
- **排序 (Sorting)**：把元素在数组内重新排列成**升序**或**降序**。

**English:**  

- Range of interest: `data[0]` … `data[length-1]`.
- **Sorting** rearranges elements into **ascending** or **descending** order within the array.

**关键概念：**
- **Unsorted array** - 无序数组：元素顺序无保证  
- **Sorted array** - 有序数组：按某规则（如数值、字母）排好序

---

# 📖 Slide 10–11: Sequential Search (Unsorted) | 顺序查找（无序）

**中文：**  

- **顺序查找**：逐个检查每一项，与要找的值比较。
- 找到则结束；否则看下一项。
- 结束条件：**找到** 或 **全部看完仍未找到** → 循环有两个结束条件。

**English:**  
Sequential search examines each item in turn; stop when found or when all items have been examined (loop with two ending conditions).

### 伪代码 | Pseudocode

```
Set Position to 0                    // 从第一个位置开始
Set found to FALSE                   // 初始未找到
WHILE (position < length AND found is FALSE)
    IF (numbers[position] equals searchItem)
        Set Found to TRUE            // 找到了
    ELSE
        Set position to position + 1 // 看下一个
```

- 数组名：`numbers`；要找的值在变量 `searchItem` 里。

---

# 📖 Slide 12–13: Booleans | 布尔类型与运算符

**中文：**  

- **Boolean variable（布尔变量）**：只能存 `true` 或 `false`。
- **AND**：两个操作数都为 true 时结果为 TRUE，否则 FALSE。
- **OR**：任一侧为 true 则 TRUE，否则 FALSE。
- **NOT**：操作数为 false 则 TRUE，为 true 则 FALSE。

**English:**  
Boolean variable holds true/false; AND / OR / NOT as in logic.

**关键概念：**
- **Boolean** - 布尔：真/假  
- **AND, OR, NOT** - 与、或、非

---

# 📖 Slide 14–15: Sequential Search (Sorted Array) | 有序数组上的顺序查找

**中文：**  
数组已排序时，若当前元素 **大于** 目标值，后面都不用看了，可直接结束（把 index 设为 length 等），因为后面只会更大。

**English:**  
In a sorted array, if `data[index] > searchItem`, we can stop searching (e.g. set index to length).

### 伪代码 | Pseudocode

```
Set index to 0                       // 从 0 开始
Set found to FALSE                   // 初始未找到
WHILE (index < length AND NOT found)
    IF (data[index] equals searchItem)
        Set found to TRUE            // 找到
    ELSE IF (data[index] > searchItem)
        Set index to length          // 后面更大，提前结束
    ELSE
        Set index to index + 1       // 继续往后
```

---

# 📖 Slide 16–17: Binary Search | 二分查找

**中文：**  

- **顺序查找**：从表头开始，直到找到或查完整个表。
- **二分查找**：**要求表已排序**。从**中间**开始，找到则结束；否则排除一半，在剩下那一半里重复同样过程。

**English:**  
Binary search (list must be sorted): start at the middle; find the item or eliminate half; repeat on the half where the item might be.

### 伪代码 | Pseudocode

```
Set first to 0                       // 左边界
Set last to length - 1              // 右边界
Set found to FALSE                  // 是否找到
WHILE (first <= last AND NOT found)
    Set middle to (first + last) / 2  // 取中间下标（整数除）
    IF (item equals data[middle])
        Set found to TRUE           // 找到
    ELSE
        IF (item < data[middle])
            Set last to middle - 1  // 在左半部分
        ELSE
            Set first to middle + 1 // 在右半部分
RETURN found                        // 返回是否找到
```

**关键概念：**
- **Binary search** - 二分查找：每次比较排除一半  
- **Sorted list required** - 必须先排序

---

# 📖 Slide 18–20: Binary Search – Trace & When to Use

**中文：**  

- 手写时按 **First, Last, found, Middle, Comparison** 列表追踪。
- **二分查找一定更好吗？** 不一定：数据量很小或只查一次时，顺序查找可能更简单；且二分要求先排序。

**English:**  
Trace using First, Last, found, Middle, Comparison. Binary search is not always better (e.g. small list or one-time search; requires sorted data).

---

# 📖 Slide 21–22: Sorting – Definitions | 排序的定义

**中文：**  

- **Sorting（排序）**：按某一（或多个）**字段**的次序重排集合中的元素。
- **Sort Key（排序键）**：作为排序依据的字段。
- **Sorting algorithms**：根据排序键对元素进行排序的算法。

**English:**  
Sorting = arranging items so there is an ordering on one or more fields. Sort key = field(s) used for ordering.

**关键概念：**
- **Sort key** - 排序键  
- **Ascending / Descending** - 升序 / 降序

---

# 📖 Slide 23–33: Simple Sort (Card Example) | 简单排序（扑克牌类比）

**中文：**  

1. 把若干未排序的牌放一排。  
2. 重复：在未排序牌中**比较**，**选出最小的**，移到“已排序”那一排。  
3. 直到未排序排空为止。

**English:**  
Place unsorted cards in a row; repeatedly compare, select the smallest, move to sorted row; repeat until unsorted row is empty.

---

# 📖 Slide 34–35: Sorting Algorithms & Swap | 排序算法列表与交换

**中文：**  
本章要掌握的排序：**Selection Sort, Bubble Sort, Insertion Sort**，以及递归的 **Quicksort**。  
排序前要会**交换 (Swap)** 两个元素。

**English:**  
Selection Sort, Bubble Sort, Insertion Sort, Quicksort. Before sorting, we need to **swap** two elements.

---

# 📖 Slide 36–38: Selection Sort | 选择排序

**中文：**  
**思路：** 每次在“未排序区”里选最小的，和未排序区的**第一个**交换，然后未排序区前移一位。

步骤简述：  
1. 摆一排未排序的牌，在未排序区最前面放一个**标记**。  
2. 重复直到未排序区只剩一张：比较所有未排序牌 → 选最小的 → 与未排序区第一张**交换** → 标记右移一位。  
3. 停止。

**English:**  
Easiest one. Find smallest in unsorted section; swap with first in unsorted section; advance marker.

**关键概念：**
- **Selection Sort** - 选择排序：每次选最小（或最大）放到正确位置  
- **Marker** - 标记：区分已排序与未排序部分

---

# 📖 Slide 39–49: Selection Sort – Passes

**中文：**  
每一轮 (pass)：在未排序部分找最小，与未排序部分第一个交换，标记右移。重复直到全部有序。

**English:**  
Each pass: select smallest in unsorted section, swap with first unsorted, advance marker.

---

# 📖 Slide 50–52: Bubble Sort | 冒泡排序

**中文：**  

- 策略同样是“找下一个该放的数并放到正确位置”，但**找的方式**不同。
- 从**最后一个**元素开始，**逐对比较相邻元素**，若下面比上面小就**交换**（小的一步步“冒”上去）。
- 每轮通常有一个元素到达最终位置（例如升序时每轮把当前最大“沉”到最后）。

**English:**  
Compare successive pairs from the end; swap when bottom element is smaller than the one above. After each iteration, one item is in its permanent place.

**关键概念：**
- **Bubble Sort** - 冒泡排序：相邻比较、交换，大/小值“沉”或“冒”  
- **Iteration** - 一轮：一次完整扫描

---

# 📖 Slide 53–57: Bubble Sort – Examples

**中文：**  
数值例：每轮后有一个数到位（如第一轮后最大数在最后）。  
字母例：较小字母“冒”到前面。

**English:**  
Numeric: after each iteration one item is fixed. Alphabetic: smaller items bubble up.

---

# 📖 Slide 58–59: Insertion Sort | 插入排序

**中文：**  

- 若只有 1 个元素，已有序。  
- 再拿第 2 个，与第 1 个比较并必要时交换，前 2 个有序。  
- 再拿第 3 个，**插入**到前 2 个中的正确位置，前 3 个有序。  
- 依此类推：每次把“未排序区”的**第一张**向左交换到正确位置，然后标记右移。

步骤简述：  
1. 拿一些未排序的牌，在第一张后设**已排序区**标记。  
2. 重复直到未排序区为空：取未排序区第一张 → 向左交换直到到达正确位置 → 标记右移。  
3. 停止。

**English:**  
One item is sorted; add next and insert into correct position among already-sorted items; repeat.

**关键概念：**
- **Insertion Sort** - 插入排序：维护“已排序前缀”，把新元素插入到正确位置  
- **Marker** - 标记已排序与未排序的分界

---

# 📖 Slide 60–64: Insertion Sort – Examples

**中文：**  
每步：取未排序区第一张，向左交换直到前面都不比它大（或小），然后标记右移。

**English:**  
Select first unsorted card; swap left until in correct sorted position; advance marker.

---

# 📖 Slide 65–66: Recursive Algorithm Intro | 递归算法引入

**中文：**  
能否用**更少的比较次数**排序？可以，但需要**递归 (recursion)** 和**子程序 (subprogram)**。  
有时，解决问题的最好办法是先解决**同一个问题的更小版本**——递归就是用“同类型但更小”的问题来求解。

**English:**  
Recursion solves a problem by solving a smaller problem of the same type (e.g. 3! = 3 × 2!).

**关键概念：**
- **Recursion** - 递归  
- **Subprogram（子程序）** - A named block of code that performs a specific task (e.g., function in Python). Recursion = subprogram calling itself. | 完成特定任务的命名代码块（如 Python 的 function），递归即子程序调用自己

---

# 📖 Slide 67–68: Recursion – Definitions | 递归的定义

**中文：**  

- **递归**：子程序**调用自己**的能力。
- **Base case（基本情况）**：能直接给出答案的情况（不再递归）。
- **General case（一般情况）**：用“对自身的、规模更小的调用”来表达解。

**English:**  
Recursion = subprogram calling itself. Base case = case with direct answer. General case = solution in terms of call with smaller problem.

**关键概念：**
- **Base case** - 基本情况（终止条件）  
- **General case** - 一般情况（递归关系）

---

# 📖 Slide 69: Recursion – Factorial Example | 递归示例：阶乘

**中文：**  
主程序读入 n，调用 `Factorial(n)` 并输出结果。  
`Factorial(n)`：若 n 为 0 则返回 1（base case）；否则返回 n × Factorial(n-1)（general case）。

**English:**  
Factorial: base case n=0 → return 1; else return n * Factorial(n-1).

### 伪代码 | Pseudocode

```
Write "Enter n"
Read n
Set result to Factorial(n)           // 调用子程序
Write result + " is the factorial of " + n

Factorial(n)
    IF (n equals 0)
        RETURN 1                    // 基本情况
    ELSE
        RETURN n * Factorial(n-1)   // 一般情况：更小规模
```

---

# 📖 Slide 70–72: Quicksort | 快速排序

**中文：**  

- 思想：先排少一点（如 A–F, G–L, M–R, S–Z），再合起来整张表就有序。
- 每次选一个**分割值 splitVal**，把当前段**分割**成两堆，再对两堆分别做同样的 Quicksort（更小规模），直到不需要再分（base case）。
- `first` 和 `last` 表示当前处理的数组区间。

**English:**  
Divide at splitVal; sort each smaller stack recursively; base case when no need to divide further. first/last = current segment.

### 伪代码 | Pseudocode

```
Quicksort(first, last)
    IF (first < last)                // 多于一个元素才继续
        Select splitVal             // 选分割值
        Split(splitVal)             // 分割，得到 splitPoint
        Quicksort(first, splitPoint - 1)   // 左半
        Quicksort(splitPoint + 1, last)    // 右半
```

**关键概念：**
- **Quicksort** - 快速排序：分治 + 递归  
- **splitVal / splitPoint** - 分割值 / 分割点  
- **Base case** - first ≥ last 时不再划分

---

# 📖 Slide 73–76: Quicksort – Trace & Video

**中文：**  
课件中有 Quicksort 的图示和追踪；可配合视频理解：  
https://www.youtube.com/watch?v=ywWBy6J5gz8  

**English:**  
Use slides and video to trace Quicksort step by step.

---

# 📖 Slide 77: Chapter Goals (Review) | 本章目标回顾

与 Slide 2 一致：能描述问题求解过程、区分类型与数组、应用二分查找、手写四种排序、识别递归并写递归算法。

---

# 📖 Preview Key Questions | 预习重点问题

## 🤔 思考题 | Thinking Questions

1. **问题求解四步分别对应“写程序”的哪一步？**  
   **What do the four problem-solving steps correspond to when writing a program?**

**English（作业可直接使用）：** Understand the problem → analyzing requirements, defining inputs/outputs; Devise a plan → designing the algorithm, writing pseudocode; Carry out the plan → writing code, implementing; Look back → testing, debugging, verifying results.  
**中文：** 理解问题→分析需求；制定计划→设计算法/伪代码；执行计划→写代码；回顾检查→测试调试。

---

2. **抽象步骤和具体步骤在自顶向下设计里怎么一步步变具体？**  
   **How do abstract steps become concrete in top-down design?**

**English（作业可直接使用）：** Start with abstract steps, break each into more specific sub-steps at each level, until every step is concrete (all details specified, directly executable). Subproblem names become modules at the next level.  
**中文：** 从抽象步骤开始逐层细化，直到每步都是具体步骤；子问题名在下一层变成模块。

---

3. **为什么二分查找一定要有序？顺序查找在有序和无序下有什么不同？**  
   **Why must the list be sorted for binary search? How does sequential search differ on sorted vs unsorted arrays?**

**English（作业可直接使用）：** Binary search needs sorted data to eliminate half each time (target < middle → left half; target > middle → right half). Unsorted: sequential must check every item. Sorted: sequential can stop early when current item > target.  
**中文：** 二分依赖顺序排除一半。顺序查找：无序须查完；有序可提前结束（当前 > 目标则后面更大）。

---

4. **选择、冒泡、插入排序各自"每轮确定一个位置"的是哪个位置？**  
   **In selection, bubble, and insertion sort, which position is "fixed" in each pass?**

**English（作业可直接使用）：** Selection: first position of unsorted (smallest goes there). Bubble: last position (largest sinks there). Insertion: the newly inserted element at end of sorted prefix.  
**中文：** 选择排序：未排序区第一个；冒泡：最后一个；插入：刚插入元素在已排序末尾。

---

5. **递归一定要有哪两部分？阶乘的 base case 和 general case 分别是什么？**  
   **What two parts must recursion have? What are the base and general cases for factorial?**

**English（作业可直接使用）：** (1) Base case—stops recursion, returns direct answer; (2) General case—solution in terms of smaller version. Factorial: base case n=0 → return 1; general case n × Factorial(n−1). Subprogram = named code block (e.g., function).  
**中文：** Base case 终止；General case 用更小规模表达。阶乘：n=0 返 1；n×Factorial(n−1)。Subprogram = 子程序 = 命名代码块（如 function）。

---

6. **Quicksort 的 base case 是什么？splitVal 选谁由什么决定？**  
   **What is the base case of Quicksort? How is splitVal chosen?**

**English（作业可直接使用）：** Base case: first ≥ last (0 or 1 element). splitVal: often first, last, or middle element; textbook uses first. Choice affects performance, not correctness.  
**中文：** Base case：first≥last。splitVal 常取第一/最后/中间元素，教材多用第一个。

---

# 📖 Preview Suggestions | 预习建议

## ✅ 课前准备 | Pre-class Preparation

1. **复习 Chapter 6**  
   **中文：** 伪代码、变量、循环、条件判断、数组下标。  
   **English:** Pseudocode, variables, loops, conditionals, array indices.

2. **动手写/画**  
   **中文：** 在纸上用 5–7 个数走一遍顺序查找、二分查找、选择排序、冒泡排序各一轮。  
   **English:** Trace sequential search, binary search, selection sort, and one pass of bubble sort by hand on 5–7 numbers.

3. **记下疑问**  
   **中文：** 递归、Quicksort 的分割、复杂度比较等，课上可重点听或提问。  
   **English:** Note questions on recursion, Quicksort split, and when to use which algorithm.

## 🎯 课上重点 | Class Focus

1. **二分查找**：first/last/middle 的更新、循环条件。  
2. **四种排序**：每一步“谁和谁比较、谁和谁交换、标记怎么动”。  
3. **递归**：base case 与 general case，Factorial 与 Quicksort 的对应关系。  
4. **若有 Class Activity**：按 splitVal 分割并写出第一次递归调用时的列表状态。

---

# 📖 Related Resources | 相关资源

**中文：**  
- 课本 Chapter 7: Problem Solving and Algorithms  
- Quicksort 可视化：https://www.youtube.com/watch?v=ywWBy6J5gz8  
- 顺序/二分查找、选择/冒泡/插入排序的伪代码与例题  

**English:**  
- Textbook Chapter 7  
- Quicksort video (link above)  
- Pseudocode and examples for search and sort algorithms  

---

**中文：** **祝预习顺利，上课见！** 🎓✨  
**English:** **Good luck with your preview! See you in class!** 🎓✨
