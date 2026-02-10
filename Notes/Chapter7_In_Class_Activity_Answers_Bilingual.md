# Chapter 7: Algorithm Design In-Class Activity - Bilingual Answers
# 第七章：算法设计课堂活动 - 双语答案

---

## Question 1: Problem-Solving Process
## 问题1：问题求解过程

**Question | 问题：**  
If a program runs but produces incorrect results, which step of the problem-solving process should be revisited?  
若程序能运行但结果不对，应回到问题求解过程的哪一步？

**Answer | 答案：**

**English（作业可直接使用）：**  
**Look back.** The problem-solving process has four steps: Understand the problem → Devise a plan → Carry out the plan → Look back. When a program runs but produces incorrect results, it means the plan was executed but something went wrong—either our understanding, the plan itself, or the implementation. The Look back step is where we verify results, identify the error, and revise our understanding or plan.

**中文（帮助理解）：**  
**回顾检查 (Look back)。** 问题求解四步为：理解问题 → 制定计划 → 执行计划 → 回顾检查。程序能运行但结果错误，说明执行了计划，但计划或理解有误。Look back 阶段用于验证结果、发现错误，并修正计划或理解。

---

## Question 2: Abstract vs Concrete Steps
## 问题2：抽象步骤 vs 具体步骤

**Question | 问题：**  
What is the main difference between an abstract step and a concrete step in an algorithm?  
算法中抽象步骤和具体步骤的主要区别是什么？

**Answer | 答案：**

**English（作业可直接使用）：**  
- **Abstract step:** A step that contains unspecified details; it can be further refined into more specific steps.  
- **Concrete step:** A step in which all details are specified; it can be executed directly without further breakdown.  
In top-down design, we start with abstract steps and refine them until every step becomes concrete.

**中文（帮助理解）：**  
- **抽象步骤：** 含有未指定的细节，可继续细化成更具体的步骤。  
- **具体步骤：** 所有细节都已指定，可直接执行，无需再分解。  
自顶向下设计中，从抽象步骤开始，逐层细化直到每一步都变成具体步骤。

---

## Question 3: Student Database - Records vs Arrays
## 问题3：学生数据库 - 记录 vs 数组

**Question | 问题：**  
Design a student database where each student has name, ID, GPA, and list of enrolled courses.  
设计一个学生数据库，每个学生有姓名、学号、GPA 和所选课程列表。

Part A: Would you use an array or a record to store each student's information? Why?  
Part A: 用 array 还是 record 存储每个学生的信息？为什么？

Part B: If you need to store a list of students, what data structure would you use?  
Part B: 若要存储学生列表，应使用什么数据结构？

**Answer | 答案：**

**English（作业可直接使用）：**  
**Part A:** Use a **record** to store each student's information. A student's data is heterogeneous—it includes different types (name as string, ID as number, GPA as decimal, courses as list). Records allow access by field name, which fits "one entity with multiple attributes."

**Part B:** Use an **array** to store the list of students. The list is homogeneous—each element is a student record. Arrays store multiple items by position (index).

**中文（帮助理解）：**  
**Part A：** 用 **记录 (record)** 存储每个学生的信息。学生数据是异质的，包含不同类型（姓名、ID、GPA、课程列表）。记录按字段名访问，适合"一个实体多个属性"。

**Part B：** 用 **数组 (array)** 存储学生列表。列表是同质的，每个元素都是学生记录。数组按位置存储多个元素。

---

## Question 4: Library Search - Sequential vs Binary
## 问题4：图书馆查找 - 顺序 vs 二分

**Question | 问题：**  
A library has books with unique ISBN numbers.  
图书馆有书籍，每本有唯一 ISBN 号。

Part A: If books are stored in no particular order, which search algorithm should be used? Why?  
Part A: 若书籍无序存放，应使用哪种查找算法？为什么？

Part B: If books are sorted by ISBN, which algorithm would be more efficient, and why?  
Part B: 若按 ISBN 排序，哪种算法更高效？为什么？

**Answer | 答案：**

**English（作业可直接使用）：**  
**Part A:** Use **sequential search**. When books are stored in no particular order, we must examine each item one by one from the beginning. Binary search cannot be used because it requires the data to be sorted.

**Part B:** Use **binary search**. When books are sorted by ISBN, binary search is more efficient because each comparison eliminates half of the remaining items. It has O(log n) time complexity versus O(n) for sequential search.

**中文（帮助理解）：**  
**Part A：** 用**顺序查找**。无序时只能从头到尾逐个比较，二分查找要求数据已排序，无法使用。

**Part B：** 用**二分查找**。已排序时，每次比较可排除一半数据，时间复杂度 O(log n)，比顺序查找 O(n) 更高效。

---

## Question 5: Selection Sort & Bubble Sort
## 问题5：选择排序 & 冒泡排序

**Question | 问题：**  
Given list [7, 3, 8, 5, 2]. Perform two passes of Selection Sort and two iterations of Bubble Sort.  
给定列表 [7, 3, 8, 5, 2]。执行选择排序两轮和冒泡排序两轮。

**Answer | 答案：**

**English（作业可直接使用）：**

*Part 1 — Selection Sort:* Each pass finds the smallest in the unsorted section and swaps it with the first unsorted element.

| Pass | Unsorted List | Smallest Found | Swap? | New List After Swap |
|:-----|:--------------|:---------------|:------|:--------------------|
| 1st | [7, 3, 8, 5, 2] | 2 | Yes: 7 ↔ 2 | [**2**, 3, 8, 5, 7] |
| 2nd | [3, 8, 5, 7] | 3 | No | [2, **3**, 8, 5, 7] |

*Part 2 — Bubble Sort:* Each iteration compares adjacent pairs; larger values "sink" to the right (ascending order).

| Iteration | Step 1 | Step 2 | Step 3 | Step 4 | List After |
|:----------|:-------|:-------|:-------|:-------|:-----------|
| 1st | 3,7,8,5,2 | 3,7,5,8,2 | 3,5,7,8,2 | 3,5,7,2,8 | [3, 5, 7, 2, **8**] |
| 2nd | 3,5,7,2,8 | 3,5,2,7,8 | 3,2,5,7,8 | 2,3,5,7,8 | [2, 3, 5, 7, **8**] |

**中文（帮助理解）：**  
选择排序：每轮在未排序部分找最小值，与未排序区第一个交换。  
冒泡排序：每轮相邻比较，大数沉到右边（升序）。

---

## Question 6: Recursive Function `count_down`
## 问题6：递归函数 count_down

**Question | 问题：**  
```python
def count_down(n):
    if n == 0:
        print("Done!")
    else:
        print(n)
        count_down(n - 1)
```
Part A: What will be printed if you call `count_down(3)`?  
Part A: 调用 `count_down(3)` 会输出什么？

Part B: What is the base case and why is it important?  
Part B: 该函数的 base case（基本情况）是什么？为什么重要？

**Answer | 答案：**

**English（作业可直接使用）：**

**Part A:** The output is: **3, 2, 1, Done!**  
Trace: count_down(3) → print 3 → count_down(2) → print 2 → count_down(1) → print 1 → count_down(0) → print "Done!"

**Part B:** The base case is `n == 0`. It is important because it stops the recursion. Without a base case, the function would call itself forever (infinite recursion), leading to a stack overflow. The base case ensures the recursion eventually terminates.

**中文（帮助理解）：**  
**Part A：** 输出为 3, 2, 1, Done!  
**Part B：** Base case 是 `n == 0`，它是递归的终止条件。没有 base case 会无限递归、栈溢出。Base case 确保递归能正确结束。

---

## Question 7: Quicksort Partitioning
## 问题7：快速排序分割

**Question | 问题：**  
Given [6, 2, 9, 4, 7], choose the first element as pivot. Show how the list is divided. What is the next step after partitioning?  
给定 [6, 2, 9, 4, 7]，以第一个元素为 pivot（枢轴）。展示列表如何分割，分割后的下一步是什么？

**Answer | 答案：**

**English（作业可直接使用）：**

*Part 1 — Partitioning:* With pivot = 6 (first element):
- Left (elements < 6): [2, 4]
- Right (elements ≥ 6): [9, 7]
- The pivot 6 is now in its correct final position.

*Part 2 — Next step:* Recursively call Quicksort on the two subarrays [2, 4] and [9, 7]. Repeat until each segment has at most one element (base case).

**中文（帮助理解）：**  
分割：pivot=6，左子列 [2, 4]，右子列 [9, 7]，6 已在正确位置。  
下一步：对 [2, 4] 和 [9, 7] 分别递归调用 Quicksort，直到子列表长度 ≤ 1。

---

## Question 8: Quicksort Divide-and-Conquer
## 问题8：快速排序的分治思想

**Question | 问题：**  
Quicksort is a divide-and-conquer algorithm. What does this mean, and how does Quicksort apply this concept?  
Quicksort 是分治算法。分治是什么意思？Quicksort 如何应用这一概念？

**Answer | 答案：**

**English（作业可直接使用）：**

*What does divide-and-conquer mean?*  
Divide-and-conquer is an algorithm design paradigm with three steps:  
1. **Divide:** Break the problem into smaller subproblems.  
2. **Conquer:** Solve the subproblems (usually recursively).  
3. **Combine:** Merge the solutions of subproblems into the final answer.

*How does Quicksort apply this concept?*  
- **Divide:** Select a pivot and partition the array into two parts: elements less than the pivot and elements greater than or equal to the pivot.  
- **Conquer:** Recursively call Quicksort on each of the two subarrays.  
- **Combine:** In Quicksort, the pivot is already in its correct position after partitioning. Once the left and right parts are sorted, the whole array is sorted—no explicit merge step is needed.

---

**中文（帮助理解）：**

*分治是什么意思？*  
分治是一种算法设计思想，包含三步：  
1. **分 (Divide)：** 把大问题拆成更小的子问题。  
2. **治 (Conquer)：** 解决子问题（通常递归）。  
3. **合 (Combine)：** 将子问题的解合并成最终答案。

*Quicksort 如何应用？*  
- **分：** 选 pivot，将数组分为"小于 pivot"和"大于等于 pivot"两部分。  
- **治：** 对两部分分别递归调用 Quicksort。  
- **合：** Quicksort 分割时 pivot 已在正确位置，左右排序完成后整体有序，无需显式合并。

---

## Question 9: Insertion Sort
## 问题9：插入排序

**Question | 问题：**  
Given [5, 2, 8, 3, 7], perform the first two passes of Insertion Sort.  
给定 [5, 2, 8, 3, 7]，执行插入排序的前两轮。

**Answer | 答案：**

**English（作业可直接使用）：**

| Pass | Element Being Inserted | Action Taken | Updated List |
|:-----|:-----------------------|:-------------|:-------------|
| Start | Initial list | No sorting yet | 5, 2, 8, 3, 7 |
| **Pass 1** | 2 | 2 is smaller than 5; insert 2 before 5 | **2, 5**, 8, 3, 7 |
| **Pass 2** | 8 | 8 is larger than 5; keep position | **2, 5, 8**, 3, 7 |

**中文（帮助理解）：**  
Pass 1：2 比 5 小，插入到 5 前面。Pass 2：8 比 5 大，保持位置。

---

## Question 10: Shopping Cart Function
## 问题10：购物车函数

**Question | 问题：**  
You are writing a program for an online store that frequently calculates the total cost of items in a shopping cart.  
你正在为在线商店编写程序，需频繁计算购物车中商品的总价。

Part A: Why use a function to calculate total cost instead of writing the same code multiple times?  
Part A: 为什么用函数计算总价，而不是多处重复写相同代码？

Part B: Write a function (pseudocode) that takes a list of item prices and returns the total cost.  
Part B: 写一个函数定义（伪代码或自然语言），接受价格列表并返回总价。

**Answer | 答案：**

**English（作业可直接使用）：**

**Part A:** Using a function provides: (1) **Reusability**—write the logic once and call it wherever needed; (2) **Maintainability**—if the calculation changes, update it in one place; (3) **Clarity**—code is cleaner and easier to read; (4) **Fewer errors**—avoids copy-paste mistakes when the same code would otherwise be duplicated.

**Part B:** Pseudocode:

```
Function calculateTotal(prices)
    Set total to 0
    FOR each price IN prices
        Set total to total + price
    RETURN total
```

**中文（帮助理解）：**  
Part A：可复用、易维护、代码更清晰、减少重复粘贴错误。  
Part B：初始化 total=0，遍历 prices 累加，返回 total。

---

## 📝 复习要点 / Review Key Points

| Topic | 知识点 | Suggestion |
|:------|:-------|:-----------|
| Problem-solving | 四步法 | Understand → Plan → Execute → Look back |
| Abstract vs Concrete | 抽象/具体步骤 | 抽象可细化，具体可执行 |
| Record vs Array | 记录 vs 数组 | Record 异质按名，Array 同质按下标 |
| Search algorithms | 查找算法 | 无序用顺序，有序用二分 |
| Four sorts | 四种排序 | Selection / Bubble / Insertion / Quicksort |
| Recursion | 递归 | Base case + General case |
| Divide-and-conquer | 分治 | Quicksort: Divide → Conquer → (Combine) |

---

**中文：** 祝复习顺利！  
**English:** Good luck with your review!
