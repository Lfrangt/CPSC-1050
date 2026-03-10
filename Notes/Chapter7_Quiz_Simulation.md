# CPSC 1050 Chapter 7 - Quiz 模拟练习
# Chapter 7 Algorithm Design Quiz Simulation (中英双语)

*全选择题形式 | All Multiple Choice Format*

---

# Multiple Choice 选择题 (共 20 题)

---

**Q1. Which step of the problem-solving process should you revisit when a program runs but produces wrong results?**  
**问题1. 程序能运行但结果错误时，应回到问题求解过程的哪一步？**

A) Understand the problem / 理解问题  
B) Devise the plan / 制定计划  
C) Carry out the plan / 执行计划  
D) Look back / 回顾检查  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** D  
**Explanation / 解释:** Look back 用于验证结果、发现错误并修正理解或计划。程序能跑但结果错说明计划已执行，需要在“回顾检查”阶段找错并修正。
</details>

---

**Q2. An algorithm must be which of the following?**  
**问题2. 算法必须满足以下哪项？**

A) Unambiguous and finite / 无歧义且有限  
B) Written in Python  
C) Faster than any other solution  
D) Used only for sorting  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** A  
**Explanation / 解释:** 算法是一组**无歧义**的指令，在**有限**时间和**有限**数据内解决问题。Unambiguous = 每一步只有一种理解；Finite = 时间与数据量有限。
</details>

---

**Q3. What is the main difference between an abstract step and a concrete step?**  
**问题3. 抽象步骤和具体步骤的主要区别是什么？**

A) Abstract is in English, concrete is in code.  
B) Abstract step has unspecified details and can be refined; concrete step has all details and can be executed directly.  
C) Abstract is for sorting only; concrete is for searching.  
D) There is no difference.  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 抽象步骤含有未指定细节，可继续细化；具体步骤所有细节已指定，可直接执行。自顶向下设计就是从抽象细化到全部具体。
</details>

---

**Q4. In top-down design, what does the name of a subproblem at one level become at the next lower level?**  
**问题4. 在自顶向下设计中，某一层子问题的名称在下一层变成什么？**

A) A variable  
B) A module / 模块  
C) A loop  
D) A comment  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 子问题的名称在下一层变成**模块 (module)**——可独立命名、调用的子任务。
</details>

---

**Q5. A record stores items that are _____; an array stores items that are _____.**  
**问题5. 记录存储_____的项；数组存储_____的项。**

A) homogeneous; heterogeneous  
B) heterogeneous; homogeneous  
C) sorted; unsorted  
D) large; small  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** Record（记录）= **异质**集合，按**名字**访问（如 name, age, wage）。Array（数组）= **同质**集合，按**下标/位置**访问。
</details>

---

**Q6. How do you access an item in an array?**  
**问题6. 如何访问数组中的一项？**

A) By name / 按名字  
B) By position (index) / 按位置（下标）  
C) By value  
D) By key  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 数组通过**位置（下标 index）**访问，如 data[0], data[length-1]。按名字访问的是 record。
</details>

---

**Q7. Binary search requires the list to be _____.**  
**问题7. 二分查找要求列表_____。**

A) unsorted / 无序  
B) sorted / 有序  
C) small  
D) stored in a record  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 二分查找必须**先排序**，才能每次比较排除一半（target < middle → 左半；target > middle → 右半）。无序时只能用顺序查找。
</details>

---

**Q8. In binary search, when the target is less than data[middle], what do you do?**  
**问题8. 二分查找中，当目标值小于 data[middle] 时，应如何更新？**

A) Set first to middle + 1  
B) Set last to middle - 1  
C) Set middle to first  
D) Set found to TRUE  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 若 item < data[middle]，目标在**左半部分**，所以把 **last** 设为 **middle - 1**，在 [first, middle-1] 继续找。
</details>

---

**Q9. In sequential search on a sorted array, when can you stop early?**  
**问题9. 在有序数组上做顺序查找时，何时可以提前结束？**

A) When you find the item  
B) When data[index] > searchItem（当前元素已大于目标）  
C) Both A and B  
D) Never; you must check every element  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** C  
**Explanation / 解释:** 找到目标可结束；若当前元素已**大于**目标，后面只会更大，也可提前结束。无序数组只能逐个查完或找到为止。
</details>

---

**Q10. What is a sort key?**  
**问题10. 什么是排序键 (sort key)？**

A) The first element of the array  
B) The field(s) used to determine the order of items  
C) The index of the smallest element  
D) The number of swaps needed  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** Sort key（排序键）= 作为排序依据的**字段**。例如按成绩排序，成绩就是 sort key。
</details>

---

**Q11. In Selection Sort, each pass finds the _____ in the unsorted section and swaps it with _____.**  
**问题11. 选择排序中，每轮在未排序区找_____，并与_____交换。**

A) largest; the last unsorted  
B) smallest; the first unsorted  
C) middle; the pivot  
D) first; the last  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 选择排序：每轮在**未排序区**找**最小**的，与未排序区的**第一个**交换，然后标记右移。
</details>

---

**Q12. In Bubble Sort (ascending), each iteration compares _____ and typically puts the _____ in its final position.**  
**问题12. 冒泡排序（升序）中，每轮比较_____，通常使_____到达最终位置。**

A) adjacent pairs; smallest  
B) adjacent pairs; largest  
C) first and last; middle  
D) every pair; pivot  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 冒泡排序：**相邻**两两比较、交换，大数“沉”到右边。每轮通常有一个元素（如**最大**）到达最终位置。
</details>

---

**Q13. Insertion Sort maintains a _____ of sorted items and repeatedly _____ the next item into the correct position.**  
**问题13. 插入排序维护一个_____的已排序部分，并反复将下一个元素_____到正确位置。**

A) shrinking; removes  
B) growing; inserts  
C) fixed; compares  
D) random; swaps  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 插入排序：前面是**逐渐变长**的已排序区，每次取未排序区**第一个**，**插入**到已排序区中的正确位置（向左交换直到到位）。
</details>

---

**Q14. Recursion requires a _____ that stops the recursion and a _____ that expresses the solution in terms of a smaller problem.**  
**问题14. 递归需要_____来终止，以及_____用更小规模表达解。**

A) loop; condition  
B) base case; general case  
C) pivot; split  
D) module; refinement  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** **Base case**（基本情况）= 直接给出答案，不再递归。**General case**（一般情况）= 用对自身、规模更小的调用来表达解（如 n! = n × (n-1)!）。
</details>

---

**Q15. In the factorial recursive algorithm, what is the base case?**  
**问题15. 阶乘递归算法中，base case 是什么？**

A) n equals 1, return 1  
B) n equals 0, return 1  
C) n equals 0, return 0  
D) n > 0, return n * Factorial(n-1)  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 阶乘的 base case：**n = 0 时 return 1**。General case：return n × Factorial(n-1)。
</details>

---

**Q16. Quicksort is a _____ algorithm that uses a _____ to divide the array.**  
**问题16. 快速排序是_____算法，用_____把数组分割。**

A) sequential; loop  
B) divide-and-conquer; pivot (splitVal)  
C) greedy; key  
D) iterative; index  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** Quicksort = **分治 (divide-and-conquer)**：选 **pivot/splitVal** 分割成“小于 pivot”和“大于等于 pivot”两部分，再对左右递归排序。
</details>

---

**Q17. In Quicksort, when do we stop dividing (base case)?**  
**问题17. 在 Quicksort 中，何时停止分割（base case）？**

A) When the array is sorted  
B) When first >= last (0 or 1 element in the segment)  
C) When splitPoint equals middle  
D) When we have done 10 passes  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** Base case：**first ≥ last**，即当前区间只有 0 或 1 个元素，已有序，直接返回。否则选 splitVal、分割，再递归左右两段。
</details>

---

**Q18. After the Split step in Quicksort, the splitPoint is where _____.**  
**问题18. Quicksort 的 Split 完成后，splitPoint 是_____所在位置。**

A) the smallest value  
B) the pivot  
C) the first unsorted element  
D) the middle index  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** 分割完成后，**pivot** 放在最终位置，该下标就是 **splitPoint**。左边都 < pivot，右边都 ≥ pivot；然后递归 Quicksort(first, splitPoint-1) 和 Quicksort(splitPoint+1, last)。
</details>

---

**Q19. Which search algorithm can stop early on a sorted array when the current element is greater than the target?**  
**问题19. 哪种查找算法在有序数组上可以在“当前元素已大于目标”时提前结束？**

A) Binary search only  
B) Sequential search only  
C) Both sequential and binary search  
D) Neither  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** B  
**Explanation / 解释:** **顺序查找**在有序时若 data[index] > searchItem 可提前结束。二分查找是通过比较 middle 排除一半，不是“当前>目标就停”这种逻辑。
</details>

---

**Q20. A subprogram that calls itself is an example of _____.**  
**问题20. 调用自己的子程序是_____的例子。**

A) a loop  
B) iteration  
C) recursion / 递归  
D) top-down design  

<details>
<summary>点击查看答案 Click for Answer</summary>

**Answer / 答案:** C  
**Explanation / 解释:** **Recursion（递归）** = 子程序**调用自己**。例如 Factorial(n) 里调用 Factorial(n-1)，Quicksort 里递归调用 Quicksort(left) 和 Quicksort(right)。
</details>

---

# 考前速记 Checklist

- [ ] 问题求解四步：Understand → Devise plan → Carry out → **Look back**
- [ ] 算法：**Unambiguous** + **Finite**
- [ ] 抽象步骤 vs 具体步骤；自顶向下 → 子问题变 **module**
- [ ] **Record** = 异质、按名访问；**Array** = 同质、按**下标**访问
- [ ] **二分查找**必须先**有序**；item < middle → **last = middle - 1**
- [ ] 顺序查找在**有序**时可提前结束（当前 > 目标）
- [ ] **Selection**：每轮选最小与未排序第一个交换；**Bubble**：相邻比较，大数沉底；**Insertion**：已排序区扩大，新元素插入
- [ ] 递归：**Base case** + **General case**；阶乘 base case **n=0 → 1**
- [ ] **Quicksort**：分治 + **pivot**；base case **first ≥ last**；splitPoint 是 pivot 最终位置

---

*End of Chapter 7 Quiz Simulation*
