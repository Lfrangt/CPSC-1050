# CPSC 1050 Midterm 半页 A4 考场笔记
> Feb 26 Thu, 90min, 闭卷；可带**半页手写**。题型：MCQ / 填空 / 简答 / Tracing。建议 8–9pt 单面打印或手抄。

---

## Ch 2 Binary & Number Systems 二进制与数制

- **位置权重** = base^position（从右往左 0,1,2…）| **基数 N**：数字 0～N-1
- **2⁰~2⁸** = 1,2,4,8,16,32,64,128,256 | **1 Byte = 8 bits**（必记）
- **Hex A–F** = 10,11,**12**,13,14,15 → **C=12, B=11**（Quiz 常考）
- **n bits → 2ⁿ 种取值**；表示 **N 样东西最少位数** = ⌈log₂N⌉（如 6 样→3 bits）
- **→十进制:** 按权求和 | **十进制→他进制:** 除基取余，**余数从下往上读**
- **Bin↔Oct** 3 位一组 | **Bin↔Hex** 4 位一组（不足左补 0）
- **十六进制排序:** 按**数值大小**排（与十进制一致）。比较时：要么先转十进制再比，要么从**最高位**起逐位比；同一位上 **0&lt;1&lt;…&lt;9&lt;A&lt;B&lt;C&lt;D&lt;E&lt;F**
- **二进制加减:** 1+1=10 进位；0-1 借 2

---

## Ch 3 Data Representation 数据表示

- **analog 模拟** 连续 / **digital 数字** 离散
- **Two's complement 补码:** 取反+1。**n-bit 范围:** -2ⁿ⁻¹ ~ 2ⁿ⁻¹−1（8-bit: -128~127）
- **overflow 溢出:** 结果**放不进** allotted space（不是 radix point 或 mixed 类型）
- **signed-magnitude 原码:** 有**两种零** → 导致 **unnecessary complexity**（不是 wasted memory）
- **floating point 浮点:** value = **mantissa 尾数 × base^exponent**；小数转二进制：**×2 取整**，从上往下读
- **radix point** = 非十进制时的“小数点”
- **压缩:** **Huffman** = 变长编码、常用字符短码；**run-length** = 连续重复（不是“替换单词”）
- **Quiz 易错:** resolution 由像素数决定，**不是** color depth（F）；JPEG 适合照片、GIF 适合线条图（不要反）；**Unicode** > 65,000 字符；RGB 模拟人眼感知

---

## Ch 4 Gates & Circuits 门与电路

- **NOT** 0↔1 | **AND** 全1→1 | **OR** 有1→1（**inclusive OR**）| **XOR** 相异→1（OR 与 XOR 仅 A=B=1 时输出不同）
- **NAND** AND 后 NOT（圆圈在**输出**上，不 negate 输入）| **NOR** OR 后 NOT。**universal gate:** NAND, NOR
- **Boolean:** **identity** A·1=A；**associative** (AB)C=A(BC)；**De Morgan's** (A+B)'=A'B'，(AB)'=A'+B'
- **truth table** = 所有输入组合及对应输出；**gate** = 对电信号做基本运算的器件；**transistor** = switch
- **half adder:** Sum=A⊕B, Carry=AB | **full adder:** Sum=A⊕B⊕Cin
- **combinational** 无记忆 | **sequential** 有记忆、需时钟
- **inversion bubble** = NOT 门符号上的小圆圈

---

## Ch 5 Computing Components 计算组件

- **von Neumann:** CPU + memory + I/O，由 **bus 总线**连接（传 **address, data, control**）
- **CPU:** **ALU** 运算 + **CU** 控制（**IR 在 CU 里**）+ **registers**
- **PC (Program Counter)** = **下一条指令的地址**（不是 instruction 也不是 data）| **IR (Instruction Register)** = **当前正在执行的指令**
- **fetch-decode-execute:** fetch 从 memory 取**下一条指令**
- **RAM** 主存、**volatile**；**ROM** **non-volatile**；**两者都是 random access**
- **Addressability** = 每个可寻址单元存的**位数**（如 8-bit = 1 byte）
- **辅助存储:** **光学** CD/DVD（**不是** magnetized particles）；**磁** HDD、磁带
- **Cache** L1/L2/L3；**pipelining** 指令分阶段；**task-level parallelism** 多处理器不同任务同时执行

---

## Ch 6 Low-Level & Pseudocode 低级语言与伪代码

- **执行顺序:** **machine language**（CPU 直接执行）← **assembly**（**assembler** 翻译）← **high-level**（compiler）
- **assembly** 用 **mnemonics** 表示指令；**loader** = 把**机器语言**程序装入 memory
- **Pseudocode:** Get/Read, Set/←, Write/Print；IF/ELSE 注意区间（如 **0 < x ≤ 10** 打印 B）
- **Tracing:** WHILE/FOR 手算循环（e.g. product×count 累乘；**嵌套循环** count 次数 = 各层次数相乘，注意 count++ 从 -1 开始时最终 = 乘积-1）；**PC 顺序** 有 loop 时会重复经过同一条指令
- **IPO** Input→Process→Output | **flowchart:** 椭圆 起/止，矩形 过程，菱形 判断，平行四边形 I/O

**伪代码 — 三种完整示例:**

**(1) IF/ELSE 分支:**
```
Read x
IF (x > 10)
    Print 'A'
ELSE IF (x > 0)
    Print 'B'
ELSE
    Print 'C'
END IF
```
*(打印 B 时: 0 < x ≤ 10。多条件: IF (a >= 20 AND a <= 30) …)*

**(2) WHILE 循环:**
```
Set count to 1
Set product to 1
WHILE (count < 5)
    Set product to product * count
    Set count to count + 1
END WHILE
Display "Product is " + product
```
*(结果 24。多输入: Read a, b)*

**(3) FOR 循环（嵌套）:**
```
Set count to 0
FOR i = 1 To 2
    FOR j = 1 To 3
        Set count to count + 1
    End For
End For
Display "Count is " + count
Return count
```
*(共 6 次。数组 list[i]；记录 item.name)*

---

## Ch 7 Problem Solving & Algorithms 问题求解与算法

- **sequential search** 从**开头**逐个（不是从中间）；**binary search** 列表**必须先排序**，**divide and conquer**，mid=(first+last)/2，< → last=mid-1，> → first=mid+1；**比较次数**可手算（每次比较砍掉约一半）
- **selection sort** 每轮选未排序最小与当前位交换
- **bubble sort** 相邻比较交换，每轮一最大沉底
- **insertion sort** 保持前段有序，把下一个插入正确位置
- **quicksort** 选 **pivot**，分成 <pivot 与 ≥pivot，**递归**左右；基于 **recursion**
- **recursion:** **base case** 直接返回；**general case** 调用自身（规模更小）；**至少**要这两种
- **array** = 同质集合；**record** = 异质集合、按名字访问
- **top-down design:** 主模块最抽象；**abstract step** = 细节未完全指定

---

## 考场速查与易错提醒

| 问法 | 答案 |
|------|------|
| PC 存什么？ | **下一条指令的地址**（不是 instruction/data） |
| IR 存什么？在谁里？ | **当前指令**；在 **Control Unit** |
| Addressability？ | 每个可寻址位置存的**位数** |
| CD 存数据用？ | **光学**（不是 magnetized particles） |
| Bus 传什么？ | **address, data, control** |
| RAM/ROM 易失？ | RAM **volatile**，ROM **non-volatile**；两者都 **random access** |
| Hex C = ? 11 = ? | **C=12, B=11** |
| n bits 可表示几种？ | **2ⁿ** |
| 两种零的表示方式？ | **signed-magnitude**；导致 **unnecessary complexity** |
| OR 与 XOR 区别？ | 仅当 **A=B=1** 时不同（OR=1, XOR=0） |

**Good luck! 加油！**
