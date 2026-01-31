# Chapter 4: Gates and Circuits
# 第四章：门电路

---

# 📖 Slide 1: Chapter Goals | 本章目标

**中文：** 学完这章，你将能够：

**English:** After completing this chapter, you will be able to:

1. **理解布尔代数 (Boolean Algebra) 的基本概念**  
   Understand the basic concepts of **Boolean Algebra**

2. **掌握逻辑门 (Logic Gates) 的工作原理**  
   Master how **Logic Gates** work

3. **学习如何用逻辑门构建组合电路 (Combinational Circuits)**  
   Learn how to build **Combinational Circuits** using logic gates

4. **理解加法器 (Adders) 和多路复用器 (Multiplexers) 的设计**  
   Understand the design of **Adders** and **Multiplexers**

5. **了解时序电路 (Sequential Circuits) 和存储元件**  
   Understand **Sequential Circuits** and storage elements

6. **掌握电路设计的基本原则和方法**  
   Master the basic principles and methods of circuit design

---

# 📖 Slide 2: Why Learn This? | 为什么学这个？

**中文：**  
> 计算机是由 **电路** 构成的！

那么问题来了：

- 计算机如何做运算？ → 加、减、乘、除怎么实现？
- CPU内部是什么样的？ → 为什么CPU可以执行指令？
- 计算机如何存储信息？ → 0和1是怎么被保存的？
- 为什么电路能做到这么复杂的事情？ → 从简单到复杂的构建过程

**这章就是回答这些问题！**

**English:**  
> Computers are built from **circuits**!

So the questions arise:

- How do computers perform calculations? → How are addition, subtraction, multiplication, and division implemented?
- What does the inside of a CPU look like? → Why can a CPU execute instructions?
- How do computers store information? → How are 0s and 1s saved?
- Why can circuits do such complex things? → The building process from simple to complex

**This chapter answers these questions!**

---

# 📖 Slide 3: Boolean Algebra | 布尔代数基础

## What is Boolean Algebra? | 什么是布尔代数？

**中文：**  
**只处理两种值：`TRUE` (1) 和 `FALSE` (0) 的代数系统**

想象一下：
- 电灯开关 → 开(1) 或 关(0)
- 真假判断 → 对(1) 或 错(0)
- 电路状态 → 高电压(1) 或 低电压(0)

**English:**  
**An algebraic system that only deals with two values: `TRUE` (1) and `FALSE` (0)**

Think about:
- Light switch → On(1) or Off(0)
- True/False judgment → True(1) or False(0)
- Circuit state → High voltage(1) or Low voltage(0)

## Boolean Operations | 布尔运算（三种基本运算）

### 1. NOT（非运算）- 取反 | Negation

**中文：**  
```
输入 A | 输出 NOT A
-------|-------------
   0   |      1
   1   |      0
```

**口诀：** 0变1，1变0

**English:**  
```
Input A | Output NOT A
--------|--------------
   0    |      1
   1    |      0
```

**Rule:** 0 becomes 1, 1 becomes 0

### 2. AND（与运算）- 全真才真 | Conjunction

**中文：**  
```
输入 A | 输入 B | 输出 A AND B
-------|--------|---------------
   0   |    0   |       0
   0   |    1   |       0
   1   |    0   |       0
   1   |    1   |       1
```

**口诀：** 两个都是1，结果才是1（像串联电路）

**English:**  
```
Input A | Input B | Output A AND B
--------|---------|----------------
   0    |    0    |       0
   0    |    1    |       0
   1    |    0    |       0
   1    |    1    |       1
```

**Rule:** Both must be 1 for the result to be 1 (like a series circuit)

### 3. OR（或运算）- 有真就真 | Disjunction

**中文：**  
```
输入 A | 输入 B | 输出 A OR B
-------|--------|--------------
   0   |    0   |       0
   0   |    1   |       1
   1   |    0   |       1
   1   |    1   |       1
```

**口诀：** 只要有一个是1，结果就是1（像并联电路）

**English:**  
```
Input A | Input B | Output A OR B
--------|---------|---------------
   0    |    0    |       0
   0    |    1    |       1
   1    |    0    |       1
   1    |    1    |       1
```

**Rule:** If any input is 1, the result is 1 (like a parallel circuit)

---

# 📖 Slide 4: Boolean Algebra Symbol Comparison | 布尔代数符号对比

| 运算<br>Operation | 数学符号<br>Math Symbol | 逻辑符号<br>Logic Symbol | 编程符号<br>Programming | 布尔表达式<br>Boolean Expression |
|------|----------|----------|----------|------------|
| NOT  |  ¬A      | A'       | !A       | A'         |
| AND  | A ∧ B    | A · B    | A && B   | AB         |
| OR   | A ∨ B    | A + B    | A \|\| B | A + B      |

**中文：**  
**注意：**
- `AB` 表示 A AND B（乘法简写）
- `A + B` 表示 A OR B（不是数学加法！）

**English:**  
**Note:**
- `AB` means A AND B (multiplication shorthand)
- `A + B` means A OR B (NOT mathematical addition!)

---

# 📖 Slide 5: Logic Gates | 逻辑门

## What are Logic Gates? | 什么是逻辑门？

**中文：**  
**实现布尔运算的电子元件**

就像数学运算符（+、-、×、÷）有对应的物理计算器一样，  
布尔运算符（AND、OR、NOT）也有对应的物理电路元件！

**English:**  
**Electronic components that implement Boolean operations**

Just as mathematical operators (+, -, ×, ÷) have corresponding physical calculators,  
Boolean operators (AND, OR, NOT) also have corresponding physical circuit components!

## Three Basic Logic Gates | 三种基本逻辑门

### 1. NOT Gate（非门）

**中文：**  
```
符号：
  A ──○──> A'
      NOT

真值表：
  A | A'
  --|---
  0 | 1
  1 | 0
```

**English:**  
```
Symbol:
  A ──○──> A'
      NOT

Truth Table:
  A | A'
  --|---
  0 | 1
  1 | 0
```

### 2. AND Gate（与门）

**中文：**  
```
符号：
  A ────┐
        ├──> AB
  B ────┘
      AND

真值表：
  A | B | AB
  --|---|----
  0 | 0 | 0
  0 | 1 | 0
  1 | 0 | 0
  1 | 1 | 1
```

**English:**  
```
Symbol:
  A ────┐
        ├──> AB
  B ────┘
      AND

Truth Table:
  A | B | AB
  --|---|----
  0 | 0 | 0
  0 | 1 | 0
  1 | 0 | 0
  1 | 1 | 1
```

### 3. OR Gate（或门）

**中文：**  
```
符号：
  A ────┐
        ├──> A+B
  B ────┘
      OR

真值表：
  A | B | A+B
  --|---|-----
  0 | 0 | 0
  0 | 1 | 1
  1 | 0 | 1
  1 | 1 | 1
```

**English:**  
```
Symbol:
  A ────┐
        ├──> A+B
  B ────┘
      OR

Truth Table:
  A | B | A+B
  --|---|-----
  0 | 0 | 0
  0 | 1 | 1
  1 | 0 | 1
  1 | 1 | 1
```

---

# 📖 Slide 6: Composite Logic Gates | 复合逻辑门

**中文：**  
除了基本门，还有复合门（由基本门组合而成）：

**English:**  
In addition to basic gates, there are composite gates (formed by combining basic gates):

### 4. NAND Gate（与非门）
**= NOT (A AND B)**

```
A | B | A NAND B
--|---|----------
0 | 0 |    1
0 | 1 |    1
1 | 0 |    1
1 | 1 |    0
```

**中文：** **特点：** 全1才0，其他都是1（AND的反）  
**English:** **Feature:** All 1s give 0, otherwise 1 (inverse of AND)

### 5. NOR Gate（或非门）
**= NOT (A OR B)**

```
A | B | A NOR B
--|---|---------
0 | 0 |   1
0 | 1 |   0
1 | 0 |   0
1 | 1 |   0
```

**中文：** **特点：** 全0才1，其他都是0（OR的反）  
**English:** **Feature:** All 0s give 1, otherwise 0 (inverse of OR)

### 6. XOR Gate（异或门）
**= (A AND NOT B) OR (NOT A AND B)**

```
A | B | A XOR B
--|---|---------
0 | 0 |    0
0 | 1 |    1
1 | 0 |    1
1 | 1 |    0
```

**中文：** **口诀：** 两个输入不同时，输出为1（"异"=不同）  
**English:** **Rule:** Output is 1 when inputs differ ("异" = different)

### 7. XNOR Gate（同或门）
**= NOT (A XOR B)**

```
A | B | A XNOR B
--|---|----------
0 | 0 |    1
0 | 1 |    0
1 | 0 |    0
1 | 1 |    1
```

**中文：** **口诀：** 两个输入相同时，输出为1（"同"=相同）  
**English:** **Rule:** Output is 1 when inputs are the same ("同" = same)

---

# 📖 Slide 7: Boolean Algebra Laws | 布尔代数定律

**中文：**  
就像普通代数有交换律、结合律一样，布尔代数也有！

**English:**  
Just as regular algebra has commutative and associative laws, Boolean algebra has them too!

## Basic Laws | 基本定律

### Commutative Law | 交换律
- `A + B = B + A`
- `AB = BA`

### Associative Law | 结合律
- `(A + B) + C = A + (B + C)`
- `(AB)C = A(BC)`

### Distributive Law | 分配律
- `A(B + C) = AB + AC`
- `A + BC = (A + B)(A + C)` ⚠️ **注意这个！** | **Note this!**

### De Morgan's Law | 德摩根定律
- `(A + B)' = A'B'`
- `(AB)' = A' + B'`

**中文：**  
**记忆技巧：**
- NOT (A OR B) = NOT A AND NOT B
- NOT (A AND B) = NOT A OR NOT B

**English:**  
**Memory Tip:**
- NOT (A OR B) = NOT A AND NOT B
- NOT (A AND B) = NOT A OR NOT B

### Identities | 恒等式
- `A + 0 = A`      **中文：** （0是OR的零元素） | **English:** (0 is the identity element for OR)
- `A · 1 = A`      **中文：** （1是AND的单位元素） | **English:** (1 is the identity element for AND)
- `A + 1 = 1`      **中文：** （任何数OR 1都是1） | **English:** (Anything OR 1 is 1)
- `A · 0 = 0`      **中文：** （任何数AND 0都是0） | **English:** (Anything AND 0 is 0)
- `A + A' = 1`     **中文：** （互补律） | **English:** (Complement law)
- `A · A' = 0`     **中文：** （互补律） | **English:** (Complement law)
- `A + A = A`      **中文：** （幂等律） | **English:** (Idempotent law)
- `A · A = A`      **中文：** （幂等律） | **English:** (Idempotent law)
- `(A')' = A`      **中文：** （双重否定） | **English:** (Double negation)

---

# 📖 Slide 8: Combinational Circuits | 组合电路

## What are Combinational Circuits? | 什么是组合电路？

**中文：**  
**输出只取决于当前输入，与历史状态无关的电路**

特点：
- ✅ 没有记忆功能
- ✅ 输入一改变，输出立即改变
- ✅ 可以用真值表完全描述

**English:**  
**Circuits where output depends only on current inputs, independent of historical state**

Features:
- ✅ No memory function
- ✅ Output changes immediately when input changes
- ✅ Can be completely described by a truth table

### Circuit Analysis Steps | 电路分析步骤

**中文：**  
1. **列出真值表** - 确定所有可能的输入组合
2. **写出布尔表达式** - 从真值表推导
3. **化简表达式** - 使用布尔代数定律
4. **画出电路图** - 用逻辑门实现

**English:**  
1. **List truth table** - Determine all possible input combinations
2. **Write Boolean expression** - Derive from truth table
3. **Simplify expression** - Use Boolean algebra laws
4. **Draw circuit diagram** - Implement using logic gates

---

# 📖 Slide 9: Circuit Example: Simple Adder | 电路示例：简单加法器

## Half Adder（半加器）

**中文：**  
**功能：** 计算两个1位二进制数的和

**English:**  
**Function:** Computes the sum of two 1-bit binary numbers

### Truth Table | 真值表

```
A | B | Sum | Carry
--|---|-----|-------
0 | 0 |  0  |   0
0 | 1 |  1  |   0
1 | 0 |  1  |   0
1 | 1 |  0  |   1
```

### Boolean Expression | 布尔表达式

- `Sum = A XOR B`     **中文：** （和 = 异或） | **English:** (Sum = XOR)
- `Carry = AB`        **中文：** （进位 = 与） | **English:** (Carry = AND)

### Circuit Implementation | 电路实现

```
A ────┐
      ├─XOR─> Sum
B ────┘
      │
A ────┐
      ├─AND─> Carry
B ────┘
```

---

# 📖 Slide 10: Full Adder（全加器）

## What is a Full Adder? | 什么是全加器？

**中文：**  
**可以处理三个输入（两个加数 + 一个进位）的加法器**

**English:**  
**An adder that can handle three inputs (two addends + one carry-in)**

### Truth Table | 真值表

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

### Boolean Expression | 布尔表达式

- `Sum = A XOR B XOR Cin`
- `Cout = AB + (A XOR B) · Cin`

**中文：** **或者：** `Cout = AB + ACin + BCin`  
**English:** **Or:** `Cout = AB + ACin + BCin`

### Implementation Method | 实现方法

**中文：**  
可以用两个半加器组合实现！

**English:**  
Can be implemented using two half adders in combination!

```
     Half Adder 1
A ────────┐
          ├─> Sum1 ─┐
B ────────┘         │
                    ├─> Half Adder 2 ─> Sum
Cin ────────────────┘
                    │
                    └─> OR ─> Cout
```

---

# 📖 Slide 11: Multiplexer (MUX) | 多路复用器

## What is a Multiplexer? | 什么是多路复用器？

**中文：**  
**从多个输入中选择一个输出的电路**

**English:**  
**A circuit that selects one output from multiple inputs**

### 2-to-1 MUX（2选1）

**中文：**  
**功能：** 根据选择信号，从2个输入中选择1个输出

**English:**  
**Function:** According to the selection signal, select 1 output from 2 inputs

### Truth Table | 真值表

```
S | I0 | I1 | Out
--|----|----|-----
0 |  0 |  0 |  0
0 |  0 |  1 |  0
0 |  1 |  0 |  1
0 |  1 |  1 |  1
1 |  0 |  0 |  0
1 |  0 |  1 |  1
1 |  1 |  0 |  0
1 |  1 |  1 |  1
```

**中文：**  
**规律：** 当 S=0 时，输出 = I0；当 S=1 时，输出 = I1

**English:**  
**Rule:** When S=0, output = I0; when S=1, output = I1

### Boolean Expression | 布尔表达式

```
Out = S'I0 + SI1
```

### Circuit Implementation | 电路实现

```
I0 ────┐
       ├─AND──┐
S' ────┘      ├─OR─> Out
              │
I1 ────┐      │
       ├─AND──┘
S  ────┘
```

---

# 📖 Slide 12: Decoder | 译码器

## What is a Decoder? | 什么是译码器？

**中文：**  
**将编码输入转换为多个输出（只有一个为1）的电路**

**English:**  
**A circuit that converts encoded input into multiple outputs (only one is 1)**

### 2-to-4 Decoder（2-4译码器）

**中文：**  
**功能：** 2位输入编码，4个输出（一次只有一个为1）

**English:**  
**Function:** 2-bit input encoding, 4 outputs (only one is 1 at a time)

### Truth Table | 真值表

```
A | B | D0 | D1 | D2 | D3
--|---|----|----|----|----
0 | 0 |  1 |  0 |  0 |  0
0 | 1 |  0 |  1 |  0 |  0
1 | 0 |  0 |  0 |  1 |  0
1 | 1 |  0 |  0 |  0 |  1
```

### Boolean Expression | 布尔表达式

- `D0 = A'B'`
- `D1 = A'B`
- `D2 = AB'`
- `D3 = AB`

**中文：**  
**特点：** 输入是地址，输出是选择信号

**English:**  
**Feature:** Input is address, output is selection signal

---

# 📖 Slide 13: Sequential Circuits | 时序电路

## What are Sequential Circuits? | 什么是时序电路？

**中文：**  
**输出不仅取决于当前输入，还取决于历史状态的电路**

特点：
- ✅ 有记忆功能
- ✅ 需要存储元件（如触发器）
- ✅ 可以用来实现计数器、寄存器等

**English:**  
**Circuits where output depends not only on current input but also on historical state**

Features:
- ✅ Has memory function
- ✅ Requires storage elements (such as flip-flops)
- ✅ Can be used to implement counters, registers, etc.

### Difference from Combinational Circuits | 与组合电路的区别

| 特性<br>Feature | 组合电路<br>Combinational | 时序电路<br>Sequential |
|------|----------|----------|
| 输出<br>Output | 只取决于当前输入<br>Only depends on current input | 取决于当前输入+历史状态<br>Depends on current input + history |
| 记忆<br>Memory | ❌ 无<br>No | ✅ 有<br>Yes |
| 时钟<br>Clock | 不需要<br>Not needed | 通常需要<br>Usually needed |
| 应用<br>Application | 加法器、MUX<br>Adders, MUX | 寄存器、计数器、内存<br>Registers, counters, memory |

---

# 📖 Slide 14: Flip-Flops | 触发器

## What is a Flip-Flop? | 什么是触发器？

**中文：**  
**最基本的存储元件，可以保存1位信息（0或1）**

**English:**  
**The most basic storage element that can store 1 bit of information (0 or 1)**

### RS Flip-Flop（RS触发器）

**中文：**  
**功能：** 根据 R（Reset）和 S（Set）信号设置或清除状态

**English:**  
**Function:** Sets or clears state according to R (Reset) and S (Set) signals

### Truth Table | 真值表

```
S | R | Q | Q'
--|---|----|----
0 | 0 | Q₀ | Q₀'  (保持 | Hold)
0 | 1 | 0  | 1   (清除 | Clear)
1 | 0 | 1  | 0   (设置 | Set)
1 | 1 | ?  | ?   (禁用状态！| Forbidden state!)
```

⚠️ **中文：** **注意：** S=1 且 R=1 是禁用状态（不允许）！  
⚠️ **English:** **Note:** S=1 and R=1 is a forbidden state (not allowed)!

### State Diagram | 状态图

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

# 📖 Slide 15: Clocked Flip-Flops | 时钟触发器

## What is a Clock? | 什么是时钟？

**中文：**  
**一个周期性信号，用于同步电路操作**

**English:**  
**A periodic signal used to synchronize circuit operations**

```
时钟信号 | Clock Signal:
    ┌─┐  ┌─┐  ┌─┐
    │ │  │ │  │ │
────┘ └──┘ └──┘ └──
```

### D Flip-Flop (D触发器)

**中文：**  
**功能：** 在时钟边沿（上升沿或下降沿）保存D的值到Q

**English:**  
**Function:** Saves the value of D to Q at the clock edge (rising or falling edge)

### Truth Table (Rising Edge Trigger) | 真值表（上升沿触发）

```
CLK | D | Q | Q'
----|---|----|----
↑   | 0 | 0 | 1
↑   | 1 | 1 | 0
其他 | X | Q₀| Q₀'  (保持 | Hold)
```

**中文：**  
**特点：** 
- ✅ 简单：Q = D（延迟一个时钟周期）
- ✅ 避免了RS触发器的禁用状态问题

**English:**  
**Features:** 
- ✅ Simple: Q = D (delayed by one clock cycle)
- ✅ Avoids the forbidden state problem of RS flip-flop

### Applications | 应用

**中文：**  
- 数据寄存器
- 状态机
- 存储器

**English:**  
- Data registers
- State machines
- Memory

---

# 📖 Slide 16: Register | 寄存器 (Register)

## What is a Register? | 什么是寄存器？

**中文：**  
**一组触发器的集合，用来存储多位数据**

**English:**  
**A collection of flip-flops used to store multi-bit data**

### 4-bit Register | 4位寄存器

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

**中文：**  
**功能：** 在时钟边沿，将输入的4位数据保存到寄存器中

**English:**  
**Function:** At the clock edge, saves the input 4-bit data into the register

### Applications | 应用

**中文：**  
- CPU中的通用寄存器
- 程序计数器 (PC)
- 指令寄存器 (IR)

**English:**  
- General-purpose registers in CPU
- Program Counter (PC)
- Instruction Register (IR)

---

# 📖 Slide 17: Counter | 计数器 (Counter)

## What is a Counter? | 什么是计数器？

**中文：**  
**可以递增（或递减）计数的时序电路**

**English:**  
**A sequential circuit that can count incrementally (or decrementally)**

### Binary Counter | 二进制计数器

**中文：**  
**功能：** 每个时钟周期，计数加1

**English:**  
**Function:** Each clock cycle, count increases by 1

### Counting Sequence (3-bit Binary Counter) | 计数序列（3位二进制计数器）

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
  8  |   8   |  0 0 0   |   0 (溢出，重新开始 | Overflow, restart)
```

### Implementation Method | 实现方法

**中文：**  
- 使用 T Flip-Flop (Toggle Flip-Flop)
- 或使用 D Flip-Flop + 逻辑门

**English:**  
- Use T Flip-Flop (Toggle Flip-Flop)
- Or use D Flip-Flop + logic gates

---

# 📖 Slide 18: Memory | 内存 (Memory)

## What is Memory? | 什么是内存？

**中文：**  
**由大量存储单元组成的阵列，可以存储和读取数据**

**English:**  
**An array of many storage cells that can store and read data**

### Memory Structure | 内存结构

```
地址线 | Address Lines ──> 地址译码器 | Address Decoder ──> 选择存储单元 | Select Storage Cell
                    │
                    ▼
                存储单元阵列 | Storage Cell Array
                    │
数据线 | Data Lines <────────────┴────────────> 读/写 | Read/Write
```

### Memory Operations | 内存操作

#### 1. Write | 写入（Write）

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

#### 2. Read | 读取（Read）

**中文：**  
1. 提供地址（Address）
2. 发送读信号（Read Enable）
3. 数据从指定地址读出

**English:**  
1. Provide address
2. Send read signal (Read Enable)
3. Data is read from the specified address

### Memory Capacity Calculation | 内存容量计算

**中文：**  
**容量 = 地址数量 × 数据宽度**

例如：
- 1K × 8 bits = 1024 地址 × 8位 = 8192 bits = 1 KB
- 需要 10 根地址线（2¹⁰ = 1024）
- 需要 8 根数据线

**English:**  
**Capacity = Number of addresses × Data width**

Example:
- 1K × 8 bits = 1024 addresses × 8 bits = 8192 bits = 1 KB
- Need 10 address lines (2¹⁰ = 1024)
- Need 8 data lines

---

# 📖 Slide 19: Circuit Design Process | 电路设计流程

## From Requirements to Circuit | 从需求到电路

### Step 1: Understand Requirements | 步骤1：理解需求

**中文：**  
- 输入是什么？
- 输出是什么？
- 需要什么功能？

**English:**  
- What are the inputs?
- What are the outputs?
- What functionality is needed?

### Step 2: List Truth Table | 步骤2：列出真值表

**中文：**  
- 穷举所有可能的输入组合
- 确定每种输入对应的输出

**English:**  
- Enumerate all possible input combinations
- Determine the output for each input

### Step 3: Write Boolean Expression | 步骤3：写出布尔表达式

**中文：**  
- 从真值表推导布尔表达式
- 使用 SOP（Sum of Products）或 POS（Product of Sums）

**English:**  
- Derive Boolean expression from truth table
- Use SOP (Sum of Products) or POS (Product of Sums)

### Step 4: Simplify Expression | 步骤4：化简表达式

**中文：**  
- 使用布尔代数定律
- 使用卡诺图（Karnaugh Map）
- 目标：用最少的门实现

**English:**  
- Use Boolean algebra laws
- Use Karnaugh Map
- Goal: Implement with minimum gates

### Step 5: Draw Circuit Diagram | 步骤5：画出电路图

**中文：**  
- 选择合适的逻辑门
- 连接输入和输出
- 标记清楚

**English:**  
- Choose appropriate logic gates
- Connect inputs and outputs
- Label clearly

### Step 6: Verify Circuit | 步骤6：验证电路

**中文：**  
- 测试各种输入组合
- 检查输出是否符合预期

**English:**  
- Test various input combinations
- Check if outputs match expectations

---

# 📖 Slide 20: Key Concepts Summary | 关键概念总结

## 🎯 Core Concepts | 核心概念

**中文：**  
1. **布尔代数** - 只处理0和1的数学
2. **逻辑门** - 实现布尔运算的物理元件
3. **组合电路** - 输出只取决于当前输入
4. **时序电路** - 输出取决于当前输入和历史状态
5. **触发器** - 基本的存储元件
6. **寄存器** - 多触发器的组合
7. **内存** - 大量存储单元的阵列

**English:**  
1. **Boolean Algebra** - Mathematics that only deals with 0 and 1
2. **Logic Gates** - Physical components that implement Boolean operations
3. **Combinational Circuits** - Output depends only on current input
4. **Sequential Circuits** - Output depends on current input and historical state
5. **Flip-Flops** - Basic storage elements
6. **Registers** - Combination of multiple flip-flops
7. **Memory** - Array of many storage cells

## 🔑 Important Formulas | 重要公式

- `A + A' = 1` **中文：** （互补律） | **English:** (Complement law)
- `A · A' = 0` **中文：** （互补律） | **English:** (Complement law)
- `(A + B)' = A'B'` **中文：** （德摩根定律） | **English:** (De Morgan's law)
- `(AB)' = A' + B'` **中文：** （德摩根定律） | **English:** (De Morgan's law)

## 💡 Design Principles | 设计原则

**中文：**  
1. **简单优于复杂** - 用最少的门实现功能
2. **可读性** - 电路图要清晰易懂
3. **可测试性** - 易于验证和调试
4. **效率** - 考虑延迟和功耗

**English:**  
1. **Simplicity over complexity** - Implement functionality with minimum gates
2. **Readability** - Circuit diagrams should be clear and understandable
3. **Testability** - Easy to verify and debug
4. **Efficiency** - Consider delay and power consumption

---

# 📖 Preview Key Questions | 预习重点问题

## 🤔 Thinking Questions | 思考题

1. **为什么需要布尔代数？** | **Why do we need Boolean algebra?**
   **中文：** 计算机如何用电路实现逻辑运算？  
   **English:** How do computers implement logical operations using circuits?

2. **AND、OR、NOT这三个基本门够吗？** | **Are AND, OR, NOT three basic gates enough?**
   **中文：** 能不能只用这三个门实现所有功能？  
   **English:** Can we implement all functions using only these three gates?

3. **组合电路和时序电路的区别是什么？** | **What is the difference between combinational and sequential circuits?**
   **中文：** 为什么有些电路需要记忆，有些不需要？  
   **English:** Why do some circuits need memory while others don't?

4. **CPU是如何执行指令的？** | **How does a CPU execute instructions?**
   **中文：** 指令是如何被解析和执行的？  
   **English:** How are instructions parsed and executed?

5. **内存是如何工作的？** | **How does memory work?**
   **中文：** 为什么可以按地址访问数据？  
   **English:** Why can we access data by address?

---

# 📖 Preview Suggestions | 预习建议

## ✅ Pre-class Preparation | 课前准备

1. **复习Chapter 3** | **Review Chapter 3**
   **中文：**  
   - 确保理解二进制数表示
   - 理解0和1在计算机中的作用
   
   **English:**  
   - Ensure understanding of binary number representation
   - Understand the role of 0 and 1 in computers

2. **理解基本概念** | **Understand Basic Concepts**
   **中文：**  
   - 布尔代数的三种基本运算
   - 逻辑门的真值表
   - 电路图的基本符号
   
   **English:**  
   - Three basic operations of Boolean algebra
   - Truth tables of logic gates
   - Basic symbols of circuit diagrams

3. **准备问题** | **Prepare Questions**
   **中文：**  
   - 记录不理解的概念
   - 准备好课上提问
   
   **English:**  
   - Record concepts you don't understand
   - Prepare questions for class

## 🎯 Class Focus | 课上重点

1. **认真听讲** | **Listen Carefully**
   **中文：**  
   - 电路图的绘制方法
   - 真值表的分析方法
   - 布尔表达式的化简技巧
   
   **English:**  
   - Methods for drawing circuit diagrams
   - Methods for analyzing truth tables
   - Techniques for simplifying Boolean expressions

2. **动手练习** | **Hands-on Practice**
   **中文：**  
   - 完成课堂练习题
   - 绘制电路图
   - 验证真值表
   
   **English:**  
   - Complete in-class exercises
   - Draw circuit diagrams
   - Verify truth tables

3. **积极提问** | **Ask Questions Actively**
   **中文：**  
   - 不理解的地方及时问
   - 与其他同学讨论
   
   **English:**  
   - Ask questions immediately when unclear
   - Discuss with classmates

---

# 📖 Related Resources | 相关资源

## 📚 Recommended Reading | 推荐阅读

**中文：**  
- 课本 Chapter 4: Gates and Circuits
- 逻辑门真值表速查
- 布尔代数定律总结

**English:**  
- Textbook Chapter 4: Gates and Circuits
- Quick reference for logic gate truth tables
- Summary of Boolean algebra laws

## 🔧 Online Tools | 在线工具

**中文：**  
- 逻辑门模拟器（可以用来测试电路）
- 真值表生成器
- 布尔表达式化简工具

**English:**  
- Logic gate simulators (can be used to test circuits)
- Truth table generators
- Boolean expression simplification tools

---

**中文：** **祝预习顺利！明天上课见！** 🎓✨  
**English:** **Good luck with your preview! See you in class tomorrow!** 🎓✨
