# Chapter 6: Low-Level Programming Languages and Pseudocode (Complete)
# 第六章：低级编程语言与伪代码（完整版）

*Based on Pre + Post Lecture Materials | 基于课前+课后课件*

---

# 📖 Page 1-2: Chapter Overview | 章节概览

**中文：**  

### 本章背景

Chapter 6 建立在之前章节的基础上：
- **Components** - 组件
- **Circuits** - 电路
- **Gates** - 门
- **Transistors** - 晶体管

**English:**  

### Chapter Background

Chapter 6 builds on previous chapters:
- Components → Circuits → Gates → Transistors

---

# 📖 Page 3: Chapter Goals | 本章目标

**中文：** 学完这章，你将能够：

**English:** After completing this chapter, you will be able to:

1. **描述用于表达算法的伪代码结构**  
   Describe the pseudocode constructs used in expressing an algorithm

2. **使用伪代码表达算法**  
   Use pseudocode to express an algorithm

3. **描述两种测试方法**  
   Describe two approaches to testing

4. **为简单的汇编语言程序设计和实施测试计划**  
   Design and implement a test plan for a simple assembly-language program

---

# 📖 Page 4: Abstractions | 抽象层次

**中文：**  

### 你在这里 (You are here)

从底层硬件（晶体管、门、电路）到高级编程，我们处于**抽象层次**的某个位置。

**English:**  

### You are here

From low-level hardware (transistors, gates, circuits) to high-level programming—we are at a certain level of **abstraction**.

---

# 📖 Page 5: Programming | 编程

**中文：**  

### 什么是编程？

- **编程 (Programming)** = 为计算机编写指令，使其执行特定操作或表现出期望行为
- 我们需要学习一种**语言**来编写指令
- **编程语言 (Programming Language)** = 向计算机传达指令的工具

**English:**  

### What is Programming?

- **Programming** = Writing instructions for the computer to perform specific operations or exhibit a certain desired behaviour
- We need to learn a **language** to write instructions
- **Programming Language** = Communicates instructions to a computer

---

# 📖 Page 6-7: Machine Language | 机器语言

**中文：**  

### 机器语言 (Machine Language)

- 用**二进制 (1和0)** 编写的计算机程序，由计算机硬件设计定义
- 用机器语言编程**缓慢且繁琐**

**特点：**
- 每种处理器类型都有自己特定的机器指令集
- CPU的数字逻辑识别指令的二进制表示
- 每条机器语言指令只执行一个（通常）非常低级的任务

**English:**  

### Machine Language

- Computer programs written in **binary (1s and 0s)** defined by the computer's hardware design
- Programming in machine language is **slow and tedious**

**Characteristics:**
- Every processor type has its own specific set of machine instructions
- The digital logic of the CPU recognizes the binary representations of the instructions
- Each machine-language instruction does only one (typically) very low-level task

---

# 📖 Page 8-9: Assembly Language | 汇编语言

**中文：**  

### 汇编语言 (Assembly Language)

- 使用**类似英语的缩写（助记符 mnemonic codes）** 表示基本操作
- **汇编器 (Assemblers)** 将汇编语言程序转换为机器语言

**English:**  

### Assembly Language

- **English-like abbreviations (mnemonic codes)** to represent elementary operations
- **Translator programs (assemblers)** convert programs in assembly language to machine language

---

# 📖 Page 10: High-Level Language | 高级语言

**中文：**  

### 高级语言 (High-Level Language)

- 用高级语言编写的程序包含**类似日常英语的语句**，可完成大量任务
- **编译器 (Compilers)** 将高级语言程序转换为机器语言

**English:**  

### High-Level Language

- A program written in a high-level language contains **single statements, almost like everyday English**, to accomplish substantial tasks
- **Compilers** convert programs in high-level languages into machine language

---

# 📖 Page 11: What is an Algorithm? | 什么是算法？

**中文：**  

### 算法 (Algorithm)

**用于解决问题的步骤**

**问题必须：**
- **明确定义 (Well defined)**
- **被程序员完全理解 (Fully understood)**

**步骤必须：**
- **有序 (Ordered)**
- **无歧义 (Unambiguous)**
- **完整 (Complete)**

**English:**  

### Algorithm

**Steps used to solve a problem**

**Problem must be:** Well defined, Fully understood by the programmer

**Steps must be:** Ordered, Unambiguous, Complete

---

# 📖 Page 12: Program Development | 程序开发

**中文：**  

### 程序开发四步骤

1. **理解问题** - Understand the problem
2. **表示解决方案（算法）** - Represent your solution (algorithm)
   - 伪代码 (Pseudocode)
   - 流程图 (Flowchart)
3. **在程序中实现算法** - Implement the algorithm in a program
4. **测试和调试程序** - Test and debug your program

**English:**  

### Four Steps of Program Development

1. Understand the problem
2. Represent your solution (Pseudocode / Flowchart)
3. Implement the algorithm in a program
4. Test and debug your program

---

# 📖 Page 13: Step 1 - Understanding the Problem | 理解问题

**中文：**  

### IPO 模型

- **Input (输入)** - 你获得了什么信息或数据？
- **Process (处理)** - 你必须对信息/数据做什么？→ 这就是你的**算法**！
- **Output (输出)** - 你的交付物是什么？

**English:**  

### IPO Model

- **Input** - What information or data are you given?
- **Process** - What must you do with the information/data? → This is your **algorithm**!
- **Output** - What are your deliverables?

---

# 📖 Page 14: "Area" Example | 面积示例

**中文：**  

### 任务：创建计算矩形面积的程序

- **Input:** 矩形的长和宽
- **Process:** 长 × 宽 = 面积
- **Output:** 显示计算出的面积

**English:**  

### Task: Create a program to calculate the area of a rectangle

- **Input:** Length and width of the rectangle
- **Process:** Multiply length by width to find the area
- **Output:** Display the calculated area

---

# 📖 Page 15-16: Pseudocode | 伪代码

**中文：**  

### 伪代码 (Pseudocode)

- 一种表达算法的方式，使用**英语短语和缩进**使解题步骤明确
- 伪代码**没有语法规则**，但保持**一致性和无歧义**很重要

**English:**  

### Pseudocode

- A way of expressing algorithms that uses a **mixture of English phrases and indentation** to make the steps in the solution explicit
- There are **no grammar rules** in pseudocode, but it's important to be **consistent and unambiguous**

---

# 📖 Page 17: Pseudocode Functionality | 伪代码功能

**中文：**  

| 功能 | 说明 | 关键词 |
|-----|------|--------|
| **变量 (Variables)** | 存储值的命名位置 | quotient, decimalNum |
| **赋值 (Assignment)** | 将表达式的值存入变量 | Set quotient to 64 或 quotient ← 64 |
| **输入 (Input)** | 从外部获取值并存入变量 | Get, Read |
| **输出 (Output)** | 在输出设备上打印值 | Write, Print |

**输出示例：**
- `Write "Err"` - 在屏幕上显示双引号之间的字符
- `Write sum` - 在屏幕上显示变量 sum 的内容（sum 的值不变）

**English:**  

| Function | Description | Keywords |
|----------|-------------|----------|
| **Variables** | Names of places to store values | quotient, decimalNum |
| **Assignment** | Storing the value of an expression into a variable | Set quotient to 64 OR quotient ← 64 |
| **Input** | Getting values from the outside world | Get, Read |
| **Output** | Printing a value on an output device | Write, Print |

---

# 📖 Page 18: Pseudocode – Area Example | 面积伪代码示例

**中文：**  

```
Start
Prompt the user to enter the length of the rectangle
Get the Length
Prompt the user to enter the width of the rectangle
Get the Width
Calculate the area of the rectangle (area = length * width)
Display the calculated area of the rectangle
End
```

**English:** Same as above (Pseudocode is language-agnostic)

---

# 📖 Page 19-20: Flowchart Symbols | 流程图符号

**中文：**  

| 符号 | 名称 | 用途 |
|-----|------|------|
| 椭圆形 | Start/End | 开始/结束 |
| 矩形 | Data Processing | 数据处理 |
| 平行四边形 | Input/Output | 输入/输出 |
| 菱形 | Decision | 判断/分支 |
| 箭头 | Flow Control | 流程控制 |

**English:**  

| Symbol | Name | Purpose |
|--------|------|---------|
| Oval | Start/End | Start/End Symbol |
| Rectangle | Data Processing | Data Processing Symbol |
| Parallelogram | Input/Output | Input/Output |
| Diamond | Decision | Decision Symbol |
| Arrows | Flow Control | Flow Control Arrows |

---

# 📖 Page 21: Pseudocode – Area Example with Validation | 带验证的面积示例

**中文：**  

```
Start
Prompt the user to enter the length of the rectangle
Get the Length
Prompt the user to enter the width of the rectangle
Get the Width
Check if the length and width are non-negative numbers
  If either length or width is negative, display an error message and stop
  Otherwise, continue to the next step
Calculate the area of the rectangle (area = length * width)
Display the calculated area of the rectangle
End
```

**关键点：** 增加了**输入验证 (Input Validation)** —— 检查长和宽是否非负

**English:** Key addition: **Input validation** - check if length and width are non-negative

---

# 📖 Page 22-23: Control Structures | 控制结构

**中文：**  

### 控制结构 (Control Structures)

控制程序**流程**或**运行顺序**的结构

**三种重要控制结构：**

1. **顺序 (Sequence)** - 一步接一步，无分支
2. **决策 (Decision Making)** - 根据条件选择执行路径
3. **循环 (Looping)** - 重复执行

**English:**  

### Control Structures

Structures that control how the program **"flows"** or operates, and in what order

1. **Sequence** - One step after another, with no branches
2. **Decision Making** - Selecting one choice from many based on a condition
3. **Looping** - Doing something over and over again

---

# 📖 Page 24-27: Decision Making | 决策/选择

**中文：**  

### 决策 (Decision Making)

- 根据**特定原因或条件**从多个选择中选一个
- 如果某条件为真，做 A；否则做 B

### 示例：判断数字是否为正数

```
Display "Enter the number: "
Get the number
If number > 0
  Display "It is positive"
Else
  Display "It is negative"
```

### 选择结构 (Selection) - 多分支

```
IF (age < 12)
  Write "Pay children's rate"
  Write "You get a free box of popcorn"
ELSE IF (age < 65)
  Write "Pay regular rate"
ELSE
  Write "Pay senior citizens rate"
```

**English:**  

### Decision Making

- **If something is true, do A … if it's not, do B**
- Selection: Choose to execute one statement (or group) or another

---

# 📖 Page 28-30: Super Simple CPU Example #1 | Super Simple CPU 示例1

**中文：**  

### 汇编程序分析

```
LOD ONE   ; 将 2 加载到累加器 (A)
SUB TWO   ; A - 6
JNG DONE  ; 如果 A 为负，跳转到 DONE
STO TWO   ; 将 A 的值存入 TWO
DONE STP  ; 停止程序
ONE DAT 2 ; 常量 2
TWO DAT 6 ; 常量 6
```

**执行过程：** A=2 → A=2-6=-4 → A为负，跳转DONE → 停止

**结果：** TWO 被修改为 -4（原为6）

**Super Simple CPU 条件跳转指令：** JNG, JZR, JMP

**English:**  

### Assembly Program Analysis

- **LOD** - Load into accumulator
- **SUB** - Subtract
- **JNG** - Jump if Negative (to DONE)
- **STO** - Store
- **STP** - Stop
- **DAT** - Data value

---

# 📖 Page 31-34: Looping / Repetition | 循环/重复

**中文：**  

### 循环 (Looping)

- **重复做某事**
- 必须与**决策**结合使用，否则会**无限循环 (infinite loop)**

### 示例：从1数到20

```
Set num = 1
While num <= 20
  Display num
  num = num + 1
End loop
```

### 重复结构伪代码

```
Set count to 1
WHILE (count < 10)
  Write "Enter an integer number"
  Read aNumber
  Write "You entered " + aNumber
  Set count to count + 1
```

**English:**  

### Looping

- **Doing something over and over again**
- Used in combination with **decision making** - otherwise we loop forever (**infinite loop**)

---

# 📖 Page 35-36: Loop Strategies | 循环策略

**中文：**  

### 循环设计要点

1. **是否需要循环？** - 是否有重复的动作？
2. **只有重复的语句放在循环内**
3. **条件是什么？** - 需要初始化条件
4. **循环何时停止？** - 循环控制语句通常在循环末尾

### 计数控制循环 (Count-Controlled Loop) 三部分

| 部分 | 说明 |
|-----|------|
| **初始化 (Initialization)** | 循环控制变量在循环外初始化 |
| **测试 (Testing)** | 循环控制变量与预定值比较 |
| **递增/递减 (Incrementation)** | 循环控制变量在循环内更新 |

**English:**  

### Loop Strategies

- **Initialization** - Loop control variable initialized outside the loop
- **Testing** - Tested against a predetermined value
- **Incrementation** - Incremented (or decremented) inside the loop

---

# 📖 Page 37-39: Repetition Examples | 重复结构示例

**中文：**  

### 示例1：打印消息5次

```
Set count to 5
WHILE (count >= 1)
  Write "I like Programming!"
  Set count to count - 1
```

### 示例2：读入10个数并打印

```
Set count to 0
WHILE (count < 10)
  Write "Enter an integer number"
  Read number
  Write "You entered " + number
  Increment count
```

### 示例3：显示1到10

```
Set count to 1
WHILE (count <= 10)
  Write count + " "
  Increment count
```

### 示例4：显示1到100的偶数

```
Set count to 2
WHILE (count <= 100)
  Write count + ", "
  Set count to count + 2
```

**English:** Same logic - counter initialization, test, update

---

# 📖 Page 40-41: Super Simple CPU Example #2 | Super Simple CPU 示例2（循环）

**中文：**  

### 带循环的汇编程序

```
LDI 10      ; 将 10 加载到 A
TOP JNG DONE ; 如果 A 为负，跳转到 DONE
SUB NUM     ; A - 2
JMP TOP     ; 跳回循环顶部
DONE STP    ; 停止
NUM DAT 2   ; 常量 2
```

**执行过程：** A=10 → 10-2=8 → 8-2=6 → ... → 2-2=0 → 0-2=-2 → 跳转DONE

**功能：** 循环执行 10/2=5 次减法，相当于 A = 10 - 2×5 = 0（实际会到-2时停止）

**English:**  

### Loop in Assembly

- **LDI** - Load Immediate
- **JMP** - Unconditional Jump (back to TOP)
- Loop: Subtract 2 from A until A becomes negative

---

# 📖 Page 42: Testing | 测试

**中文：**  

| 术语 | 定义 |
|-----|------|
| **测试计划 (Test Plan)** | 规定程序必须运行多少次、用什么数据才能彻底测试的文档 |
| **代码覆盖 (Code Coverage)** | 通过查看代码设计测试用例的方法 |
| **数据覆盖 (Data Coverage)** | 通过查看允许的数据值设计测试用例的方法 |

**English:**  

### Testing Concepts

- **Test plan** - Specifies how many times and with what data the program must be run
- **Code coverage** - Design test cases by looking at the code
- **Data coverage** - Design test cases by looking at allowable data values

---

# 📖 Page 43-45: Errors ("Bugs") | 错误（Bug）

**中文：**  

### 两类主要错误

| 类型 | 说明 | 示例 |
|-----|------|------|
| **语法错误 (Syntax Errors)** | 阻止编程语言理解要做什么 | 关键词拼写错误：True/False 不是 Ture/Flase |
| **逻辑错误 (Logical Errors)** | 导致程序运行不正确 | 用错值、步骤顺序错误 |

### 逻辑错误示例

- `currentYear = 2000`（用了错误的值）
- "到学校。坐公交。开果酱瓶。"（步骤顺序错了）

**English:**  

### Two Main Classifications

- **Syntax errors** - Prevent the language from understanding (like grammar/spelling)
- **Logical errors** - Program runs but does wrong thing (wrong value, wrong order)

---

# 📖 Page 46-47: Test Plan Implementation | 测试计划实施

**中文：**  

### 测试计划实施 (Test Plan Implementation)

使用测试计划中列出的**测试用例**来验证程序输出是否符合**预期结果**。

**English:**  

### Test Plan Implementation

Using the test cases outlined in the test plan to verify that the program outputs the **predicted results**.

---

# 📖 Page 49-50: Admin Notes | 课程通知 (Post 独有)

**中文：**  

- **HW3 – Ch 5** 已在 Brightspace 上发布
- **Quiz – Ch 5** 已在 Brightspace 上发布

**English:**  

- HW3 – Ch 5 available on Brightspace
- Quiz – Ch 5 is available on Brightspace

---

# 📖 Page 51-52: Group Activity - Sort Three Integers | 小组活动：三数排序 (Post 独有)

**中文：**  

### 任务：写伪代码算法，从用户获取三个整数并按数字顺序打印

```
Write "Enter three integer values"
Read first, second, third
IF (first < second)
  IF (second < third)
    Write first, second, third
  ELSE
    IF (first < third)
      Write first, third, second
    ELSE
      Write third, first, second
ELSE
  IF (first < third)
    Write second, first, third
  ELSE
    IF (second < third)
      Write second, third, first
    ELSE
      Write third, second, first
```

**English:** Nested IF-ELSE to handle all 6 orderings of three numbers

---

# 📖 Page 53: Class Activity | 课堂活动 (Post 独有)

**中文：**  

### 任务1：伪代码

写一个伪代码算法：读入三个值，输出 (第一个 + 第三个) - 第二个 的结果

### 任务2：汇编实现

将上述算法实现为汇编语言程序

**English:**  

1. Pseudocode: Read three values, output (first + third) - second
2. Implement as assembly-language program

---

# 📖 Page 54: Syntax Error Examples | 语法错误示例 (Post 独有)

**中文：**  

### 找出每行代码的语法错误

1. `prnit("Hi")` → **print** 拼写错误
2. `print("What"s up?")` → 引号使用错误（字符串内引号冲突）
3. `print("Aloha!)` → 缺少闭合引号
4. `print("Good Monring")` → **Morning** 拼写错误

**English:**  

1. prnit → print
2. Nested quotes issue
3. Missing closing quote
4. Monring → Morning

---

# 📖 Page 55-56: Exercises | 练习 (Post 独有)

**中文：**  

### 练习1：Hello NAME

写一个算法：询问用户姓名，然后回应 "Hello NAME"
- 可用流程图或伪代码

### 练习2：Letter Grade

写一个算法：询问用户成绩，告诉他们字母等级

| 等级 | 分数范围 |
|-----|---------|
| A | 100 - 90 |
| B | <90 - 80 |
| C | <80 - 70 |
| D | <70 - 60 |
| F | <60 - 0 |

**English:**  

- Exercise 1: Get name, output "Hello NAME"
- Exercise 2: Get grade, output letter grade (A/B/C/D/F)

---

# 📖 Page 57: Practice Problems | 练习题 (Post 独有)

**中文：**  

1. 完成前两页的两个练习
2. 修改"数到20"算法，使其从0数到100，每次增加5
3. 设计一个算法，求三个考试成绩的平均值（伪代码或流程图）
4. **进阶：** 设计算法：向用户要两个数，问他们想乘、加还是减；执行用户选择的操作并显示结果

**English:**  

1. Complete the 2 exercises on previous slides
2. Modify "count to 20" → count 0 to 100, increments of 5
3. Design algorithm: average of three exam scores
4. **Advanced:** Two numbers + operation choice (multiply/add/subtract) → show result

---

# 📋 Terminology Table | 术语表

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Algorithm | 算法 | 解决问题的有序、无歧义、完整步骤 |
| Pseudocode | 伪代码 | 用英语短语和缩进表达算法的形式 |
| Flowchart | 流程图 | 用符号表示算法流程的图形 |
| Machine Language | 机器语言 | 二进制形式的机器指令 |
| Assembly Language | 汇编语言 | 使用助记符的低级语言 |
| Assembler | 汇编器 | 将汇编语言转为机器语言的程序 |
| Compiler | 编译器 | 将高级语言转为机器语言的程序 |
| Control Structure | 控制结构 | 顺序、决策、循环 |
| Sequence | 顺序 | 顺序执行，无分支 |
| Decision Making / Selection | 决策/选择 | 根据条件选择执行路径 |
| Looping / Repetition | 循环/重复 | 重复执行语句 |
| Count-Controlled Loop | 计数控制循环 | 按预定次数重复的循环 |
| Test Plan | 测试计划 | 规定测试次数和数据的文档 |
| Code Coverage | 代码覆盖 | 基于代码设计测试用例 |
| Data Coverage | 数据覆盖 | 基于数据值设计测试用例 |
| Syntax Error | 语法错误 | 违反语言规则的错误 |
| Logical Error | 逻辑错误 | 程序逻辑错误，运行结果不对 |

---

# 📝 Study Tips | 学习建议

**中文：**  

1. **掌握伪代码结构** - 变量、赋值、输入、输出、IF-ELSE、WHILE 的写法
2. **理解三种控制结构** - 顺序、决策、循环是所有语言的基础
3. **练习流程图与伪代码互换** - 能互相转换表示同一算法
4. **掌握计数循环三要素** - 初始化、测试、递增/递减
5. **熟悉 Super Simple CPU** - LOD, SUB, STO, JNG, JZR, JMP, LDI, DAT, STP
6. **区分两种错误** - 语法错误 vs 逻辑错误
7. **理解测试方法** - 代码覆盖 vs 数据覆盖
8. **多写多练** - 完成课件中的 Group Activity、Exercises、Practice Problems

**English:**  

1. **Master pseudocode constructs** - Variables, assignment, input, output, IF-ELSE, WHILE
2. **Understand three control structures** - Sequence, Decision, Looping
3. **Practice flowchart ↔ pseudocode conversion**
4. **Count-controlled loop: Initialization, Testing, Incrementation**
5. **Super Simple CPU instructions** - LOD, SUB, STO, JNG, JZR, JMP, LDI, DAT, STP
6. **Distinguish Syntax vs Logical errors**
7. **Understand Code coverage vs Data coverage**
8. **Practice** - Complete Group Activity, Exercises, Practice Problems

---

**准备就绪！开始学习 Chapter 6 吧！**  
**Ready! Let's start learning Chapter 6!**
