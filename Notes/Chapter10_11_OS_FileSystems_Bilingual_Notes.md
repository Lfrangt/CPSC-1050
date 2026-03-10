# 📖 Chapter 10 & 11 合并笔记 | Operating Systems & File Systems

**说明：** 老师将 Ch10（操作系统）与 Ch11（文件系统与目录）合并讲授，本笔记覆盖两周内容。  
**Note:** Ch10 (OS) and Ch11 (File Systems) were taught together; this note covers both.

---

# Part 1: Chapter 10 — Operating Systems | 操作系统

## 📖 1. 计算机系统结构与软件分类

**中文：**
- 计算机系统可分为四大组件：硬件、操作系统、应用软件、用户。
- **应用软件 (Application software)**：为解决实际问题而编写的软件。
- **系统软件 (System software)**：在基础层面管理计算机系统的软件。
- **操作系统 (Operating system)**：系统软件，负责管理内存与 I/O 等资源、提供人机交互界面、并让应用程序能使用这些资源。

**English:**  
Computer system: hardware, OS, application software, users. **Application software** addresses specific needs. **System software** manages the system at a fundamental level. **Operating system** manages resources (memory, I/O), provides user interface, and lets applications use system resources.

---

## 📖 2. 操作系统的角色 (Roles of an Operating System)

**关键概念 / Key Concepts:**

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Multiprogramming | 多道程序设计 | 让多个竞争 CPU 的程序同时驻留主存以便执行 |
| Memory management | 内存管理 | 跟踪哪些程序在内存中以及它们的位置 |
| Process | 进程 | 正在执行的程序 (a program in execution) |
| Process management | 进程管理 | 跟踪进程及其各中间状态 |
| CPU scheduling | CPU 调度 | 决定任一时刻由哪个进程占用 CPU |

**中文：**  
多道程序设计把多个程序同时放在主存；内存管理记录程序在内存中的位置；进程是“运行中的程序”；进程管理跟踪每个进程的状态；CPU 调度决定当前该运行哪个进程。

**English:**  
Multiprogramming keeps multiple programs in main memory; memory management tracks where programs reside; a process is a program in execution; process management tracks process states; CPU scheduling decides which process runs.

---

## 📖 3. 内存管理 — 逻辑地址与物理地址

**中文：**
- **逻辑地址 (Logical address)**：相对于“程序自身”的存储引用，不是主存真实位置。
- **物理地址 (Physical address)**：主存中的实际地址。
- **地址转换 (Address translation)**：把虚拟/逻辑地址转换为物理地址的过程。
- 若程序从地址 A 开始加载，逻辑地址 L 对应的物理地址 = **A + L**（单连续内存时）。

**English:**  
**Logical (virtual) address**: reference relative to the program. **Physical address**: actual address in main memory. **Address translation**: converting virtual to physical. In single contiguous MM: physical = base A + logical L.

**Key Concepts:**
- **Logical address** - Reference relative to the program (not actual memory location)
- **Physical address** - Actual address in main memory
- **Base register** - Holds start address of current partition
- **Bounds register** - Holds length of current partition

---

## 📖 4. 内存管理技术 (Memory Management Techniques)

### 4.1 Single Contiguous 单连续内存管理

**中文：** 内存里只有两类程序：操作系统 + 一个应用程序。物理地址 = 程序起始地址 A + 逻辑地址 L。

**English:** Only OS and one application in memory. Physical address = A + L.

---

### 4.2 Partition 分区内存管理

**中文：**
- 内存被划分为多个分区，可同时存放多个程序。
- **固定分区 (Fixed partitions)**：主存预先分成固定数量的分区。
- **动态分区 (Dynamic partitions)**：按需创建分区以容纳等待加载的程序。
- **分区选择算法：**
  - **First fit**：分配到第一个足够大的分区。
  - **Best fit**：分配到足够大的**最小**分区。
  - **Worst fit**：分配到足够大的**最大**分区。

**English:** Partitions: fixed (predetermined) or dynamic (created as needed). **First fit** = first big enough; **Best fit** = smallest big enough; **Worst fit** = largest big enough.

---

### 4.3 Paged Memory 分页内存管理

**关键概念 / Key Concepts:**

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Frame | 帧 | 主存中固定大小的块，用于存放一页 |
| Page | 页 | 进程被划分的固定大小块，存入某一 frame |
| Page table / PMT | 页表 | 将逻辑页号映射到物理帧号 |
| Demand paging | 按需分页 | 需要时才把页调入内存 |
| Page swap | 页交换 | 从辅存调入一页，常伴随把另一页写回辅存 |
| Virtual memory | 虚拟内存 | 程序大小不受物理内存限制的“错觉” |
| Thrashing | 抖动 | 频繁页交换导致的低效 |

**中文：**
- 逻辑地址 → 先算 **page number = 地址 DIV 页大小**，**offset = 地址 MOD 页大小**，即 \<page, offset\>。
- 再用页表 (PMT) 把页号换成帧号，得到物理地址。
- 例：2566，页大小 1024 → page = 2566 DIV 1024 = 2，offset = 2566 MOD 1024 = 518 → \<2, 518\>。

**English:** Logical address → \<page number, offset\> (page = address DIV page_size, offset = address MOD page_size). PMT maps page to frame. Virtual memory + demand paging allow programs larger than physical RAM; thrashing = too many page swaps.

---

## 📖 5. 进程管理 (Process Management)

**关键概念 / Key Concepts:**

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Process control block (PCB) | 进程控制块 | 存放进程信息：PC、寄存器、base/bounds 或页表、统计信息等 |
| Context switch | 上下文切换 | 换进程时：旧进程寄存器存回其 PCB，新进程从 PCB 装入寄存器 |

**中文：** 每个进程有一个 PCB。只有一套 CPU 寄存器，当前运行进程的值在寄存器里；切换时把当前寄存器存进其 PCB，再把要运行的进程的 PCB 装入寄存器。

**English:** One PCB per process. CPU holds current process's registers; on switch, save to PCB and load next process's PCB (context switch).

---

## 📖 6. CPU 调度 (CPU Scheduling)

**中文：**
- **非抢占式 (Nonpreemptive)**：当前进程主动让出 CPU。
- **抢占式 (Preemptive)**：OS 决定剥夺当前进程，把 CPU 给别的进程。
- **周转时间 (Turnaround time)**：从进程第一次进入就绪到最后一次离开运行的总时间。

**English:** Nonpreemptive = process gives up CPU voluntarily. Preemptive = OS preempts. Turnaround time = from first arrival in ready to last exit from running.

### 三种算法对比

| 算法 | 英文 | 特点 | 抢占? |
|------|------|------|-------|
| 先来先服务 | FCFS (First-Come, First-Served) | 按到达顺序上 CPU | Nonpreemptive |
| 最短作业优先 | SJN (Shortest Job Next) | 就绪队列中估计运行时间最短的先运行 | Nonpreemptive |
| 时间片轮转 | RR (Round Robin) | 每个进程运行一个 time slice（quantum），未完成则回就绪队尾 | Preemptive |

**Key Concepts:**
- **Time slice (quantum)** - 每个进程在被抢占前运行的一段时间 / Time each process runs before being preempted in RR.

---

# Part 2: Chapter 11 — File Systems and Directories | 文件系统与目录

## 📖 7. 文件与文件类型

**关键概念 / Key Concepts:**

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Text file | 文本文件 | 由 ASCII/Unicode 字符组成的文件 |
| Binary file | 二进制文件 | 以特定格式存储、需按位解释的文件 |
| File type | 文件类型 | 文件所包含的信息种类 |
| File extension | 文件扩展名 | 文件名中表示类型的部分，如 .doc, .jpg, .wav, .mp3 |

**中文：** 文件名常为“文件名.扩展名”。例如 Chapter.doc（文档）、Figure1.jpg（图像）、Interview.wav / MyFavorite.mp3（音频）。

**English:** File name = name + extension. Extensions indicate type (e.g. .doc, .jpg, .mp3).

---

## 📖 8. 文件访问与保护

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Sequential access | 顺序访问 | 按线性顺序访问；要读最后一条须先读前面所有 |
| Direct access | 直接访问 | 文件被分成编号的逻辑记录，可按记录号直接访问 |
| File protection | 文件保护 | 限制谁可以访问文件、用于何种目的（如 Unix 的 rwx 三类权限） |

---

## 📖 9. 目录树与路径 (Directory Trees & Paths)

**关键概念 / Key Concepts:**

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Directory tree | 目录树 | 文件系统的逻辑视图；嵌套目录结构 |
| Root directory | 根目录 | 最顶层的目录 |
| Parent directory | 父目录 | 包含当前目录的目录 |
| Subdirectory | 子目录 | 被包含在另一目录内的目录 |
| Working directory | 工作目录 | 当前所在目录 |
| Path | 路径 | 文件或子目录在文件系统中的文字位置 |
| Absolute path | 绝对路径 | 从根开始、包含所有子目录的路径 |
| Relative path | 相对路径 | 从当前工作目录开始的路径 |

**中文：**  
绝对路径例：`C:\Program Files\MS Office\WinWord.exe`。若当前目录是 `C:\My Documents\letters`，相对路径例：`cancelMag.doc`、`applications\calState.doc`。

**English:** Absolute path starts at root; relative path starts at current working directory.

---

## 📖 10. 磁盘调度 (Disk Scheduling)

**中文：**  
OS 的职责包括内存管理、CPU 调度、**磁盘（辅存）管理**。多个进程会产生大量磁盘访问请求，OS 用 **磁盘调度 (disk scheduling)** 决定先响应哪个请求。

**English:** OS manages memory, CPU, and disk. Disk scheduling determines which disk request to satisfy first.

### 三种磁盘调度算法

| 算法 | 英文 | 特点 |
|------|------|------|
| 先来先服务 | FCFS | 按请求到达顺序服务，不考虑磁头当前位置 |
| 最短寻道时间优先 | SSTF | 磁头移动到离当前位置**最近**的请求，减少寻道 |
| 扫描（电梯） | SCAN | 磁头沿一个方向连续移动（如向里或向外），经过的请求依次服务，像电梯 |

**中文：**
- **FCFS**：请求顺序即服务顺序。例：磁头在 53，请求顺序 98, 183, 37, 122, 14, 124, 65, 67 → 下一个去 98。
- **SSTF**：从当前磁头位置选距离最小的请求。不保证总移动量最小，但通常比 FCFS 好。
- **SCAN**：需约定磁头移动方向（如向低柱面/向主轴）。先服务当前方向上的请求，到头再反方向。

**English:** FCFS = service in arrival order. SSTF = serve nearest request to current head. SCAN = move in one direction (e.g. toward spindle), service as encountered, then reverse.

---

# 📋 术语速查表 (Terminology Quick Reference)

| 英文 (English) | 中文 (Chinese) |
|----------------|----------------|
| Operating system | 操作系统 |
| Logical address | 逻辑地址 |
| Physical address | 物理地址 |
| Base register | 基址寄存器 |
| Bounds register | 界限寄存器 |
| First fit / Best fit / Worst fit | 首次适应 / 最佳适应 / 最差适应 |
| Page, Frame, Page table (PMT) | 页，帧，页表 |
| Virtual memory, Thrashing | 虚拟内存，抖动 |
| Process, PCB, Context switch | 进程，进程控制块，上下文切换 |
| FCFS, SJN, Round Robin (RR) | 先来先服务，最短作业优先，时间片轮转 |
| Time slice (quantum) | 时间片 |
| Turnaround time | 周转时间 |
| Text file, Binary file, File extension | 文本文件，二进制文件，文件扩展名 |
| Sequential access, Direct access | 顺序访问，直接访问 |
| Absolute path, Relative path | 绝对路径，相对路径 |
| Root directory, Working directory | 根目录，工作目录 |
| Disk scheduling, FCFS, SSTF, SCAN | 磁盘调度，先来先服务，最短寻道优先，扫描 |

---

# 📝 课堂活动要点 (In-Class Activity Takeaways)

**Ch10**
- 单连续：程序加载在 30215，逻辑地址 9223 → 物理 = 30215 + 9223 = 39438。
- 固定分区：base=42993, bounds=2031 → 逻辑 104 → 物理 42993+104=43097；逻辑 3041 > 2031 → 越界 (out of bounds)。
- First/Best/Worst fit：新作业 52 块时，在 60、52、100 三个空分区中选哪个（First 选第一个≥52，Best 选最小≥52 即 52，Worst 选最大≥52 即 100）。
- CPU 调度：给定 burst time，会算 FCFS/SJN/RR 的调度顺序与平均周转时间。

**Ch11**
- 路径：根据目录树写出某文件的绝对路径（从根写起）。
- 磁盘调度：给定柱面请求序列和磁头起始位置（及 SCAN 的移动方向），写出 FCFS、SSTF、SCAN 的服务顺序。  
  例：请求 40, 12, 22, 66, 67, 33, 80，磁头在 50，向高柱面 SCAN → 66, 67, 80, 40, 33, 22, 12。

---

# 📌 学习建议 (Study Tips)

1. **Ch10** 重点：逻辑/物理地址换算（单连续、分区时的 base+bounds）、分页的 page/offset 与页表、FCFS/SJN/RR 谁抢占谁非抢占、会算简单周转时间。
2. **Ch11** 重点：绝对路径 vs 相对路径、目录树名词、三种磁盘调度 FCFS/SSTF/SCAN 的服务顺序。
3. Quiz 可能考：术语对应、小计算（地址、分区选择、调度顺序）、选择题形式的算法比较。
4. 需要练题可以说「生成 Ch10 Ch11 的 quiz」或「出几道磁盘调度/路径题」。

---

# 🔢 复习自测 (Quick Self-Check) — 选择题

**Q1.** Which memory management allows only OS + one application in memory?  
哪种内存管理方式下内存里只有操作系统和一个应用程序？  
**A)** Partition **B)** Single contiguous **C)** Paged **D)** Virtual  
**Answer / 答案:** B

**Q2.** In paged memory, logical address 2566 with page size 1024 gives page number ____ and offset ____.  
分页系统中页大小 1024，逻辑地址 2566 的页号____、偏移____。  
**A)** 2, 518 **B)** 518, 2 **C)** 3, 514 **D)** 2566, 0  
**Answer / 答案:** A（page=2566/1024=2, offset=2566%1024=518）

**Q3.** Which CPU scheduling algorithm is preemptive? 哪种 CPU 调度算法是抢占式的？  
**A)** FCFS **B)** SJN **C)** Round Robin **D)** Both A and B  
**Answer / 答案:** C

**Q4.** A path that starts at the root and lists every subdirectory is a(n) ____.  
从根开始并列出每一级子目录的路径是____。  
**A)** relative path **B)** absolute path **C)** working directory **D)** file extension  
**Answer / 答案:** B

**Q5.** SSTF in disk scheduling chooses the request ____.  
磁盘调度中 SSTF 选择____的请求。  
**A)** that arrived first **B)** nearest to current head **C)** with largest cylinder **D)** in one direction only  
**Answer / 答案:** B
