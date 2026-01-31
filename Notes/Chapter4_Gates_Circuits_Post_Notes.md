# Chapter 4: Gates and Circuits - Post-Class Notes
# 第四章：门电路 - 课后笔记完整版

---

## 📚 目录 | Table of Contents

1. [课程回顾与重点总结](#课程回顾与重点总结)
2. [布尔代数深入理解](#布尔代数深入理解)
3. [逻辑门详细分析](#逻辑门详细分析)
4. [组合电路设计方法](#组合电路设计方法)
5. [时序电路原理与应用](#时序电路原理与应用)
6. [实际应用案例](#实际应用案例)
7. [常见错误与注意事项](#常见错误与注意事项)
8. [练习题与解答](#练习题与解答)
9. [考试重点速查](#考试重点速查)

---

# 📖 第一部分：课程回顾与重点总结
# Part 1: Course Review and Key Points Summary

---

## 🎯 本章核心概念回顾
## Core Concepts Review

### 1. 布尔代数（Boolean Algebra）

**中文：**  
布尔代数是处理**只有两个值（0和1）**的数学系统，是数字电路设计的基础。

**关键点：**
- ✅ 只有两个值：`TRUE (1)` 和 `FALSE (0)`
- ✅ 三种基本运算：`NOT`、`AND`、`OR`
- ✅ 遵循特定的代数定律（交换律、结合律、分配律、德摩根定律等）

**English:**  
Boolean algebra is a mathematical system that deals with **only two values (0 and 1)**, forming the foundation of digital circuit design.

**Key Points:**
- ✅ Only two values: `TRUE (1)` and `FALSE (0)`
- ✅ Three basic operations: `NOT`, `AND`, `OR`
- ✅ Follows specific algebraic laws (commutative, associative, distributive, De Morgan's laws, etc.)

---

### 2. 逻辑门（Logic Gates）

**中文：**  
逻辑门是实现布尔运算的**物理电子元件**，是构建数字电路的基本单元。

**基本逻辑门：**
1. **NOT门（非门）** - 取反操作
2. **AND门（与门）** - 全真才真
3. **OR门（或门）** - 有真就真
4. **XOR门（异或门）** - 输入不同时输出1
5. **NAND门（与非门）** - AND的反
6. **NOR门（或非门）** - OR的反

**English:**  
Logic gates are **physical electronic components** that implement Boolean operations, forming the basic building blocks of digital circuits.

**Basic Logic Gates:**
1. **NOT Gate** - Negation operation
2. **AND Gate** - All inputs must be true
3. **OR Gate** - At least one input must be true
4. **XOR Gate** - Output 1 when inputs differ
5. **NAND Gate** - Inverse of AND
6. **NOR Gate** - Inverse of OR

---

### 3. 组合电路 vs 时序电路
### Combinational vs Sequential Circuits

**中文：**  
这是本章最重要的概念区分！

| 特征 | 组合电路 | 时序电路 |
|------|---------|---------|
| **输出依赖** | 只取决于当前输入 | 取决于当前输入 + 过去状态 |
| **记忆功能** | ❌ 无 | ✅ 有 |
| **时钟信号** | 不需要 | 通常需要 |
| **存储元件** | 无 | 触发器、寄存器 |
| **描述方法** | 真值表 | 状态表、状态图 |
| **例子** | 加法器、MUX、译码器 | 寄存器、计数器、内存 |

**English:**  
This is the most important conceptual distinction in this chapter!

| Feature | Combinational | Sequential |
|---------|--------------|------------|
| **Output Dependency** | Only current input | Current input + past state |
| **Memory** | ❌ No | ✅ Yes |
| **Clock Signal** | Not needed | Usually needed |
| **Storage Elements** | None | Flip-flops, registers |
| **Description Method** | Truth table | State table, state diagram |
| **Examples** | Adders, MUX, decoders | Registers, counters, memory |

---

# 📖 第二部分：布尔代数深入理解
# Part 2: Deep Understanding of Boolean Algebra

---

## 🔢 布尔运算详解
## Detailed Boolean Operations

### 1. NOT运算（非运算）

**中文：**  
**功能：** 取反操作，将0变成1，将1变成0

**真值表：**
```
A | A' (NOT A)
--|------------
0 |     1
1 |     0
```

**符号表示：**
- 数学符号：`¬A`
- 逻辑符号：`A'`
- 编程符号：`!A`

**记忆技巧：** "0变1，1变0"

**English:**  
**Function:** Negation operation, converts 0 to 1 and 1 to 0

**Truth Table:**
```
A | A' (NOT A)
--|------------
0 |     1
1 |     0
```

**Symbol Representations:**
- Math symbol: `¬A`
- Logic symbol: `A'`
- Programming: `!A`

**Memory Tip:** "0 becomes 1, 1 becomes 0"

---

### 2. AND运算（与运算）

**中文：**  
**功能：** 全真才真 - 只有当**所有输入都是1**时，输出才是1

**真值表：**
```
A | B | AB (A AND B)
--|---|-------------
0 | 0 |      0
0 | 1 |      0
1 | 0 |      0
1 | 1 |      1    ← 只有这种情况输出1
```

**符号表示：**
- 数学符号：`A ∧ B`
- 逻辑符号：`A · B` 或 `AB`
- 编程符号：`A && B`

**记忆技巧：** 
- "两个都是1，结果才是1"
- 想象串联电路：两个开关都闭合，灯才亮

**English:**  
**Function:** All true - output is 1 only when **all inputs are 1**

**Truth Table:**
```
A | B | AB (A AND B)
--|---|-------------
0 | 0 |      0
0 | 1 |      0
1 | 0 |      0
1 | 1 |      1    ← Only this case outputs 1
```

**Symbol Representations:**
- Math symbol: `A ∧ B`
- Logic symbol: `A · B` or `AB`
- Programming: `A && B`

**Memory Tip:**
- "Both must be 1 for result to be 1"
- Think of series circuit: both switches closed, light is on

---

### 3. OR运算（或运算）

**中文：**  
**功能：** 有真就真 - 只要**至少有一个输入是1**，输出就是1

**真值表：**
```
A | B | A+B (A OR B)
--|---|--------------
0 | 0 |      0    ← 只有这种情况输出0
0 | 1 |      1
1 | 0 |      1
1 | 1 |      1
```

**符号表示：**
- 数学符号：`A ∨ B`
- 逻辑符号：`A + B` ⚠️ **注意：不是数学加法！**
- 编程符号：`A || B`

**记忆技巧：**
- "只要有一个是1，结果就是1"
- 想象并联电路：只要有一条路通，灯就亮

**English:**  
**Function:** At least one true - output is 1 if **at least one input is 1**

**Truth Table:**
```
A | B | A+B (A OR B)
--|---|--------------
0 | 0 |      0    ← Only this case outputs 0
0 | 1 |      1
1 | 0 |      1
1 | 1 |      1
```

**Symbol Representations:**
- Math symbol: `A ∨ B`
- Logic symbol: `A + B` ⚠️ **Note: NOT mathematical addition!**
- Programming: `A || B`

**Memory Tip:**
- "If any input is 1, result is 1"
- Think of parallel circuit: if any path is open, light is on

---

### 4. XOR运算（异或运算）

**中文：**  
**功能：** 输入不同时输出1 - 当两个输入**不同**时（一个0，一个1），输出为1

**真值表：**
```
A | B | A XOR B
--|---|---------
0 | 0 |    0    ← 相同，输出0
0 | 1 |    1    ← 不同，输出1
1 | 0 |    1    ← 不同，输出1
1 | 1 |    0    ← 相同，输出0
```

**重要区别：XOR vs OR**
| 输入 | OR输出 | XOR输出 |
|------|--------|---------|
| 0, 0 | 0 | 0 |
| 0, 1 | 1 | 1 |
| 1, 0 | 1 | 1 |
| 1, 1 | **1** | **0** ⚠️ **不同！** |

**布尔表达式：**
```
A XOR B = A'B + AB'
```
这表示：`(NOT A AND B) OR (A AND NOT B)`

**记忆技巧：**
- "异" = 不同
- 输入不同时输出1，输入相同时输出0

**English:**  
**Function:** Output 1 when inputs differ - when two inputs are **different** (one 0, one 1), output is 1

**Truth Table:**
```
A | B | A XOR B
--|---|---------
0 | 0 |    0    ← Same, output 0
0 | 1 |    1    ← Different, output 1
1 | 0 |    1    ← Different, output 1
1 | 1 |    0    ← Same, output 0
```

**Important Difference: XOR vs OR**
| Input | OR Output | XOR Output |
|-------|-----------|------------|
| 0, 0 | 0 | 0 |
| 0, 1 | 1 | 1 |
| 1, 0 | 1 | 1 |
| 1, 1 | **1** | **0** ⚠️ **Different!** |

**Boolean Expression:**
```
A XOR B = A'B + AB'
```
This means: `(NOT A AND B) OR (A AND NOT B)`

**Memory Tip:**
- "异" = different
- Output 1 when inputs differ, output 0 when inputs are same

---

## 📐 布尔代数定律详解
## Detailed Boolean Algebra Laws

### 1. 交换律（Commutative Law）

**中文：**  
```
A + B = B + A
AB = BA
```

**含义：** 运算顺序可以交换，结果不变

**English:**  
```
A + B = B + A
AB = BA
```

**Meaning:** Order of operations can be swapped, result unchanged

---

### 2. 结合律（Associative Law）

**中文：**  
```
(A + B) + C = A + (B + C)
(AB)C = A(BC)
```

**含义：** 括号位置可以改变，结果不变

**English:**  
```
(A + B) + C = A + (B + C)
(AB)C = A(BC)
```

**Meaning:** Parentheses position can change, result unchanged

---

### 3. 分配律（Distributive Law）

**中文：**  
```
A(B + C) = AB + AC          ← 类似数学分配律
A + BC = (A + B)(A + C)     ⚠️ 注意这个！布尔代数特有
```

**第二个公式很重要！** 这是布尔代数与普通代数的主要区别之一。

**English:**  
```
A(B + C) = AB + AC          ← Similar to math distributive law
A + BC = (A + B)(A + C)     ⚠️ Note this! Unique to Boolean algebra
```

**The second formula is important!** This is one of the main differences between Boolean algebra and regular algebra.

---

### 4. 德摩根定律（De Morgan's Law）⭐⭐⭐

**中文：**  
这是**最重要的定律之一**，必须熟练掌握！

```
(A + B)' = A'B'      ← NOT (A OR B) = NOT A AND NOT B
(AB)' = A' + B'      ← NOT (A AND B) = NOT A OR NOT B
```

**记忆技巧：**
1. 打破NOT横线（去掉括号外的NOT）
2. 改变符号（AND ↔ OR）
3. 对每个变量取反

**应用示例：**
```
简化：(A + B)'C'

步骤1: (A + B)' = A'B'      （德摩根定律）
步骤2: 最终 = A'B'C'
```

**English:**  
This is **one of the most important laws**, must master it!

```
(A + B)' = A'B'      ← NOT (A OR B) = NOT A AND NOT B
(AB)' = A' + B'      ← NOT (A AND B) = NOT A OR NOT B
```

**Memory Technique:**
1. Break the NOT line (remove NOT outside parentheses)
2. Change symbol (AND ↔ OR)
3. Negate each variable

**Application Example:**
```
Simplify: (A + B)'C'

Step 1: (A + B)' = A'B'      (De Morgan's law)
Step 2: Final = A'B'C'
```

---

### 5. 恒等式（Identities）

**中文：**  
```
A + 0 = A          ← 0是OR的零元素（恒等元素）
A · 1 = A          ← 1是AND的单位元素
A + 1 = 1          ← 任何数OR 1都是1
A · 0 = 0          ← 任何数AND 0都是0
A + A' = 1         ← 互补律（Complement law）
A · A' = 0         ← 互补律
A + A = A          ← 幂等律（Idempotent law）
A · A = A          ← 幂等律
(A')' = A          ← 双重否定（Double negation）
```

**English:**  
```
A + 0 = A          ← 0 is identity element for OR
A · 1 = A          ← 1 is identity element for AND
A + 1 = 1          ← Anything OR 1 is 1
A · 0 = 0          ← Anything AND 0 is 0
A + A' = 1         ← Complement law
A · A' = 0         ← Complement law
A + A = A          ← Idempotent law
A · A = A          ← Idempotent law
(A')' = A          ← Double negation
```

---

# 📖 第三部分：逻辑门详细分析
# Part 3: Detailed Logic Gate Analysis

---

## 🔌 基本逻辑门电路符号与真值表
## Basic Logic Gate Circuit Symbols and Truth Tables

### 1. NOT门（非门）

**中文：**  
**电路符号：**
```
    A ──○──> A'
       NOT
```

**真值表：**
```
A | A'
--|---
0 | 1
1 | 0
```

**布尔表达式：** `A'` 或 `NOT A`

**English:**  
**Circuit Symbol:**
```
    A ──○──> A'
       NOT
```

**Truth Table:**
```
A | A'
--|---
0 | 1
1 | 0
```

**Boolean Expression:** `A'` or `NOT A`

---

### 2. AND门（与门）

**中文：**  
**电路符号：**
```
A ────┐
      ├──> AB
B ────┘
    AND
```

**真值表：**
```
A | B | AB
--|---|----
0 | 0 | 0
0 | 1 | 0
1 | 0 | 0
1 | 1 | 1    ← 只有这个输出1
```

**布尔表达式：** `AB` 或 `A·B` 或 `A AND B`

**English:**  
**Circuit Symbol:**
```
A ────┐
      ├──> AB
B ────┘
    AND
```

**Truth Table:**
```
A | B | AB
--|---|----
0 | 0 | 0
0 | 1 | 0
1 | 0 | 0
1 | 1 | 1    ← Only this outputs 1
```

**Boolean Expression:** `AB` or `A·B` or `A AND B`

---

### 3. OR门（或门）

**中文：**  
**电路符号：**
```
A ────┐
      ├──> A+B
B ────┘
    OR
```

**真值表：**
```
A | B | A+B
--|---|-----
0 | 0 | 0    ← 只有这个输出0
0 | 1 | 1
1 | 0 | 1
1 | 1 | 1
```

**布尔表达式：** `A + B` 或 `A OR B`

**English:**  
**Circuit Symbol:**
```
A ────┐
      ├──> A+B
B ────┘
    OR
```

**Truth Table:**
```
A | B | A+B
--|---|-----
0 | 0 | 0    ← Only this outputs 0
0 | 1 | 1
1 | 0 | 1
1 | 1 | 1
```

**Boolean Expression:** `A + B` or `A OR B`

---

### 4. XOR门（异或门）

**中文：**  
**电路符号：**
```
A ────┐
      ├──⊕──> A XOR B
B ────┘
    XOR
```

**真值表：**
```
A | B | A XOR B
--|---|---------
0 | 0 |    0    ← 相同，输出0
0 | 1 |    1    ← 不同，输出1
1 | 0 |    1    ← 不同，输出1
1 | 1 |    0    ← 相同，输出0
```

**布尔表达式：** `A XOR B = A'B + AB'`

**重要应用：** 半加器的和位（Sum）计算

**English:**  
**Circuit Symbol:**
```
A ────┐
      ├──⊕──> A XOR B
B ────┘
    XOR
```

**Truth Table:**
```
A | B | A XOR B
--|---|---------
0 | 0 |    0    ← Same, output 0
0 | 1 |    1    ← Different, output 1
1 | 0 |    1    ← Different, output 1
1 | 1 |    0    ← Same, output 0
```

**Boolean Expression:** `A XOR B = A'B + AB'`

**Important Application:** Sum bit calculation in half adder

---

### 5. NAND门（与非门）

**中文：**  
**定义：** `NAND = NOT (A AND B)`

**真值表：**
```
A | B | A NAND B
--|---|----------
0 | 0 |    1
0 | 1 |    1
1 | 0 |    1
1 | 1 |    0    ← 只有这个输出0
```

**特点：** 全1才0，其他都是1（AND的反）

**重要性：** NAND门是**通用门**（Universal Gate），可以用NAND门实现所有其他逻辑门！

**English:**  
**Definition:** `NAND = NOT (A AND B)`

**Truth Table:**
```
A | B | A NAND B
--|---|----------
0 | 0 |    1
0 | 1 |    1
1 | 0 |    1
1 | 1 |    0    ← Only this outputs 0
```

**Feature:** All 1s give 0, otherwise 1 (inverse of AND)

**Importance:** NAND gate is a **Universal Gate** - can implement all other logic gates using only NAND gates!

---

### 6. NOR门（或非门）

**中文：**  
**定义：** `NOR = NOT (A OR B)`

**真值表：**
```
A | B | A NOR B
--|---|---------
0 | 0 |    1    ← 只有这个输出1
0 | 1 |    0
1 | 0 |    0
1 | 1 |    0
```

**特点：** 全0才1，其他都是0（OR的反）

**重要性：** NOR门也是**通用门**（Universal Gate）！

**English:**  
**Definition:** `NOR = NOT (A OR B)`

**Truth Table:**
```
A | B | A NOR B
--|---|---------
0 | 0 |    1    ← Only this outputs 1
0 | 1 |    0
1 | 0 |    0
1 | 1 |    0
```

**Feature:** All 0s give 1, otherwise 0 (inverse of OR)

**Importance:** NOR gate is also a **Universal Gate**!

---

## 🔄 逻辑门之间的转换
## Conversion Between Logic Gates

### 用NAND门实现其他门

**中文：**  
由于NAND是通用门，可以用它实现所有其他门：

**NOT门：**
```
A ──NAND──> A'
    (A, A)
```

**AND门：**
```
A ──┐
    ├─NAND──○──> AB
B ──┘        NOT
```

**OR门：**
```
A' ──┐
     ├─NAND──> A+B
B' ──┘
```

**English:**  
Since NAND is a universal gate, it can implement all other gates:

**NOT Gate:**
```
A ──NAND──> A'
    (A, A)
```

**AND Gate:**
```
A ──┐
    ├─NAND──○──> AB
B ──┘        NOT
```

**OR Gate:**
```
A' ──┐
     ├─NAND──> A+B
B' ──┘
```

---

# 📖 第四部分：组合电路设计方法
# Part 4: Combinational Circuit Design Methods

---

## 🎯 组合电路设计流程
## Combinational Circuit Design Process

### 完整设计步骤

**中文：**  
设计组合电路的完整流程：

1. **理解需求**
   - 输入是什么？（有几个输入？）
   - 输出是什么？（有几个输出？）
   - 需要什么功能？

2. **列出真值表**
   - 穷举所有可能的输入组合
   - 确定每种输入对应的输出值
   - 对于n个输入，有2ⁿ种组合

3. **写出布尔表达式**
   - 从真值表推导
   - 使用SOP（Sum of Products）或POS（Product of Sums）形式
   - SOP：找出所有输出为1的行，写成乘积项的和

4. **化简表达式**
   - 使用布尔代数定律
   - 使用卡诺图（Karnaugh Map）
   - 目标：用最少的门实现

5. **画出电路图**
   - 选择合适的逻辑门
   - 连接输入和输出
   - 标记清楚

6. **验证电路**
   - 测试各种输入组合
   - 检查输出是否符合预期

**English:**  
Complete process for designing combinational circuits:

1. **Understand Requirements**
   - What are the inputs? (How many?)
   - What are the outputs? (How many?)
   - What functionality is needed?

2. **List Truth Table**
   - Enumerate all possible input combinations
   - Determine output value for each input
   - For n inputs, there are 2ⁿ combinations

3. **Write Boolean Expression**
   - Derive from truth table
   - Use SOP (Sum of Products) or POS (Product of Sums) form
   - SOP: Find all rows with output 1, write as sum of product terms

4. **Simplify Expression**
   - Use Boolean algebra laws
   - Use Karnaugh Map
   - Goal: Implement with minimum gates

5. **Draw Circuit Diagram**
   - Choose appropriate logic gates
   - Connect inputs and outputs
   - Label clearly

6. **Verify Circuit**
   - Test various input combinations
   - Check if outputs match expectations

---

## ➕ 加法器设计详解
## Detailed Adder Design

### 1. 半加器（Half Adder）

**中文：**  
**功能：** 计算两个1位二进制数的和（不考虑来自低位的进位）

**输入：** A, B（两个1位二进制数）
**输出：** Sum（和位）, Carry（进位位）

**真值表：**
```
A | B | Sum | Carry
--|---|-----|-------
0 | 0 |  0  |   0
0 | 1 |  1  |   0
1 | 0 |  1  |   0
1 | 1 |  0  |   1    ← 1+1=10（二进制），所以Sum=0, Carry=1
```

**布尔表达式：**
```
Sum = A XOR B
Carry = AB
```

**电路实现：**
```
A ────┐
      ├─XOR─> Sum
B ────┘
      │
A ────┐
      ├─AND─> Carry
B ────┘
```

**应用：** 用于最低位的加法（没有进位输入）

**English:**  
**Function:** Computes sum of two 1-bit binary numbers (without considering carry from lower bit)

**Inputs:** A, B (two 1-bit binary numbers)
**Outputs:** Sum, Carry

**Truth Table:**
```
A | B | Sum | Carry
--|---|-----|-------
0 | 0 |  0  |   0
0 | 1 |  1  |   0
1 | 0 |  1  |   0
1 | 1 |  0  |   1    ← 1+1=10 (binary), so Sum=0, Carry=1
```

**Boolean Expression:**
```
Sum = A XOR B
Carry = AB
```

**Circuit Implementation:**
```
A ────┐
      ├─XOR─> Sum
B ────┘
      │
A ────┐
      ├─AND─> Carry
B ────┘
```

**Application:** Used for least significant bit addition (no carry input)

---

### 2. 全加器（Full Adder）

**中文：**  
**功能：** 计算三个1位二进制数的和（两个加数 + 一个来自低位的进位）

**输入：** A, B, Cin（进位输入）
**输出：** Sum（和位）, Cout（进位输出）

**真值表：**
```
A | B | Cin | Sum | Cout
--|---|-----|-----|-----
0 | 0 |  0  |  0  |  0
0 | 0 |  1  |  1  |  0
0 | 1 |  0  |  1  |  0
0 | 1 |  1  |  0  |  1
1 | 0 |  0  |  1  |  0
1 | 0 |  1  |  0  |  1
1 | 1 |  0  |  0  |  1
1 | 1 |  1  |  1  |  1
```

**布尔表达式：**
```
Sum = A XOR B XOR Cin
Cout = AB + (A XOR B) · Cin
```

**或者：**
```
Cout = AB + ACin + BCin
```

**实现方法：** 可以用两个半加器组合实现！

**电路实现（使用两个半加器）：**
```
     Half Adder 1
A ────────┐
          ├─> Sum1 ─┐
B ────────┘         │
                    ├─> Half Adder 2 ─> Sum
Cin ────────────────┘
                    │
                    └─> OR ─> Cout
                    (Carry1 + Carry2)
```

**应用：** 用于所有位位置的加法（可以处理进位输入）

**English:**  
**Function:** Computes sum of three 1-bit binary numbers (two addends + one carry from lower bit)

**Inputs:** A, B, Cin (carry input)
**Outputs:** Sum, Cout (carry output)

**Truth Table:**
```
A | B | Cin | Sum | Cout
--|---|-----|-----|-----
0 | 0 |  0  |  0  |  0
0 | 0 |  1  |  1  |  0
0 | 1 |  0  |  1  |  0
0 | 1 |  1  |  0  |  1
1 | 0 |  0  |  1  |  0
1 | 0 |  1  |  0  |  1
1 | 1 |  0  |  0  |  1
1 | 1 |  1  |  1  |  1
```

**Boolean Expression:**
```
Sum = A XOR B XOR Cin
Cout = AB + (A XOR B) · Cin
```

**Or:**
```
Cout = AB + ACin + BCin
```

**Implementation Method:** Can be implemented using two half adders!

**Circuit Implementation (using two half adders):**
```
     Half Adder 1
A ────────┐
          ├─> Sum1 ─┐
B ────────┘         │
                    ├─> Half Adder 2 ─> Sum
Cin ────────────────┘
                    │
                    └─> OR ─> Cout
                    (Carry1 + Carry2)
```

**Application:** Used for all bit positions in addition (can handle carry input)

---

### 3. 多位加法器（Multi-bit Adder）

**中文：**  
**功能：** 将多个全加器连接起来，实现多位二进制数的加法

**4位加法器示例：**
```
    A₃ B₃    A₂ B₂    A₁ B₁    A₀ B₀
     │ │      │ │      │ │      │ │
     ▼ ▼      ▼ ▼      ▼ ▼      ▼ ▼
    ┌───┐    ┌───┐    ┌───┐    ┌───┐
    │FA │    │FA │    │FA │    │HA │
    └───┘    └───┘    └───┘    └───┘
     │ │      │ │      │ │      │ │
     │ └─Cout─┘ └─Cout─┘ └─Cout─┘ │
     │         │         │         │
     ▼         ▼         ▼         ▼
    S₃        S₂        S₁        S₀
```

**工作原理：**
- 最低位使用半加器（没有进位输入）
- 其他位使用全加器（有进位输入）
- 每个全加器的进位输出连接到下一个全加器的进位输入

**English:**  
**Function:** Connect multiple full adders to implement multi-bit binary addition

**4-bit Adder Example:**
```
    A₃ B₃    A₂ B₂    A₁ B₁    A₀ B₀
     │ │      │ │      │ │      │ │
     ▼ ▼      ▼ ▼      ▼ ▼      ▼ ▼
    ┌───┐    ┌───┐    ┌───┐    ┌───┐
    │FA │    │FA │    │FA │    │HA │
    └───┘    └───┘    └───┘    └───┘
     │ │      │ │      │ │      │ │
     │ └─Cout─┘ └─Cout─┘ └─Cout─┘ │
     │         │         │         │
     ▼         ▼         ▼         ▼
    S₃        S₂        S₁        S₀
```

**Working Principle:**
- Least significant bit uses half adder (no carry input)
- Other bits use full adders (with carry input)
- Each full adder's carry output connects to next full adder's carry input

---

## 🔀 多路复用器（Multiplexer, MUX）

**中文：**  
**功能：** 从多个输入中选择一个输出

**2选1 MUX：**
- **输入：** I₀, I₁（两个数据输入）
- **控制信号：** S（1个选择线）
- **输出：** Out

**真值表：**
```
S | I₀ | I₁ | Out
--|----|----|-----
0 |  0 |  0 |  0
0 |  0 |  1 |  0
0 |  1 |  0 |  1    ← S=0时，Out=I₀
0 |  1 |  1 |  1
1 |  0 |  0 |  0
1 |  0 |  1 |  1    ← S=1时，Out=I₁
1 |  1 |  0 |  0
1 |  1 |  1 |  1
```

**规律：** 当 S=0 时，输出 = I₀；当 S=1 时，输出 = I₁

**布尔表达式：**
```
Out = S'I₀ + SI₁
```

**电路实现：**
```
I₀ ────┐
       ├─AND──┐
S' ────┘      ├─OR─> Out
              │
I₁ ────┐      │
       ├─AND──┘
S  ────┘
```

**选择线数量规律：**
- 2选1 MUX：1条选择线（2¹ = 2）
- 4选1 MUX：2条选择线（2² = 4）
- 8选1 MUX：3条选择线（2³ = 8）
- **规律：** 2ⁿ选1 MUX需要n条选择线

**English:**  
**Function:** Selects one output from multiple inputs

**2-to-1 MUX:**
- **Inputs:** I₀, I₁ (two data inputs)
- **Control Signal:** S (1 selection line)
- **Output:** Out

**Truth Table:**
```
S | I₀ | I₁ | Out
--|----|----|-----
0 |  0 |  0 |  0
0 |  0 |  1 |  0
0 |  1 |  0 |  1    ← When S=0, Out=I₀
0 |  1 |  1 |  1
1 |  0 |  0 |  0
1 |  0 |  1 |  1    ← When S=1, Out=I₁
1 |  1 |  0 |  0
1 |  1 |  1 |  1
```

**Rule:** When S=0, output = I₀; when S=1, output = I₁

**Boolean Expression:**
```
Out = S'I₀ + SI₁
```

**Circuit Implementation:**
```
I₀ ────┐
       ├─AND──┐
S' ────┘      ├─OR─> Out
              │
I₁ ────┐      │
       ├─AND──┘
S  ────┘
```

**Selection Line Count Rule:**
- 2-to-1 MUX: 1 selection line (2¹ = 2)
- 4-to-1 MUX: 2 selection lines (2² = 4)
- 8-to-1 MUX: 3 selection lines (2³ = 8)
- **Rule:** 2ⁿ-to-1 MUX needs n selection lines

---

## 🔓 译码器（Decoder）

**中文：**  
**功能：** 将编码输入转换为多个输出（只有一个为1）

**2-4译码器：**
- **输入：** A, B（2位编码）
- **输出：** D₀, D₁, D₂, D₃（4个输出，一次只有一个为1）

**真值表：**
```
A | B | D₀ | D₁ | D₂ | D₃
--|---|----|----|----|----
0 | 0 |  1 |  0 |  0 |  0    ← 输入00，D₀=1
0 | 1 |  0 |  1 |  0 |  0    ← 输入01，D₁=1
1 | 0 |  0 |  0 |  1 |  0    ← 输入10，D₂=1
1 | 1 |  0 |  0 |  0 |  1    ← 输入11，D₃=1
```

**布尔表达式：**
```
D₀ = A'B'
D₁ = A'B
D₂ = AB'
D₃ = AB
```

**特点：** 输入是地址，输出是选择信号

**应用：** 内存地址译码、显示驱动等

**English:**  
**Function:** Converts encoded input into multiple outputs (only one is 1)

**2-to-4 Decoder:**
- **Inputs:** A, B (2-bit encoding)
- **Outputs:** D₀, D₁, D₂, D₃ (4 outputs, only one is 1 at a time)

**Truth Table:**
```
A | B | D₀ | D₁ | D₂ | D₃
--|---|----|----|----|----
0 | 0 |  1 |  0 |  0 |  0    ← Input 00, D₀=1
0 | 1 |  0 |  1 |  0 |  0    ← Input 01, D₁=1
1 | 0 |  0 |  0 |  1 |  0    ← Input 10, D₂=1
1 | 1 |  0 |  0 |  0 |  1    ← Input 11, D₃=1
```

**Boolean Expression:**
```
D₀ = A'B'
D₁ = A'B
D₂ = AB'
D₃ = AB
```

**Feature:** Input is address, output is selection signal

**Application:** Memory address decoding, display driving, etc.

---

# 📖 第五部分：时序电路原理与应用
# Part 5: Sequential Circuit Principles and Applications

---

## 🕐 时序电路基础
## Sequential Circuit Basics

### 时序电路的特点

**中文：**  
**定义：** 输出取决于当前输入值和电路的前一个状态（历史）的电路

**关键特征：**
- ✅ **有记忆功能** - 可以存储信息
- ✅ **输出取决于当前输入 + 过去状态** - 有历史依赖
- ✅ **通常需要时钟信号** - 同步工作
- ✅ **包含存储元件** - 触发器（Flip-Flops）
- ✅ **有反馈路径** - 输出可以影响输入

**与组合电路的区别：**
| 特征 | 组合电路 | 时序电路 |
|------|---------|---------|
| 输出依赖 | 只取决于当前输入 | 当前输入 + 过去状态 |
| 记忆 | ❌ 无 | ✅ 有 |
| 时钟 | 不需要 | 通常需要 |
| 存储元件 | 无 | 触发器、寄存器 |

**English:**  
**Definition:** Circuits where output depends on current input value and circuit's previous state (history)

**Key Features:**
- ✅ **Has memory function** - Can store information
- ✅ **Output depends on current input + past state** - Has historical dependency
- ✅ **Usually needs clock signal** - Synchronous operation
- ✅ **Contains storage elements** - Flip-flops
- ✅ **Has feedback path** - Output can affect input

**Difference from Combinational Circuits:**
| Feature | Combinational | Sequential |
|---------|--------------|------------|
| Output Dependency | Only current input | Current input + past state |
| Memory | ❌ No | ✅ Yes |
| Clock | Not needed | Usually needed |
| Storage Elements | None | Flip-flops, registers |

---

## 🔄 触发器（Flip-Flops）

### 1. RS触发器（RS Flip-Flop）

**中文：**  
**功能：** 根据 R（Reset）和 S（Set）信号设置或清除状态

**真值表：**
```
S | R | Q | Q'
--|---|----|----
0 | 0 | Q₀ | Q₀'  ← 保持（Hold）
0 | 1 | 0  | 1   ← 清除（Clear/Reset）
1 | 0 | 1  | 0   ← 设置（Set）
1 | 1 | ?  | ?   ← ⚠️ 禁用状态！（Forbidden state!）
```

**⚠️ 重要：** S=1 且 R=1 是**禁用状态**（不允许）！

**状态图：**
```
         S=1, R=0
      ┌─────────────┐
      │             │
      ▼             │
    Q=1 (Set)       │
      │             │
      │             │
    S=0, R=0        │
      │             │
      ▼             │
    Q=0 (Reset)     │
      │             │
      │             │
      └─────────────┘
      S=0, R=1
```

**English:**  
**Function:** Sets or clears state according to R (Reset) and S (Set) signals

**Truth Table:**
```
S | R | Q | Q'
--|---|----|----
0 | 0 | Q₀ | Q₀'  ← Hold
0 | 1 | 0  | 1   ← Clear/Reset
1 | 0 | 1  | 0   ← Set
1 | 1 | ?  | ?   ← ⚠️ Forbidden state!
```

**⚠️ Important:** S=1 and R=1 is a **forbidden state** (not allowed)!

**State Diagram:**
```
         S=1, R=0
      ┌─────────────┐
      │             │
      ▼             │
    Q=1 (Set)       │
      │             │
      │             │
    S=0, R=0        │
      │             │
      ▼             │
    Q=0 (Reset)     │
      │             │
      │             │
      └─────────────┘
      S=0, R=1
```

---

### 2. D触发器（D Flip-Flop）

**中文：**  
**功能：** 在时钟边沿（上升沿或下降沿）保存D的值到Q

**真值表（上升沿触发）：**
```
CLK | D | Q | Q'
----|---|----|----
↑   | 0 | 0 | 1   ← 时钟边沿时，Q = D
↑   | 1 | 1 | 0   ← 时钟边沿时，Q = D
其他 | X | Q₀| Q₀' ← 保持之前的值（记忆！）
```

**特点：**
- ✅ **简单：** Q = D（延迟一个时钟周期）
- ✅ **避免了RS触发器的禁用状态问题**
- ✅ 只需要一个数据输入D

**时钟信号：**
```
时钟信号 | Clock Signal:
    ┌─┐  ┌─┐  ┌─┐
    │ │  │ │  │ │
────┘ └──┘ └──┘ └──
```

**应用：**
- 数据寄存器
- 状态机
- 存储器

**English:**  
**Function:** Saves the value of D to Q at the clock edge (rising or falling edge)

**Truth Table (Rising Edge Trigger):**
```
CLK | D | Q | Q'
----|---|----|----
↑   | 0 | 0 | 1   ← At clock edge, Q = D
↑   | 1 | 1 | 0   ← At clock edge, Q = D
Other| X | Q₀| Q₀' ← Hold previous value (memory!)
```

**Features:**
- ✅ **Simple:** Q = D (delayed by one clock cycle)
- ✅ **Avoids forbidden state problem of RS flip-flop**
- ✅ Only needs one data input D

**Clock Signal:**
```
Clock Signal:
    ┌─┐  ┌─┐  ┌─┐
    │ │  │ │  │ │
────┘ └──┘ └──┘ └──
```

**Applications:**
- Data registers
- State machines
- Memory

---

## 📦 寄存器（Register）

**中文：**  
**定义：** 一组触发器的集合，用来存储多位数据

**4位寄存器示例：**
```
输入 | Input: D₃ D₂ D₁ D₀
      │  │  │  │
      ▼  ▼  ▼  ▼
    ┌──┐┌──┐┌──┐┌──┐
    │D ││D ││D ││D │
    │FF││FF││FF││FF│
    └──┘└──┘└──┘└──┘
      │  │  │  │
      ▼  ▼  ▼  ▼
输出 | Output: Q₃ Q₂ Q₁ Q₀

CLK ──┴──┴──┴──┴──
```

**功能：** 在时钟边沿，将输入的4位数据保存到寄存器中

**应用：**
- CPU中的通用寄存器
- 程序计数器 (PC)
- 指令寄存器 (IR)
- 累加器

**English:**  
**Definition:** A collection of flip-flops used to store multi-bit data

**4-bit Register Example:**
```
Input: D₃ D₂ D₁ D₀
      │  │  │  │
      ▼  ▼  ▼  ▼
    ┌──┐┌──┐┌──┐┌──┐
    │D ││D ││D ││D │
    │FF││FF││FF││FF│
    └──┘└──┘└──┘└──┘
      │  │  │  │
      ▼  ▼  ▼  ▼
Output: Q₃ Q₂ Q₁ Q₀

CLK ──┴──┴──┴──┴──
```

**Function:** At the clock edge, saves the input 4-bit data into the register

**Applications:**
- General-purpose registers in CPU
- Program Counter (PC)
- Instruction Register (IR)
- Accumulator

---

## 🔢 计数器（Counter）

**中文：**  
**定义：** 可以递增（或递减）计数的时序电路

**二进制计数器：**
- **功能：** 每个时钟周期，计数加1

**3位二进制计数器计数序列：**
```
时钟 | Clock | Q₂ Q₁ Q₀ | 十进制 | Decimal
-----|-------|----------|--------
  0  |   0   |  0 0 0   |   0
  1  |   1   |  0 0 1   |   1
  2  |   2   |  0 1 0   |   2
  3  |   3   |  0 1 1   |   3
  4  |   4   |  1 0 0   |   4
  5  |   5   |  1 0 1   |   5
  6  |   6   |  1 1 0   |   6
  7  |   7   |  1 1 1   |   7
  8  |   8   |  0 0 0   |   0    ← 溢出，重新开始
```

**实现方法：**
- 使用 T Flip-Flop (Toggle Flip-Flop)
- 或使用 D Flip-Flop + 逻辑门

**应用：**
- 时钟分频
- 地址生成
- 定时器

**English:**  
**Definition:** A sequential circuit that can count incrementally (or decrementally)

**Binary Counter:**
- **Function:** Each clock cycle, count increases by 1

**3-bit Binary Counter Counting Sequence:**
```
Clock | Q₂ Q₁ Q₀ | Decimal
------|----------|--------
  0   |  0 0 0   |   0
  1   |  0 0 1   |   1
  2   |  0 1 0   |   2
  3   |  0 1 1   |   3
  4   |  1 0 0   |   4
  5   |  1 0 1   |   5
  6   |  1 1 0   |   6
  7   |  1 1 1   |   7
  8   |  0 0 0   |   0    ← Overflow, restart
```

**Implementation Methods:**
- Use T Flip-Flop (Toggle Flip-Flop)
- Or use D Flip-Flop + logic gates

**Applications:**
- Clock division
- Address generation
- Timers

---

## 💾 内存（Memory）

**中文：**  
**定义：** 由大量存储单元组成的阵列，可以存储和读取数据

**内存结构：**
```
地址线 | Address Lines ──> 地址译码器 | Address Decoder ──> 选择存储单元 | Select Storage Cell
                    │
                    ▼
                存储单元阵列 | Storage Cell Array
                    │
数据线 | Data Lines <────────────┴────────────> 读/写 | Read/Write
```

### 内存操作

#### 1. 写入（Write）

**中文：**  
1. 提供地址（Address）
2. 提供数据（Data）
3. 发送写信号（Write Enable）
4. 数据被保存到指定地址

**English:**  
1. Provide address
2. Provide data
3. Send write signal (Write Enable)
4. Data is saved to the specified address

#### 2. 读取（Read）

**中文：**  
1. 提供地址（Address）
2. 发送读信号（Read Enable）
3. 数据从指定地址读出

**English:**  
1. Provide address
2. Send read signal (Read Enable)
3. Data is read from the specified address

### 内存容量计算

**中文：**  
**容量 = 地址数量 × 数据宽度**

**例子：**
- **1K × 8 bits** = 1024 地址 × 8位 = 8192 bits = **1 KB**
- 需要 **10 根地址线**（2¹⁰ = 1024）
- 需要 **8 根数据线**

**计算规律：**
- 地址线数量：n根地址线可以寻址2ⁿ个地址
- 数据线数量：等于数据宽度（位数）

**English:**  
**Capacity = Number of addresses × Data width**

**Example:**
- **1K × 8 bits** = 1024 addresses × 8 bits = 8192 bits = **1 KB**
- Need **10 address lines** (2¹⁰ = 1024)
- Need **8 data lines**

**Calculation Rule:**
- Address lines: n address lines can address 2ⁿ addresses
- Data lines: equals data width (number of bits)

---

# 📖 第六部分：实际应用案例
# Part 6: Practical Application Cases

---

## 💡 电路设计实例

### 实例1：设计一个简单的门控电路

**中文：**  
**需求：** 设计一个电路，当开关A和B都打开时，灯L才亮

**分析：**
- 输入：A（开关A），B（开关B）
- 输出：L（灯）
- 功能：A AND B

**真值表：**
```
A | B | L
--|---|--
0 | 0 | 0
0 | 1 | 0
1 | 0 | 0
1 | 1 | 1    ← 只有两个都打开，灯才亮
```

**布尔表达式：** `L = AB`

**电路实现：**
```
A ────┐
      ├─AND─> L
B ────┘
```

**English:**  
**Requirement:** Design a circuit where light L is on only when both switches A and B are on

**Analysis:**
- Inputs: A (switch A), B (switch B)
- Output: L (light)
- Function: A AND B

**Truth Table:**
```
A | B | L
--|---|--
0 | 0 | 0
0 | 1 | 0
1 | 0 | 0
1 | 1 | 1    ← Only when both are on, light is on
```

**Boolean Expression:** `L = AB`

**Circuit Implementation:**
```
A ────┐
      ├─AND─> L
B ────┘
```

---

### 实例2：设计一个多数表决电路

**中文：**  
**需求：** 设计一个3人表决电路，当至少2人同意时，输出为1

**分析：**
- 输入：A, B, C（三个人的投票，1=同意，0=不同意）
- 输出：F（结果，1=通过，0=不通过）
- 功能：至少2个输入为1

**真值表：**
```
A | B | C | F
--|---|---|--
0 | 0 | 0 | 0
0 | 0 | 1 | 0
0 | 1 | 0 | 0
0 | 1 | 1 | 1    ← 至少2个1
1 | 0 | 0 | 0
1 | 0 | 1 | 1    ← 至少2个1
1 | 1 | 0 | 1    ← 至少2个1
1 | 1 | 1 | 1    ← 至少2个1
```

**布尔表达式（SOP形式）：**
```
F = A'BC + AB'C + ABC' + ABC
```

**化简：**
```
F = A'BC + AB'C + ABC' + ABC
  = A'BC + AB'C + ABC' + ABC + ABC + ABC  （添加重复项）
  = BC(A' + A) + AC(B' + B) + AB(C' + C)
  = BC + AC + AB
```

**电路实现：**
```
A ────┐
      ├─AND─┐
B ────┘     │
            ├─OR─> F
A ────┐     │
      ├─AND─┤
C ────┘     │
            │
B ────┐     │
      ├─AND─┘
C ────┘
```

**English:**  
**Requirement:** Design a 3-person voting circuit where output is 1 when at least 2 agree

**Analysis:**
- Inputs: A, B, C (three people's votes, 1=agree, 0=disagree)
- Output: F (result, 1=pass, 0=fail)
- Function: At least 2 inputs are 1

**Truth Table:**
```
A | B | C | F
--|---|---|--
0 | 0 | 0 | 0
0 | 0 | 1 | 0
0 | 1 | 0 | 0
0 | 1 | 1 | 1    ← At least 2 ones
1 | 0 | 0 | 0
1 | 0 | 1 | 1    ← At least 2 ones
1 | 1 | 0 | 1    ← At least 2 ones
1 | 1 | 1 | 1    ← At least 2 ones
```

**Boolean Expression (SOP form):**
```
F = A'BC + AB'C + ABC' + ABC
```

**Simplification:**
```
F = A'BC + AB'C + ABC' + ABC
  = A'BC + AB'C + ABC' + ABC + ABC + ABC  (add duplicates)
  = BC(A' + A) + AC(B' + B) + AB(C' + C)
  = BC + AC + AB
```

**Circuit Implementation:**
```
A ────┐
      ├─AND─┐
B ────┘     │
            ├─OR─> F
A ────┐     │
      ├─AND─┤
C ────┘     │
            │
B ────┐     │
      ├─AND─┘
C ────┘
```

---

# 📖 第七部分：常见错误与注意事项
# Part 7: Common Mistakes and Important Notes

---

## ⚠️ 常见错误

### 错误1：混淆OR和XOR

**❌ 错误：** 认为 `1 OR 1 = 0`

**✅ 正确：**
- `1 OR 1 = 1`（OR：至少一个是1，输出就是1）
- `1 XOR 1 = 0`（XOR：输入相同时输出0）

**记忆技巧：**
- OR = "或" = 至少一个
- XOR = "异或" = 不同

---

### 错误2：混淆布尔加法和数学加法

**❌ 错误：** 认为 `A + B` 是数学加法

**✅ 正确：**
- 在布尔代数中，`A + B` 表示 **OR运算**，不是数学加法
- `1 + 1 = 1`（布尔OR），不是 `1 + 1 = 2`（数学加法）

**注意：**
- 布尔代数：`+` = OR，`·` = AND
- 数学：`+` = 加法，`×` = 乘法

---

### 错误3：德摩根定律应用错误

**❌ 错误：** `(A + B)' = A' + B'`

**✅ 正确：** `(A + B)' = A'B'`

**记忆技巧：**
1. 打破NOT横线
2. **改变符号**（AND ↔ OR）
3. 对每个变量取反

**例子：**
```
(A + B)' = A'B'      ← OR变AND
(AB)' = A' + B'      ← AND变OR
```

---

### 错误4：混淆组合电路和时序电路

**❌ 错误：** 认为组合电路有记忆功能

**✅ 正确：**
- **组合电路：** 无记忆，输出只取决于当前输入
- **时序电路：** 有记忆，输出取决于当前输入+过去状态

**判断标准：**
- 有触发器/寄存器 → 时序电路
- 有时钟信号 → 通常是时序电路
- 只有逻辑门 → 组合电路

---

### 错误5：半加器和全加器混淆

**❌ 错误：** 认为半加器有3个输入

**✅ 正确：**
- **半加器：** 2个输入（A, B），2个输出（Sum, Carry）
- **全加器：** 3个输入（A, B, Cin），2个输出（Sum, Cout）

**区别：**
- 半加器：用于最低位（没有进位输入）
- 全加器：用于其他位（有进位输入）

---

## 📝 重要注意事项

### 1. 布尔代数符号约定

**中文：**  
- `AB` 或 `A·B` = A AND B（可以省略乘号）
- `A + B` = A OR B（**不是数学加法！**）
- `A'` 或 `Ā` = NOT A

**优先级：**
1. NOT（最高）
2. AND
3. OR（最低）

**English:**  
- `AB` or `A·B` = A AND B (multiplication sign can be omitted)
- `A + B` = A OR B (**NOT mathematical addition!**)
- `A'` or `Ā` = NOT A

**Precedence:**
1. NOT (highest)
2. AND
3. OR (lowest)

---

### 2. 真值表的完整性

**中文：**  
- 对于n个输入，必须有2ⁿ行
- 必须列出所有可能的输入组合
- 不能遗漏任何情况

**例子：** 2个输入 → 2² = 4行
```
A | B | ...
--|---|----
0 | 0 | ...
0 | 1 | ...
1 | 0 | ...
1 | 1 | ...
```

**English:**  
- For n inputs, must have 2ⁿ rows
- Must list all possible input combinations
- Cannot omit any case

**Example:** 2 inputs → 2² = 4 rows
```
A | B | ...
--|---|----
0 | 0 | ...
0 | 1 | ...
1 | 0 | ...
1 | 1 | ...
```

---

### 3. 电路设计的优化原则

**中文：**  
1. **简单优于复杂** - 用最少的门实现功能
2. **可读性** - 电路图要清晰易懂
3. **可测试性** - 易于验证和调试
4. **效率** - 考虑延迟和功耗

**English:**  
1. **Simplicity over complexity** - Implement with minimum gates
2. **Readability** - Circuit diagrams should be clear
3. **Testability** - Easy to verify and debug
4. **Efficiency** - Consider delay and power consumption

---

# 📖 第八部分：练习题与解答
# Part 8: Practice Problems and Solutions

---

## 📝 练习题1：布尔表达式化简

**题目：**  
化简表达式：`(A + B)'C + ABC'`

**解答步骤：**

**步骤1：** 应用德摩根定律
```
(A + B)' = A'B'
```

**步骤2：** 代入原式
```
原式 = A'B'C + ABC'
```

**步骤3：** 提取公因子
```
= C(A'B' + AB')
```

**步骤4：** 进一步分析
```
= C[(A' + A)B']
= C[1 · B']
= CB'
```

**最终答案：** `CB'`

---

## 📝 练习题2：从真值表写出布尔表达式

**题目：**  
给定真值表，写出布尔表达式：

```
A | B | C | F
--|---|---|--
0 | 0 | 0 | 0
0 | 0 | 1 | 1    ← 输出为1
0 | 1 | 0 | 0
0 | 1 | 1 | 1    ← 输出为1
1 | 0 | 0 | 0
1 | 0 | 1 | 0
1 | 1 | 0 | 1    ← 输出为1
1 | 1 | 1 | 1    ← 输出为1
```

**解答：**

**步骤1：** 找出所有输出为1的行
- 第2行：A=0, B=0, C=1 → `A'B'C`
- 第4行：A=0, B=1, C=1 → `A'BC`
- 第7行：A=1, B=1, C=0 → `ABC'`
- 第8行：A=1, B=1, C=1 → `ABC`

**步骤2：** 写成SOP形式
```
F = A'B'C + A'BC + ABC' + ABC
```

**步骤3：** 化简
```
F = A'B'C + A'BC + ABC' + ABC
  = A'C(B' + B) + AB(C' + C)
  = A'C + AB
```

**最终答案：** `F = A'C + AB`

---

## 📝 练习题3：设计组合电路

**题目：**  
设计一个电路，当输入A、B、C中恰好有2个为1时，输出F为1。

**解答：**

**步骤1：** 列出真值表
```
A | B | C | F
--|---|---|--
0 | 0 | 0 | 0
0 | 0 | 1 | 0
0 | 1 | 0 | 0
0 | 1 | 1 | 1    ← 恰好2个1
1 | 0 | 0 | 0
1 | 0 | 1 | 1    ← 恰好2个1
1 | 1 | 0 | 1    ← 恰好2个1
1 | 1 | 1 | 0
```

**步骤2：** 写出布尔表达式
```
F = A'BC + AB'C + ABC'
```

**步骤3：** 化简
```
F = A'BC + AB'C + ABC'
  = BC(A' + A) + AB'C + ABC'
  = BC + AB'C + ABC'
  = BC + AC(B' + B)
  = BC + AC
```

**步骤4：** 画出电路图
```
B ────┐
      ├─AND─┐
C ────┘     │
            ├─OR─> F
A ────┐     │
      ├─AND─┘
C ────┘
```

---

# 📖 第九部分：考试重点速查
# Part 9: Exam Key Points Quick Reference

---

## ⚡ 必背公式速查表

### 布尔代数定律

```
交换律：    A + B = B + A
           AB = BA

结合律：    (A + B) + C = A + (B + C)
           (AB)C = A(BC)

分配律：    A(B + C) = AB + AC
           A + BC = (A + B)(A + C)  ⚠️

德摩根定律： (A + B)' = A'B'  ⭐⭐⭐
           (AB)' = A' + B'    ⭐⭐⭐

恒等式：    A + 0 = A
           A · 1 = A
           A + 1 = 1
           A · 0 = 0
           A + A' = 1
           A · A' = 0
           (A')' = A
```

---

### 逻辑门真值表速查

**NOT门：**
```
A | A'
--|---
0 | 1
1 | 0
```

**AND门：**
```
A | B | AB
--|---|----
0 | 0 | 0
0 | 1 | 0
1 | 0 | 0
1 | 1 | 1    ← 只有这个输出1
```

**OR门：**
```
A | B | A+B
--|---|-----
0 | 0 | 0    ← 只有这个输出0
0 | 1 | 1
1 | 0 | 1
1 | 1 | 1
```

**XOR门：**
```
A | B | A XOR B
--|---|---------
0 | 0 |    0    ← 相同，输出0
0 | 1 |    1    ← 不同，输出1
1 | 0 |    1    ← 不同，输出1
1 | 1 |    0    ← 相同，输出0
```

---

### 加法器公式

**半加器：**
```
Sum = A XOR B
Carry = AB
```

**全加器：**
```
Sum = A XOR B XOR Cin
Cout = AB + (A XOR B) · Cin
```

---

### 多路复用器公式

**2选1 MUX：**
```
Out = S'I₀ + SI₁
```

**选择线数量：** 2ⁿ选1 MUX需要n条选择线

---

## 🎯 关键概念对比

### 组合电路 vs 时序电路

| 特征 | 组合电路 | 时序电路 |
|------|---------|---------|
| 输出依赖 | 只取决于当前输入 | 当前输入 + 过去状态 |
| 记忆 | ❌ 无 | ✅ 有 |
| 时钟 | 不需要 | 通常需要 |
| 存储元件 | 无 | 触发器、寄存器 |
| 描述方法 | 真值表 | 状态表、状态图 |
| 例子 | 加法器、MUX | 寄存器、计数器 |

---

### 半加器 vs 全加器

| 特征 | 半加器 | 全加器 |
|------|--------|--------|
| 输入数量 | 2个（A, B） | 3个（A, B, Cin） |
| 输出 | Sum, Carry | Sum, Cout |
| 应用 | 最低位 | 所有位 |
| Sum公式 | A XOR B | A XOR B XOR Cin |
| Carry公式 | AB | AB + (A XOR B)·Cin |

---

## 💡 记忆技巧总结

1. **AND门：** "全真才真" - 想象串联电路
2. **OR门：** "有真就真" - 想象并联电路
3. **XOR门：** "异"=不同 - 输入不同时输出1
4. **NAND：** AND的反 - 全1才0
5. **NOR：** OR的反 - 全0才1
6. **德摩根定律：** "打破横线，改变符号"
7. **组合电路：** "无记忆，立即响应"
8. **时序电路：** "有记忆，需要时钟"

---

## 📋 考试前检查清单

```
□ 熟记所有逻辑门的真值表
□ 理解AND、OR、NOT、XOR的区别
□ 掌握德摩根定律（两个公式）
□ 理解组合电路 vs 时序电路的区别
□ 知道半加器和全加器的区别
□ 理解多路复用器的工作原理
□ 能够从真值表写出布尔表达式
□ 能够使用德摩根定律简化表达式
□ 理解布尔代数基本定律
□ 知道如何判断电路是组合还是时序
□ 理解触发器和寄存器的工作原理
□ 知道内存的容量计算方法
```

---

## 🚀 快速复习（5分钟版）

### 核心公式
- `(A + B)' = A'B'` ⭐
- `(AB)' = A' + B'` ⭐
- `Sum = A XOR B`（半加器）
- `Carry = AB`（半加器）

### 关键区别
- **XOR vs OR：** 1 XOR 1 = 0；1 OR 1 = 1
- **组合 vs 时序：** 组合无记忆，时序有记忆
- **半加器 vs 全加器：** 半加器2输入，全加器3输入

### 必背真值表
- **AND：** 只有1,1→1
- **OR：** 只有0,0→0
- **XOR：** 不同→1，相同→0

---

# 📖 总结
# Summary

---

## 🎓 本章学习要点

**中文：**  
通过本章学习，你应该掌握：

1. ✅ **布尔代数的基本概念和运算**
   - 理解NOT、AND、OR、XOR等运算
   - 掌握布尔代数定律

2. ✅ **逻辑门的工作原理**
   - 熟悉各种逻辑门的真值表和符号
   - 理解逻辑门之间的转换

3. ✅ **组合电路的设计方法**
   - 掌握从需求到电路的设计流程
   - 理解加法器、多路复用器等电路

4. ✅ **时序电路的基本原理**
   - 理解触发器和寄存器的工作原理
   - 掌握计数器和内存的概念

5. ✅ **实际应用能力**
   - 能够分析和设计简单电路
   - 能够解决实际问题

**English:**  
After studying this chapter, you should master:

1. ✅ **Basic concepts and operations of Boolean algebra**
   - Understand NOT, AND, OR, XOR operations
   - Master Boolean algebra laws

2. ✅ **Working principles of logic gates**
   - Familiar with truth tables and symbols of various gates
   - Understand conversion between logic gates

3. ✅ **Design methods of combinational circuits**
   - Master design process from requirements to circuits
   - Understand adders, multiplexers, etc.

4. ✅ **Basic principles of sequential circuits**
   - Understand working principles of flip-flops and registers
   - Master concepts of counters and memory

5. ✅ **Practical application ability**
   - Able to analyze and design simple circuits
   - Able to solve practical problems

---

## 📚 推荐复习资源

**中文：**  
1. 课本 Chapter 4: Gates and Circuits
2. 课堂活动题目和解答
3. 在线逻辑门模拟器（练习电路设计）
4. 布尔表达式化简工具

**English:**  
1. Textbook Chapter 4: Gates and Circuits
2. In-class activity questions and solutions
3. Online logic gate simulators (practice circuit design)
4. Boolean expression simplification tools

---

**祝学习顺利！Good luck with your studies!** 🎓✨

---

*最后更新：基于Chapter 4课后课件整理*
*Last Updated: Based on Chapter 4 Post-Class Lecture Materials*
