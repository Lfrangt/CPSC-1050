# Chapter 5: Computing Components (Complete)
# 第五章：计算组件（完整版）

---

# 📖 Page 1: Chapter Title | 章节标题

**Chapter 5: Computing Components**

---

# 📖 Page 2: Chapter Goals | 本章目标

**中文：** 学完这章，你将能够：

**English:** After completing this chapter, you will be able to:

1. **列出冯·诺依曼机器的组件及其功能**  
   List the components and their function in a von Neumann machine

2. **描述冯·诺依曼机器的取指-译码-执行周期**  
   Describe the fetch-decode-execute cycle of the von Neumann machine

3. **描述计算机内存是如何组织和访问的**  
   Describe how computer memory is organized and accessed

4. **命名并描述不同的辅助存储设备**  
   Name and describe different auxiliary storage devices

---

# 📖 Page 3: Memory | 内存

**中文：**  
**内存 (Memory)** - 一组存储单元，每个单元都有唯一的物理地址

**关键概念：**
- 大多数计算机是**字节可寻址的 (byte-addressable)**
- 地址为 `11111110` 的存储单元包含 `10101010`

**English:**  
**Memory** - A collection of cells, each with a unique physical address

**Key Concepts:**
- Most computers are **byte-addressable**
- Cell at address `11111110` contains `10101010`

---

# 📖 Page 4: Memory Types | 内存类型

**中文：**  
内存分为两大类：

- **主存储器 (Primary Memory)**
- **辅助存储器 (Secondary Memory)**

**English:**  
Memory is divided into two main types:

- **Primary Memory**
- **Secondary Memory**

---

# 📖 Page 5: Memory Details | 内存详解

**中文：**  

**现代计算机使用多种内存类型的组合，每种都有其自己的性能和成本特征**

### 主存储器 (Main Memory / Primary Memory)
- **速度快且昂贵**
- 数据以**电路中的电信号**形式存储
- 用于存储**活动数据 (active data)**
- **例子：** 随机存取存储器 (RAM)、缓存 (cache)

### 辅助存储器 (Secondary Memory)
- **速度较慢但更便宜**
- 使用不同的技术（硬盘上的磁信号、CD上的反射点）
- **例子：** 硬盘 (hard disk)、闪存驱动器 (flash drive)、光盘 (compact disk, CD)

**English:**  

**Modern computers use a combination of memory types, each with its own performance and cost characteristics**

### Main Memory (or Primary Memory)
- **Fast and expensive**
- Data is stored as **electric signals in circuitry**
- Used to store **active data**
- **Examples:** Random Access Memory (RAM), cache

### Secondary Memory
- **Slower but cheaper**
- Use different technologies (magnetic signals on hard disk, reflective spots on CD)
- **Examples:** hard disk, flash drive, compact disk (CD)

---

# 📖 Page 6: RAM – Random Access Memory | RAM - 随机存取存储器

**中文：**  

### RAM - 随机存取存储器

- 被认为是**"主存储器" (Main Memory)**
- **"随机" (random)** 的含义：任何存储位置都可以在几乎相同的时间内被访问，无论其在内存中的位置如何
- **易失性内存 (Volatile Memory)**
  - 断电 → 所有数据丢失

**English:**  

### RAM – Random Access Memory

- Considered as **"Main Memory"**
- The term **"random"** means any memory location can be accessed in very nearly the same amount of time for any storage location, regardless of its position in the memory
- **Volatile Memory**
  - Power Lost → All Data Lost

---

# 📖 Page 7: Program Execution | 程序执行

**中文：**  

### 程序执行 (Program Execution)

- **程序代码在执行之前从硬盘复制到RAM中**

**English:**  

### Program Execution

- **Program code is copied from your hard drive into RAM before it is executed**

---

# 📖 Page 8: Secondary Storage | 辅助存储

**中文：**  

### 辅助存储 (Secondary Storage)

- **存储信息**
- **非易失性 (Non-volatile)**，永久存储
- **特征 (Characteristics):**
  - **介质 (Media)**
  - **容量 (Capacity)**
  - **访问时间 (Access time)**

**English:**  

### Secondary Storage

- **Stores the information**
- **Non-volatile, permanent storage**
- **Characteristics:**
  - **Media**
  - **Capacity**
  - **Access time**

---

# 📖 Page 9: Magnetic Tape | 磁带

**中文：**  

### 磁带 (Magnetic Tape)

- 第一个真正的大规模辅助存储设备是**磁带驱动器 (magnetic tape drive)**

**问题：** 磁带驱动器有一个主要问题，你能描述它吗？

**English:**  

### Magnetic Tape

- The first truly mass auxiliary storage device was the **magnetic tape drive**

**Question:** Tape drives have a major problem; can you describe it?

---

# 📖 Page 10: Magnetic Disks | 磁盘

**中文：**  

### 磁盘 (Magnetic Disks)

**English:**  

### Magnetic Disks

---

# 📖 Page 11: Magnetic Disks Details | 磁盘详解

**中文：**  

### 磁盘相关术语

- **寻道时间 (Seek time)** - 读写头移动到正确磁道所需的时间
- **延迟 (Latency)** - 扇区就位所需的时间
- **访问时间 (Access time)** - 开始读取一个数据块所需的时间；寻道时间和延迟的总和
- **传输速率 (Transfer rate)** - 数据从磁盘移动到内存的速率

**English:**  

### Magnetic Disk Terms

- **Seek time** - Time for read/write head to be over the right track
- **Latency** - Time for the sector to be in position
- **Access time** - The time it takes for a block to start being read; the sum of seek time and latency
- **Transfer rate** - The rate at which data moves from the disk to memory

---

# 📖 Page 12: Optical Disks | 光盘

**中文：**  

### 光盘 (Optical Disks)

#### CD (Compact Disk)
- 使用激光读取存储在塑料涂层磁盘上的光学信息
- 数据均匀分布在螺旋轨道周围
- **CD-ROM** - 只读存储器 (read-only memory)
- **CD-DA** - 数字音频 (digital audio)
- **CD-WORM** - 一次写入，多次读取 (write once, read many)
- **RW 或 RAM** - 可读可写 (both read from and written to)

#### DVD (Digital Versatile Disk)
- 用于存储音频和视频

#### Blu-ray
- 更高容量的DVD，允许更高分辨率的视频等

**English:**  

### Optical Disks

#### CD - A compact disk that uses a laser to read information stored optically on a plastic-coated disk; data is evenly distributed around spiral track
- **CD-ROM** - read-only memory
- **CD-DA** - digital audio
- **CD-WORM** - write once, read many
- **RW or RAM** - both read from and written to

#### DVD - Digital Versatile Disk
- Used for storing audio and video

#### Blu-ray
- Higher capacity DVD allowing higher resolution video, etc.

---

# 📖 Page 13: Flash Memory | 闪存

**中文：**  

### 闪存 (Flash Memory)

- **非易失性 (Nonvolatile)**
- **可以擦除和重写 (Can be erased and rewritten)**
- 支持**USB大容量存储标准 (USB mass storage standard)**

**闪存驱动器 (Flash Drives)**

**English:**  

### Flash Memory

- **Nonvolatile**
- **Can be erased and rewritten**
- Supports **USB mass storage standard**

**Flash Drives**

---

# 📖 Page 14: Touch Screens | 触摸屏

**中文：**  

### 触摸屏 (Touch Screen)

- 可以响应用户的计算机显示器
- 用户可以用**触控笔 (stylus)** 或**手指 (finger)** 触摸屏幕

**English:**  

### Touch Screen

- A computer monitor that can respond to the user, touching the screen with a **stylus** or **finger**

---

# 📖 Page 15: CPU – Central Processing Unit | CPU - 中央处理单元

**中文：**  

### CPU - 中央处理单元

- CPU是计算机的**"大脑"**，负责控制其内部工作
- 由**电路 (circuitry)** 制成 - 电子元件连接在一起以控制电信号的流动
- 电路嵌入在一个小的**硅芯片 (silicon chip)** 中，1-2平方英寸
- 尽管体积小，CPU是计算机最复杂的部分
- (CPU电路可以有**数亿个独立组件**)
- **商业例子：** Intel Core 2 Duo, Intel i5, AMD Sempron, AMD Athlon

**English:**  

### CPU – Central Processing Unit

- The CPU is the **"brains"** of the computer, responsible for controlling its inner workings
- Made of **circuitry** – electronic components wired together to control the flow of electrical signals
- The circuitry is embedded in a small **silicon chip**, 1-2 inches square
- Despite its small size, the CPU is the most complex part of a computer
- (CPU circuitry can have **100's of millions of individual components**)
- **Commercial examples:** Intel Core 2 Duo, Intel i5, AMD Sempron, AMD Athlon

---

# 📖 Page 16: Microarchitecture | 微架构

**中文：**  

### 微架构 (Microarchitecture)

- 两家公司都使用**代码名称 (code names)** 来跟踪模型内的变化（微架构）
- 标记为相同型号的CPU可能内部CPU与早期版本的该型号**非常不同**
- **相同品牌，不同能力 (Same branding, different capabilities)**

**English:**  

### Microarchitecture

- Both companies use **code names** to track variations (microarchitectures) within models
- CPUs labeled as the same model may have CPUs inside that are **very different** from earlier versions of that model
- **Same branding, different capabilities**

---

# 📖 Page 17: To Understand Von Neumann Architecture | 理解冯·诺依曼架构

**中文：**  

### 理解冯·诺依曼架构

- **只考虑单核处理器 (Consider only single core processor)**
- 将CPU作为一个整体来理解

### 冯·诺依曼架构特点

冯·诺依曼架构具有以下特点：
- 一个带有**ALU和CU**的CPU
- **内存**存储数据和指令
- **I/O设备**通过**总线 (bus)** 连接

**English:**  

### To Understand Von Neumann Architecture

- **Consider only single core processor (CPU as a whole)**

### The von Neumann Architecture Features

The von Neumann architecture features:
- A CPU with **ALU and CU**
- **Memory** storing both data and instructions
- **I/O devices** connected via a **bus**

---

# 📖 Page 18: Arithmetic/Logic Unit | 算术逻辑单元

**中文：**  

### 算术逻辑单元 (ALU)

- 执行基本算术运算，如**加法 (addition)** 和**减法 (subtraction)**
- 执行逻辑运算，如 **AND、OR、NOT**
- 大多数现代ALU都有少量称为**寄存器 (registers)** 的特殊存储单元
- 寄存器可以比主内存**更快地访问**

**English:**  

### Arithmetic/Logic Unit

- Performs basic arithmetic operations such as **addition** and **subtraction**
- Performs logical operations such as **AND, OR, and NOT**
- Most modern ALUs have a small amount of special storage units called **registers** that can be accessed **faster than main memory**

---

# 📖 Page 19: Registers | 寄存器

**中文：**  

### 寄存器 (Registers)

**快速独立的存储位置，在CPU中临时保存数据**

#### 主要寄存器类型：

1. **PC (Program Counter) - 程序计数器**
   - **就像一个指针**，用来跟踪CPU在程序中的位置
   - 主要功能是存储**下一条**要获取的指令的内存地址
   - 每次获取指令时，PC会自动更新（通常递增1）指向下一行代码
   - 是取指-执行周期中的关键组件

2. **Instruction Register - 指令寄存器**
   - 存储当前正在执行的指令

3. **Data/Accumulator Registers - 数据/累加器寄存器**
   - 在处理之前保存数据

**English:**  

### Registers

**Fast stand-alone storage locations that hold data temporarily in CPU**

#### Main Register Types:

1. **PC (Program Counter)**
   - **Like a pointer** that keeps track of where the CPU is in the program
   - Main function is to store the memory address of the **next** instruction to be fetched
   - Every time an instruction is fetched, the PC automatically updates (usually increments by 1) to point to the next line of code
   - A key component in the fetch-execute cycle

2. **Instruction Register**
   - Store the instruction currently being executed

3. **Data/Accumulator Registers**
   - Hold data before it can be processed

---

# 📖 Page 20: Registers and Machine Language | 寄存器和机器语言

**中文：**  

### 寄存器和机器语言

- **CPU代码本 (CPU codebook)** 识别CPU指令（用机器语言），这些指令标识如何处理寄存器中的数据
- 这些命令称为**机器语言 (machine language)**
- **一个命令是一行代码**
- 处理器的**完整命令集**是其**指令集 (instruction set)**

**English:**  

### Registers

- **CPU codebook** identifies CPU instructions (in machine language) that identify what to do with the data in the registers
- The commands are called **machine language**
- **One command is a line of code**
- The complete set of commands for a processor is its **instruction set**

---

# 📖 Page 21: Register Details | 寄存器详解

**中文：**  

### 寄存器详解

- 一个特殊的、高速的存储区域，位于CPU内部
- **所有数据在处理之前必须在寄存器中表示**
- **例子：** 如果要乘以两个数字，两个数字都必须在寄存器中，结果也放在寄存器中

### CPU的功率和速度由以下因素决定：

1. **CPU拥有的寄存器数量**
2. **每个寄存器的大小（位数）**

**例子：** 
- **32位CPU** 是指每个寄存器都是32位宽的CPU
- 因此，每个CPU指令可以操作**32位数据**

**English:**  

### Register

- A special, high-speed storage area within the CPU
- **All data must be represented in a register before it can be processed**
- **For example:** If two numbers are to be multiplied, both numbers must be in registers, and the result is also placed in a register

### The power and speed of a CPU determined by:

1. **The number of registers that a CPU has**
2. **The size of each (number of bits)**

**Example:**
- A **32-bit CPU** is one in which each register is 32 bits wide
- Therefore, each CPU instruction can manipulate **32 bits of data**

---

# 📖 Page 22: Control Unit | 控制单元

**中文：**  

### 控制单元 (Control Unit)

- 就像人脑中控制身体各部分操作的部分
- 控制通过**电线 (wires)** 实现，从控制单元到ALU
- 电线可以是**开/关 (on/off)** 状态
- **4根电线 → 16种操作**

**English:**  

### Control Unit

- Like the part of the human brain that control the operation of each part of the body
- Controlling is achieved through **wires** (form Control unit to ALU) that can be **on/off**
- **4 wires → 16 operations**

---

# 📖 Page 23: Input/Output Units | 输入/输出单元

**中文：**  

### 输入单元 (Input Unit)

- 外部世界的数据和程序通过它进入计算机系统的设备
- **你能说出三个吗？**

### 输出单元 (Output Unit)

- 存储在计算机内存中的结果通过它提供给计算机系统外部的设备
- **你能说出两个吗？**

**English:**  

### Input Unit

- A device through which data and programs from the outside world enter the computer system
- **Can you name three?**

### Output Unit

- A device through which results stored in the computer memory are made available outside the computer system
- **Can you name two?**

---

# 📖 Page 24: Cache | 缓存

**中文：**  

### 缓存 (Cache)

- 缓存通过使用内置的、非常高速的RAM（称为**静态RAM (SRAM)**）来减少等待状态
- **SRAM** 预加载尽可能多的指令
- CPU上的缓存被称为**L1缓存**，因为它是CPU首先使用的
- 主板上的缓存被称为**L2缓存**，是CPU其次使用的
- 后来添加到CPU封装中
- 大多数较新的CPU包括**三个缓存**（L1, L2, L3）

**English:**  

### Cache

- A cache reduces wait states by using built-in, very high-speed RAM called **static RAM (SRAM)**
- **SRAM** preloads as many instructions as possible
- The cache on the CPU was called the **L1 cache** because it was used first by the CPU
- The cache on the motherboard was called the **L2 cache**, and used second by the CPU
- Later added to CPU package
- Most newer CPUs include **three caches**

---

# 📖 Page 25: Memory Hierarchy | 内存层次结构

**中文：**  

### 内存层次结构

**缓存内存 (Cache memory)** 是一种小容量、高速的易失性计算机内存，它：
- 为处理器提供高速数据访问
- 存储**经常使用的**计算机程序、应用程序和数据

**English:**  

### Memory Hierarchy

**Cache memory** is a small-sized, high-speed type of volatile computer memory that provides:
- High-speed data access to a processor
- Stores **frequently used** computer programs, applications, and data

---

# 📖 Page 26: Common Desktop Hardware | 常见桌面硬件

**中文：**  

### 常见桌面硬件

**系统单元 (System unit)**
- 包含CPU、RAM（主内存）和其他支持组件

**屏幕 (Screen)**
- 输出设备 (output device)

**扬声器 (Speakers)**
- 输出设备 (output device)

**键盘 (Keyboard)**
- 输入设备 (input device)

**鼠标 (Mouse)**
- 输入设备 (input device)

**CD-ROM驱动器 (CD-ROM drive)**
- 辅助内存 (secondary memory)

**硬盘驱动器 (Hard-disk drive)**
- 辅助内存 (secondary memory)

**English:**  

### Common Desktop Hardware

**System unit**
- Contains CPU, RAM (main memory), and other supporting components

**Screen**
- (output device)

**Speakers**
- (output device)

**Keyboard**
- (input device)

**Mouse**
- (input device)

**CD-ROM drive**
- (secondary memory)

**Hard-disk drive**
- (secondary memory)

---

# 📖 Page 27: Bus | 总线

**中文：**  

### 总线 (Bus)

**一般定义：** 在计算机内部组件之间或计算机之间传输数据的通信系统；包括**介质 (medium)**（电线、光纤等）和**协议 (protocols)**（共享介质的规则）

**"这个"总线：** 连接CPU、主内存、I/O设备，可能还有其他组件（例如硬盘驱动器）

**信息流 (Flow of Information)**

**English:**  

### Bus

**In general:** A communication system that transfers data between components inside a computer or between computers; the **medium** (wires, optical fiber, etc.) and the **protocols** (rules for sharing the medium nicely)

**"The" bus:** Connects the CPU, main memory, I/O devices, and possibly other components (e.g. hard disk drive)

**Flow of Information**

---

# 📖 Page 28: Address Bus | 地址总线

**中文：**  

### 地址总线 (Address Bus)

- CPU和RAM需要通信方法，所以它们使用**EDB (External Data Bus)**
- CPU不知道如何与内存通信，所以它需要一个助手——**内存控制器芯片 (MCC - Memory Controller Chip)**
- **MCC** 促进从RAM到CPU的数据流
- **地址总线：** 通过**内存控制器芯片 (MCC)** 连接CPU和RAM，MCC"抓取"CPU的RAM
- **地址总线**是一组电线，使CPU能够通过MCC寻址RAM

**English:**  

### Address Bus

- CPU and RAM need communication methods, so they use the **EDB (External Data Bus)**
- The CPU doesn't know how to talk to memory, so it needs a helper—the **memory controller chip (MCC)**
- The **MCC** facilitates data flow from the RAM to the CPU
- **Address bus:** Connects the CPU and RAM via a **memory controller chip (MCC)**, which "grabs" the CPU's RAM
- An **address bus** is a set of wires that enables the CPU to address the RAM via the MCC

---

# 📖 Page 29: Von Neumann Architecture | 冯·诺依曼架构

**中文：**  

### 冯·诺依曼架构

- 该架构以数学家**约翰·冯·诺依曼 (John Von Neumann)** 命名
- 他提出在计算机内存中存储指令，并使用控制单元来处理**取指-译码-执行周期**：

1. **取指 (fetch)** 一条指令
2. **译码 (decode)** 指令
3. **获取数据**（如果需要）
4. **执行 (execute)** 指令

**有趣的事实：** 类似的架构在1830年由**查尔斯·巴贝奇 (Charles Babbage)** 为他的分析机提出

**English:**  

### Von Neumann Architecture

- The architecture is named after the mathematician, **John Von Neumann**
- He supposedly proposed storing instructions in the memory of a computer and using a control unit to handle the **fetch-decode-execute cycle**:
  1. **Fetch** an instruction
  2. **Decode** the instruction
  3. **Get the data** if needed
  4. **Execute** the instruction

**Interestingly:** A similar architecture was proposed in 1830 by **Charles Babbage** for his Analytic Engine

---

# 📖 Page 30: Stored-Program Concept | 存储程序概念

**中文：**  

### 存储程序概念 (Stored-Program Concept)

**指令和数据都存储在内存单元中**

**English:**  

### Stored-Program Concept

**Instructions and data both stored in memory unit**

---

# 📖 Page 31: All Computer Does | 计算机所做的全部

**中文：**  

### 计算机所做的全部...

**重复永远（或直到你拔掉电源或系统崩溃）：**

1. **取指 (Fetch)** 下一条指令
2. **译码 (Decode)** 指令
3. **获取数据**（如果需要）
4. **执行 (Execute)** 指令

**取指-执行周期 (The Fetch-Execute Cycle)**

**English:**  

### All Computer Does Is…

**Repeat forever (or until you pull the plug or the system crashes):**

1. **Fetch** the next instruction
2. **Decode** the instruction
3. **Get data** if needed
4. **Execute** the instruction

**The Fetch-Execute Cycle**

---

# 📖 Page 32: The Fetch-Execute Cycle | 取指-执行周期

**中文：**  

### 取指-执行周期

**English:**  

### The Fetch-Execute Cycle

---

# 📖 Page 33: The Fetch-Execute Cycle Details | 取指-执行周期详解

**中文：**  

### 取指-执行周期的详细步骤

#### 1. 取指 (Fetch) 下一条指令
- 指令的地址在**PC (程序计数器)** 中
- 控制单元访问内存中的上述地址
- 将指令从该地址**复制到IR (指令寄存器)**
- PC存储下一条指令的地址
- 控制单元**递增PC**

#### 2. 译码 (Decode) 指令
- 控制单元确定指令
- 指令内置于每台机器的电路中

#### 3. 获取数据（如果需要）
- 如果需要，从内存访问数据

#### 4. 执行 (Execute) 指令
- 控制单元向ALU发送信号以执行处理

**English:**  

### The Fetch-Execute Cycle

#### 1. Fetch the next instruction
- The address of the instruction is in **PC**
- Control unit goes to the above address in memory
- **Copies the instruction** from that address to **IR**
- PC stores the address of the next instruction
- Control unit **increments the PC**

#### 2. Decode the instruction
- Control unit determines the instruction
- The instructions are built into the circuits of each machine

#### 3. Get data if needed
- Access data from memory if needed

#### 4. Execute the instruction
- Control unit sends signals to ALU to carry out the processing

---

# 📖 Page 34: What Determine CPU Performance | 什么决定CPU性能

**中文：**  

### 决定CPU性能的因素

1. **数据总线宽度 (Data bus width)**
   - CPU内传输数据的路径数量（8、16、32、64）

2. **字长 (Word size)**
   - CPU一次可以处理的最大数据位数（8位、16位、32位、64位）

3. **每周期操作数 (Operations per cycle)** - 时钟速度
   - 每秒的时钟周期数，以**兆赫 (MHz)** 或**千兆赫 (GHz)** 测量

**English:**  

### What Determine CPU Performance

1. **Data bus width**
   - The number of pathways within the CPU that transfers data (8, 16, 32, 64)

2. **Word size**
   - The maximum number of bits of data that the CPU can process at a time (8 bits, 16 bits, 32 bits, 64 bits)

3. **Operations per cycle (clock speed)**
   - The number of clock cycles per second measured in **Megahertz (MHz)** or **Gigahertz (GHz)**

---

# 📖 Page 35: Super Simple CPU | 超级简单CPU

**中文：**  

### 超级简单CPU

- 我们将使用一个简单的CPU模拟器进行练习
- 它具有计算机的组件，如内存、CPU和IO

### 超级简单CPU内存

- **16个内存位置**
- 内存地址是**0到FF或15**
- 每个内存位置有**16位**
- **字长是2字节**
- 比较地址和内容的位数

**English:**  

### Super Simple CPU

- We are going to practice with a simple CPU simulator
- It has the components of a computer like memory, CPU, and IO

### Super Simple CPU Memory

- **16 memory locations**
- Memory addresses are **0 to FF or 15**
- **16 bits** at each memory location
- The **word length is 2 bytes**
- Compare the number of bits for address and contents

---

# 📖 Page 36: Super Simple CPU Registers | 超级简单CPU寄存器

**中文：**  

### 超级简单CPU寄存器

#### PC (Program Counter) - 程序计数器
- 包含要执行的下一条指令的地址

#### IR (Instruction Register) - 指令寄存器
- 包含正在执行的指令的副本

#### A (Accumulator) - 累加器寄存器
- 用于保存数据和操作结果

**English:**  

### Super Simple CPU

#### Registers

- **PC (Program Counter)**
  - Contains the address of the next instruction to be executed

- **The instruction register (IR)**
  - Contains a copy of the instruction being executed

- **The accumulator (A register)**
  - Used to hold data and results of operations

---

# 📖 Page 37: Super Simple CPU Instructions Format | 超级简单CPU指令格式

**中文：**  

### 超级简单CPU指令格式

- 每条指令是**16位**
  - **4位操作码 (opcode)** - 表示指令
  - **12位操作数 (operand)** - 保存4种不同类型的信息：

#### 1. 一个常数 (A constant)
- **LDI (Load Immediate)** - 立即加载：数据立即加载到累加器中

#### 2. 数据的地址 (The address of the data)
- **ADD, SUB, STO, LOD** - 使用该地址中的数据

#### 3. 下一条指令的地址 (The address of the next instruction)
- **JMP, JZR, JNG** - 控制跳转到该地址

#### 4. 无 (Nothing)
- **STP, IN, OUT** 类型

**English:**  

### Super Simple CPU

- Each instruction is **16 bits**
  - **4-bit opcode** - Represents the instruction
  - **12-bit operand** holds 4 different type of information:

#### 1. A constant
- **LDI (Load Immediate)**: data is immediately loaded into the accumulator

#### 2. The address of the data
- **ADD, SUB, STO, and LOD**: data in that address is used

#### 3. The address of the next instruction
- **JMP, JZR, JNG**: control jumps into this address

#### 4. Nothing
- **STP, IN, OUT** types

---

# 📖 Page 38: Super Simple CPU Instruction Set | 超级简单CPU指令集

**中文：**  

### 超级简单CPU指令集

- 这是超级简单CPU的指令集
- 表格显示了每条指令的**二进制代码**和**助记符代码（汇编语言）**

**English:**  

### Super Simple CPU

- This is the set of instructions for Super Simple CPU
- The table shows the **binary code** and **Mnemonic code (assembly language)** for each instruction

---

# 📖 Page 39: Super Simple CPU Example | 超级简单CPU示例

**中文：**  

### 超级简单CPU示例

以下程序：
- 有**4个内存位置**用于指令，**2个用于数据 (DAT)**
- 将一个值（5）加载到累加器
- 将其与地址X（40）中的值相加
- 将其存储在地址Y（5）

**English:**  

### Super Simple CPU

**Example:** The following program:
- Has **4 memory location** for instructions and **2 for data (DAT)**
- Loads a value (5) into accumulator
- Adds it to the value in address X (40)
- Stores it in address Y (5)

---

# 📖 Page 40: Super Simple CPU Instructions (Part 1) | 超级简单CPU指令（第一部分）

**中文：**  

### 超级简单CPU指令

#### 1111 STP (Stop)
- 停止计算机；不再有取指/译码/执行周期，直到你重置

#### 0001 ADD (Add)
- 从内存获取一个数字并将其添加到累加器的内容中，替换累加器中的值
- **例子：** `0001000000001111` - 获取内存位置15的值并将其添加到累加器

#### 0010 SUB (Subtract)
- 从内存获取一个数字并从累加器的内容中减去它，替换累加器中的值

#### 0011 LOD (Load)
- 从内存获取一个数字并将其存储在累加器中，替换累加器的旧值
- **例子：** `0011000000001111` - 获取内存位置15的值并将其存储在累加器中

#### 0100 LDI (Load Immediate)
- 立即加载；要放入累加器的值是操作数（指令的最右边12位）；不像LOD那样去内存
- **例子：** `0100000000001111` - 将值15存储在累加器中

#### 0101 STO (Store)
- 将累加器的值存储在指定位置的内存中
- **例子：** `0101000000001111` - 将累加器的值存储在内存位置15

**English:**  

### Super Simple CPU Instructions

#### 1111 STP
- This stops the computer; no more fetch/decode/execute cycles until you reset

#### 0001 ADD
- Fetch a number from memory and add it to the contents of the accumulator, replacing the value in the accumulator
- (e.g., `0001000000001111`: Get the value at memory location 15 and add that to the accumulator.)

#### 0010 SUB
- Fetch a number from memory and subtract it from the contents of the accumulator, replacing the value in the accumulator

#### 0011 LOD
- Fetch a number from memory and store it in the accumulator, replacing the accumulator's old value
- (e.g., `0011000000001111`: Get the value at memory location 15 and store that value in the accumulator.)

#### 0100 LDI
- Load immediate; the value to be put in the accumulator is the operand (the rightmost 12 bits of the instruction); do not go to memory like LOD
- (e.g., `0100000000001111`: Store the value 15 in the accumulator.)

#### 0101 STO
- Store the accumulator's value in memory at the indicated location
- (e.g., `0101000000001111`: Store the accumulator's value in memory location 15.)

---

# 📖 Page 41: Super Simple CPU Instructions (Part 2) | 超级简单CPU指令（第二部分）

**中文：**  

### 超级简单CPU指令（续）

#### 0110 INP (Input)
- 向用户请求一个数字并将其存储在累加器中

#### 0111 OUT (Output)
- 将累加器中的值复制到输出区域

#### 1000 JMP (Jump)
- 跳转到指定内存地址的指令
- **例子：** `1000000000001111` - 将值15放入PC，这将导致下一条指令从内存的位置15获取

#### 1001 JNG (Jump if Negative)
- 如果累加器的值为负数，则跳转到指定内存位置的指令；否则只是将PC加1
- **例子：** `1001000000001111` - 如果累加器 < 0，则将值15放入PC；否则转到下一条指令

#### 1010 JZR (Jump if Zero)
- 如果累加器的值为零，则跳转到指定内存位置的指令；否则只是将PC加1
- **例子：** `1010000000001111` - 如果累加器 = 0，则将值15放入PC；否则转到下一条指令

**English:**  

### Super Simple CPU Instructions

#### 0110 INP
- Ask the user for one number and store that in the accumulator

#### 0111 OUT
- Copy the value in the accumulator to the output area

#### 1000 JMP
- Jump to the instruction at the indicated memory address
- (e.g., `1000000000001111`: Put the value 15 into the PC, which will cause the next instruction to be taken from location 15 of the memory.)

#### 1001 JNG
- Jump to the instruction at the indicated memory location if the accumulator's value is negative; otherwise just add 1 to the PC
- (e.g., `1001000000001111`: Put the value 15 into the PC, if accumulator < 0; otherwise go to the next instruction.)

#### 1010 JZR
- Jump to the instruction at the indicated memory location if the accumulator's value is zero; otherwise just add 1 to the PC
- (e.g., `1010000000001111`: Put the value 15 into the PC, if accumulator = 0; otherwise go to the next instruction.)

---

# 📖 Page 42: Some Resources | 一些资源

**中文：**  

### 一些资源

**观看视频：**
- How Computers Calculate - the ALU（计算机如何计算 - ALU）
- Registers and RAM（寄存器和RAM）
- The Central Processing Unit (CPU)（中央处理单元）
- Instructions & Programs（指令和程序）
- Advanced CPU Designs（高级CPU设计）

**English:**  

### Some Resources

**To watch:**
- How Computers Calculate - the ALU
- Registers and RAM
- The Central Processing Unit (CPU)
- Instructions & Programs
- Advanced CPU Designs

---

# 📖 Page 43: Chapter Goals Review | 章节目标回顾

**中文：**  

### 章节目标回顾

学完这章，你应该能够：

1. **列出冯·诺依曼机器的组件及其功能**  
   List the components and their function in a von Neumann machine

2. **描述冯·诺依曼机器的取指-译码-执行周期**  
   Describe the fetch-decode-execute cycle of the von Neumann machine

3. **描述计算机内存是如何组织和访问的**  
   Describe how computer memory is organized and accessed

4. **命名并描述不同的辅助存储设备**  
   Name and describe different auxiliary storage devices

**English:**  

### Chapter Goals

1. List the components and their function in a von Neumann machine
2. Describe the fetch-decode-execute cycle of the von Neumann machine
3. Describe how computer memory is organized and accessed
4. Name and describe different auxiliary storage devices

---

# 📝 Study Tips | 学习建议

**中文：**  

1. **理解内存层次** - 理解主存储器和辅助存储器的区别和用途
2. **掌握取指-执行周期** - 熟练掌握四个步骤：取指、译码、获取数据、执行
3. **理解CPU组件** - 清楚ALU、控制单元、寄存器的不同作用
4. **掌握Super Simple CPU** - 理解指令格式和指令集
5. **理解缓存层次** - 掌握L1、L2、L3缓存的作用
6. **理解总线系统** - 掌握地址总线、数据总线的功能
7. **联系实际** - 将概念与实际计算机硬件联系起来

**English:**  

1. **Understand Memory Hierarchy** - Understand the differences and uses of primary and secondary memory
2. **Master Fetch-Execute Cycle** - Master the four steps: Fetch, Decode, Get Data, Execute
3. **Understand CPU Components** - Clearly understand the different roles of ALU, Control Unit, and Registers
4. **Master Super Simple CPU** - Understand instruction format and instruction set
5. **Understand Cache Hierarchy** - Master the roles of L1, L2, L3 caches
6. **Understand Bus System** - Master the functions of address bus and data bus
7. **Connect to Reality** - Connect concepts to actual computer hardware

---

**准备就绪！开始学习 Chapter 5 吧！**  
**Ready! Let's start learning Chapter 5!**
