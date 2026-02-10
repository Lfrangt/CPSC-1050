# Chapter 7: Algorithm Design In-Class Activity - Bilingual Answers
# 第七章：算法设计课堂活动 - 双语答案

---

## Question 1: Problem-Solving Process
## 问题1：问题求解过程

**Question | 问题：**  
If a program runs but produces incorrect results, which step of the problem-solving process should be revisited?  
若程序能运行但结果不对，应回到问题求解过程的哪一步？

**Answer | 答案：**  
**Look back（回顾检查 / 回顾）**

**Explanation | 解释：**

**中文：**  
问题求解四步为：Understand（理解）→ Devise a plan（制定计划）→ Carry out the plan（执行计划）→ Look back（回顾检查）。程序能运行但结果错误，说明执行了计划，但计划或理解有误。Look back 阶段用于验证结果、修正计划或理解。

**English:**  
The four steps are: Understand → Devise a plan → Carry out the plan → Look back. When a program runs but produces wrong results, we need to revisit Look back to verify and revise our understanding or plan.

---

## Question 2: Abstract vs Concrete Steps
## 问题2：抽象步骤 vs 具体步骤

**Question | 问题：**  
What is the main difference between an abstract step and a concrete step in an algorithm?  
算法中抽象步骤和具体步骤的主要区别是什么？

**Answer | 答案：**

| Type<br>类型 | Characteristic<br>特征 |
|:-------------|:----------------------|
| **Abstract Step<br>抽象步骤** | Contains **unspecified details**; can be further refined<br>含有**未指定的细节**，可继续细化 |
| **Concrete Step<br>具体步骤** | **All details specified**; can be executed directly<br>**所有细节都已指定**，可直接执行 |

**Explanation | 解释：**

**中文：**  
自顶向下设计（Top-down design）中，从抽象步骤开始，逐层细化直到每一步都变成具体步骤。

**English:**  
In top-down design, we start with abstract steps and refine until every step is concrete.

---

## Question 3: Student Database - Records vs Arrays
## 问题3：学生数据库 - 记录 vs 数组

**Question | 问题：**  
Design a student database where each student has name, ID, GPA, and list of enrolled courses.  
Part A: Would you use an array or a record to store each student's information? Why?  
Part B: If you need to store a list of students, what data structure would you use?

**Answer | 答案：**

**Part A:** Use **Record（记录）** for each student.

**中文：**  
一个学生的信息是**异质 (heterogeneous)** 的：name（字符串）、ID（数字）、GPA（浮点）、courses（列表）。Record 通过**名字**访问字段，适合表示"一个实体有多个不同属性"。

**English:**  
A student's data is heterogeneous (different types). Records are accessed by name and suit "one entity with multiple attributes."

**Part B:** Use **Array（数组）** for the list of students.

**中文：**  
学生列表是**同质 (homogeneous)** 的：每个元素都是"学生"记录。数组按位置存储多个学生。

**English:**  
The student list is homogeneous; each element is a student record. Arrays store multiple items by position.

---

## Question 4: Library Search - Sequential vs Binary
## 问题4：图书馆查找 - 顺序 vs 二分

**Question | 问题：**  
A library has books with unique ISBN numbers.  
Part A: If books are stored in no particular order, which search algorithm should be used? Why?  
Part B: If books are sorted by ISBN, which algorithm would be more efficient, and why?

**Answer | 答案：**

**Part A:** **Sequential Search（顺序查找）**

**中文：**  
无序时只能从头到尾逐个比较，无法利用顺序信息。二分查找要求数据已排序。

**English:**  
Unordered data requires examining each item in turn. Binary search requires sorted data.

**Part B:** **Binary Search（二分查找）**

**中文：**  
已排序时，二分查找每次比较可排除一半数据，时间复杂度 O(log n)，比顺序查找 O(n) 更高效。

**English:**  
With sorted data, binary search eliminates half each time — O(log n) vs O(n) for sequential.

---

## Question 5: Selection Sort & Bubble Sort
## 问题5：选择排序 & 冒泡排序

**Question | 问题：**  
Given list [7, 3, 8, 5, 2]. Perform two passes of Selection Sort and two iterations of Bubble Sort.

**Answer | 答案：**

### Part 1: Selection Sort（选择排序）

| Pass | Unsorted List | Smallest Found | Swap? | New List After Swap |
|:-----|:--------------|:---------------|:------|:--------------------|
| 1st | [7, 3, 8, 5, 2] | 2 | Yes: 7 ↔ 2 | [**2**, 3, 8, 5, 7] |
| 2nd | [3, 8, 5, 7] | 3 | No | [2, **3**, 8, 5, 7] |

### Part 2: Bubble Sort（冒泡排序）

*升序：每轮相邻比较，大数沉到右边*

| Iteration | Step 1 | Step 2 | Step 3 | Step 4 | List After |
|:----------|:-------|:-------|:-------|:-------|:-----------|
| 1st | 3,7,8,5,2 | 3,7,5,8,2 | 3,5,7,8,2 | 3,5,7,2,8 | [3, 5, 7, 2, **8**] |
| 2nd | 3,5,7,2,8 | 3,5,2,7,8 | 3,2,5,7,8 | 2,3,5,7,8 | [2, 3, 5, 7, **8**] |

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
Part B: What is the base case and why is it important?

**Answer | 答案：**

**Part A:** Output: **3, 2, 1, Done!**

**Trace | 追踪：**
- count_down(3) → print 3 → count_down(2)
- count_down(2) → print 2 → count_down(1)
- count_down(1) → print 1 → count_down(0)
- count_down(0) → print "Done!"

**Part B:** **Base case:** `n == 0`

**中文：**  
Base case 是递归的终止条件。若没有 base case，函数会无限递归，导致栈溢出。Base case 确保递归能正确结束。

**English:**  
Base case stops recursion. Without it, infinite recursion causes stack overflow.

---

## Question 7: Quicksort Partitioning
## 问题7：快速排序分割

**Question | 问题：**  
Given [6, 2, 9, 4, 7], choose the first element as pivot. Show how the list is divided. What is the next step after partitioning?

**Answer | 答案：**

**Part 1: Partitioning 分割**

- **Pivot:** 6
- **Left (＜6):** [2, 4]
- **Right (≥6):** [9, 7]
- **Pivot position:** 6 在正确位置

**Part 2: Next step 下一步**

**中文：**  
对 [2, 4] 和 [9, 7] 分别递归调用 Quicksort。直到子列表长度 ≤ 1（base case）。

**English:**  
Recursively call Quicksort on [2, 4] and [9, 7] until base case (segment has ≤ 1 element).

---

## Question 8: Quicksort Divide-and-Conquer
## 问题8：快速排序的分治思想

**Question | 问题：**  
Quicksort is a divide-and-conquer algorithm. What does this mean, and how does Quicksort apply this concept?

**Answer | 答案：**

**Divide-and-Conquer 含义：**
1. **Divide（分）：** 把大问题拆成更小的子问题
2. **Conquer（治）：** 解决子问题（通常递归）
3. **Combine（合）：** 合并子问题的解（Quicksort 中通过原地划分实现，无需显式合并）

**Quicksort 的应用：**
- **Divide：** 选 pivot，将数组分为"小于 pivot"和"大于等于 pivot"两部分
- **Conquer：** 对两部分分别递归调用 Quicksort
- **Combine：** 分割时 pivot 已在正确位置，左右排序完成后整体有序

---

## Question 9: Insertion Sort
## 问题9：插入排序

**Question | 问题：**  
Given [5, 2, 8, 3, 7], perform the first two passes of Insertion Sort.

**Answer | 答案：**

| Pass | Element Being Inserted | Action Taken | Updated List |
|:-----|:-----------------------|:-------------|:-------------|
| Start | Initial list | No sorting yet | 5, 2, 8, 3, 7 |
| **Pass 1** | 2 | 2 比 5 小，插入到 5 前面 | **2, 5**, 8, 3, 7 |
| **Pass 2** | 8 | 8 比 5 大，保持位置 | **2, 5, 8**, 3, 7 |

---

## Question 10: Shopping Cart Function
## 问题10：购物车函数

**Question | 问题：**  
Part A: Why use a function to calculate total cost instead of writing the same code multiple times?  
Part B: Write a function (pseudocode) that takes a list of item prices and returns the total cost.

**Answer | 答案：**

**Part A: 使用函数的好处**

| Benefit | 中文 | English |
|:--------|:-----|:--------|
| Reusability | 可复用 | Write once, use多处 |
| Maintainability | 易维护 | Change in one place |
| Clarity | 代码更清晰 | Cleaner, more readable |
| Fewer errors | 减少重复粘贴错误 | Avoid copy-paste mistakes |

**Part B: 函数定义（伪代码）**

```
Function calculateTotal(prices)
    Set total to 0                    // 初始化总价为 0
    FOR each price IN prices         // 遍历价格列表
        Set total to total + price   // 累加每个价格
    RETURN total                     // 返回总价
```

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
