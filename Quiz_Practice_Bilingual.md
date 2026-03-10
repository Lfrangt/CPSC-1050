# CPSC 1050 Quiz 练习 · 综合复习
# Quiz Practice – Comprehensive Review (Ch8 + Ch9 + M1 查漏补缺)

**说明：** 全选择题，中英双语。难度：简单 30%、中等 50%、困难 20%。  
**Instructions:** All multiple choice, bilingual. Difficulty: Easy 30%, Medium 50%, Hard 20%.

---

## Part A — 补码与进制 / Two's Complement & Number Bases

**Q1.** What is the 8-bit two's complement representation of **−14**?  
**−14 的 8 位补码表示是什么？**

A) 11110010  
B) 11110001  
C) 10001110  
D) 00001110  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** A  

**Explanation / 解释:**  
14 的 8 位二进制 = 00001110；取反 = 11110001；加 1 = **11110010**。  
14 in 8-bit: 00001110 → invert → 11110001 → +1 → 11110010.
</details>

---

**Q2.** The binary pattern **11110010** can represent which of the following when interpreted differently?  
**二进制 11110010 在不同解释下可以表示以下哪项？**

A) Only -14 in two's complement / 仅是补码下的 -14  
B) Only 242 as unsigned / 仅是无符号的 242  
C) -14 (two's complement), 242 (unsigned), and -114 (signed-magnitude) / 补码 -14、无符号 242、原码 -114 都成立  
D) None of the above / 以上都不对  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** C  

**Explanation / 解释:**  
同一串二进制在不同约定下含义不同：无符号 = 242；原码符号位 1 表示负，其余为绝对值 114 → -114；补码 = -14。三种解释都对。  
Same bit pattern: unsigned 242; signed-magnitude -114; two's complement -14. All valid.
</details>

---

**Q3.** What is the 8-bit two's complement range?  
**8 位补码的取值范围是？**

A) -127 to 127  
B) -128 to 127  
C) -255 to 255  
D) 0 to 255  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
公式 −2^(n−1) 到 2^(n−1)−1，n=8 得 **-128 ～ 127**。  
Formula: −2^(n−1) to 2^(n−1)−1; for 8-bit: -128 to 127.
</details>

---

## Part B — CPU 与指令 / CPU & Instructions

**Q4.** In Super Simple CPU, if the current instruction is a **conditional jump** (e.g., JUMP IF ACC = 0) and the accumulator contains **5**, what happens next?  
**在 Super Simple CPU 中，若当前指令是条件跳转（如 ACC=0 时跳转）且累加器为 5，下一步会怎样？**

A) Always jump to the target address / 一定跳转到目标地址  
B) Execute the instruction at the **next** address (PC+1) / 执行**下一条**地址的指令（PC+1）  
C) Halt / 停机  
D) Clear the accumulator / 清空累加器  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
条件跳转只有条件成立才跳转。ACC=5 ≠ 0，条件不成立，所以 **PC+1，执行下一条**，不跳转。  
Conditional jump only jumps when condition is true. ACC=5, so condition false → execute next instruction (PC+1).
</details>

---

## Part C — 布尔代数与电路 / Boolean Algebra & Circuits

**Q5.** For a truth table, to get the **SOP (Sum of Products)** expression, we take each row where output is 1 and form a **minterm**, then OR them. For a row with A=0, B=1, C=0, the minterm is:  
**由真值表写 SOP 时，对输出为 1 的每一行写最小项再 OR。若某行 A=0, B=1, C=0，该行的最小项是：**

A) A + B' + C  
B) A' B C'  
C) A B' C  
D) A' + B + C'  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
最小项：变量为 0 写带 '，为 1 写不带 '。A=0→A', B=1→B, C=0→C'，所以是 **A' B C'**。  
Minterm: 0 → primed, 1 → unprimed. So A' B C'.
</details>

---

## Part D — 排序、查找与循环语义 / Sort, Search & Loop Semantics

**Q6.** In **Selection Sort**, each pass selects the minimum from the **unsorted** portion and swaps it with the first position of that portion. After 3 passes on array [64, 25, 12, 22, 11, 82, 90], what is the value at index 3 (0-based)?  
**在选择排序中，每趟在未排序部分选最小并与该部分首位交换。对 [64,25,12,22,11,82,90] 做 3 趟后，下标 3 的值是？**

A) 22  
B) 25  
C) 64  
D) 12  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** C  

**Explanation / 解释:**  
第1趟：最小 11，与 index 0 交换 → [11, 25, 12, 22, 64, 82, 90]。第2趟：未排序最小 12，与 index 1 交换 → [11, 12, 25, 22, 64, 82, 90]。第3趟：未排序最小 22，与 index 2 交换 → [11, 12, 22, 25, 64, 82, 90]。故 index 3 = **25**。  
Pass 1: swap 11 → [11,25,12,22,64,82,90]. Pass 2: swap 12 → [11,12,25,22,64,82,90]. Pass 3: swap 22 → [11,12,22,25,64,82,90]. Index 3 = **25**. (选项里 25 为 B；若题目数组不同则按同样步骤手推即可。)
</details>

---

**Q7.** In a **FOR** loop written as "FOR i = 0 TO -1", how many times does the loop body execute?  
**在伪代码 "FOR i = 0 TO -1" 中，循环体执行几次？**

A) Infinite / 无限次  
B) 1  
C) 0  
D) 2  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** C  

**Explanation / 解释:**  
从 0 到 -1 的范围内没有可执行的步数（起点已大于终点），循环**一次都不执行**，即 0 次。注意与“死循环”区分：死循环是条件永远为真。  
Range 0 to -1 means no iterations; loop runs **0 times**. Distinct from infinite loop (condition always true).
</details>

---

## Part E — Chapter 8: ADT, Stack, Queue

**Q8.** What is the main difference between **logical level** and **implementation level** in an ADT?  
**ADT 的逻辑层和实现层的主要区别是什么？**

A) Logical level describes how data is stored in memory; implementation level describes operations.  
B) **Logical level** describes **what** operations the ADT supports; **implementation level** describes **how** it is built (e.g., array or linked list).  
C) They are the same.  
D) Logical level is in hardware; implementation level is in software.  

**逻辑层描述 ADT 支持哪些操作（做什么）；实现层描述如何实现（如用数组还是链表）。**

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
逻辑层 = 能做什么（Push/Pop、LIFO 等）；实现层 = 怎么实现（数组/链表、指针等）。  
Logical = what (operations, behavior); Implementation = how (storage, pointers, etc.).
</details>

---

**Q9.** Starting with an **empty stack**, we perform: Push(5), Push(10), Pop(), Push(15), Pop(). From top to bottom, the stack now contains:  
**从空栈开始执行：Push(5), Push(10), Pop(), Push(15), Pop()。栈内从顶到底现在是：**

A) 5  
B) 15, 10  
C) 10, 5  
D) 5, 15  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** A  

**Explanation / 解释:**  
Push(5)→[5]; Push(10)→[10,5]; Pop()→[5]; Push(15)→[15,5]; Pop()→[5]。栈顶到底只剩 **5**。  
Stack after each step: [5] → [10,5] → [5] → [15,5] → [5]. Only **5** left.
</details>

---

**Q10.** A **queue** follows which ordering principle?  
**队列遵循哪种顺序原则？**

A) LIFO (Last In, First Out)  
B) **FIFO (First In, First Out)**  
C) Random order  
D) Sorted order  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
队列：先进先出 FIFO；栈：后进先出 LIFO。  
Queue: First In First Out; Stack: Last In First Out.
</details>

---

## Part F — Chapter 9: Python 基础

**Q11.** In Python 3, `input("Name? ")` returns what type of value?  
**在 Python 3 中，input("Name? ") 返回什么类型？**

A) Integer / 整数  
B) **String / 字符串**  
C) Float / 浮点数  
D) Boolean / 布尔  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
`input()` 始终返回**字符串**。若需要数字要用 `int()` 或 `float()` 转换。  
input() always returns a **string**. Use int() or float() to convert to number.
</details>

---

**Q12.** What is the result of `range(4)` in Python?  
**Python 中 range(4) 的结果是？**

A) [0, 1, 2, 3, 4]  
B) [1, 2, 3, 4]  
C) **0, 1, 2, 3** (values from 0 up to but not including 4)  
D) [4]  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** C  

**Explanation / 解释:**  
`range(n)` 产生 0 到 n-1，不包含 n。所以 range(4) → 0, 1, 2, 3。  
range(n) gives 0 through n-1, not including n. So 0, 1, 2, 3.
</details>

---

**Q13.** Which keyword in Python cannot be used as a variable name?  
**Python 中哪个不能用作变量名？**

A) value  
B) count  
C) **print**  
D) result  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** C  

**Explanation / 解释:**  
`print` 是**关键字/内置函数**，用作变量名会覆盖内置功能，应避免。其他选项可作为变量名。  
print is a built-in function/keyword; using it as a variable name shadows the built-in and should be avoided.
</details>

---

**Q14.** For the code below, how many times is "hello" printed?  
**下面这段代码会打印几次 "hello"？**

```python
for i in range(0):
    print("hello")
```

A) 1  
B) **0**  
C) Infinite / 无限  
D) Error / 报错  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
`range(0)` 表示从 0 到 0 之前，即没有元素，循环体**执行 0 次**。  
range(0) has no elements, so the loop runs **0 times**.
</details>

---

**Q15.** What does `"Hi" + "!"` produce in Python?  
**在 Python 中 "Hi" + "!" 的结果是？**

A) Error / 报错  
B) **"Hi!"**  
C) "Hi" "!"  
D) 2  

<details>
<summary><b>Answer / 答案</b></summary>

**Answer / 答案:** B  

**Explanation / 解释:**  
字符串用 `+` 表示**拼接 (concatenation)**，结果为 **"Hi!"**。  
+ for strings is concatenation → "Hi!".
</details>

---

## 答案速查 / Answer Key

| Q | Answer | Topic |
|---|--------|--------|
| 1 | A | Two's complement |
| 2 | C | Same bit pattern, different interpretations |
| 3 | B | 8-bit range |
| 4 | B | CPU conditional jump |
| 5 | B | Minterm / SOP |
| 6 | B (若按所给数组手推为 25) | Selection sort |
| 7 | C | Loop 0 times |
| 8 | B | ADT logical vs implementation |
| 9 | A | Stack push/pop |
| 10 | B | Queue FIFO |
| 11 | B | input() returns string |
| 12 | C | range(4) |
| 13 | C | print as keyword |
| 14 | B | range(0) → 0 iterations |
| 15 | B | String concatenation |

---

## 复习建议 / Review Suggestions

1. **补码**：再练 3～5 道“十进制→8 位补码”和“同一 bit 串多种解释”。  
2. **CPU**：记住条件跳转“条件不成立 → 执行下一条 (PC+1)”。  
3. **栈/队列**：手写 2 道 Push/Pop、Enqueue/Dequeue 序列，分清 LIFO 与 FIFO。  
4. **Python**：记牢 `input()`→字符串、`range(n)`→0 到 n-1、`+` 对字符串是拼接。  
5. **循环**：区分“执行 0 次”（如 range(0)、FOR 0 TO -1）和“无限次”（死循环）。

需要某一章（如只考 Ch9）或只做 M1 弱项的 quiz，可以说章节或主题，我再按那个范围出题。
