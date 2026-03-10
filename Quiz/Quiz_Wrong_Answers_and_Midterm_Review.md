# 📋 CPSC 1050 Quiz 错题本 + 期中复习重点

**用途：** 汇总各章测验错题，并整理期中考试重点。  
**更新方式：** 每收到一周的 quiz 记录后，把错题和重点追加到对应章节。

---

# Part 1: 错题记录 (Wrong Answers by Chapter)

## Ch 2 – Binary Numbers (Jan 8, 2026 | 19/28, C+)

- **错题数量：** 9 题（具体题目待补充）
- **已知正确题示例：** “C 在十六进制中表示 11” → **False**（C=12，11=B）
- *若有每道错题的截图或文字，发给我后可逐条补进这里。*

---

## Ch 5 – Super Simple CPU (Jan 29, 2026 | 15/18, A-)

### 错题 1：Program Counter 存什么？
- **题目：** The program counter is used to store which of the following?  
- **你的答案：** the data used by an instruction  
- **正确答案：** the memory location of an instruction  
- **要点：** PC 存的是**下一条指令的地址**，不存指令本身，也不存数据。

### 错题 2：Addressability 定义
- **题目：** Addressability is the number of bits stored in each addressable location in memory.  
- **你的答案：** False  
- **正确答案：** True  
- **要点：** Addressability = 每个可寻址内存单元里存的**位数**（如 8-bit addressability = 每地址 1 byte）。

### 错题 3：CD 的存储方式
- **题目：** A compact disc stores data using magnetized particles.  
- **你的答案：** True  
- **正确答案：** False  
- **要点：** CD 是**光学存储**（激光+反射面）；**磁化粒子**用于硬盘、磁带。

---

## Ch 6 – (待补充)
*把之后的 Ch 6 quiz 错题粘贴到这里*

## Ch 7 – (待补充)
*把之后的 Ch 7 quiz 错题粘贴到这里*

---

# Part 2: 期中复习重点 (Midterm Key Concepts)

## Ch 5 – Super Simple CPU

| 概念 | 英文 | 必记要点 |
|------|------|----------|
| 程序计数器 | Program Counter (PC) | 存**下一条指令的地址**，不是指令或数据 |
| 指令寄存器 | Instruction Register (IR) | 存**当前正在执行的指令**，在 Control Unit 里 |
| 地址能力 | Addressability | 每个可寻址位置存的**位数**（如 8-bit = 1 byte） |
| 总线 | Bus | 一组导线，传 **address / data / control** |
| RAM vs ROM | - | RAM 易失，ROM 非易失；**两者都是** random access |
| 存储技术 | Storage | **光学**：CD/DVD；**磁**：HDD、磁带 |
| 流水线 | Pipelining | 把指令执行分阶段，提高效率 |
| 任务级并行 | Task-level parallelism | 多处理器同时执行不同任务 |
| CPU 组成 | - | Control Unit + ALU + Registers |
| Fetch-Execute | - | Fetch：取**下一条指令**；Execute：执行 |

---

## Ch 2 – Binary Numbers & Number Systems

| 概念 | 英文 | 必记要点 |
|------|------|----------|
| 十六进制字母 | Hex A–F | A=10, B=11, **C=12**, D=13, E=14, F=15 |
| 位置计数法 | Positional notation | 每位 = 数字 × 底数的幂（Section 2.2） |
| 二进制→十进制 | Binary to decimal | 乘权求和（按 2 的幂） |
| 十进制→二进制 | Decimal to binary | 除 2 取余，余数从下往上读 |
| 二进制↔十六进制 | Binary ↔ hex | 4 位一组，从右往左 |
| 字节 | Byte | **1 byte = 8 bits**（必背） |
| 2 的幂 | Powers of 2 | 2⁰=1, 2¹=2, 2²=4, 2³=8, 2⁴=16, 2⁵=32, 2⁶=64, 2⁷=128, 2⁸=256 |

*更全的 Ch2/Ch3 术语与例题见：Notes/Quiz_Review_Ch2_Ch3.md*

---

## 其他章节 (待补充)
*随每周 quiz 更新，把易错点和考点加到这里*

---

# Part 3: 快速自测 (Quick Self-Check)

考前可快速过一遍：

- [ ] PC 存的是 address 还是 instruction 还是 data？ → **address**
- [ ] IR 存的是？ → **current instruction**
- [ ] Addressability 是什么意思？ → **bits per addressable location**
- [ ] CD 是 optical 还是 magnetic？ → **optical**
- [ ] Bus 传哪三类信号？ → **address, data, control**
- [ ] RAM 易失还是非易失？ROM 呢？ → **RAM 易失，ROM 非易失**
- [ ] 十六进制里 C 表示几？11 是哪个字母？ → **C=12；11=B**
- [ ] 1 byte = ? bits → **8**

---

*最后更新：Ch 2、Ch 5 已录入。Ch 2 错题 9 题待补充题目内容。*
