# CPSC 1050 Midterm 最后一轮复习：英文题目理解
# Midterm Final Review — Understanding English Exam Questions

> 明天考试全英文，容易在**题目理解**上丢分。本文档帮你：① 常见考题用语中英对照 ② 易错表述“别读错” ③ 快速概念自测 ④ 题目理解小练习。

---

# Part 1: 考题常见英文表述 — 看到就能懂

## 1.1 选择题 / Multiple Choice 常用句

| 英文表述 | 中文意思 | 题目在问什么 |
|---------|----------|--------------|
| **Which of the following** is/does…? | 以下**哪一项**是/会…？ | 四/五选一，选**符合描述**的那一项 |
| Which of the following **is NOT** …? | 以下哪一项**不是**…？ | 选**不符合**的那一项（注意 NOT） |
| **All of the following** … **EXCEPT** | 以下都…**除了** | 选**例外**的那一项 |
| The program counter **is used to store** … | PC **用来存**… | 问 PC **存的是什么**（答：address of next instruction） |
| **Which** … **contains** the instruction register? | **哪个**…**里有** IR？ | 答：**Control Unit** |
| **What is the minimum number of bits** needed to represent N things? | 表示 N 样东西**最少需要几位**？ | 用 ⌈log₂N⌉（如 6 样→3 bits） |
| **What is the range of values** for x if … prints B? | 若…打印 B，x 的**取值范围**是？ | 看 IF/ELSE 分支条件（如 0 < x ≤ 10） |
| **What is the printout** of the following pseudocode? | 下面伪代码**输出**是什么？ | **Tracing**：按行执行，记变量变化 |
| A(n) ________ is a program that translates … | 把…翻译成…的程序叫________。 | 填空/选词：assembler / compiler / loader 等 |

## 1.2 True/False 注意点

| 英文表述 | 易错点 | 正确理解 |
|----------|--------|----------|
| The letter **C** is used to represent the number **11** in hexadecimal. | 容易选 True | **False** — C=**12**，11=**B** |
| Resolution is **determined by** the **color depth**. | 容易选 True | **False** — resolution 由**像素数**决定，不是 color depth |
| A compact disc stores data using **magnetized particles**. | 容易选 True | **False** — CD 是 **optical**，磁化粒子是 HDD/tape |
| RAM is **non-volatile** and ROM is **volatile**. | 容易记反 | **False** — RAM **volatile**，ROM **non-volatile** |
| Signed-magnitude **wastes memory** because of two representations of zero. | 常见错误选项 | 错 — 导致的是 **unnecessary complexity**，不是 wasted memory |

## 1.3 动词 / 短语 快速对照

| English | 中文 | 用法 |
|---------|------|------|
| **store** | 存储 | What does PC **store**? → address |
| **hold** | 存放、保存 | What does IR **hold**? → current instruction |
| **contain** | 包含 | Which unit **contains** IR? → Control Unit |
| **carry** | 携带、传输 | What does the bus **carry**? → address, data, control |
| **determine** | 决定 | Resolution is **determined by** pixel count. |
| **represent** | 表示 | n bits **represent** 2ⁿ values. |
| **translate** | 翻译 | Assembler **translates** assembly → machine code. |
| **execute** | 执行 | CPU **executes** machine language. |
| **fetch** | 取（指令） | Fetch **next instruction** from memory. |
| **trace** | 追踪、手算 | **Trace** the loop: 按步写变量变化。 |

---

# Part 2: 别读错 — 易因理解偏差做错的题

## 2.1 你之前错过的（来自错题本）

| 题目考点 | 错误理解 | 正确理解 |
|----------|----------|----------|
| **PC stores** | 存的是 data / instruction | 存的是 **memory location (address) of (next) instruction** |
| **Addressability** | 以为是“可寻址数量”等 | **每个可寻址位置里存的位数**（e.g. 8-bit = 1 byte） |
| **CD 存数据** | magnetized particles (True) | **False** — **optical**（激光+反射），不是磁 |

## 2.2 其他高频“陷阱”表述

- **“Two representations of zero”** → 问的是 **signed-magnitude**；后果写 **unnecessary complexity**（不写 wasted memory）。
- **“OR vs XOR”** → 仅当 **A=B=1** 时不同：OR=1，XOR=0。
- **“Resolution”** → 由 **像素数量** 决定，**不是** color depth。
- **JPEG / GIF** → JPEG 适合**照片**，GIF 适合**线条/简单图**，不要反着选。
- **“What does the bus carry?”** → 三个：**address, data, control**（缺一不可）。
- **Loader** → 把 **machine language** 程序装入内存；**assembler** 才是 assembly → machine code。

---

# Part 3: 按章节 — 看到英文能秒反应

## Ch 2 Binary & Number Systems

- **positional weight** = 位置权重 = base^position  
- **minimum number of bits for N items** = ⌈log₂N⌉  
- **Hex:** C=12, B=11；排序按**数值**，同一位 0<…<9<A<…<F  
- **Decimal → other base:** divide by base, **remainders read bottom-up**

## Ch 3 Data Representation

- **Two's complement:** invert + 1；**range** −2ⁿ⁻¹ ~ 2ⁿ⁻¹−1  
- **Overflow** = 结果放不进 allotted space（不是 radix point）  
- **Floating point:** mantissa × base^exponent  
- **Huffman** = variable-length, 常用字符短码；**run-length** = 连续重复  
- **Unicode** > 65,000 characters

## Ch 4 Gates & Circuits

- **NAND** = AND then NOT，bubble 在**输出**  
- **Universal gates:** NAND, NOR  
- **Half adder:** Sum=A⊕B, Carry=AB；**Full adder:** Sum=A⊕B⊕Cin  
- **De Morgan's:** (A+B)'=A'B', (AB)'=A'+B'

## Ch 5 Computing Components

- **PC** = address of **next** instruction | **IR** = **current** instruction（in **CU**）  
- **Bus:** address, data, control  
- **RAM** volatile, **ROM** non-volatile；**both** random access  
- **Addressability** = bits **per** addressable location  
- **CD/DVD** = **optical**；**HDD, tape** = magnetic  
- **Fetch-decode-execute:** fetch **next** instruction

## Ch 6 Low-Level & Pseudocode

- **Assembler** → assembly to machine code；**loader** → load **machine language** into memory  
- **IF (x>10) … ELSE IF (x>0) …** → 打印 B 时 **0 < x ≤ 10**  
- **Tracing WHILE:** product×count，count 从 1 到 4 → product=24（不是 120）  
- **Flowchart:** oval 起/止，rectangle 过程，diamond 判断，parallelogram I/O  

## Ch 7 Algorithms

- **Binary search:** 列表必须 **sorted**；target < mid → **last = mid−1**；target > mid → **first = mid+1**  
- **Record** = heterogeneous, 按**名字**访问；**Array** = homogeneous, 按**下标**访问  
- **Abstract step** = 细节未完全指定，可继续细化  
- **Recursion:** 至少 **base case** + **general case**

---

# Part 4: 题目理解小练习（读题 → 选“在问什么” → 答案）

**说明：** 先看英文题干，用中文想“这道题在考什么”，再对答案。

---

**Q1.**  
*“The program counter is used to store which of the following?”*

- 题目在问：PC **存的是什么**？（地址 / 指令 / 数据 / 指令条数…）  
- **答案：** the **memory location (address) of an instruction**（下一条指令的地址）

---

**Q2.**  
*“What is the minimum number of bits needed to represent 6 things?”*

- 题目在问：表示 **6 样东西** 最少要几位？  
- **答案：** 3（⌈log₂6⌉ = 3）

---

**Q3.**  
*“What is the possible range of values for x if the following pseudocode prints B?”*  
*(IF x>10 → 'A'; ELSE IF x>0 → 'B'; ELSE → 'C')*

- 题目在问：打印 **B** 时，x 的范围？  
- **答案：** **0 < x ≤ 10**

---

**Q4.**  
*“Which technique uses variable-length binary strings, assigning frequently used characters short codes?”*

- 题目在问：**变长编码**、常用字符短码 = 哪种压缩？  
- **答案：** **Huffman encoding**

---

**Q5.**  
*“A compact disc stores data using magnetized particles. True or False?”*

- 题目在问：CD 是不是用**磁化粒子**存数据？  
- **答案：** **False** — CD 是 **optical**

---

**Q6.**  
*“Which of the following contains the instruction register?”*

- 题目在问：IR 在**哪个部件**里？  
- **答案：** **Control Unit**

---

**Q7.**  
*“A(n) ________ is a program that translates an assembly-language program into machine code.”*

- 题目在问：把 **assembly** 翻成 **machine code** 的程序叫？  
- **答案：** **assembler**

---

**Q8.**  
*“Signed-magnitude has two representations of zero, which leads to __________.”*

- 题目在问：两种零导致什么？（不要选 wasted memory）  
- **答案：** **unnecessary complexity**

---

# Part 5: 考前 5 分钟检查清单

- [ ] **PC** 存的是 **address**（next instruction），不是 instruction 或 data  
- [ ] **IR** 存 **current instruction**，在 **Control Unit**  
- [ ] **Addressability** = 每个可寻址位置的**位数**  
- [ ] **Bus** 传 **address, data, control**  
- [ ] **CD** = **optical**；**RAM** volatile，**ROM** non-volatile  
- [ ] **Hex** C=**12**，11=**B**  
- [ ] **n bits** → **2ⁿ** 种取值；6 样东西 → **3 bits**  
- [ ] 看到 **NOT / EXCEPT** 时圈出来，别选反  
- [ ] **Tracing** 题：看清 loop 起止（count 从几到几）、product 怎么乘  

---

祝你明天考试顺利，题目都读懂、不丢冤枉分。  
Good luck on your midterm — read every question carefully!
