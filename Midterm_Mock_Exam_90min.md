# CPSC 1050 Midterm — Mock Exam (90 minutes)
# 期中模拟卷（90 分钟）

**Time: 90 minutes | 闭卷 Closed-book | 建议带半页手写 cheat sheet 计时练习**

**Suggested time allocation / 建议用时：**
- Part A True/False: ~15 min  
- Part B Multiple Choice: ~45 min  
- Part C Fill in the blank: ~8 min  
- Part D Short Answer: ~12 min  
- Part E Tracing: ~10 min  

---

# Part A: True or False (15 × 1 mark = 15)

Write **T** or **F** on the line.

1. In hexadecimal, the letter C represents the number 12. _______

2. The program counter holds the memory address of the next instruction to be executed. _______

3. RAM is volatile and ROM is non-volatile. _______

4. A compact disc stores data using magnetized particles. _______

5. Resolution of an image is determined by the color depth of the display device. _______

6. Both RAM and ROM are random-access memory. _______

7. Addressability is the number of bits stored in each addressable location in memory. _______

8. Signed-magnitude representation has two representations of zero, which causes unnecessary complexity. _______

9. Binary search can be applied to an unsorted list. _______

10. An array stores items that are homogeneous; a record stores items that are heterogeneous. _______

11. The instruction register (IR) is part of the Control Unit. _______

12. A bus carries address, data, and control signals. _______

13. The assembler translates high-level language into machine code. _______

14. OR and XOR produce the same output when both inputs are 1. _______

15. In two's complement, 8 bits can represent integers from −128 to 127. _______

---

# Part B: Multiple Choice (22 × 2 marks = 44)

Choose the **one best** answer.

**1.** What is the minimum number of bits needed to represent 10 different items?  
A) 2  
B) 3  
C) 4  
D) 10  

**2.** The program counter is used to store which of the following?  
A) the current instruction being executed  
B) the memory location of an instruction  
C) the data used by an instruction  
D) the number of instructions in the program  

**3.** Which of the following contains the instruction register?  
A) ALU  
B) Control Unit  
C) RAM  
D) Bus  

**4.** Which compression technique uses variable-length codes, assigning shorter codes to frequently used characters?  
A) run-length encoding  
B) Huffman encoding  
C) keyword encoding  
D) ASCII encoding  

**5.** In which representation do we have two different bit patterns for zero?  
A) two's complement  
B) signed-magnitude  
C) floating point  
D) fixed-point  

**6.** Which storage technology is used by a CD or DVD?  
A) magnetic  
B) optical  
C) solid-state  
D) magnetized particles  

**7.** What does the loader do?  
A) translates assembly language to machine code  
B) loads a machine-language program into memory  
C) compiles high-level code  
D) executes the program  

**8.** A(n) _______________ is a program that translates an assembly-language program into machine code.  
A) compiler  
B) loader  
C) assembler  
D) interpreter  

**9.** In binary search, when the target is less than the value at the middle position, we should:  
A) set first to middle + 1  
B) set last to middle − 1  
C) set first to middle  
D) set last to middle  

**10.** Which of the following is a universal gate?  
A) AND  
B) OR  
C) NAND  
D) XOR  

**11.** In a half adder, the Sum output equals:  
A) A AND B  
B) A OR B  
C) A XOR B  
D) NOT (A AND B)  

**12.** De Morgan's law states that (A + B)' equals:  
A) A' + B'  
B) A' · B'  
C) A · B  
D) A + B  

**13.** How many distinct values can be represented with 5 bits?  
A) 5  
B) 10  
C) 25  
D) 32  

**14.** Which format is best suited for compressing photographic images?  
A) GIF  
B) JPEG  
C) run-length  
D) Huffman  

**15.** In the fetch-decode-execute cycle, the fetch step retrieves:  
A) the current instruction  
B) the next instruction  
C) data from the ALU  
D) the program counter value  

**16.** Pipelining is a technique that:  
A) uses multiple processors for different tasks  
B) divides instruction execution into stages to improve throughput  
C) increases the size of cache  
D) stores instructions in ROM  

**17.** In pseudocode, if we have:  
`IF (x > 10) Print 'A'`  
`ELSE IF (x > 0) Print 'B'`  
`ELSE Print 'C'`  
For which range of x does the algorithm print 'B'?  
A) x > 10  
B) x > 0  
C) 0 < x ≤ 10  
D) x ≤ 0  

**18.** Recursion requires at least:  
A) a base case  
B) a general case  
C) both a base case and a general case  
D) a loop  

**19.** Which sort repeatedly compares and swaps adjacent elements so the largest "bubbles" to the end?  
A) selection sort  
B) insertion sort  
C) bubble sort  
D) quicksort  

**20.** An abstract step in top-down design is one that:  
A) is written in code  
B) has unspecified details and can be refined further  
C) is the same as a concrete step  
D) only applies to sorting  

**21.** In a flowchart, a decision is represented by a:  
A) rectangle  
B) oval  
C) diamond  
D) parallelogram  

**22.** Overflow occurs when:  
A) the radix point is in the wrong place  
B) the result of an operation does not fit in the allotted number of bits  
C) we mix signed and unsigned numbers  
D) we use floating-point representation  

---

# Part C: Fill in the Blank (4 × 2 marks = 8)

Write the correct term on the line.

1. The _______________ holds the current instruction being executed. (Hint: it is inside the Control Unit.)

2. In base 16 (hexadecimal), the digit B represents the decimal number _______________.

3. With n bits in two's complement, the range of integers is from _______________ to _______________.

4. _______________ is the number of bits stored in each addressable location in memory.

---

# Part D: Short Answer (3 × 4 marks = 12)

Answer briefly in English (one or two sentences).

1. What three types of information does a computer bus carry?

2. What is the main disadvantage of signed-magnitude representation (related to zero)?

3. What is the key requirement for a list before we can use binary search on it?

---

# Part E: Tracing (2 questions = 21 marks)

**E1. (10 marks)** What is the **output** of the following pseudocode? Show your trace (values of `count` and `product` at each step).

```
Set count to 0
Set product to 1
WHILE (count < 4)
    Set product to product * count
    Set count to count + 1
END WHILE
Display "Result is " + product
```

**E2. (11 marks)** Trace **binary search** for target **7** in the sorted list:  
`[2, 5, 7, 9, 12, 15]`  
Use indices: first, last, middle. For each step, write first, last, middle, and whether you found the target or go left/right. How many comparisons until found?

---

*End of Mock Exam. Check your time; then use the Answer Key to grade.*

---

# Answer Key 答案与解析

## Part A: True or False

| # | Answer | Note |
|---|--------|------|
| 1 | **T** | C = 12 in hex |
| 2 | **T** | PC = address of *next* instruction |
| 3 | **T** | RAM volatile, ROM non-volatile |
| 4 | **F** | CD is **optical**, not magnetized particles |
| 5 | **F** | Resolution by **pixel count**, not color depth |
| 6 | **T** | Both are random access |
| 7 | **T** | Addressability = bits per location |
| 8 | **T** | Two zeros → unnecessary complexity |
| 9 | **F** | Binary search requires a **sorted** list |
| 10 | **T** | Array = homogeneous; record = heterogeneous |
| 11 | **T** | IR is in the Control Unit |
| 12 | **T** | Bus: address, data, control |
| 13 | **F** | Assembler: assembly → machine code; compiler: high-level → … |
| 14 | **F** | OR=1, XOR=0 when A=B=1 |
| 15 | **T** | −2⁷ to 2⁷−1 = −128 to 127 |

## Part B: Multiple Choice

| # | Answer | # | Answer |
|---|--------|---|--------|
| 1 | C (4; ⌈log₂10⌉=4) | 12 | B (A'·B') |
| 2 | B (memory location of instruction) | 13 | D (32 = 2⁵) |
| 3 | B (Control Unit) | 14 | B (JPEG) |
| 4 | B (Huffman) | 15 | B (next instruction) |
| 5 | B (signed-magnitude) | 16 | B (stages) |
| 6 | B (optical) | 17 | C (0 < x ≤ 10) |
| 7 | B (loads machine code into memory) | 18 | C (base + general) |
| 8 | C (assembler) | 19 | C (bubble sort) |
| 9 | B (last = middle − 1) | 20 | B (unspecified details) |
| 10 | C (NAND) | 21 | C (diamond) |
| 11 | C (A XOR B) | 22 | B (result doesn't fit) |

## Part C: Fill in the Blank

1. **Instruction Register** (or IR)  
2. **11** (B = 11 in hex)  
3. **−2^(n−1)** to **2^(n−1) − 1** (e.g. −128 to 127 for 8 bits)  
4. **Addressability**

## Part D: Short Answer

1. **Address, data, and control** (signals).  
2. **Two representations of zero** (positive zero and negative zero), which leads to **unnecessary complexity** (not wasted memory).  
3. The list **must be sorted** (in order).

## Part E: Tracing

**E1.**  
- count=0: product=1*0=**0**, then count=1  
- count=1: product=0*1=**0**, then count=2  
- count=2: product=0*2=**0**, then count=3  
- count=3: product=0*3=**0**, then count=4  
- count=4 fails (count < 4 false), exit loop.  

**Output: "Result is 0"**

**E2. Binary search for 7 in [2, 5, 7, 9, 12, 15]**  
- Step 1: first=0, last=5, middle=2; data[2]=7 → **found**.  
Comparisons: **1**.

(If you trace with mid=(first+last)/2: (0+5)/2=2; 7==7, done. So 1 comparison.)

---

**Scoring:** Part A 15 + Part B 44 + Part C 8 + Part D 12 + Part E 21 = **100 marks total.**

Good luck on your real exam! 考试加油！
