# 📖 Chapter 10 & 11 详细讲解笔记 | Detailed Lecture Notes

**说明：** 本笔记按课件顺序详细讲解 Ch10（操作系统）与 Ch11（文件系统）的所有知识点，包含概念解释、公式推导、例题步骤。每个部分先完整中文，再完整英文。

---

# ═══════════════════════════════════════════
# 第一部分：Chapter 10 — 操作系统
# Part 1: Chapter 10 — Operating Systems
# ═══════════════════════════════════════════

---

## 一、学习目标 | Learning Outcomes

### 中文

学完本章后，你应该能够：
1. 描述操作系统的两大核心职责：**内存管理**和**进程管理**。
2. 解释**逻辑地址**与**物理地址**之间的关系。
3. 比较三种内存管理技术：单连续、分区、分页。
4. 解释各种 CPU 调度算法：先来先服务（FCFS）、最短作业优先（SJN）、时间片轮转（RR）。

### English

After this chapter, you should be able to:
1. Describe two main OS responsibilities: **memory management** and **process management**.
2. Explain the relationship between **logical** and **physical addresses**.
3. Compare memory management techniques: single contiguous, partition, and paged.
4. Explain CPU scheduling algorithms: FCFS, SJN, and Round Robin.

---

## 二、计算机系统结构与软件分类

### 中文

**计算机系统四大组件：**
1. **硬件（Hardware）**：CPU、内存、I/O 设备等物理组件。
2. **操作系统（Operating System）**：管理硬件资源、提供用户接口的系统软件。
3. **应用软件（Application Software）**：为解决实际问题而编写的软件，如 Word、浏览器、游戏。
4. **用户（Users）**：使用计算机的人或其他系统。

**软件分类：**
- **应用软件**：针对特定需求编写，解决现实世界的问题。例如：文字处理软件、电子表格、图像编辑器。
- **系统软件**：在底层管理计算机系统。例如：操作系统、设备驱动程序、编译器。

**操作系统的定义：**  
操作系统是一种系统软件，它：
- 管理计算机资源（如内存、输入输出设备）；
- 提供人机交互的界面（命令行或图形界面）；
- 允许应用程序与系统资源交互。

### English

**Four components of a computer system:**
1. **Hardware:** Physical components—CPU, memory, I/O devices.
2. **Operating System:** System software that manages hardware and provides user interface.
3. **Application Software:** Programs written to solve real-world problems—Word, browsers, games.
4. **Users:** People or other systems using the computer.

**Software categories:**
- **Application software:** Written for specific needs; solves real-world problems. Examples: word processors, spreadsheets, image editors.
- **System software:** Manages the computer at a fundamental level. Examples: OS, device drivers, compilers.

**Definition of Operating System:**  
An OS is system software that:
- Manages computer resources (memory, I/O devices);
- Provides an interface for human interaction (CLI or GUI);
- Allows applications to interact with system resources.

---

## 三、操作系统的角色

### 中文

操作系统有以下主要角色：

| 术语 | 含义 |
|------|------|
| **多道程序设计（Multiprogramming）** | 让多个程序同时驻留在主存中，竞争使用 CPU。当一个程序等待 I/O 时，CPU 可以执行另一个程序，提高利用率。 |
| **内存管理（Memory Management）** | 跟踪哪些程序在内存中、它们占用哪些位置。 |
| **进程（Process）** | 正在执行的程序。程序是静态的代码文件；进程是动态的、有状态的执行实例。 |
| **进程管理（Process Management）** | 跟踪每个进程的执行进度和中间状态。 |
| **CPU 调度（CPU Scheduling）** | 决定在任一时刻由哪个进程占用 CPU。 |

**分时系统（Timesharing）：**  
让多个用户同时与一台计算机交互。每个用户感觉自己在独占机器，这种"错觉"叫做**虚拟机（Virtual Machine）**。分时通常配合时间片轮转调度实现。

### English

Key roles of an OS:

| Term | Meaning |
|------|---------|
| **Multiprogramming** | Keeping multiple programs in main memory at once, competing for CPU. When one waits for I/O, CPU runs another, improving utilization. |
| **Memory Management** | Tracking which programs are in memory and where they reside. |
| **Process** | A program in execution. A program is static code; a process is a dynamic, running instance with state. |
| **Process Management** | Tracking each process's progress and intermediate states. |
| **CPU Scheduling** | Deciding which process in memory runs on the CPU at any given time. |

**Timesharing:**  
Allows multiple users to interact with one computer simultaneously. Each user feels they have their own machine—this illusion is called a **virtual machine**. Timesharing typically uses Round Robin scheduling.

---

## 四、内存管理 — 逻辑地址与物理地址

### 中文

**核心问题：**  
操作系统需要解决两个问题：
1. 如何让多个程序共享一个 CPU？
2. 如何让多个程序共享一块主存？

**逻辑地址 vs 物理地址：**

| 类型 | 说明 |
|------|------|
| **逻辑地址（Logical Address）** | 程序内部使用的地址，相对于程序自身起点的偏移量。也叫虚拟地址。每个进程有自己的逻辑地址空间。 |
| **物理地址（Physical Address）** | 主存中的实际地址，由硬件直接访问。 |

**地址转换（Address Translation）：**  
程序使用逻辑地址编写和运行。当程序访问内存时，硬件（在操作系统帮助下）把逻辑地址转换成物理地址。这个过程叫地址转换或地址映射。

**类比理解：**  
- 逻辑地址就像"办公家具在仓库的相对位置"；
- 物理地址就像"仓库中的实际货架编号"。

### English

**Core problems:**  
The OS must solve:
1. How to share one CPU among several programs?
2. How to share one main memory among several programs?

**Logical vs Physical Address:**

| Type | Description |
|------|-------------|
| **Logical Address** | Address used inside a program, relative to the program's starting point. Also called virtual address. Each process has its own logical address space. |
| **Physical Address** | Actual address in main memory, accessed directly by hardware. |

**Address Translation:**  
Programs are written using logical addresses. When a program accesses memory, the hardware (with OS help) converts the logical address to a physical address. This is called address translation or address mapping.

**Analogy:**  
- Logical address = "relative position of office furniture in warehouse";
- Physical address = "actual shelf number in the warehouse."

---

## 五、内存管理技术详解

### 5.1 单连续内存管理（Single Contiguous MM）

#### 中文

**基本思想：**  
内存中只有两个程序：
1. 操作系统（固定在内存低端或高端）；
2. 一个应用程序（占用剩余空间）。

**地址转换公式：**  
如果程序从物理地址 A 开始加载，那么逻辑地址 L 对应的物理地址为：

```
物理地址 = A + L
```

**例题：**  
程序加载在地址 30,215，逻辑地址 9,223 对应的物理地址是多少？

**解答：**  
物理地址 = 30,215 + 9,223 = **39,438**

**特点：**
- 简单，易于实现。
- 缺点：同一时刻只能运行一个应用程序，CPU 利用率低。

#### English

**Basic idea:**  
Only two programs in memory:
1. The operating system (fixed at low or high end);
2. One application program (occupies the rest).

**Address translation formula:**  
If a program is loaded starting at physical address A, then logical address L maps to:

```
Physical address = A + L
```

**Example:**  
Program loaded at 30,215; logical address 9,223. What is the physical address?

**Solution:**  
Physical address = 30,215 + 9,223 = **39,438**

**Characteristics:**
- Simple to implement.
- Drawback: Only one application can run at a time; low CPU utilization.

---

### 5.2 分区内存管理（Partition MM）

#### 中文

**基本思想：**  
内存被划分为多个分区，可以同时存放多个程序。

**两种分区方式：**

| 类型 | 说明 |
|------|------|
| **固定分区（Fixed Partitions）** | 内存预先被分成固定数量、固定大小的分区。程序必须放入某个足够大的分区。 |
| **动态分区（Dynamic Partitions）** | 分区大小按需创建，刚好容纳程序。程序结束后释放空间，可能产生碎片。 |

**分区选择算法（Partition Selection Algorithms）：**

当有多个空闲分区时，新程序应该放入哪个？

| 算法 | 策略 | 特点 |
|------|------|------|
| **First Fit（首次适应）** | 选择第一个足够大的分区 | 快速，但可能浪费大分区 |
| **Best Fit（最佳适应）** | 选择足够大的最小分区 | 尽量保留大分区，但产生小碎片 |
| **Worst Fit（最差适应）** | 选择足够大的最大分区 | 剩余空间较大，可能容纳其他程序 |

**例题：**  
内存：OS | P1 | 空(60) | P2 | P3 | 空(52) | 空(100)  
新作业需要 52 块。三种算法分别选哪个分区？

**解答：**
- **First Fit**：从前往后找第一个 ≥52 的空区 → **60 块**（第一个空区）
- **Best Fit**：找 ≥52 且最小的 → **52 块**（刚好）
- **Worst Fit**：找 ≥52 且最大的 → **100 块**

**Base Register 和 Bounds Register：**

在分区系统中，有两个重要的寄存器：

| 寄存器 | 作用 |
|--------|------|
| **基址寄存器（Base Register）** | 保存当前运行进程所在分区的起始地址 |
| **界限寄存器（Bounds Register）** | 保存当前分区的长度 |

**地址转换：**
1. 检查逻辑地址是否小于 Bounds（否则越界错误）；
2. 物理地址 = Base + 逻辑地址。

**例题：**  
Base = 42,993，Bounds = 2,031。逻辑地址 104 和 3,041 的物理地址分别是？

**解答：**
- 逻辑地址 104：104 < 2,031 ✓，物理地址 = 42,993 + 104 = **43,097**
- 逻辑地址 3,041：3,041 > 2,031 ✗，**越界错误（out of bounds）**

#### English

**Basic idea:**  
Memory is divided into partitions; multiple programs can be in memory at once.

**Two partition types:**

| Type | Description |
|------|-------------|
| **Fixed Partitions** | Memory is pre-divided into a fixed number of fixed-size partitions. Programs must fit into one. |
| **Dynamic Partitions** | Partitions are created as needed, sized exactly for each program. May cause fragmentation after programs exit. |

**Partition Selection Algorithms:**

When multiple free partitions exist, which should a new program use?

| Algorithm | Strategy | Notes |
|-----------|----------|-------|
| **First Fit** | First partition large enough | Fast, but may waste large partitions |
| **Best Fit** | Smallest partition large enough | Preserves large partitions, but creates small fragments |
| **Worst Fit** | Largest partition large enough | Leaves larger leftover space |

**Example:**  
Memory: OS | P1 | Free(60) | P2 | P3 | Free(52) | Free(100)  
New job needs 52 blocks. Which partition under each algorithm?

**Solution:**
- **First Fit:** First partition ≥52 from front → **60 blocks**
- **Best Fit:** Smallest ≥52 → **52 blocks** (exact fit)
- **Worst Fit:** Largest ≥52 → **100 blocks**

**Base Register and Bounds Register:**

In partition systems, two important registers:

| Register | Purpose |
|----------|---------|
| **Base Register** | Holds starting address of current process's partition |
| **Bounds Register** | Holds length of current partition |

**Address translation:**
1. Check if logical address < Bounds (else: out of bounds error);
2. Physical address = Base + logical address.

**Example:**  
Base = 42,993, Bounds = 2,031. Physical addresses for logical 104 and 3,041?

**Solution:**
- Logical 104: 104 < 2,031 ✓, physical = 42,993 + 104 = **43,097**
- Logical 3,041: 3,041 > 2,031 ✗, **out of bounds error**

---

### 5.3 分页内存管理（Paged MM）

#### 中文

**基本思想：**  
把物理内存划分为固定大小的块，叫**帧（Frame）**；把程序划分为同样大小的块，叫**页（Page）**。程序的各页可以分散存放在内存的各帧中，不需要连续。

| 术语 | 说明 |
|------|------|
| **帧（Frame）** | 主存中固定大小的块，用于存放一页 |
| **页（Page）** | 进程被划分的固定大小块 |
| **页表（Page Table / PMT）** | 记录每一页存放在哪个帧中 |

**逻辑地址的拆分：**

逻辑地址被拆分为两部分：
- **页号（Page Number）** = 逻辑地址 **DIV** 页大小（整除）
- **页内偏移（Offset）** = 逻辑地址 **MOD** 页大小（取余）

**例题：**  
逻辑地址 2,566，页大小 1,024。求页号和偏移。

**解答：**
- 页号 = 2,566 ÷ 1,024 = **2**（取整数部分）
- 偏移 = 2,566 mod 1,024 = 2,566 - 2×1,024 = 2,566 - 2,048 = **518**
- 结果：\<2, 518\>

**地址转换过程：**
1. 把逻辑地址拆成 \<页号, 偏移\>；
2. 用页号查页表，得到对应的帧号；
3. 物理地址 = 帧号 × 页大小 + 偏移。

**按需分页（Demand Paging）：**  
只在需要时才把页调入内存，而不是一开始就把整个程序全部加载。

**页交换（Page Swap）：**  
把一页从辅存调入主存；通常同时要把另一页写回辅存以腾出空间。

**虚拟内存（Virtual Memory）：**  
由于按需分页，程序不需要全部在内存中，因此程序大小可以超过物理内存。这种"内存不受限"的错觉叫虚拟内存。

**抖动（Thrashing）：**  
如果页交换过于频繁（刚调入的页马上又被换出），系统大部分时间花在换页而不是执行程序，导致效率极低。这种现象叫抖动。

#### English

**Basic idea:**  
Divide physical memory into fixed-size blocks called **frames**; divide programs into same-size blocks called **pages**. Pages of a program can be scattered across non-contiguous frames.

| Term | Description |
|------|-------------|
| **Frame** | Fixed-size block in main memory that holds one page |
| **Page** | Fixed-size block of a process |
| **Page Table (PMT)** | Records which frame each page is stored in |

**Splitting the logical address:**

A logical address is split into:
- **Page Number** = logical address **DIV** page size (integer division)
- **Offset** = logical address **MOD** page size (remainder)

**Example:**  
Logical address 2,566, page size 1,024. Find page number and offset.

**Solution:**
- Page number = 2,566 ÷ 1,024 = **2** (integer part)
- Offset = 2,566 mod 1,024 = 2,566 - 2×1,024 = **518**
- Result: \<2, 518\>

**Address translation process:**
1. Split logical address into \<page number, offset\>;
2. Look up page number in page table to get frame number;
3. Physical address = frame number × page size + offset.

**Demand Paging:**  
Pages are loaded into memory only when needed, not all at once when the program starts.

**Page Swap:**  
Bringing a page from secondary storage into main memory; usually another page must be written back to make room.

**Virtual Memory:**  
Because of demand paging, a program doesn't need to be entirely in memory, so program size can exceed physical RAM. This illusion of unlimited memory is called virtual memory.

**Thrashing:**  
If page swaps happen too frequently (a page is brought in and immediately swapped out), the system spends most of its time swapping rather than executing. This severe inefficiency is called thrashing.

---

## 六、进程管理

### 中文

**进程控制块（PCB）：**  
每个进程有一个 PCB，操作系统用它来记录进程的所有信息：
- 程序计数器（PC）的当前值；
- 所有 CPU 寄存器的值；
- 基址/界限寄存器的值（或页表指针）；
- 记账信息（已用 CPU 时间等）。

每种状态（就绪、运行、阻塞等）都有一个 PCB 列表。

**上下文切换（Context Switch）：**  
CPU 同一时刻只能运行一个进程。当需要切换进程时：
1. 把当前进程的寄存器值保存到它的 PCB；
2. 把当前 PCB 移到相应状态列表（如就绪队列）；
3. 从新进程的 PCB 中恢复寄存器值到 CPU；
4. 新进程开始运行。

这个"保存旧状态、恢复新状态"的过程叫上下文切换。上下文切换有开销，切换过于频繁会降低效率。

### English

**Process Control Block (PCB):**  
Each process has a PCB where the OS stores all process information:
- Current value of Program Counter (PC);
- Values of all CPU registers;
- Base/bounds register values (or page table pointer);
- Accounting info (CPU time used, etc.).

Each state (ready, running, blocked, etc.) has a list of PCBs.

**Context Switch:**  
Only one process can run on the CPU at a time. When switching processes:
1. Save current process's register values into its PCB;
2. Move current PCB to appropriate state list (e.g., ready queue);
3. Load new process's register values from its PCB into CPU;
4. New process begins running.

This "save old state, restore new state" process is called a context switch. Context switches have overhead; too many reduce efficiency.

---

## 七、CPU 调度算法详解

### 中文

**CPU 调度：**  
决定哪个就绪进程下一个进入运行状态。

**两种调度方式：**

| 方式 | 说明 |
|------|------|
| **非抢占式（Nonpreemptive）** | 进程主动让出 CPU（运行完或等待 I/O）才切换 |
| **抢占式（Preemptive）** | 操作系统可以强制剥夺当前进程的 CPU，让给其他进程 |

**周转时间（Turnaround Time）：**  
从进程第一次进入就绪队列到它最后一次退出运行状态的总时间。简单情况下（所有进程同时到达、无 I/O），周转时间 = 完成时间 - 到达时间 = 完成时间（若到达时间为 0）。

---

### 7.1 先来先服务（FCFS）

**规则：** 按进程到达就绪队列的顺序依次运行，先来的先运行完。

**特点：**
- 非抢占式；
- 简单公平；
- 缺点：短作业可能被长作业阻塞很久（护航效应）。

**例题：**  
P1=8, P2=6, P3=1, P4=9, P5=3，全部 time 0 到达，按 P1→P2→P3→P4→P5 顺序。

| 进程 | 运行时间 | 完成时间 | 周转时间 |
|------|----------|----------|----------|
| P1 | 8 | 8 | 8 |
| P2 | 6 | 14 | 14 |
| P3 | 1 | 15 | 15 |
| P4 | 9 | 24 | 24 |
| P5 | 3 | 27 | 27 |

平均周转时间 = (8+14+15+24+27)/5 = **17.6 ms**

---

### 7.2 最短作业优先（SJN）

**规则：** 每次从就绪队列中选运行时间最短的进程运行。

**特点：**
- 非抢占式（选中后运行到完成）；
- 平均周转时间通常最短；
- 缺点：需要预知运行时间；长作业可能饥饿。

**例题（同上数据）：**  
按运行时间排序：P3(1) → P5(3) → P2(6) → P1(8) → P4(9)

| 进程 | 运行时间 | 完成时间 | 周转时间 |
|------|----------|----------|----------|
| P3 | 1 | 1 | 1 |
| P5 | 3 | 4 | 4 |
| P2 | 6 | 10 | 10 |
| P1 | 8 | 18 | 18 |
| P4 | 9 | 27 | 27 |

平均周转时间 = (1+4+10+18+27)/5 = **12 ms**

---

### 7.3 时间片轮转（Round Robin）

**规则：** 每个进程运行一个固定的时间片（quantum），时间到了就被强制切换，放到就绪队列末尾。

**特点：**
- 抢占式；
- 公平，每个进程都有机会运行；
- 响应性好，适合分时系统；
- 时间片选择很重要：太小则切换开销大，太大则退化成 FCFS。

**例题（quantum = 2 ms）：**  
执行过程：
- 0-2: P1 运行 2（剩 6）
- 2-4: P2 运行 2（剩 4）
- 4-5: P3 运行 1（**完成**）
- 5-7: P4 运行 2（剩 7）
- 7-9: P5 运行 2（剩 1）
- 9-11: P1 运行 2（剩 4）
- 11-13: P2 运行 2（剩 2）
- 13-15: P4 运行 2（剩 5）
- 15-16: P5 运行 1（**完成**）
- 16-18: P1 运行 2（剩 2）
- 18-20: P2 运行 2（**完成**）
- 20-22: P4 运行 2（剩 3）
- 22-24: P1 运行 2（**完成**）
- 24-26: P4 运行 2（剩 1）
- 26-27: P4 运行 1（**完成**）

| 进程 | 完成时间 | 周转时间 |
|------|----------|----------|
| P1 | 24 | 24 |
| P2 | 20 | 20 |
| P3 | 5 | 5 |
| P4 | 27 | 27 |
| P5 | 16 | 16 |

平均周转时间 = (24+20+5+27+16)/5 = **18.4 ms**

---

### 7.4 三种算法对比

| 算法 | 抢占？ | 平均周转（此例） | 优点 | 缺点 |
|------|--------|------------------|------|------|
| FCFS | 非抢占 | 17.6 ms | 简单 | 短作业等待久 |
| SJN | 非抢占 | 12 ms | 周转时间短 | 需预知运行时间 |
| RR | 抢占 | 18.4 ms | 公平、响应快 | 切换开销 |

### English

**CPU Scheduling:**  
Determines which ready process runs next.

**Two scheduling types:**

| Type | Description |
|------|-------------|
| **Nonpreemptive** | Process gives up CPU voluntarily (finishes or waits for I/O) |
| **Preemptive** | OS can forcibly take CPU from current process and give it to another |

**Turnaround Time:**  
Total time from when a process first enters the ready state until it finally exits the running state. For simple cases (all arrive at time 0, no I/O), turnaround = completion time.

---

### 7.1 First-Come, First-Served (FCFS)

**Rule:** Processes run in order of arrival; first to arrive runs to completion first.

**Characteristics:**
- Nonpreemptive;
- Simple and fair;
- Drawback: Short jobs may wait long behind long jobs (convoy effect).

**Example:**  
P1=8, P2=6, P3=1, P4=9, P5=3, all arrive at time 0 in order P1→P2→P3→P4→P5.

| Process | Burst | Completion | Turnaround |
|---------|-------|------------|------------|
| P1 | 8 | 8 | 8 |
| P2 | 6 | 14 | 14 |
| P3 | 1 | 15 | 15 |
| P4 | 9 | 24 | 24 |
| P5 | 3 | 27 | 27 |

Average turnaround = (8+14+15+24+27)/5 = **17.6 ms**

---

### 7.2 Shortest Job Next (SJN)

**Rule:** Always run the ready process with shortest burst time.

**Characteristics:**
- Nonpreemptive (once selected, runs to completion);
- Usually gives shortest average turnaround;
- Drawback: Must know burst times in advance; long jobs may starve.

**Example (same data):**  
Sorted by burst: P3(1) → P5(3) → P2(6) → P1(8) → P4(9)

| Process | Burst | Completion | Turnaround |
|---------|-------|------------|------------|
| P3 | 1 | 1 | 1 |
| P5 | 3 | 4 | 4 |
| P2 | 6 | 10 | 10 |
| P1 | 8 | 18 | 18 |
| P4 | 9 | 27 | 27 |

Average turnaround = (1+4+10+18+27)/5 = **12 ms**

---

### 7.3 Round Robin (RR)

**Rule:** Each process runs for a fixed time slice (quantum), then is preempted and moved to back of ready queue.

**Characteristics:**
- Preemptive;
- Fair; every process gets CPU time;
- Good responsiveness; suits timesharing;
- Quantum choice matters: too small = high overhead; too large = degrades to FCFS.

**Example (quantum = 2 ms):**  
[Execution trace as above]

| Process | Completion | Turnaround |
|---------|------------|------------|
| P1 | 24 | 24 |
| P2 | 20 | 20 |
| P3 | 5 | 5 |
| P4 | 27 | 27 |
| P5 | 16 | 16 |

Average turnaround = (24+20+5+27+16)/5 = **18.4 ms**

---

### 7.4 Algorithm Comparison

| Algorithm | Preemptive? | Avg Turnaround (this example) | Pros | Cons |
|-----------|-------------|------------------------------|------|------|
| FCFS | No | 17.6 ms | Simple | Short jobs wait |
| SJN | No | 12 ms | Short turnaround | Need burst times |
| RR | Yes | 18.4 ms | Fair, responsive | Switch overhead |

---

# ═══════════════════════════════════════════
# 第二部分：Chapter 11 — 文件系统与目录
# Part 2: Chapter 11 — File Systems and Directories
# ═══════════════════════════════════════════

---

## 八、学习目标 | Learning Outcomes

### 中文

学完本章后，你应该能够：
1. 描述文件、文件系统和目录的作用。
2. 通过扩展名识别各种文件类型。
3. 定义对文件的基本操作。
4. 比较顺序访问和直接访问。
5. 描述目录树结构。
6. 为目录树写绝对路径和相对路径。
7. 描述几种磁盘调度算法。

### English

After this chapter, you should be able to:
1. Describe the purpose of files, file systems, and directories.
2. Identify file types by their extensions.
3. Define basic operations on a file.
4. Compare sequential and direct file access.
5. Describe a directory tree.
6. Create absolute and relative paths.
7. Describe several disk-scheduling algorithms.

---

## 九、文件类型与扩展名

### 中文

**文本文件 vs 二进制文件：**

| 类型 | 说明 | 例子 |
|------|------|------|
| **文本文件（Text File）** | 包含 ASCII 或 Unicode 字符的文件，可用文本编辑器打开阅读 | .txt, .html, .csv, .py |
| **二进制文件（Binary File）** | 以特定格式存储的文件，需要专门程序解释其位模式 | .jpg, .mp3, .exe, .docx |

**文件扩展名（File Extension）：**  
文件名通常分为两部分：**文件名.扩展名**（如 report.txt）。扩展名指示文件类型。

| 扩展名 | 文件类型 |
|--------|----------|
| .doc / .docx | Word 文档 |
| .jpg / .png | 图像 |
| .wav / .mp3 | 音频 |
| .mp4 | 视频 |
| .py | Python 源代码 |

### English

**Text File vs Binary File:**

| Type | Description | Examples |
|------|-------------|----------|
| **Text File** | Contains ASCII or Unicode characters; readable in text editor | .txt, .html, .csv, .py |
| **Binary File** | Data in specific format; requires special program to interpret | .jpg, .mp3, .exe, .docx |

**File Extension:**  
File names usually have two parts: **name.extension** (e.g., report.txt). The extension indicates file type.

| Extension | File Type |
|-----------|-----------|
| .doc / .docx | Word document |
| .jpg / .png | Image |
| .wav / .mp3 | Audio |
| .mp4 | Video |
| .py | Python source code |

---

## 十、文件访问与保护

### 中文

**文件访问方式：**

| 方式 | 说明 | 适用场景 |
|------|------|----------|
| **顺序访问（Sequential Access）** | 按线性顺序访问数据；要读最后一条记录必须先读前面所有记录 | 日志文件、磁带、音视频流 |
| **直接访问（Direct Access）** | 文件被分成编号的逻辑记录，可按记录号直接跳转访问 | 数据库、索引文件 |

**文件保护（File Protection）：**  
限制谁可以访问文件、可以做什么操作。在多用户系统中尤其重要——防止用户访问他人文件。

**Unix 文件权限：**  
Unix 把权限分为三类用户：
- **Owner（所有者）**：文件创建者；
- **Group（组）**：与所有者同组的用户；
- **Others（其他）**：其他所有用户。

每类用户有三种权限：
- **r（读）**：可以读取文件内容；
- **w（写）**：可以修改文件内容；
- **x（执行）**：可以执行文件（如脚本或程序）。

**权限示例：**  
`rwx r-x r--` 表示：所有者可读写执行，组用户可读执行，其他用户只能读。

### English

**File Access Methods:**

| Method | Description | Use Cases |
|--------|-------------|-----------|
| **Sequential Access** | Data accessed linearly; must read all preceding records to reach the last | Log files, tapes, audio/video streams |
| **Direct Access** | File divided into numbered logical records; jump directly to any record | Databases, index files |

**File Protection:**  
Limits who can access a file and what operations they can perform. Especially important in multi-user systems to prevent unauthorized access.

**Unix File Permissions:**  
Unix divides users into three categories:
- **Owner:** File creator;
- **Group:** Users in same group as owner;
- **Others:** All other users.

Each category has three permission types:
- **r (read):** Can read file contents;
- **w (write):** Can modify file contents;
- **x (execute):** Can run the file (scripts, programs).

**Permission example:**  
`rwx r-x r--` means: owner can read/write/execute, group can read/execute, others can only read.

---

## 十一、目录树与路径

### 中文

**目录（Directory）：**  
一个命名的文件组。目录可以包含文件和其他目录（子目录）。

**目录树术语：**

| 术语 | 说明 |
|------|------|
| **根目录（Root Directory）** | 文件系统最顶层的目录（如 `C:\` 或 `/`） |
| **父目录（Parent Directory）** | 包含当前目录的上一级目录 |
| **子目录（Subdirectory）** | 被包含在另一目录内的目录 |
| **工作目录（Working Directory）** | 当前所在的目录 |
| **目录树（Directory Tree）** | 文件系统的逻辑视图，显示嵌套的目录结构 |

**路径（Path）：**  
文件或目录在文件系统中的位置的文字表示。

| 类型 | 说明 | 例子 |
|------|------|------|
| **绝对路径（Absolute Path）** | 从根目录开始，列出到目标的完整路径；与当前位置无关 | `C:\Users\John\Documents\file.txt` |
| **相对路径（Relative Path）** | 从当前工作目录开始；用 `..` 表示上一级 | `../DataScience/data.csv` |

**例题：**  
目录树：
```
C:\Users\John\Documents
├── Projects
│   ├── WebApp
│   │   ├── index.html
│   │   └── script.js
│   └── DataScience
│       ├── analysis.py
│       └── results.csv
└── Reports
    └── summary.pdf
```

- `results.csv` 的绝对路径：`C:\Users\John\Documents\Projects\DataScience\results.csv`
- 若当前目录是 `WebApp`，到 `analysis.py` 的相对路径：`..\DataScience\analysis.py`

### English

**Directory:**  
A named group of files. Directories can contain files and other directories (subdirectories).

**Directory tree terminology:**

| Term | Description |
|------|-------------|
| **Root Directory** | Top-level directory in file system (`C:\` or `/`) |
| **Parent Directory** | Directory that contains the current one |
| **Subdirectory** | Directory contained within another |
| **Working Directory** | Current directory you are in |
| **Directory Tree** | Logical view showing nested directory structure |

**Path:**  
Text designation of a file or directory's location in the file system.

| Type | Description | Example |
|------|-------------|---------|
| **Absolute Path** | Starts from root, lists full path to target; independent of current location | `C:\Users\John\Documents\file.txt` |
| **Relative Path** | Starts from current working directory; `..` means parent | `../DataScience/data.csv` |

**Example:**  
Directory tree:
```
C:\Users\John\Documents
├── Projects
│   ├── WebApp
│   │   ├── index.html
│   │   └── script.js
│   └── DataScience
│       ├── analysis.py
│       └── results.csv
└── Reports
    └── summary.pdf
```

- Absolute path for `results.csv`: `C:\Users\John\Documents\Projects\DataScience\results.csv`
- If current directory is `WebApp`, relative path to `analysis.py`: `..\DataScience\analysis.py`

---

## 十二、磁盘调度算法详解

### 中文

**磁盘管理：**  
操作系统的职责还包括管理磁盘（辅存）。多个进程会产生大量磁盘访问请求，OS 使用**磁盘调度**算法决定服务顺序。

---

### 12.1 先来先服务（FCFS）

**规则：** 按请求到达顺序服务，不考虑磁头当前位置。

**特点：**
- 简单公平；
- 缺点：磁头移动距离可能很大，效率低。

**例题：**  
请求序列：98, 183, 37, 122, 14, 124, 65, 67。磁头在 53。

服务顺序：98 → 183 → 37 → 122 → 14 → 124 → 65 → 67

总移动量：
- 53→98(45) + 98→183(85) + 183→37(146) + 37→122(85) + 122→14(108) + 14→124(110) + 124→65(59) + 65→67(2)
- = 45+85+146+85+108+110+59+2 = **640**

---

### 12.2 最短寻道时间优先（SSTF）

**规则：** 每次选择离当前磁头位置最近的请求。

**特点：**
- 减少磁头移动；
- 不保证最优，但通常比 FCFS 好；
- 可能导致远距离请求饥饿。

**例题（同上数据）：**  
磁头 53 → 最近的是 65(12) → 67(2) → 37(30) → 14(23) → 98(84) → 122(24) → 124(2) → 183(59)

服务顺序：65 → 67 → 37 → 14 → 98 → 122 → 124 → 183

总移动量：12+2+30+23+84+24+2+59 = **236**

---

### 12.3 扫描算法（SCAN / 电梯算法）

**规则：** 磁头沿一个方向移动（如向低柱面），服务途中遇到的所有请求；到达边界后反向，继续服务。像电梯一样来回扫描。

**需要知道：** 磁头初始移动方向。

**例题（同上数据，磁头向低柱面移动）：**  
磁头 53，向低（向 0）：先服务 53 以下的请求，从近到远：37 → 14；到达 0 后反向；再服务 53 以上的：65 → 67 → 98 → 122 → 124 → 183。

服务顺序：37 → 14 → 65 → 67 → 98 → 122 → 124 → 183

总移动量：53→37(16) + 37→14(23) + 14→0(14，到边界) + 0→65(65) + 65→67(2) + 67→98(31) + 98→122(24) + 122→124(2) + 124→183(59) = 16+23+14+65+2+31+24+2+59 = **236**（如果不经过 0 则不同）

---

### 12.4 三种磁盘调度对比

| 算法 | 特点 | 总移动量（课件例） |
|------|------|-------------------|
| FCFS | 按到达顺序，简单 | 640（最大） |
| SSTF | 每次选最近，较优 | 236 |
| SCAN | 电梯来回扫描，公平且稳定 | 236（或更少） |

### English

**Disk Management:**  
The OS also manages disk (secondary storage). Multiple processes generate disk requests; the OS uses **disk scheduling** algorithms to determine service order.

---

### 12.1 First-Come, First-Served (FCFS)

**Rule:** Service requests in arrival order, ignoring current head position.

**Characteristics:**
- Simple and fair;
- Drawback: Head movement can be very large; inefficient.

**Example:**  
Request sequence: 98, 183, 37, 122, 14, 124, 65, 67. Head at 53.

Service order: 98 → 183 → 37 → 122 → 14 → 124 → 65 → 67

Total head movement:
- 53→98(45) + 98→183(85) + 183→37(146) + 37→122(85) + 122→14(108) + 14→124(110) + 124→65(59) + 65→67(2)
- = 45+85+146+85+108+110+59+2 = **640**

---

### 12.2 Shortest Seek Time First (SSTF)

**Rule:** Always choose the request nearest to current head position.

**Characteristics:**
- Reduces head movement;
- Not guaranteed optimal, but usually better than FCFS;
- May cause starvation for distant requests.

**Example (same data):**  
Head 53 → nearest is 65(12) → 67(2) → 37(30) → 14(23) → 98(84) → 122(24) → 124(2) → 183(59)

Service order: 65 → 67 → 37 → 14 → 98 → 122 → 124 → 183

Total movement: 12+2+30+23+84+24+2+59 = **236**

---

### 12.3 SCAN (Elevator Algorithm)

**Rule:** Head moves in one direction (e.g., toward low cylinders), servicing all requests along the way; at the boundary, it reverses and continues. Like an elevator going up and down.

**Requires:** Knowing the initial direction of head movement.

**Example (same data, head moving toward lower cylinders):**  
Head 53 moving toward 0: first service requests below 53 from near to far: 37 → 14; at boundary reverse; then service above 53: 65 → 67 → 98 → 122 → 124 → 183.

Service order: 37 → 14 → 65 → 67 → 98 → 122 → 124 → 183

Total movement: depends on whether head goes all the way to 0 before reversing. Approximately 236.

---

### 12.4 Disk Scheduling Comparison

| Algorithm | Characteristics | Total Movement (textbook example) |
|-----------|-----------------|-----------------------------------|
| FCFS | Arrival order, simple | 640 (largest) |
| SSTF | Choose nearest, better | 236 |
| SCAN | Elevator scan, fair and stable | 236 or less |

---

## 十三、课堂练习精选题解

### 中文

**磁盘调度练习：**  
请求：40, 12, 22, 66, 67, 33, 80。磁头在 50。

**FCFS：** 40 → 12 → 22 → 66 → 67 → 33 → 80  
移动量：10+28+10+44+1+34+47 = **174**

**SSTF：** 50 → 40(10) → 33(7) → 22(11) → 12(10) → 66(54) → 67(1) → 80(13)  
顺序：40 → 33 → 22 → 12 → 66 → 67 → 80  
移动量：10+7+11+10+54+1+13 = **106**

**SCAN（向高柱面）：** 50 → 66(16) → 67(1) → 80(13) → 40(40) → 33(7) → 22(11) → 12(10)  
顺序：66 → 67 → 80 → 40 → 33 → 22 → 12  
移动量：16+1+13+40+7+11+10 = **98**

**结论：** SCAN 最小（98），SSTF 次之（106），FCFS 最大（174）。

### English

**Disk scheduling practice:**  
Requests: 40, 12, 22, 66, 67, 33, 80. Head at 50.

**FCFS:** 40 → 12 → 22 → 66 → 67 → 33 → 80  
Movement: 10+28+10+44+1+34+47 = **174**

**SSTF:** 50 → 40(10) → 33(7) → 22(11) → 12(10) → 66(54) → 67(1) → 80(13)  
Order: 40 → 33 → 22 → 12 → 66 → 67 → 80  
Movement: 10+7+11+10+54+1+13 = **106**

**SCAN (toward higher cylinders):** 50 → 66(16) → 67(1) → 80(13) → 40(40) → 33(7) → 22(11) → 12(10)  
Order: 66 → 67 → 80 → 40 → 33 → 22 → 12  
Movement: 16+1+13+40+7+11+10 = **98**

**Conclusion:** SCAN is smallest (98), SSTF next (106), FCFS largest (174).

---

# 📌 复习要点总结

## 中文

**Chapter 10 必记：**
1. 逻辑地址 vs 物理地址；地址转换公式。
2. 三种内存管理：单连续、分区（First/Best/Worst fit）、分页（页号=DIV, 偏移=MOD）。
3. Base/Bounds 寄存器的作用和越界检查。
4. 分页相关概念：帧、页、页表、按需分页、虚拟内存、抖动。
5. PCB 和上下文切换。
6. 三种 CPU 调度算法及其特点（抢占/非抢占）。
7. 会计算平均周转时间。

**Chapter 11 必记：**
1. 文本文件 vs 二进制文件；文件扩展名。
2. 顺序访问 vs 直接访问的适用场景。
3. Unix 文件权限（rwx, owner/group/others）。
4. 目录树术语；绝对路径 vs 相对路径。
5. 三种磁盘调度算法及服务顺序。
6. 会计算总磁头移动量。

## English

**Chapter 10 must-know:**
1. Logical vs physical address; translation formula.
2. Three MM techniques: single contiguous, partition (First/Best/Worst fit), paged (page=DIV, offset=MOD).
3. Base/Bounds registers and bounds checking.
4. Paging concepts: frame, page, page table, demand paging, virtual memory, thrashing.
5. PCB and context switch.
6. Three CPU scheduling algorithms and characteristics (preemptive/nonpreemptive).
7. Calculate average turnaround time.

**Chapter 11 must-know:**
1. Text vs binary files; file extensions.
2. Sequential vs direct access use cases.
3. Unix file permissions (rwx, owner/group/others).
4. Directory tree terminology; absolute vs relative paths.
5. Three disk scheduling algorithms and service order.
6. Calculate total head movement.

---

**📌 学习建议：** 本笔记较长，建议分两次读：先读 Ch10（内存+调度），再读 Ch11（文件+磁盘）。每部分读完后做对应的课堂活动题自检。
