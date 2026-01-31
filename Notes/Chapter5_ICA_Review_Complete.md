# CPSC 1050 - Chapter 5 课上活动 (ICA) 完整回顾
# Chapter 5 - Computing Components In-Class Activity — Full Review

---

## 第 1–6 题（来自 ICA 答案 PDF 第 1 页）

---

### 1. Von Neumann 机器的四个主要组件及各自的主要功能

| 组件 | 主要功能 |
|------|----------|
| **Memory（内存）** | 存储数据和指令 |
| **Control Unit（控制单元）** | 指挥数据与指令在系统中的流动 |
| **Arithmetic/Logic Unit - ALU（算术/逻辑单元）** | 执行数学运算和逻辑运算 |
| **Input/Output Units（输入/输出单元）** | 负责计算机与外部环境之间的通信 |

---

### 2. Fetch–Decode–Execute 周期的步骤

- **Fetch（取指）**：用程序计数器 (PC) 中的地址，从内存取出下一条指令  
- **Decode（译码）**：解释该指令，确定要执行的操作  
- **Execute（执行）**：用 ALU、寄存器等部件完成该操作  

顺序：**取指 → 译码 → 执行**，然后循环。

---

### 3. 主存 vs 辅存（速度、成本、易失性 + 各举一例）

| 类型 | 速度 | 成本 | 易失性 | 例子 |
|------|------|------|--------|------|
| **Primary（主存）** | 更快 | 更贵 | 易失（断电丢失） | RAM、Cache |
| **Secondary（辅存）** | 更慢 | 更便宜 | 非易失 | 硬盘、U盘 |

---

### 4. 两种辅助存储设备及各自一个优点

- **Hard Disk（硬盘）**：容量大  
- **Flash Drive（U盘）**：便携、便于携带和转移  

---

### 5. 为什么说 RAM 是易失性内存？它的主要优点是什么？

- **易失性原因**：断电后其中数据会丢失  
- **主要优点**：访问速度快，便于 CPU 快速读写数据  

---

### 6. CPU 在计算机中的作用，以及为什么常被称为“大脑”？

- **作用**：控制指令执行、进行运算、管理数据在系统中的流动（协调各部件）。  
- **“大脑”的比喻**：由 CPU 统一指挥取指、译码、执行，并协调内存、ALU、I/O 等部件。  

---

## 第 7–13 题（来自 ICA 答案 PDF 第 2 页）

---

### 7. Arithmetic/Logic Unit (ALU) 执行哪些类型的操作？

**题目：** What types of operations does the Arithmetic/Logic Unit (ALU) perform in a computer?

**答：**  
The ALU performs **arithmetic operations** (e.g., addition, subtraction) and **logical operations** (e.g., AND, OR, NOT).

**中文：** ALU 执行**算术运算**（如加法、减法）和**逻辑运算**（如 AND、OR、NOT）。

---

### 8. 控制单元如何与输入/输出单元交互？

**题目：** How does the Control Unit interact with Input and Output Units in a computer system?

**答：**  
The Control Unit directs data flow between the CPU and Input/Output Units, ensuring that inputs are processed correctly and outputs are delivered to external devices.

**中文：** 控制单元指挥 CPU 与输入/输出单元之间的数据流，确保输入被正确处理，输出被传送到外部设备。

---

### 9. 内存类型匹配题

**题目：** Match each type of memory with its key characteristic:

| 内存类型 | 特征 |
|---------|------|
| A. Cache Memory | 1. Non-volatile and used for long-term data storage |
| B. RAM (Main Memory) | 2. Volatile memory that stores active data and programs |
| C. Secondary Storage | 3. Small, high-speed memory for frequently used data |

**答：**  
**A → 3** (Cache Memory matches with Small, high-speed memory for frequently used data)  
**B → 2** (RAM matches with Volatile memory that stores active data and programs)  
**C → 1** (Secondary Storage matches with Non-volatile and used for long-term data storage)

---

### 10. 冯·诺依曼架构组件表格填空

**题目：** Complete the table by filling in the missing information about the components of the Von Neumann Architecture:

| Component | Description |
|:----------|:-----------|
| Memory | Stores data and \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ |
| Control Unit | Coordinates the flow of \_\_\_\_\_\_\_\_\_\_\_\_\_ between components |
| Arithmetic/Logic Unit | Performs \_\_\_\_\_\_\_\_\_\_\_\_\_ and logical operations |
| Input/Output Units | Allows communication between the computer and \_\_\_\_\_\_\_\_\_\_\_\_\_ |

**答：**

| Component | Description |
|:----------|:-----------|
| **Memory** | Stores data and **instructions** |
| **Control Unit** | Coordinates the flow of **data and instructions** between components |
| **Arithmetic/Logic Unit** | Performs **arithmetic** and logical operations |
| **Input/Output Units** | Allows communication between the computer and **external devices** |

---

### 11. CPU 性能因素匹配题

**题目：** Match each CPU performance factor with its description:

| Factor | Description |
|:------|:------------|
| A. Clock Speed | 1. Determines how much data the CPU can process at once |
| B. Word Size | 2. The number of pathways for transferring data within the CPU |
| C. Data Bus Width | 3. The number of cycles per second, measured in GHz |

**答：**  
**A → 3** (Clock Speed: The number of cycles per second, measured in GHz)  
**B → 1** (Word Size: Determines how much data the CPU can process at once)  
**C → 2** (Data Bus Width: The number of pathways for transferring data within the CPU)

---

### 12. Super Simple CPU 的三个主要寄存器及作用

**题目：** What are the three main registers in a Super Simple CPU, and what is their purpose?

**答：**

a. **Program Counter (PC)** – Holds the address of the next instruction.  
b. **Instruction Register (IR)** – Stores the current instruction being executed.  
c. **Accumulator (A Register)** – Holds data and results of operations.

**中文：**
- **PC (Program Counter) 程序计数器** – 存放下一条指令的地址
- **IR (Instruction Register) 指令寄存器** – 存放当前正在执行的指令
- **A (Accumulator) 累加器** – 存放数据和运算结果

---

### 13. Super Simple CPU 指令解码

**题目：** A program on a Super Simple CPU contains the following instructions:

```
0110000000000001
0100000000000010
0011000000000011
0001000000000100
1010000000000001
```

**a) Decode the instructions step by step.**

**答：**

每条指令为 16 位：前 4 位为**操作码 (opcode)**，后 12 位为**操作数 (operand)**。

| 二进制指令 | Opcode | Operand | 解码结果 |
|:---------|:-------|:--------|:---------|
| `0110000000000001` | `0110` | `000000000001` | **INP** – Takes input from the user and stores it in the accumulator. |
| `0100000000000010` | `0100` | `000000000010` | **LDI 2** – Loads the value 2 into the accumulator. |
| `0011000000000011` | `0011` | `000000000011` | **LOD 3** – Loads the value from memory address 3 into the accumulator. |
| `0001000000000100` | `0001` | `000000000100` | **ADD 4** – Adds the value from memory address 4 to the accumulator. |
| `1010000000000001` | `1010` | `000000000001` | **JZR 1** – Jumps to instruction 1 if the accumulator = 0. |

---

## 速记要点（考前可扫一眼）

- Von Neumann 四件套：**Memory, CU, ALU, I/O**
- 执行周期：**Fetch → Decode → Execute**
- 主存：快、贵、易失（RAM, Cache）；辅存：慢、便宜、非易失（硬盘、U盘）
- RAM：易失、速度快
- CPU = “大脑”：控制执行、运算、数据流
- ALU：算术 + 逻辑运算
- 三个关键寄存器：**PC**（下条指令地址）、**IR**（当前指令）、**A**（累加器）
- 机器语言 / 指令集：CPU 能识别的完整命令集合

---

*第 1–6 题来自 ICA 答案 PDF 第 1 页；第 7–13 题来自 ICA 答案 PDF 第 2 页。所有答案均已与课上 ICA 答案核对一致。*
