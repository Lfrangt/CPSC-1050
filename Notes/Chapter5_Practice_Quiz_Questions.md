# Chapter 5 选择题练习 | Chapter 5 Multiple Choice Practice Questions
## Computing Components | 计算组件

---

## Question 1

**What type of memory is RAM (Random Access Memory)?**

1. Non-volatile memory
2. **Volatile memory** ✓
3. Secondary memory
4. Optical memory
5. Flash memory

**答案：** 2. Volatile memory  
**解释：** RAM是易失性内存，断电后所有数据都会丢失。

---

## Question 2

**True or False? RAM stands for "Random Access Memory" because any memory location can be accessed in very nearly the same amount of time, regardless of its position in the memory.**

1. **True** ✓
2. False

**答案：** 1. True  
**解释：** "随机"访问的含义是任何存储位置都可以在几乎相同的时间内被访问，无论其在内存中的位置如何。

---

## Question 3

**Which of the following is NOT a characteristic of secondary storage?**

1. Non-volatile
2. Permanent storage
3. Slower than primary memory
4. **Faster than RAM** ✓
5. Cheaper than primary memory

**答案：** 4. Faster than RAM  
**解释：** 辅助存储比主存储器（RAM）慢，但更便宜且非易失性。

---

## Question 4

**What operations does the Arithmetic/Logic Unit (ALU) perform?**

1. Only arithmetic operations
2. Only logic operations
3. **Both arithmetic and logic operations** ✓
4. Only data storage operations
5. Only control operations

**答案：** 3. Both arithmetic and logic operations  
**解释：** ALU执行算术运算（如加法和减法）以及逻辑运算（如AND、OR、NOT）。

---

## Question 5

**Which register contains the address of the next instruction to be executed?**

1. Instruction Register (IR)
2. **Program Counter (PC)** ✓
3. Accumulator (A)
4. Data Register
5. Address Register

**答案：** 2. Program Counter (PC)  
**解释：** PC（程序计数器）存放下一条要执行的指令的地址。

---

## Question 6

**True or False? All data must be represented in a register before it can be processed by the CPU.**

1. **True** ✓
2. False

**答案：** 1. True  
**解释：** 所有数据在处理之前必须在寄存器中表示。

---

## Question 7

**What does a 32-bit CPU mean?**

1. The CPU has 32 registers
2. The CPU can process 32 instructions at once
3. **Each register is 32 bits wide** ✓
4. The CPU has 32 cache levels
5. The CPU operates at 32 MHz

**答案：** 3. Each register is 32 bits wide  
**解释：** 32位CPU是指每个寄存器都是32位宽的CPU，因此每个CPU指令可以操作32位数据。

---

## Question 8

**Which component of the CPU controls the operation of each part and coordinates data flow?**

1. Arithmetic/Logic Unit (ALU)
2. **Control Unit (CU)** ✓
3. Program Counter (PC)
4. Instruction Register (IR)
5. Accumulator

**答案：** 2. Control Unit (CU)  
**解释：** 控制单元控制CPU各部分的操作，并协调数据流。

---

## Question 9

**How many operations can be controlled with 4 wires from the Control Unit?**

1. 4 operations
2. 8 operations
3. 12 operations
4. **16 operations** ✓
5. 32 operations

**答案：** 4. 16 operations  
**解释：** 4根电线（每根可以是开/关状态）可以表示2^4 = 16种不同的操作。

---

## Question 10

**What are the three main components of the Von Neumann Architecture?**

1. CPU, RAM, Hard Drive
2. **CPU (with ALU and CU), Memory, I/O devices** ✓
3. ALU, Control Unit, Registers
4. Primary Memory, Secondary Memory, Cache
5. Input, Output, Storage

**答案：** 2. CPU (with ALU and CU), Memory, I/O devices  
**解释：** 冯·诺依曼架构包含：带有ALU和CU的CPU、存储数据和指令的内存、通过总线连接的I/O设备。

---

## Question 11

**True or False? In the Von Neumann Architecture, instructions and data are both stored in the memory unit.**

1. **True** ✓
2. False

**答案：** 1. True  
**解释：** 这是存储程序概念（Stored-Program Concept）的核心：指令和数据都存储在内存单元中。

---

## Question 12

**What is the correct order of steps in the fetch-decode-execute cycle?**

1. Execute, Decode, Fetch, Get Data
2. Fetch, Execute, Decode, Get Data
3. **Fetch, Decode, Get Data, Execute** ✓
4. Decode, Fetch, Get Data, Execute
5. Get Data, Fetch, Decode, Execute

**答案：** 3. Fetch, Decode, Get Data, Execute  
**解释：** 取指-执行周期的正确顺序是：1) 取指 2) 译码 3) 获取数据（如果需要）4) 执行。

---

## Question 13

**What happens to the Program Counter (PC) after fetching an instruction?**

1. It is reset to zero
2. It is decremented
3. **It is incremented** ✓
4. It remains unchanged
5. It is loaded with the instruction

**答案：** 3. It is incremented  
**解释：** 在取指后，控制单元会递增PC，使其指向下一条指令。

---

## Question 14

**In Super Simple CPU, how many bits does each instruction contain?**

1. 8 bits
2. 12 bits
3. **16 bits** ✓
4. 32 bits
5. 64 bits

**答案：** 3. 16 bits  
**解释：** Super Simple CPU的每条指令是16位：4位操作码 + 12位操作数。

---

## Question 15

**What is the opcode for the STP (Stop) instruction in Super Simple CPU?**

1. 0000
2. 0001
3. 1110
4. **1111** ✓
5. 1010

**答案：** 4. 1111  
**解释：** STP指令的操作码是1111（停止计算机）。

---

## Question 16

**Which Super Simple CPU instruction loads a constant value directly into the accumulator without accessing memory?**

1. LOD
2. **LDI** ✓
3. STO
4. ADD
5. SUB

**答案：** 2. LDI  
**解释：** LDI (Load Immediate) 立即加载常数到累加器，不像LOD那样去内存。

---

## Question 17

**Decode the following Super Simple CPU instruction: `0100 000000000101`**

1. LOD 5
2. **LDI 5** ✓
3. ADD 5
4. STO 5
5. SUB 5

**答案：** 2. LDI 5  
**解释：** 操作码0100是LDI，操作数000000000101是5（二进制），所以是LDI 5。

---

## Question 18

**What does the instruction `1010 000000000011` do in Super Simple CPU?**

1. Jump unconditionally to address 3
2. Jump to address 3 if accumulator is negative
3. **Jump to address 3 if accumulator is zero** ✓
4. Load value 3 into accumulator
5. Store accumulator to address 3

**答案：** 3. Jump to address 3 if accumulator is zero  
**解释：** 操作码1010是JZR (Jump if Zero)，如果累加器=0则跳转到地址3。

---

## Question 19

**True or False? Cache memory uses SRAM (Static RAM) which is faster than regular RAM.**

1. **True** ✓
2. False

**答案：** 1. True  
**解释：** 缓存使用SRAM（静态RAM），这是一种非常高速的RAM，比普通RAM更快。

---

## Question 20

**Which cache level is located on the CPU and is used first by the CPU?**

1. L2 cache
2. L3 cache
3. **L1 cache** ✓
4. L4 cache
5. Main cache

**答案：** 3. L1 cache  
**解释：** L1缓存位于CPU上，是CPU首先使用的缓存（因此被称为L1）。

---

## Question 21

**What connects the CPU and RAM, allowing the CPU to address memory locations?**

1. Data Bus
2. Control Bus
3. **Address Bus** ✓
4. Memory Bus
5. System Bus

**答案：** 3. Address Bus  
**解释：** 地址总线通过内存控制器芯片（MCC）连接CPU和RAM，使CPU能够寻址RAM。

---

## Question 22

**Which of the following is NOT a factor that determines CPU performance?**

1. Data bus width
2. Word size
3. Clock speed
4. **Number of hard drives** ✓
5. Operations per cycle

**答案：** 4. Number of hard drives  
**解释：** CPU性能由数据总线宽度、字长和时钟速度（每周期操作数）决定，与硬盘数量无关。

---

## Question 23

**What is clock speed measured in?**

1. Bytes per second
2. Bits per second
3. **Megahertz (MHz) or Gigahertz (GHz)** ✓
4. Megabytes (MB)
5. Operations per second

**答案：** 3. Megahertz (MHz) or Gigahertz (GHz)  
**解释：** 时钟速度以每秒的周期数测量，单位是MHz或GHz。

---

## Question 24

**True or False? Word size determines the maximum number of bits of data that the CPU can process at a time.**

1. **True** ✓
2. False

**答案：** 1. True  
**解释：** 字长决定CPU一次可以处理的最大数据位数（如8位、16位、32位、64位）。

---

## Question 25

**In Super Simple CPU, how many memory locations are available?**

1. 8 locations (0-7)
2. **16 locations (0-15 or 0-FF)** ✓
3. 32 locations (0-31)
4. 64 locations (0-63)
5. 256 locations (0-255)

**答案：** 2. 16 locations (0-15 or 0-FF)  
**解释：** Super Simple CPU有16个内存位置，地址从0到15（或0到FF）。

---

## Question 26

**Which Super Simple CPU instruction outputs the value in the accumulator?**

1. INP
2. **OUT** ✓
3. STO
4. LOD
5. ADD

**答案：** 2. OUT  
**解释：** OUT指令将累加器中的值复制到输出区域。

---

## Question 27

**What is the purpose of the Memory Controller Chip (MCC)?**

1. To store data permanently
2. To increase CPU clock speed
3. **To facilitate data flow from RAM to CPU** ✓
4. To decode instructions
5. To execute arithmetic operations

**答案：** 3. To facilitate data flow from RAM to CPU  
**解释：** MCC（内存控制器芯片）促进从RAM到CPU的数据流，帮助CPU与内存通信。

---

## Question 28

**True or False? Secondary storage devices like hard disks and flash drives are non-volatile.**

1. **True** ✓
2. False

**答案：** 1. True  
**解释：** 辅助存储设备（如硬盘、闪存驱动器）是非易失性的，提供永久存储。

---

## Question 29

**Which register stores a copy of the instruction currently being executed?**

1. Program Counter (PC)
2. **Instruction Register (IR)** ✓
3. Accumulator (A)
4. Data Register
5. Address Register

**答案：** 2. Instruction Register (IR)  
**解释：** IR（指令寄存器）存储当前正在执行的指令的副本。

---

## Question 30

**What is the main difference between LOD and LDI instructions in Super Simple CPU?**

1. LOD is faster than LDI
2. LOD uses more bits than LDI
3. **LOD loads from memory address, LDI loads immediate constant** ✓
4. LOD can only load zero
5. LDI cannot be used with addresses

**答案：** 3. LOD loads from memory address, LDI loads immediate constant  
**解释：** LOD从内存地址加载值，而LDI直接将操作数中的常数加载到累加器，不需要访问内存。

---

## 📊 答案统计 | Answer Key Summary

| 题目 | 正确答案 | 知识点 |
|------|---------|--------|
| 1 | 2 | RAM易失性 |
| 2 | 1 | RAM随机访问 |
| 3 | 4 | 辅助存储特点 |
| 4 | 3 | ALU功能 |
| 5 | 2 | PC寄存器 |
| 6 | 1 | 寄存器作用 |
| 7 | 3 | CPU位数 |
| 8 | 2 | 控制单元 |
| 9 | 4 | 控制单元操作数 |
| 10 | 2 | 冯·诺依曼架构 |
| 11 | 1 | 存储程序概念 |
| 12 | 3 | 取指-执行周期 |
| 13 | 3 | PC递增 |
| 14 | 3 | Super Simple CPU指令格式 |
| 15 | 4 | STP指令码 |
| 16 | 2 | LDI指令 |
| 17 | 2 | 指令解码 |
| 18 | 3 | JZR指令 |
| 19 | 1 | 缓存SRAM |
| 20 | 3 | L1缓存 |
| 21 | 3 | 地址总线 |
| 22 | 4 | CPU性能因素 |
| 23 | 3 | 时钟速度单位 |
| 24 | 1 | 字长定义 |
| 25 | 2 | Super Simple CPU内存 |
| 26 | 2 | OUT指令 |
| 27 | 3 | MCC作用 |
| 28 | 1 | 辅助存储非易失性 |
| 29 | 2 | IR寄存器 |
| 30 | 3 | LOD vs LDI |

---

## 💡 练习建议 | Practice Tips

1. **先不看答案，自己做一遍**
2. **做错的题目重点复习相关知识点**
3. **特别关注Super Simple CPU指令解码题（17、18题）**
4. **熟记取指-执行周期的顺序（12题）**
5. **区分LOD和LDI的区别（30题）**

---

**Good luck on your quiz! 祝你quiz顺利！🍀**
