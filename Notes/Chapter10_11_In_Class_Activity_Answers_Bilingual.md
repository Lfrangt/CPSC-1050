# 📋 CPSC 1050 Ch10 OS & Ch11 FS — 课堂活动详细讲解

**说明：** 以下为课堂活动的详细讲解版答案，包含解题思路、步骤分解和图示。每道题先完整中文，再完整英文。仅供自检，交作业请独立完成。

---

# ═══════════════════════════════════════════════════
# 第 1 题 — 单连续内存
# Question 1 — Single Contiguous Memory
# ═══════════════════════════════════════════════════

**题目：** 程序从物理地址 **30,215** 开始加载。求逻辑地址 **9,223** 对应的物理地址。

---

## 中文详细讲解

### 背景知识：什么是逻辑地址和物理地址？

想象你写了一个程序，程序里说"把数据存到地址 100"。但这个"100"是程序自己的编号，不是内存的真实位置。

- **逻辑地址**：程序内部使用的地址，从 0 开始编号，相对于程序自己的起点。
- **物理地址**：内存条上的真实位置。

程序不知道自己被加载到内存的哪里，所以它只能用逻辑地址。操作系统负责把逻辑地址翻译成物理地址。

### 单连续内存的特点

在单连续内存管理下：
- 内存里只有两样东西：操作系统 + 一个应用程序
- 程序占用一整块连续的内存空间
- 转换公式非常简单

### 转换公式

```
物理地址 = 程序起始地址（基址） + 逻辑地址
```

### 解题步骤

```
已知：
  - 程序起始地址（基址）= 30,215
  - 逻辑地址 = 9,223

求：物理地址 = ？

计算：
  物理地址 = 30,215 + 9,223
           = 39,438
```

### 图示理解

```
内存布局：
┌─────────────────────┐ 地址 0
│     操作系统        │
├─────────────────────┤ 地址 30,215 ← 程序起始（基址）
│                     │
│     应用程序        │ ← 逻辑地址 9,223 在这里面
│                     │     实际位置 = 30,215 + 9,223 = 39,438
│                     │
├─────────────────────┤
│     空闲空间        │
└─────────────────────┘

程序内部视角：              实际内存视角：
┌───────────┐ 逻辑 0        ┌───────────┐ 物理 30,215
│           │              │           │
│  地址 9,223 ────────────→│  地址 39,438
│           │              │           │
└───────────┘              └───────────┘
```

### 答案

**物理地址 = 39,438**

---

## English Detailed Explanation

### Background: What are logical and physical addresses?

Imagine you write a program that says "store data at address 100." But this "100" is just the program's own numbering, not the actual memory location.

- **Logical address:** Address used inside the program, starting from 0, relative to the program's own starting point.
- **Physical address:** The actual location on the memory chip.

The program doesn't know where it's loaded in memory, so it uses logical addresses. The OS translates logical addresses to physical addresses.

### Single Contiguous Memory

In single contiguous memory management:
- Only two things in memory: OS + one application
- The program occupies one continuous block
- Conversion formula is very simple

### Conversion Formula

```
Physical address = Program starting address (base) + Logical address
```

### Solution Steps

```
Given:
  - Program starting address (base) = 30,215
  - Logical address = 9,223

Find: Physical address = ?

Calculation:
  Physical address = 30,215 + 9,223
                   = 39,438
```

### Answer

**Physical address = 39,438**

---

# ═══════════════════════════════════════════════════
# 第 2 题 — 固定分区：First / Best / Worst Fit
# Question 2 — Fixed Partition Selection
# ═══════════════════════════════════════════════════

**题目：** 内存分区为 OS | P1 | 空(60) | P2 | P3 | 空(52) | 空(100)。新作业需要 **52 块**。用三种算法选分区。

---

## 中文详细讲解

### 背景知识：三种分区选择算法

当有多个空闲分区都能装下新程序时，选哪个？三种策略：

| 算法 | 选择策略 | 记忆口诀 |
|------|----------|----------|
| **First Fit** | 选**第一个**够大的 | "先到先得" |
| **Best Fit** | 选**最小的**够大的 | "刚刚好" |
| **Worst Fit** | 选**最大的**够大的 | "大材小用" |

### 当前内存状态

```
┌────┬────┬─────────┬────┬────┬─────────┬──────────┐
│ OS │ P1 │ 空(60)  │ P2 │ P3 │ 空(52)  │ 空(100)  │
└────┴────┴─────────┴────┴────┴─────────┴──────────┘
              ↑                   ↑          ↑
          第1个空区           第2个空区   第3个空区
          60 块               52 块       100 块
```

新作业需要 **52 块**。

### 解题步骤

**第一步：列出所有空闲分区及大小**

| 空区编号 | 大小 | 能装下 52 块？ |
|----------|------|----------------|
| 1 | 60 块 | 能（60 ≥ 52）✓ |
| 2 | 52 块 | 能（52 ≥ 52）✓ |
| 3 | 100 块 | 能（100 ≥ 52）✓ |

三个都能装下！那怎么选？

**第二步：按三种算法分别选择**

**First Fit（首次适应）：**
- 从前往后扫描，遇到第一个能装下的就选它
- 第 1 个空区（60 块）≥ 52 → **选 60 块的分区**
- 分配后：60 - 52 = 8 块剩余

**Best Fit（最佳适应）：**
- 在所有能装下的分区中，选最小的
- 能装下的：60, 52, 100
- 最小的是 **52 块** → **选 52 块的分区**
- 分配后：52 - 52 = 0 块剩余（刚好用完）

**Worst Fit（最差适应）：**
- 在所有能装下的分区中，选最大的
- 能装下的：60, 52, 100
- 最大的是 **100 块** → **选 100 块的分区**
- 分配后：100 - 52 = 48 块剩余

### 分配后的内存图示

**First Fit：选 60 块分区**
```
┌────┬────┬──────────────────┬────┬────┬─────────┬──────────┐
│ OS │ P1 │ 新作业(52) │空8│ P2 │ P3 │ 空(52)  │ 空(100)  │
└────┴────┴──────────────────┴────┴────┴─────────┴──────────┘
              ↑ 这里被选中
```

**Best Fit：选 52 块分区**
```
┌────┬────┬─────────┬────┬────┬───────────┬──────────┐
│ OS │ P1 │ 空(60)  │ P2 │ P3 │ 新作业(52)│ 空(100)  │
└────┴────┴─────────┴────┴────┴───────────┴──────────┘
                                  ↑ 这里被选中（刚好用完）
```

**Worst Fit：选 100 块分区**
```
┌────┬────┬─────────┬────┬────┬─────────┬───────────────────┐
│ OS │ P1 │ 空(60)  │ P2 │ P3 │ 空(52)  │ 新作业(52) │空48│
└────┴────┴─────────┴────┴────┴─────────┴───────────────────┘
                                              ↑ 这里被选中
```

### 答案总结

| 算法 | 选中分区 | 剩余空间 |
|------|----------|----------|
| First Fit | 60 块（第1个空区） | 8 块 |
| Best Fit | 52 块（第2个空区） | 0 块 |
| Worst Fit | 100 块（第3个空区） | 48 块 |

---

## English Detailed Explanation

### Background: Three Partition Selection Algorithms

When multiple free partitions can fit a new program, which to choose?

| Algorithm | Selection Strategy | Memory Trick |
|-----------|-------------------|--------------|
| **First Fit** | Choose the **first** one large enough | "First come, first served" |
| **Best Fit** | Choose the **smallest** one large enough | "Just right" |
| **Worst Fit** | Choose the **largest** one large enough | "Overkill" |

### Current Memory State

```
┌────┬────┬─────────┬────┬────┬─────────┬──────────┐
│ OS │ P1 │Free(60) │ P2 │ P3 │Free(52) │Free(100) │
└────┴────┴─────────┴────┴────┴─────────┴──────────┘
              ↑                   ↑          ↑
          1st hole            2nd hole    3rd hole
          60 blocks           52 blocks   100 blocks
```

New job needs **52 blocks**.

### Solution

**Step 1: List all free partitions**

| Hole # | Size | Can fit 52? |
|--------|------|-------------|
| 1 | 60 | Yes ✓ |
| 2 | 52 | Yes ✓ |
| 3 | 100 | Yes ✓ |

All three can fit! How to choose?

**Step 2: Apply each algorithm**

- **First Fit:** First hole ≥ 52 → **60-block partition** → 8 blocks remain
- **Best Fit:** Smallest hole ≥ 52 → **52-block partition** → 0 blocks remain
- **Worst Fit:** Largest hole ≥ 52 → **100-block partition** → 48 blocks remain

---

# ═══════════════════════════════════════════════════
# 第 3 题 — 分页：页号与偏移
# Question 3 — Paged Memory: Page & Offset
# ═══════════════════════════════════════════════════

**题目：** 逻辑地址 **2,566**，页大小 **1,024**。求页号和偏移量。

---

## 中文详细讲解

### 背景知识：什么是分页？

分页就是把内存和程序都切成固定大小的小块：
- 内存被切成 **帧（Frame）**
- 程序被切成 **页（Page）**
- 每一页刚好能放进一帧

### 为什么要算页号和偏移？

逻辑地址 2,566 表示"程序中第 2,566 个字节的位置"。但分页系统需要知道：
- 这个地址在**第几页**？
- 在这一页的**第几个位置**（偏移）？

### 计算公式

```
页号 = 逻辑地址 ÷ 页大小    （取整数部分，DIV 运算）
偏移 = 逻辑地址 mod 页大小  （取余数，MOD 运算）
```

### 解题步骤

```
已知：
  - 逻辑地址 = 2,566
  - 页大小 = 1,024

第一步：算页号（整除）
  页号 = 2,566 ÷ 1,024
       = 2.505...
       = 2（只取整数部分）
  
  理解：2,566 字节里有几个完整的 1,024？
        1,024 × 2 = 2,048 ✓（不超过 2,566）
        1,024 × 3 = 3,072 ✗（超过 2,566 了）
        所以是第 2 页（页从 0 开始编号：第 0 页、第 1 页、第 2 页...）

第二步：算偏移（取余）
  偏移 = 2,566 mod 1,024
       = 2,566 - (2 × 1,024)
       = 2,566 - 2,048
       = 518
  
  理解：前 2 页用掉了 2,048 字节，还剩 518 字节，就是页内偏移。
```

### 图示理解

```
程序内存空间（总共 2,566+ 字节）：

地址 0 ─────────┬───────────────────┐
               │     第 0 页       │ 0 ~ 1,023
地址 1,024 ────┼───────────────────┤
               │     第 1 页       │ 1,024 ~ 2,047
地址 2,048 ────┼───────────────────┤
               │     第 2 页       │ 2,048 ~ 3,071
               │                   │
               │   地址 2,566 ←────┼── 在第 2 页内
               │   偏移 = 2,566    │   页内位置 = 2,566 - 2,048 = 518
               │         - 2,048   │
               │         = 518     │
               │                   │
               └───────────────────┘

所以：逻辑地址 2,566 = <页号 2, 偏移 518>
```

### 验算

页号 × 页大小 + 偏移 = 2 × 1,024 + 518 = 2,048 + 518 = 2,566 ✓

### 答案

- **页号 = 2**
- **偏移 = 518**
- 记作 **\<2, 518\>**

---

## English Detailed Explanation

### Background: What is Paging?

Paging divides memory and programs into fixed-size blocks:
- Memory is divided into **frames**
- Programs are divided into **pages**
- Each page fits exactly into one frame

### Why calculate page number and offset?

Logical address 2,566 means "the 2,566th byte in the program." The paging system needs to know:
- Which **page** is this address in?
- What **position within that page** (offset)?

### Formulas

```
Page number = Logical address ÷ Page size    (integer division, DIV)
Offset = Logical address mod Page size       (remainder, MOD)
```

### Solution Steps

```
Given:
  - Logical address = 2,566
  - Page size = 1,024

Step 1: Calculate page number (integer division)
  Page number = 2,566 ÷ 1,024 = 2 (integer part only)

Step 2: Calculate offset (remainder)
  Offset = 2,566 mod 1,024
         = 2,566 - (2 × 1,024)
         = 2,566 - 2,048
         = 518
```

### Verification

Page number × Page size + Offset = 2 × 1,024 + 518 = 2,566 ✓

### Answer

- **Page number = 2**
- **Offset = 518**
- Written as **\<2, 518\>**

---

# ═══════════════════════════════════════════════════
# 第 4 题 — CPU 调度：平均周转时间
# Question 4 — CPU Scheduling: Average Turnaround Time
# ═══════════════════════════════════════════════════

**题目：** P1=8, P2=6, P3=1, P4=9, P5=3（单位 ms），全部 time 0 到达。求 FCFS、SJN、RR(quantum=2) 的平均周转时间。

---

## 中文详细讲解

### 背景知识

**周转时间 = 完成时间 - 到达时间**

因为所有进程都在 time 0 到达，所以：周转时间 = 完成时间

**平均周转时间 = 所有进程周转时间之和 ÷ 进程数**

---

### (a) FCFS — 先来先服务

**规则：** 谁先到就先运行谁，运行完了再运行下一个。

**执行过程：**

```
时间轴：
0        8       14  15         24         27
├────────┼────────┼──┼──────────┼──────────┤
│   P1   │   P2   │P3│    P4    │    P5    │
│  (8ms) │  (6ms) │1 │   (9ms)  │   (3ms)  │
└────────┴────────┴──┴──────────┴──────────┘

详细过程：
- P1 先到，运行 8ms，在 time=8 完成
- P2 接着，运行 6ms，在 time=8+6=14 完成
- P3 接着，运行 1ms，在 time=14+1=15 完成
- P4 接着，运行 9ms，在 time=15+9=24 完成
- P5 最后，运行 3ms，在 time=24+3=27 完成
```

**计算表格：**

| 进程 | 运行时间 | 开始时间 | 完成时间 | 周转时间 |
|------|----------|----------|----------|----------|
| P1 | 8 | 0 | 0+8=8 | 8 |
| P2 | 6 | 8 | 8+6=14 | 14 |
| P3 | 1 | 14 | 14+1=15 | 15 |
| P4 | 9 | 15 | 15+9=24 | 24 |
| P5 | 3 | 24 | 24+3=27 | 27 |

**平均周转时间 = (8+14+15+24+27) ÷ 5 = 88 ÷ 5 = 17.6 ms**

---

### (b) SJN — 最短作业优先

**规则：** 每次选运行时间最短的进程运行。

**第一步：按运行时间排序**

| 进程 | 运行时间 | 排序 |
|------|----------|------|
| P3 | 1 | 第 1（最短）|
| P5 | 3 | 第 2 |
| P2 | 6 | 第 3 |
| P1 | 8 | 第 4 |
| P4 | 9 | 第 5（最长）|

**执行过程：**

```
时间轴：
0  1    4         10               18                  27
├──┼────┼─────────┼────────────────┼───────────────────┤
│P3│ P5 │   P2    │       P1       │        P4         │
│1 │ 3  │   6     │       8        │        9          │
└──┴────┴─────────┴────────────────┴───────────────────┘
```

**计算表格：**

| 进程 | 运行时间 | 开始时间 | 完成时间 | 周转时间 |
|------|----------|----------|----------|----------|
| P3 | 1 | 0 | 1 | 1 |
| P5 | 3 | 1 | 4 | 4 |
| P2 | 6 | 4 | 10 | 10 |
| P1 | 8 | 10 | 18 | 18 |
| P4 | 9 | 18 | 27 | 27 |

**平均周转时间 = (1+4+10+18+27) ÷ 5 = 60 ÷ 5 = 12 ms**

---

### (c) RR — 时间片轮转（quantum = 2 ms）

**规则：** 
- 每个进程最多运行 2 ms
- 没运行完就回到队尾排队
- 轮流执行直到全部完成

**这是最复杂的一种，我们一步一步模拟：**

**初始状态：**
- 就绪队列：[P1, P2, P3, P4, P5]
- 各进程剩余时间：P1=8, P2=6, P3=1, P4=9, P5=3

**逐步执行：**

| 时间段 | 运行进程 | 运行时长 | 剩余时间 | 完成？ | 队列变化 |
|--------|----------|----------|----------|--------|----------|
| 0-2 | P1 | 2 | 8→6 | 否 | P1 回队尾 → [P2,P3,P4,P5,P1] |
| 2-4 | P2 | 2 | 6→4 | 否 | P2 回队尾 → [P3,P4,P5,P1,P2] |
| 4-5 | P3 | 1 | 1→0 | **完成!** | P3 出队 → [P4,P5,P1,P2] |
| 5-7 | P4 | 2 | 9→7 | 否 | P4 回队尾 → [P5,P1,P2,P4] |
| 7-9 | P5 | 2 | 3→1 | 否 | P5 回队尾 → [P1,P2,P4,P5] |
| 9-11 | P1 | 2 | 6→4 | 否 | P1 回队尾 → [P2,P4,P5,P1] |
| 11-13 | P2 | 2 | 4→2 | 否 | P2 回队尾 → [P4,P5,P1,P2] |
| 13-15 | P4 | 2 | 7→5 | 否 | P4 回队尾 → [P5,P1,P2,P4] |
| 15-16 | P5 | 1 | 1→0 | **完成!** | P5 出队 → [P1,P2,P4] |
| 16-18 | P1 | 2 | 4→2 | 否 | P1 回队尾 → [P2,P4,P1] |
| 18-20 | P2 | 2 | 2→0 | **完成!** | P2 出队 → [P4,P1] |
| 20-22 | P4 | 2 | 5→3 | 否 | P4 回队尾 → [P1,P4] |
| 22-24 | P1 | 2 | 2→0 | **完成!** | P1 出队 → [P4] |
| 24-26 | P4 | 2 | 3→1 | 否 | P4 继续 |
| 26-27 | P4 | 1 | 1→0 | **完成!** | 全部完成 |

**时间轴图示：**

```
0   2   4 5   7   9  11  13  15 16  18  20  22  24  26 27
├───┼───┼─┼───┼───┼───┼───┼───┼──┼───┼───┼───┼───┼───┼─┤
│P1 │P2 │3│P4 │P5 │P1 │P2 │P4 │P5│P1 │P2 │P4 │P1 │P4 │4│
│ 2 │ 2 │1│ 2 │ 2 │ 2 │ 2 │ 2 │1 │ 2 │ 2 │ 2 │ 2 │ 2 │1│
└───┴───┴─┴───┴───┴───┴───┴───┴──┴───┴───┴───┴───┴───┴─┘
        ↑               ↑       ↑       ↑       ↑      ↑
       P3完成          P5完成  P2完成  P1完成  P4完成
       (5ms)          (16ms)  (20ms)  (24ms)  (27ms)
```

**结果汇总：**

| 进程 | 完成时间 | 周转时间 |
|------|----------|----------|
| P1 | 24 | 24 |
| P2 | 20 | 20 |
| P3 | 5 | 5 |
| P4 | 27 | 27 |
| P5 | 16 | 16 |

**平均周转时间 = (24+20+5+27+16) ÷ 5 = 92 ÷ 5 = 18.4 ms**

---

### 三种算法对比

| 算法 | 平均周转时间 | 特点 |
|------|--------------|------|
| FCFS | 17.6 ms | 简单，但短作业可能等很久 |
| SJN | **12 ms（最短）** | 短作业优先，周转时间最短 |
| RR | 18.4 ms | 公平，每个进程都能运行 |

---

## English Detailed Explanation

### (a) FCFS — First-Come, First-Served

Run in order: P1 → P2 → P3 → P4 → P5

| Process | Burst | Start | Completion | Turnaround |
|---------|-------|-------|------------|------------|
| P1 | 8 | 0 | 8 | 8 |
| P2 | 6 | 8 | 14 | 14 |
| P3 | 1 | 14 | 15 | 15 |
| P4 | 9 | 15 | 24 | 24 |
| P5 | 3 | 24 | 27 | 27 |

**Average = (8+14+15+24+27)/5 = 17.6 ms**

### (b) SJN — Shortest Job Next

Sort by burst time: P3(1) → P5(3) → P2(6) → P1(8) → P4(9)

| Process | Burst | Start | Completion | Turnaround |
|---------|-------|-------|------------|------------|
| P3 | 1 | 0 | 1 | 1 |
| P5 | 3 | 1 | 4 | 4 |
| P2 | 6 | 4 | 10 | 10 |
| P1 | 8 | 10 | 18 | 18 |
| P4 | 9 | 18 | 27 | 27 |

**Average = (1+4+10+18+27)/5 = 12 ms**

### (c) RR — Round Robin (quantum = 2 ms)

Each process runs at most 2 ms per turn. [See detailed simulation above]

| Process | Completion | Turnaround |
|---------|------------|------------|
| P1 | 24 | 24 |
| P2 | 20 | 20 |
| P3 | 5 | 5 |
| P4 | 27 | 27 |
| P5 | 16 | 16 |

**Average = (24+20+5+27+16)/5 = 18.4 ms**

---

# ═══════════════════════════════════════════════════
# 第 5 题 — 抢占式与非抢占式
# Question 5 — Preemptive vs Non-preemptive
# ═══════════════════════════════════════════════════

---

## 中文详细讲解

### 什么是"抢占"？

想象你在用 ATM 取钱，"非抢占"就是你用完才换人；"抢占"就是每人只能用 1 分钟，时间到了必须让给下一个人。

- **非抢占式**：进程一旦开始运行，就一直运行到完成，除非它自己主动停下（比如等 I/O）。
- **抢占式**：操作系统可以强制停止正在运行的进程，让另一个进程运行。

### 三种算法分析

| 算法 | 是否抢占 | 理由 | 生活类比 |
|------|----------|------|----------|
| **FCFS** | 非抢占 | 进程按顺序运行，一个完成了才轮到下一个 | 排队买票，前面的人买完才轮到你 |
| **SJN** | 非抢占 | 选中最短的进程后，让它运行到完成 | 超市快速通道，但一旦开始结账就不会被打断 |
| **RR** | **抢占** | 每个进程只运行一个时间片，时间到就被强制切换 | 每人只能用电脑 5 分钟，时间到换人 |

### 举例说明

**FCFS 例子：**
```
P1(运行时间 8ms) 先开始运行
中途 P2(运行时间 2ms) 到达
→ P2 必须等 P1 运行完 8ms 才能开始
→ 即使 P2 很短，也不能"插队"
```

**RR 例子（时间片 2ms）：**
```
P1 开始运行
运行 2ms 后，时间片用完
→ P1 被强制暂停，放到队尾
→ P2 开始运行
→ 这就是"抢占"
```

### 答案

| 算法 | 抢占式？ |
|------|----------|
| FCFS | 非抢占式 |
| SJN | 非抢占式 |
| RR | **抢占式** |

---

## English Detailed Explanation

### What is "Preemption"?

- **Non-preemptive:** Once a process starts, it runs until completion (unless it voluntarily stops for I/O).
- **Preemptive:** The OS can forcibly stop a running process and give the CPU to another.

### Analysis

| Algorithm | Preemptive? | Reason |
|-----------|-------------|--------|
| FCFS | No | Processes run in order; one completes before next starts |
| SJN | No | Shortest job is selected and runs to completion |
| RR | **Yes** | Each process runs for only one time slice, then is forced to yield |

---

# ═══════════════════════════════════════════════════
# 第 6 题 — 分页地址转换
# Question 6 — Address Translation in Paging
# ═══════════════════════════════════════════════════

---

## 中文详细讲解

### 地址转换三步走

**第一步：拆分逻辑地址**

把逻辑地址拆成两部分：
- 页号 = 逻辑地址 DIV 页大小（在第几页）
- 偏移 = 逻辑地址 MOD 页大小（页内位置）

```
例：逻辑地址 5000，页大小 1024
    页号 = 5000 ÷ 1024 = 4（整数部分）
    偏移 = 5000 mod 1024 = 5000 - 4×1024 = 904
    结果：<4, 904>
```

**第二步：查页表**

页表是一张映射表，记录"第 X 页存放在第 Y 帧"。

```
页表示例：
┌────────┬────────┐
│ 页号   │ 帧号   │
├────────┼────────┤
│ 0      │ 5      │
│ 1      │ 2      │
│ 2      │ 8      │
│ 3      │ 1      │
│ 4      │ 6      │  ← 页号 4 对应帧号 6
└────────┴────────┘

查页号 4 → 得到帧号 6
```

**第三步：组成物理地址**

```
物理地址 = 帧号 × 页大小 + 偏移
         = 6 × 1024 + 904
         = 6144 + 904
         = 7048
```

### 完整流程图

```
逻辑地址 5000
      ↓
┌─────────────────────────┐
│ 第一步：拆分            │
│ 页号 = 5000 DIV 1024 = 4│
│ 偏移 = 5000 MOD 1024 = 904│
└────────────┬────────────┘
             ↓
      <页号 4, 偏移 904>
             ↓
┌─────────────────────────┐
│ 第二步：查页表          │
│ 页表[4] = 帧号 6        │
└────────────┬────────────┘
             ↓
       帧号 6, 偏移 904
             ↓
┌─────────────────────────┐
│ 第三步：计算物理地址    │
│ 物理地址 = 6×1024 + 904 │
│          = 7048         │
└─────────────────────────┘
```

---

## English Detailed Explanation

### Three-Step Address Translation

**Step 1: Split logical address**
- Page number = Logical address DIV Page size
- Offset = Logical address MOD Page size

**Step 2: Look up page table**
- Use page number as index
- Get frame number from the table

**Step 3: Form physical address**
- Physical address = Frame number × Page size + Offset

---

# ═══════════════════════════════════════════════════
# 第 7 题 — 分时与多道程序设计
# Question 7 — Timesharing & Multiprogramming
# ═══════════════════════════════════════════════════

---

## 中文详细讲解

### 多道程序设计（Multiprogramming）

**问题：** 早期计算机一次只能运行一个程序。程序等 I/O 时，CPU 就空闲了。

**解决：** 让多个程序同时在内存里。一个程序等 I/O，CPU 就去运行另一个。

```
没有多道程序设计：
┌─────────────────────────────────────────┐
│ 程序1运行 │ 等I/O(CPU空闲) │ 程序1继续 │
└─────────────────────────────────────────┘
            ↑ CPU 在这里浪费了！

有多道程序设计：
┌─────────────────────────────────────────┐
│ 程序1运行 │ 程序2运行 │ 程序1继续 │ ...│
└─────────────────────────────────────────┘
            ↑ 程序1等I/O时，CPU运行程序2
```

**优点：** CPU 利用率提高，吞吐量增加。

### 分时（Timesharing）

**问题：** 多用户要共享一台计算机，每个人都想快速得到响应。

**解决：** 把 CPU 时间切成小片，轮流分给每个用户。切换很快，每个用户感觉自己在独占电脑。

```
分时系统：
时间轴：
┌───┬───┬───┬───┬───┬───┬───┬───┐
│用户1│用户2│用户3│用户1│用户2│用户3│用户1│...│
└───┴───┴───┴───┴───┴───┴───┴───┘
  ↑ 每个用户轮流获得一小段时间
```

**优点：** 响应性好，公平。

### 代价：上下文切换开销

每次切换进程，都要：
1. 保存当前进程的状态（寄存器、程序计数器等）
2. 加载下一个进程的状态

这需要时间！如果切换太频繁，大量时间花在切换上，反而降低效率。

---

## English Detailed Explanation

### Multiprogramming
- Multiple programs in memory at once
- When one waits for I/O, CPU runs another
- Benefit: Higher CPU utilization and throughput

### Timesharing
- CPU time is divided into small slices
- Each user gets turns in rapid succession
- Each user feels like they have their own machine
- Benefit: Better responsiveness and fairness

### Cost: Context Switch Overhead
- Switching processes takes time (save/restore state)
- Too frequent switching reduces efficiency

---

# ═══════════════════════════════════════════════════
# 第 8 题 — 文件访问方式
# Question 8 — File Access Methods
# ═══════════════════════════════════════════════════

---

## 中文详细讲解

### 两种访问方式对比

| 方式 | 说明 | 类比 |
|------|------|------|
| **顺序访问** | 从头到尾按顺序读，不能跳跃 | 看录像带，要看第 50 分钟必须快进过前面 |
| **直接访问** | 可以直接跳到任意位置读取 | DVD 可以直接跳到第 50 分钟 |

### 日志文件 vs 索引文件

**日志文件：**
- 按时间顺序记录事件
- 通常从头读到尾进行审计
- → **顺序访问更合适**

```
日志文件：
[事件1] → [事件2] → [事件3] → [事件4] → ...
                                          ↓
                                   通常从头读到尾
```

**索引文件：**
- 需要根据键值快速找到某条记录
- 不需要读前面的所有记录
- → **直接访问更合适**

```
索引文件：
想找记录 #500 → 直接跳到位置 500 → 读取
          不需要读 #1 到 #499
```

### 实际例子

| 访问方式 | 实际例子 |
|----------|----------|
| 顺序访问 | 播放音乐、看视频、读备份磁带、审计日志 |
| 直接访问 | 数据库查询、数组按下标访问、随机播放歌曲 |

---

## English Detailed Explanation

### Sequential vs Direct Access

| Method | Description | Analogy |
|--------|-------------|---------|
| Sequential | Read from start to end in order | VHS tape: must fast-forward to reach minute 50 |
| Direct | Jump directly to any position | DVD: can jump directly to minute 50 |

### Log Files vs Index Files

- **Log files:** Written in time order, read start-to-end → **Sequential access**
- **Index files:** Need to jump to specific records by key → **Direct access**

---

# ═══════════════════════════════════════════════════
# 第 9 题 — 路径
# Question 9 — Paths
# ═══════════════════════════════════════════════════

---

## 中文详细讲解

### 目录树

```
C:\Users\John\Documents          ← 这是根起点
├── Projects                     ← 子目录
│   ├── WebApp                   ← 子目录的子目录
│   │   ├── index.html           ← 文件
│   │   └── script.js            ← 文件
│   └── DataScience              ← 另一个子目录
│       ├── analysis.py          ← 目标文件 1
│       └── results.csv          ← 目标文件 2
└── Reports
    └── summary.pdf
```

### (a) 绝对路径：从根开始的完整路径

**找 results.csv 的绝对路径：**

从根往下追踪：
```
C:\Users\John\Documents
         ↓
      Projects
         ↓
     DataScience
         ↓
     results.csv
```

**答案：** `C:\Users\John\Documents\Projects\DataScience\results.csv`

### (b) 相对路径：从当前位置出发

**当前位置：** `C:\Users\John\Documents\Projects\WebApp`

**目标：** `analysis.py`（在 DataScience 文件夹里）

**思考过程：**
```
当前位置：WebApp
目标位置：DataScience\analysis.py

WebApp 和 DataScience 是什么关系？
→ 它们是"兄弟"，都在 Projects 下面

怎么从 WebApp 到 DataScience？
→ 先回到上一级（Projects）：用 ..
→ 再进入 DataScience

所以：..\DataScience\analysis.py
```

**图示：**
```
Projects/
├── WebApp/        ← 你在这里
│   ├── index.html
│   └── script.js
└── DataScience/   ← 要去这里
    ├── analysis.py ← 目标文件
    └── results.csv

路径：.. (回到 Projects) → DataScience → analysis.py
```

**答案：** `..\DataScience\analysis.py`

### (c) 绝对路径 vs 相对路径

| 类型 | 起点 | 特点 | 例子 |
|------|------|------|------|
| 绝对路径 | 从根开始（如 C:\） | 完整路径，不管你在哪里都一样 | `C:\Users\John\file.txt` |
| 相对路径 | 从当前目录开始 | 简短，但依赖于当前位置 | `..\DataScience\file.txt` |

---

## English Detailed Explanation

### (a) Absolute path for results.csv

Trace from root: C:\ → Users → John → Documents → Projects → DataScience → results.csv

**Answer:** `C:\Users\John\Documents\Projects\DataScience\results.csv`

### (b) Relative path to analysis.py

Current: WebApp. Target: DataScience\analysis.py

WebApp and DataScience are siblings under Projects.
- Go up one level: `..`
- Enter DataScience: `DataScience`
- File: `analysis.py`

**Answer:** `..\DataScience\analysis.py`

### (c) Difference

- **Absolute:** Starts from root; same no matter where you are
- **Relative:** Starts from current directory; depends on your location

---

# ═══════════════════════════════════════════════════
# 第 10 题 — 磁盘调度
# Question 10 — Disk Scheduling
# ═══════════════════════════════════════════════════

**题目：** 请求序列 40, 12, 22, 66, 67, 33, 80。磁头在 50。

---

## 中文详细讲解

### 磁盘结构简介

磁盘由多个同心圆轨道组成，每个轨道叫一个"柱面"。磁头要读取数据，必须先移动到对应柱面。

```
柱面编号（从内到外）：
0   10   20   30   40   50   60   70   80   90  100
├───┼────┼────┼────┼────┼────┼────┼────┼────┼────┤
                              ↑
                         磁头当前位置 (50)

请求的柱面：40, 12, 22, 66, 67, 33, 80
在数轴上标出：
0   10   20   30   40   50   60   70   80   90  100
├───┼────┼────┼────┼────┼────┼────┼────┼────┼────┤
    ↑    ↑    ↑    ↑    ↑    ↑ ↑       ↑
   12   22   33   40  磁头  66 67      80
```

### (a) FCFS — 先来先服务

**规则：** 按请求到达的顺序服务，不管磁头位置。

**执行过程：**
```
磁头位置：50
请求顺序：40, 12, 22, 66, 67, 33, 80

服务顺序：
50 → 40 → 12 → 22 → 66 → 67 → 33 → 80

在数轴上画移动轨迹：
0   10   20   30   40   50   60   70   80
├───┼────┼────┼────┼────┼────┼────┼────┤
         2←───1←───┐    ┌──→3─→4         
    ↑←───────────┘    └───────────→↑
   12              33              80
                   ↑←─────5───────┘
                   └────────6────→↑

磁头来回跳，很乱！
```

**计算移动量：**

| 从 | 到 | 移动距离 |
|----|----| --------|
| 50 | 40 | \|50-40\| = 10 |
| 40 | 12 | \|40-12\| = 28 |
| 12 | 22 | \|12-22\| = 10 |
| 22 | 66 | \|22-66\| = 44 |
| 66 | 67 | \|66-67\| = 1 |
| 67 | 33 | \|67-33\| = 34 |
| 33 | 80 | \|33-80\| = 47 |

**总移动量 = 10+28+10+44+1+34+47 = 174**

---

### (b) SSTF — 最短寻道时间优先

**规则：** 每次选择离当前磁头位置最近的请求。

**执行过程（一步一步来）：**

```
第 1 步：磁头在 50
  待服务：40, 12, 22, 66, 67, 33, 80
  计算距离：
    |50-40|=10, |50-12|=38, |50-22|=28, 
    |50-66|=16, |50-67|=17, |50-33|=17, |50-80|=30
  最近的是 40（距离 10）→ 服务 40
  
第 2 步：磁头移到 40
  待服务：12, 22, 66, 67, 33, 80
  计算距离：
    |40-12|=28, |40-22|=18, |40-66|=26, 
    |40-67|=27, |40-33|=7, |40-80|=40
  最近的是 33（距离 7）→ 服务 33

第 3 步：磁头移到 33
  待服务：12, 22, 66, 67, 80
  计算距离：
    |33-12|=21, |33-22|=11, |33-66|=33, 
    |33-67|=34, |33-80|=47
  最近的是 22（距离 11）→ 服务 22

第 4 步：磁头移到 22
  待服务：12, 66, 67, 80
  计算距离：
    |22-12|=10, |22-66|=44, |22-67|=45, |22-80|=58
  最近的是 12（距离 10）→ 服务 12

第 5 步：磁头移到 12
  待服务：66, 67, 80
  计算距离：
    |12-66|=54, |12-67|=55, |12-80|=68
  最近的是 66（距离 54）→ 服务 66

第 6 步：磁头移到 66
  待服务：67, 80
  计算距离：
    |66-67|=1, |66-80|=14
  最近的是 67（距离 1）→ 服务 67

第 7 步：磁头移到 67
  待服务：80
  只剩一个，服务 80
```

**服务顺序：40 → 33 → 22 → 12 → 66 → 67 → 80**

**计算移动量：**

| 从 | 到 | 移动距离 |
|----|----| --------|
| 50 | 40 | 10 |
| 40 | 33 | 7 |
| 33 | 22 | 11 |
| 22 | 12 | 10 |
| 12 | 66 | 54 |
| 66 | 67 | 1 |
| 67 | 80 | 13 |

**总移动量 = 10+7+11+10+54+1+13 = 106**

---

### (c) SCAN — 电梯算法（向高柱面移动）

**规则：** 磁头像电梯一样，先朝一个方向走到头，再反方向。

**执行过程：**

```
磁头初始位置：50，向高柱面（向右）移动

第一阶段：向右移动（50 → 高柱面方向）
  50 以上的请求：66, 67, 80
  按从小到大服务：66 → 67 → 80

第二阶段：反方向移动（80 → 低柱面方向）
  50 以下的请求：40, 33, 22, 12
  按从大到小服务：40 → 33 → 22 → 12

数轴图示：
0   10   20   30   40   50   60   70   80
├───┼────┼────┼────┼────┼────┼────┼────┤
    ↑    ↑    ↑    ↑    │    ↑  ↑    ↑
   12   22   33   40    │   66 67   80
                        │
          第二阶段 ←────┤────→ 第一阶段
       (4)←(3)←(2)←(1)←50→(1)→(2)→(3)
         40  33  22  12    66  67  80
```

**服务顺序：66 → 67 → 80 → 40 → 33 → 22 → 12**

**计算移动量：**

| 从 | 到 | 移动距离 |
|----|----| --------|
| 50 | 66 | 16 |
| 66 | 67 | 1 |
| 67 | 80 | 13 |
| 80 | 40 | 40 |
| 40 | 33 | 7 |
| 33 | 22 | 11 |
| 22 | 12 | 10 |

**总移动量 = 16+1+13+40+7+11+10 = 98**

---

### 三种算法对比

| 算法 | 服务顺序 | 总移动量 |
|------|----------|----------|
| FCFS | 40→12→22→66→67→33→80 | **174** |
| SSTF | 40→33→22→12→66→67→80 | **106** |
| SCAN | 66→67→80→40→33→22→12 | **98**（最小）|

**(c) 答案：SCAN 使寻道时间最小（总移动量 98）**

---

## English Detailed Explanation

### (a) FCFS
Order: 40→12→22→66→67→33→80
Movement: 10+28+10+44+1+34+47 = **174**

### (b) SSTF
At each step, choose nearest request.
Order: 40→33→22→12→66→67→80
Movement: 10+7+11+10+54+1+13 = **106**

### (c) SCAN (toward higher cylinders)
First go toward high: 66→67→80
Then reverse: 40→33→22→12
Order: 66→67→80→40→33→22→12
Movement: 16+1+13+40+7+11+10 = **98**

**Answer: SCAN minimizes seek time (98)**

---

# ═══════════════════════════════════════════════════
# 第 11 题 — Unix 文件权限
# Question 11 — Unix File Permissions
# ═══════════════════════════════════════════════════

---

## 中文详细讲解

### Unix 权限基础

每个文件有 9 位权限，分成 3 组：

```
┌─────────┬─────────┬─────────┐
│ Owner   │ Group   │ Others  │
│ 所有者   │ 组用户   │ 其他人   │
├─────────┼─────────┼─────────┤
│ r w x   │ r w x   │ r w x   │
└─────────┴─────────┴─────────┘
  ↑ ↑ ↑
  │ │ └── x = 执行（可以运行程序）
  │ └──── w = 写（可以修改内容）
  └────── r = 读（可以查看内容）
```

**例如 `rwx r-x r--` 表示：**
- 所有者：可读、可写、可执行
- 组用户：可读、不可写、可执行
- 其他人：可读、不可写、不可执行

### (a) 解读权限表

| 文件 | 所有者 | 组 | 其他 |
|------|--------|-----|------|
| report.txt | rw- | r-- | --- |
| script.sh | rwx | r-x | r-- |
| data.db | rw- | --- | --- |

**report.txt (rw- r-- ---)：**
```
所有者 rw-：可以读、可以写、不能执行
组用户 r--：只能读
其他人 ---：什么都不能做
```

**script.sh (rwx r-x r--)：**
```
所有者 rwx：可以读、写、执行
组用户 r-x：可以读、可以执行（但不能修改）
其他人 r--：只能读（不能执行）
```

**data.db (rw- --- ---)：**
```
所有者 rw-：可以读、写
组用户 ---：什么都不能做
其他人 ---：什么都不能做
```

### (b) 让所有人能读和执行 script.sh

**目标：** owner=rwx, group=r-x, others=r-x

**当前：** owner=rwx, group=r-x, others=r--

**方法 1：用数字**

每个权限组可以用 0-7 的数字表示：
```
r = 4, w = 2, x = 1
rwx = 4+2+1 = 7
r-x = 4+0+1 = 5
r-- = 4+0+0 = 4
```

要设置 rwx r-x r-x = 755

**命令：** `chmod 755 script.sh`

**方法 2：用符号**

`a` 表示所有人（all），`+` 表示添加权限

**命令：** `chmod a+rx script.sh`

### (c) 为什么文件保护重要？

在多用户系统中：
1. **防止未授权访问**：不让其他人看你的私人文件
2. **保护数据完整性**：不让别人修改或删除你的文件
3. **安全考虑**：只有授权用户能运行敏感程序

```
例如：
用户 A 的工资单 salary.txt
→ 应该设为 rw- --- ---（只有自己能看）
→ 不然用户 B 就能偷看 A 的工资了！
```

---

## English Detailed Explanation

### (a) Permission interpretation

| File | Owner | Group | Others |
|------|-------|-------|--------|
| report.txt | Read, Write | Read only | No access |
| script.sh | Read, Write, Execute | Read, Execute | Read only |
| data.db | Read, Write | No access | No access |

### (b) Allow everyone to read and execute script.sh

**Method 1 (numeric):** `chmod 755 script.sh`
- 7 = rwx (owner)
- 5 = r-x (group)
- 5 = r-x (others)

**Method 2 (symbolic):** `chmod a+rx script.sh`
- a = all users
- +rx = add read and execute

### (c) Why is file protection critical?

1. Prevent unauthorized access to private data
2. Protect data integrity (prevent modification/deletion)
3. Security: only authorized users can run sensitive programs

---

**📌 使用说明：** 本答案详细讲解每道题的解题思路。交作业请独立完成，仅供复习参考。

**Note:** This detailed explanation is for review only. Complete your homework independently.
