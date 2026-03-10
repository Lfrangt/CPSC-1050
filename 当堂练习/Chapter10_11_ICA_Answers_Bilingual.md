# 📋 CPSC 1050 Ch10 OS & Ch11 FS — 课堂活动参考答案

**说明：** 以下为 Ch10（操作系统）与 Ch11（文件系统）课堂活动题的参考答案。每道题先给**完整中文答案**，再给**完整英文答案**，便于分别阅读与复习。仅供自检，交作业请独立完成。

**Note:** Reference answers for in-class activity (use for self-check only). Each question has a **full Chinese section** followed by a **full English section**.

---

## 第 1 题 — 单连续内存 | Question 1 — Contiguous Memory

**题目（中文）：** 在单连续内存管理系统中，程序从物理地址 **30,215** 开始加载。求逻辑地址 **9,223** 对应的物理地址。

**题目（English）：** In a single contiguous memory management system, a program is loaded at physical address **30,215**. Compute the physical address for logical address **9,223**.

---

### 中文答案

物理地址 = 基地址 + 逻辑地址 = 30,215 + 9,223 = **39,438**。

在单连续内存管理下，整个内存只有操作系统和一个应用程序。程序内部使用的地址是相对于程序起始位置的"逻辑地址"，要得到真实内存位置，必须加上程序在主存中的起始地址（基址），得到的就是物理地址。

---

### English Answer

Physical address = base + logical = 30,215 + 9,223 = **39,438**.

In single contiguous memory management, only the OS and one application reside in memory. Addresses inside the program are logical (relative to program start). The OS adds the base address to the logical address to obtain the physical address.

---

## 第 2 题 — 固定分区 | Question 2 — Fixed Partitioning

**题目（中文）：** 固定分区当前为：OS | P1 | 空(60) | P2 | P3 | 空(52) | 空(100)。新作业需要 **52 块**。分别用 First fit、Best fit、Worst fit 说明选哪个分区，并画出分配后的内存示意图。

**题目（English）：** Memory has fixed partitions: OS | P1 | Free(60) | P2 | P3 | Free(52) | Free(100). A new job needs **52 blocks**. Show which partition is chosen for First fit, Best fit, and Worst fit, and draw memory after allocation.

---

### 中文答案

| 策略 | 选中的分区 | 内部碎片 |
|------|-----------|---------|
| First fit | 第一个够大的空区：**60 块** | 60 − 52 = 8 块 |
| Best fit | 最小够用的空区：**52 块** | 52 − 52 = 0 块 |
| Worst fit | 最大的空区：**100 块** | 100 − 52 = 48 块 |

分配后内存示意：

- **First Fit：** \| OS \| P1 \| 新作业(52) \| 空(8) \| P2 \| P3 \| 空(52) \| 空(100) \|
- **Best Fit：** \| OS \| P1 \| 空(60) \| P2 \| P3 \| 新作业(52) \| 空(100) \|
- **Worst Fit：** \| OS \| P1 \| 空(60) \| P2 \| P3 \| 空(52) \| 新作业(52) \| 空(48) \|

---

### English Answer

| Strategy | Partition chosen | Internal fragmentation |
|----------|-----------------|----------------------|
| First fit | First partition large enough: **60 blocks** | 60 − 52 = 8 blocks |
| Best fit | Smallest partition that fits: **52 blocks** | 52 − 52 = 0 blocks |
| Worst fit | Largest partition: **100 blocks** | 100 − 52 = 48 blocks |

Memory after allocation:

- **First Fit:** \| OS \| P1 \| New job(52) \| Free(8) \| P2 \| P3 \| Free(52) \| Free(100) \|
- **Best Fit:** \| OS \| P1 \| Free(60) \| P2 \| P3 \| New job(52) \| Free(100) \|
- **Worst Fit:** \| OS \| P1 \| Free(60) \| P2 \| P3 \| Free(52) \| New job(52) \| Free(48) \|

---

## 第 3 题 — 分页 | Question 3 — Paging

**题目（中文）：** 逻辑地址 **2,566**，页大小 **1,024**。求页号和偏移量。

**题目（English）：** Logical address **2,566**, page size **1,024**. Compute page number and offset.

---

### 中文答案

- 页号 = 逻辑地址 ÷ 页大小（整除）= 2,566 ÷ 1,024 = **2**
- 偏移量 = 逻辑地址 mod 页大小 = 2,566 mod 1,024 = **518**

逻辑地址 2,566 对应：页号 **2**，偏移 **518**，记作 ⟨2, 518⟩。

公式：页号 = 地址 DIV 页大小；偏移 = 地址 MOD 页大小。

---

### English Answer

- Page number = logical address DIV page size = 2,566 ÷ 1,024 = **2** (integer division)
- Offset = logical address MOD page size = 2,566 mod 1,024 = **518**

Logical address 2,566 maps to page **2**, offset **518**, written as ⟨2, 518⟩.

Formulas: page number = address DIV page_size; offset = address MOD page_size.

---

## 第 4 题 — 进程调度 | Question 4 — Process Scheduling

**题目（中文）：** 所有进程在时间 0 到达。P1=8, P2=6, P3=1, P4=9, P5=3。分别用 FCFS、SJN、Round Robin（quantum=2）计算平均周转时间。

**题目（English）：** All processes arrive at time 0. P1=8, P2=6, P3=1, P4=9, P5=3. Compute average turnaround time for FCFS, SJN, and Round Robin (quantum=2).

---

### 中文答案

**a) FCFS 先来先服务**（按 P1→P2→P3→P4→P5 顺序）

| 进程 | 完成时间 | 周转时间 |
|------|---------|---------|
| P1 | 8 | 8 |
| P2 | 14 | 14 |
| P3 | 15 | 15 |
| P4 | 24 | 24 |
| P5 | 27 | 27 |

平均周转时间 = (8 + 14 + 15 + 24 + 27) ÷ 5 = **17.6**

**b) SJN 最短作业优先**（按执行时间从短到长：P3→P5→P2→P1→P4）

| 进程 | 完成时间 | 周转时间 |
|------|---------|---------|
| P3 | 1 | 1 |
| P5 | 4 | 4 |
| P2 | 10 | 10 |
| P1 | 18 | 18 |
| P4 | 27 | 27 |

平均周转时间 = (1 + 4 + 10 + 18 + 27) ÷ 5 = **12.0**

**c) Round Robin 时间片轮转（quantum = 2）**

甘特图演变：

| 时间段 | 运行 | 各进程剩余 |
|--------|------|-----------|
| 0–2 | P1 | P1:6, P2:6, P3:1, P4:9, P5:3 |
| 2–4 | P2 | P1:6, P2:4, P3:1, P4:9, P5:3 |
| 4–5 | P3 | P3 完成 ✓ |
| 5–7 | P4 | P4:7 |
| 7–9 | P5 | P5:1 |
| 9–11 | P1 | P1:4 |
| 11–13 | P2 | P2:2 |
| 13–15 | P4 | P4:5 |
| 15–16 | P5 | P5 完成 ✓ |
| 16–18 | P1 | P1:2 |
| 18–20 | P2 | P2 完成 ✓ |
| 20–22 | P4 | P4:3 |
| 22–24 | P1 | P1 完成 ✓ |
| 24–26 | P4 | P4:1 |
| 26–27 | P4 | P4 完成 ✓ |

| 进程 | 完成时间 | 周转时间 |
|------|---------|---------|
| P1 | 24 | 24 |
| P2 | 20 | 20 |
| P3 | 5 | 5 |
| P4 | 27 | 27 |
| P5 | 16 | 16 |

平均周转时间 = (24 + 20 + 5 + 27 + 16) ÷ 5 = **18.4**

---

### English Answer

**a) FCFS** (order: P1→P2→P3→P4→P5)

| Process | Finish time | Turnaround |
|---------|------------|------------|
| P1 | 8 | 8 |
| P2 | 14 | 14 |
| P3 | 15 | 15 |
| P4 | 24 | 24 |
| P5 | 27 | 27 |

Average turnaround = (8 + 14 + 15 + 24 + 27) / 5 = **17.6**

**b) SJN** (sorted by burst: P3→P5→P2→P1→P4)

| Process | Finish time | Turnaround |
|---------|------------|------------|
| P3 | 1 | 1 |
| P5 | 4 | 4 |
| P2 | 10 | 10 |
| P1 | 18 | 18 |
| P4 | 27 | 27 |

Average turnaround = (1 + 4 + 10 + 18 + 27) / 5 = **12.0**

**c) Round Robin (quantum = 2)**

Gantt chart evolution:

| Time | Running | Remaining |
|------|---------|-----------|
| 0–2 | P1 | P1:6, P2:6, P3:1, P4:9, P5:3 |
| 2–4 | P2 | P1:6, P2:4, P3:1, P4:9, P5:3 |
| 4–5 | P3 | P3 done ✓ |
| 5–7 | P4 | P4:7 |
| 7–9 | P5 | P5:1 |
| 9–11 | P1 | P1:4 |
| 11–13 | P2 | P2:2 |
| 13–15 | P4 | P4:5 |
| 15–16 | P5 | P5 done ✓ |
| 16–18 | P1 | P1:2 |
| 18–20 | P2 | P2 done ✓ |
| 20–22 | P4 | P4:3 |
| 22–24 | P1 | P1 done ✓ |
| 24–26 | P4 | P4:1 |
| 26–27 | P4 | P4 done ✓ |

| Process | Finish time | Turnaround |
|---------|------------|------------|
| P1 | 24 | 24 |
| P2 | 20 | 20 |
| P3 | 5 | 5 |
| P4 | 27 | 27 |
| P5 | 16 | 16 |

Average turnaround = (24 + 20 + 5 + 27 + 16) / 5 = **18.4**

---

## 第 5 题 — 抢占 vs 非抢占 | Question 5 — Preemptive vs Non-preemptive

**题目（中文）：** FCFS、SJN、Round Robin 分别是抢占式还是非抢占式？解释原因。

**题目（English）：** For FCFS, SJN, and Round Robin — are they preemptive or non-preemptive? Explain why.

---

### 中文答案

- **FCFS — 非抢占式。** 进程一旦获得 CPU 就一直运行到完成，不会被其他进程打断。按到达顺序依次执行。
- **SJN — 非抢占式（标准版本）。** 选择当前等待队列中执行时间最短的进程运行，但一旦开始就不打断。（注意：抢占式版本叫 SRTF/SRT，但本题讨论的是标准 SJN。）
- **Round Robin — 抢占式。** 每个进程最多运行一个时间片（quantum），时间片用完后被强制切换到队尾，不管是否执行完毕。这就是抢占。

---

### English Answer

- **FCFS — Non-preemptive.** Once a process starts executing, it runs to completion without interruption. Processes are served in arrival order.
- **SJN — Non-preemptive (standard version).** The shortest job is selected next, but once it starts, it is not interrupted. (Note: the preemptive variant is called SRTF/SRT, but standard SJN is non-preemptive.)
- **Round Robin — Preemptive.** Each process runs for at most one time quantum. When the quantum expires, the process is forcibly moved to the back of the ready queue, regardless of whether it has finished. This forced switching is preemption.

---

## 第 6 题 — 分页地址转换过程 | Question 6 — Paged Memory Translation

**题目（中文）：** 解释在分页内存系统中，逻辑地址如何转换为物理地址。

**题目（English）：** Explain how a logical address is translated to a physical address in a paged memory system.

---

### 中文答案

1. CPU 生成一个逻辑地址，将其拆分为两部分：**页号（page number）** 和 **偏移量（offset）**。
2. 用页号去查 **页表（page table）**，找到该页在物理内存中对应的 **帧号（frame number）**。
3. 物理地址 = 帧号 × 页大小 + 偏移量。
4. 如果页表中该页的有效位（valid bit）为 0，说明该页不在内存中，触发 **缺页中断（page fault）**，操作系统从磁盘将该页加载到内存中，更新页表后重试。

这个机制让每个进程拥有自己的逻辑地址空间，物理内存可以不连续分配，提高了内存利用率。

---

### English Answer

1. The CPU generates a logical address and splits it into two parts: **page number** and **offset**.
2. The page number indexes into the **page table** to find the corresponding **frame number** in physical memory.
3. Physical address = frame number × page size + offset.
4. If the valid bit for that page is 0, the page is not in memory. A **page fault** occurs: the OS loads the page from disk into a free frame, updates the page table, and retries the instruction.

This mechanism gives each process its own logical address space while allowing non-contiguous physical allocation, improving memory utilization.

---

## 第 7 题 — 分时与多道程序 | Question 7 — Timesharing & Multiprogramming

**题目（中文）：** 分时系统和多道程序设计分别如何提高系统效率？

**题目（English）：** How do timesharing and multiprogramming improve system efficiency?

---

### 中文答案

**多道程序设计（Multiprogramming）：** 多个进程同时驻留在内存中。当一个进程因为等待 I/O（如读磁盘、等网络）而阻塞时，CPU 立刻切换到另一个就绪进程，避免 CPU 空转。核心目标是 **最大化 CPU 利用率**。

**分时系统（Timesharing）：** 每个进程被分配一个很小的时间片（quantum），轮流使用 CPU。即使进程没有阻塞，时间片用完也强制切换。这样多个用户/进程感觉自己在"同时"使用计算机。核心目标是 **快速响应时间和交互体验**。

**权衡：** 上下文切换（context switch）有开销 — 需要保存/恢复寄存器、更新页表等。进程越多、切换越频繁，开销越大。但总体上，throughput（吞吐量）和 responsiveness（响应能力）都显著提升。

---

### English Answer

**Multiprogramming:** Multiple processes are loaded into memory simultaneously. When one process blocks on I/O (disk read, network wait), the CPU immediately switches to another ready process, preventing CPU idle time. Core goal: **maximize CPU utilization**.

**Timesharing:** Each process receives a small time slice (quantum) and takes turns using the CPU. Even if a process is not blocked, it is preempted when its quantum expires. This gives multiple users/processes the illusion of simultaneous use. Core goal: **fast response time and interactivity**.

**Trade-off:** Context switching incurs overhead — saving/restoring registers, updating page tables, etc. More processes and more frequent switching means more overhead. However, overall throughput and responsiveness improve significantly.

---

## 第 8 题 — 文件访问方式 | Question 8 — File Access Methods

**题目（中文）：** (a) Log files 和 index files 各适合什么访问方式？(b) 给出现实中顺序访问和直接访问的例子。

**题目（English）：** (a) What access method suits log files vs index files? (b) Give real-world examples of sequential and direct access.

---

### 中文答案

**(a)**

- **日志文件（Log files）→ 顺序访问（Sequential access）。** 日志按时间顺序追加写入，读取时也是从头到尾顺序读。数据的自然结构就是线性的，顺序访问完美匹配。
- **索引文件（Index files）→ 直接访问（Direct access）。** 索引的目的是快速定位特定记录，需要跳转到任意位置读取，不需要从头扫描。

**(b) 现实例子：**

- **顺序访问：** 播放视频文件（从头到尾连续读取）、读取服务器日志（按行扫描）、播放音乐。
- **直接访问：** 数据库按主键查询某条记录、视频播放器拖动进度条跳到特定时间点、操作系统读取磁盘上某个特定扇区。

---

### English Answer

**(a)**

- **Log files → Sequential access.** Logs are appended chronologically and read from start to end. The linear nature of log data matches sequential access perfectly.
- **Index files → Direct access.** Indexes are designed for fast lookup of specific records, requiring jumps to arbitrary positions without scanning from the beginning.

**(b) Real-world examples:**

- **Sequential:** Streaming a video file (continuous start-to-end reading), reading server logs (line-by-line scan), playing music.
- **Direct:** Database query by primary key, video player seeking to a specific timestamp, OS reading a specific disk sector.

---

## 第 9 题 — 目录路径 | Question 9 — Directory Paths

**题目（中文）：** (a) 写出 results.csv 的绝对路径。(b) 若当前目录是 WebApp，写出到 analysis.py 的相对路径。(c) 解释绝对路径和相对路径的区别。

**题目（English）：** (a) Write the absolute path to results.csv. (b) If CWD is WebApp, write the relative path to analysis.py. (c) Explain the difference between absolute and relative paths.

---

### 中文答案

**(a)** 绝对路径：`C:\Users\John\Documents\Projects\DataScience\results.csv`

**(b)** 当前工作目录 = `C:\Users\John\Documents\Projects\WebApp`
相对路径：`..\DataScience\analysis.py`

`..` 表示返回上一级目录（到 Projects），然后进入 DataScience 文件夹。

**(c)** 区别：

- **绝对路径（Absolute path）：** 从根目录（如 `C:\`）开始的完整路径。无论当前在哪个目录，都能准确定位文件。
- **相对路径（Relative path）：** 相对于当前工作目录（CWD）的路径。路径的解析结果取决于当前所在位置，不同位置执行结果不同。

---

### English Answer

**(a)** Absolute path: `C:\Users\John\Documents\Projects\DataScience\results.csv`

**(b)** CWD = `C:\Users\John\Documents\Projects\WebApp`
Relative path: `..\DataScience\analysis.py`

`..` means go up one level (to Projects), then enter DataScience.

**(c)** Difference:

- **Absolute path:** The complete path starting from the root directory (e.g., `C:\`). It uniquely identifies a file regardless of the current directory.
- **Relative path:** A path relative to the current working directory (CWD). The resolved location depends on where you currently are; different CWDs produce different results.

---

## 第 10 题 — 磁盘调度 | Question 10 — Disk Scheduling

**题目（中文）：** 磁头起始位置 50，请求队列：40, 12, 22, 66, 67, 33, 80。分别用 FCFS、SSTF、SCAN 计算服务顺序和总磁头移动量。哪个算法移动量最少？

**题目（English）：** Head starts at 50. Request queue: 40, 12, 22, 66, 67, 33, 80. Compute service order and total head movement for FCFS, SSTF, and SCAN. Which has the least movement?

---

### 中文答案

**1. FCFS 先来先服务**

按请求到达顺序处理：50→40→12→22→66→67→33→80

移动量 = |50−40| + |40−12| + |12−22| + |22−66| + |66−67| + |67−33| + |33−80|
= 10 + 28 + 10 + 44 + 1 + 34 + 47 = **174**

**2. SSTF 最短寻道时间优先**

每次选离当前位置最近的请求：50→40→33→22→12→66→67→80

移动量 = 10 + 7 + 11 + 10 + 54 + 1 + 13 = **106**

**3. SCAN 电梯算法**

先向高磁道方向移动，到头后反向：50→66→67→80→40→33→22→12

移动量 = 16 + 1 + 13 + 40 + 7 + 11 + 10 = **98**

**结论：SCAN 的总磁头移动量最少（98），效率最高。**

---

### English Answer

**1. FCFS**

Process in arrival order: 50→40→12→22→66→67→33→80

Movement = |50−40| + |40−12| + |12−22| + |22−66| + |66−67| + |67−33| + |33−80|
= 10 + 28 + 10 + 44 + 1 + 34 + 47 = **174**

**2. SSTF (Shortest Seek Time First)**

Always go to nearest request: 50→40→33→22→12→66→67→80

Movement = 10 + 7 + 11 + 10 + 54 + 1 + 13 = **106**

**3. SCAN (Elevator Algorithm)**

Move toward higher tracks first, then reverse: 50→66→67→80→40→33→22→12

Movement = 16 + 1 + 13 + 40 + 7 + 11 + 10 = **98**

**Conclusion: SCAN has the lowest total head movement (98), making it the most efficient for this request set.**

---

## 第 11 题 — Unix 文件权限 | Question 11 — Unix File Permissions

**题目（中文）：** 给定权限表（report.txt: rw-/r--/---; script.sh: rwx/r-x/r--; data.db: rw-/---/---）。(a) 每个角色能执行什么操作？(b) 如何让所有人都能读取和执行 script.sh？(c) 为什么文件保护在多用户操作系统中至关重要？

**题目（English）：** Given the permission table (report.txt: rw-/r--/---; script.sh: rwx/r-x/r--; data.db: rw-/---/---). (a) What operations can each role perform? (b) How to allow everyone to read and execute script.sh? (c) Why is file protection critical in a multi-user OS?

---

### 中文答案

**(a) 各角色权限：**

**report.txt (rw- / r-- / ---)：**
- 所有者（Owner）：读 + 写
- 组（Group）：只读
- 其他人（Others）：无权限

**script.sh (rwx / r-x / r--)：**
- 所有者：读 + 写 + 执行
- 组：读 + 执行
- 其他人：只读

**data.db (rw- / --- / ---)：**
- 所有者：读 + 写
- 组：无权限
- 其他人：无权限

**(b) 让所有人都能读取和执行 script.sh：**

```bash
chmod 755 script.sh
```

或使用符号模式：`chmod a+rx script.sh`

这样设置后：所有者 = rwx(7)，组 = r-x(5)，其他人 = r-x(5)。当前其他人只有 r--，需要加上执行权限。如果只想加 others 的 x 位，也可以用 `chmod o+x script.sh`。

**(c) 为什么文件保护至关重要：**

在多用户操作系统中，多个用户共享相同的系统资源。没有文件保护：

1. **机密性受损** — 敏感数据（密码、个人文件、数据库）可能被未授权用户读取。
2. **完整性受损** — 任何用户都可能意外或恶意修改、删除其他用户的文件。
3. **系统稳定性受损** — 关键系统文件可能被破坏，导致整个操作系统崩溃。
4. **无法追责** — 没有权限控制就无法审计谁做了什么操作。

文件保护确保每个用户只能访问被授权的内容，在共享环境中维护安全性和系统完整性。

---

### English Answer

**(a) Permissions per role:**

**report.txt (rw- / r-- / ---):**
- Owner: read + write
- Group: read only
- Others: no access

**script.sh (rwx / r-x / r--):**
- Owner: read + write + execute
- Group: read + execute
- Others: read only

**data.db (rw- / --- / ---):**
- Owner: read + write
- Group: no access
- Others: no access

**(b) Allow everyone to read and execute script.sh:**

```bash
chmod 755 script.sh
```

Or symbolic: `chmod a+rx script.sh`

This sets: owner = rwx(7), group = r-x(5), others = r-x(5). Currently others only have r--, so execute permission must be added. Alternatively, `chmod o+x script.sh` adds just the missing execute bit for others.

**(c) Why file protection is critical:**

In a multi-user OS, multiple users share the same system resources. Without file protection:

1. **Confidentiality** — Sensitive data (passwords, personal files, databases) could be read by unauthorized users.
2. **Integrity** — Any user could modify or delete another user's files, whether accidentally or maliciously.
3. **System stability** — Critical system files could be corrupted, potentially crashing the entire OS.
4. **Accountability** — Without permission controls, there is no way to audit who performed what operations.

File protection ensures each user can only access what they are authorized to, maintaining security and system integrity in a shared environment.
