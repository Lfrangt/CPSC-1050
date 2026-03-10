# CPSC1050 M1 期中考试 · 查漏补缺 / Midterm 1 Gap Analysis

**学生 Student:** Khalil Wu
**日期 Date:** 2026-02-26
**得分 Score:** 45 / 70 (C+)（申诉后加分）
**目标 Target:** 冲 A（4.0/4.3）| 转学 UBC CS

---

## 总体评价 / Overall

- **得分概览 / Score Overview:** 45/70 (64.29%) - C+（申诉后加分）
- **一句话 / One-line:** 基础题（进制、寄存器、半加器、顺序/选择排序概念）掌握较好；薄弱在 **CPU 指令与跳转、补码、布尔代数、排序算法细节、逻辑门化简、循环语义**。
  Foundation is solid on number bases, registers, half-adder, search/sort concepts; gaps in **CPU instructions/branching, two's complement, Boolean algebra, sorting algorithm details, gate minimization, loop semantics**.

---

## 逐题反馈（仅错题与易混题）/ Item-by-Item (Wrong & Tricky Only)

### Q1 (0/2) - Super Simple CPU 下一条指令
- **你的答案 / Your answer:** instruction at address 9
- **正误 / Correct?** ❌ 错误
- **正确答案 / Reference:** instruction **in next address**（即顺序执行下一条）
- **批注 / Comment:**
  - 指令 `1001000000001101`：前 4 位 1001 为 opcode。若为**条件跳转**（如 JUMP IF ACC = 0），只有条件成立才跳转到 address 13；条件不成立则 **PC+1，执行下一条**。题目说 accumulator = 5（非 0），故条件不成立，应执行 **next address**，不是 address 9 或 13。
  - Key: 区分 **conditional jump** 与 **unconditional jump**；看清"当前 ACC 值"是否满足跳转条件。

### Q6 (0/2) - 二进制 11110010 的多种解释
- **你的答案 / Your answer:** Equal to -114 in decimal using signed-magnitude
- **正误 / Correct?** ❌ 不完整
- **正确答案 / Reference:** **All the options**（signed-magnitude -114、unsigned 242、2's complement -14 都成立）
- **批注 / Comment:**
  - 同一串二进制在不同约定下含义不同：**unsigned** 242；**signed-magnitude** 最高位为符号，故 -114；**2's complement** 为 -14。三种说法都对，应选 "All the options"。
  - 复习：signed-magnitude / 2's complement 的转换与范围（8-bit 2's comp: -128～127）。

### Q11 (0/1) - 最少门数
- **你的答案 / Your answer:** 8
- **正确答案 / Reference:** 6
- **批注 / Comment:**
  - 考查 **逻辑表达式化简**（布尔代数或卡诺图）后所需门数量。需根据给定电路或真值表写出最简 SOP/POS，再数 AND/OR/NOT 总数。
  - 建议：用 **study-helper-bilingual** 针对 "minimum number of gates" 做几道化简题 + 画电路数门。

### Q17 (0/2) - QuickSort 第一轮 pivot index
- **你的答案 / Your answer:** 5
- **正确答案 / Reference:** 4
- **批注 / Comment:**
  - 常见约定：pivot 取**中间位置**或**第一个/最后一个**。若数组下标从 0 起且长度为 9，中间 index = 4；若长度为 10，可能是 4 或 5。题目给出的是 4，说明题目采用的约定（如 floor((low+high)/2) 或固定选某位）得到的是 index 4。
  - 建议：做题时看清题目对 pivot 的选取规则（first / last / middle），并练几道手写第一轮 partition 的题。

### Q18 (0/2) - 算法返回值
- **你的答案 / Your answer:** 2
- **正确答案 / Reference:** 6
- **批注 / Comment:**
  - 需根据题目给出的伪代码或流程图**逐步执行**，记录变量变化，得到最终 return 值。易错点：循环边界、条件判断、下标从 0 还是 1 开始。
  - 建议：用"表格法"跟踪每次循环的变量，避免漏步或数错。

### Q19 (0/2) — -1 的 8-bit 2's complement  
- **你的答案 / Your answer:** 10000001  
- **正确答案 / Reference:** 11111111  
- **批注 / Comment:**  
  - 题目是 -1 的 8-bit 2's complement，正确答案是 **11111111**（全 1）。  
  - 方法：1 的二进制是 00000001，取反得 11111110，加 1 得 **11111111**。  
  - 你写的 10000001 是 -1 的 **signed-magnitude** 表示，不是 2's complement。这是两种表示方式的经典混淆——考试时必须看清题目要求哪种格式。  
  - 记忆口诀：-1 的 2's complement 永远是全 1（11111111）；-128 的 2's complement 是 10000000（最小负数）。

### Q20 (0/2) - 由真值表写布尔表达式
- **正确答案 / Reference:** A'B'C' + A'B'C + AB'C + ABC'
- **批注 / Comment:**
  - 对输出为 1 的每一行，写 **minterm**（积项），再全部 **OR** 起来。每行对应一个最小项，变量为 0 写 A'，为 1 写 A。
  - 建议：练 2～3 道 "truth table → SOP" 和 "SOP → 最简式" 的题。

### Q24 (0/2) - -114 的 8-bit two's complement
- **你的答案 / Your answer:** 1001110010（为 10 位）
- **正确答案 / Reference:** 10001110
- **批注 / Comment:**
  - -114 在 8-bit 2's complement 范围内（-128～127）。方法一：114 的二进制 01110010，取反 10001101，加 1 得 10001110。方法二：256 - 114 = 142，142 的 8-bit 二进制即 10001110。
  - 注意：答案必须是 **8 位**，不能写成 10 位。

### Q25 (0/2) - 76345 (base 8) 转十六进制
- **你的答案 / Your answer:** 7BAD
- **正确答案 / Reference:** 7CE5
- **批注 / Comment:**
  - 八进制→十六进制：可先 **8→2**（每位八进制对应 3 位二进制），再 **2→16**（每 4 位二进制对应 1 位十六进制）。
  - 76345₈ = 111 110 011 100 101₂，再按 4 位分组：0111 1100 1110 0101 → 7CE5₁₆。
  - 建议：多做几道 8↔2↔16 的转换，避免某一位换算错误。

### Q27 (0/2) - 由电路写布尔表达式
- **你的答案 / Your answer:** (AB + C')' + (BC)'
- **正确答案 / Reference:** （题目标为 Incorrect，需按电路逐级写出）
- **批注 / Comment:**
  - 从输入到输出，按门逐级写：AND → 积，OR → 和，NOT → '。注意括号与运算顺序。
  - 建议：找 2～3 道 "circuit diagram → Boolean expression" 的题，对照答案检查每一步。

### Q29 (0/2) - Selection Sort 第三趟后 index 6 的值
- **你的答案 / Your answer:** 123
- **正确答案 / Reference:** 82
- **批注 / Comment:**
  - Selection sort 每趟在**未排序部分**选最小，与当前趟的"首位置"交换。第三趟后，前三个位置已固定，index 6 属于未排序区，其值会随"当前未排序子数组"变化；题目给的数列第三趟后 index 6 应为 82。
  - 建议：用一组具体数列手写 3～4 趟 selection sort，标出每趟后每个位置的值。

### Q30 (0/2) - Binary Search 比较次数/序列
- **你的答案 / Your answer:** 4
- **正确答案 / Reference:** 52, 25, 2, 12（应为比较时访问的元素序列或类似表述）
- **批注 / Comment:**
  - 题目很可能问的是"比较过程中**依次访问的元素**"或"比较的 mid 值序列"，而不是总次数。按 binary search 的 mid 计算方式（通常 (low+high)/2），依次得到 52, 25, 2, 12 等。
  - 建议：看清题目问的是"比较次数"还是"访问的元素序列"；练一道给数组和 target 写比较序列的题。

### Q34 (0/2) - 循环打印 "hello" 的次数
- **你的答案 / Your answer:** infinite times
- **正确答案 / Reference:** 0
- **批注 / Comment:**
  - 若循环条件在第一次就不成立（例如 `FOR i = 0 TO -1` 或 `WHILE false`），则循环体**一次都不执行**，输出 0 次。
  - 易与"死循环"混淆：死循环是条件永远为真、执行无限次；这里是条件一开始就为假，执行 0 次。
  - 建议：区分 "loop never runs" vs "infinite loop"；读题时看清初始条件与边界。

### Q32 (2/4) - Run-Length Encoding，第二问与约分
- **得分 / Score:** 2/4；第一问 RLE 串正确率 24/26。
- **关于第二问「约分」/ About Part 2 (约分 reduce fraction):**
  - 若第二问要求写**压缩比、比例或分数**（例如原长/编码后长度），很多老师/评分标准会要求**约分到最简**（如 24/26 → **12/13**）。
  - **不约分会不会错？** 数学上 24/26 和 12/13 等价，但**考试里若 rubric 写明 "simplify" 或 "lowest terms"，写 24/26 可能被扣分**。
  - **以后建议 / For next time:** 凡遇到比例、分数形式的答案，**一律约分到最简**（分子分母同除 gcd），除非题目明确说 "leave as 24/26" 或 "do not simplify"。
  - *If part 2 asked for a ratio/fraction and the rubric expected simplified form, not reducing (e.g. writing 24/26 instead of 12/13) can cost marks. Always simplify fractions to lowest terms unless the question says otherwise.*

---

## 查漏补缺 / Gaps & Suggestions

### 薄弱知识点 / Weak Areas

| 知识点 / Topic | 问题简述 / Issue | 建议 / Suggestion |
|----------------|------------------|-------------------|
| **Super Simple CPU 指令与跳转** | 条件跳转时"条件不成立"应执行 next address，易误选跳转目标地址 | 用 study-helper 做"CPU 指令 + 给定 ACC 判断下一条"的 quiz |
| **补码与进制** | -110/-114 的 8-bit 2's complement、八进制转十六进制易错位或位数错 | 做 5～10 道 2's complement 与 8/16 进制转换题，严格按步骤写 |
| **同一二进制多种解释** | 易只选一种解释（如 signed-magnitude），忽略 unsigned 与 2's complement 也对 | 复习"同一 bit 串的 unsigned / signed-mag / 2's comp"对照表 |
| **布尔代数与电路** | 真值表→SOP、电路→表达式、最少门数 | 做真值表写表达式 + 电路写表达式 + 化简求最少门数 各 3 题 |
| **QuickSort / Selection Sort** | pivot 下标约定、每趟后某 index 的值 | 手写 2～3 道 QuickSort 第一轮 + 2～3 道 Selection Sort 前几趟 |
| **Binary Search** | "比较次数"与"访问元素序列"易混 | 练 1～2 道给数组和 target，写比较序列或次数的题 |
| **循环语义** | 条件一开始为假则执行 0 次，易误判为无限次 | 区分 "0 次" vs "无限次"；读伪代码时先看初始条件 |

### 复习建议 / Review Suggestions

1. **优先补**：补码（2's complement）与进制转换、Super Simple CPU 条件跳转、布尔式与电路--这些在 M2 和 Final 中仍会考。
   *Priority: two's complement & base conversion, CPU conditional branch, Boolean expressions & circuits.*

2. **用 study-helper-bilingual**：针对上表每个知识点，各做一份 **双语笔记**（定义+例题），再生成 **10～15 道选择题 quiz** 自测。
   *Use study-helper-bilingual: short bilingual notes + 10-15 MC quiz per topic.*

3. **排序与查找**：把课本/讲义中 QuickSort、Selection Sort、Binary Search 的伪代码和例题过一遍，各手写 2 道完整过程。
   *Sorting & search: review pseudocode and trace 2 full examples each for QuickSort, Selection Sort, Binary Search.*

4. **考前**：重做本文件中所有错题，并做 1～2 套综合选择题（覆盖 Ch2-Ch7），限时完成。
   *Before M2/Final: redo all wrong questions above + 1-2 full practice MC sets under time limit.*

### 推荐练习 / Recommended Practice

- **补码与进制**：Ch2/Ch3 笔记中的 2's complement、8↔2↔16 转换练习题；你已有的 `Two_Complement_补码_补漏.md` 可再过一遍。
- **CPU**：Super Simple CPU 指令集表 + 3～5 道"给指令和 ACC，求下一条"的题。
- **布尔与门**：真值表→SOP、电路→表达式、化简求最少门数，各 3 题。
- **算法**：QuickSort 第一轮 pivot 与 partition、Selection Sort 每趟结果、Binary Search 比较序列，各 2 题。
- **循环**：读伪代码判断"执行 0 次 / n 次 / 无限次"的题 3～5 道。

---

## 与 GPA 顾问的联动 / Link to GPA Advisor

- **COURSE_GRADES.md** 已更新：M1 实际 43/70（61.43%），当前加权约 **42.77%**；要冲 A（85%），**M2 + Final 平均约需 89%**。
- 本次查漏补缺对应的薄弱项，已在 **COURSE_GRADES.md** 的「查漏补缺重点」中列出；后续用 **study-helper-bilingual** 做笔记和 quiz 时，可优先做上述表格中的知识点。
- 下次 **Midterm 2 或 Final** 出分后，把成绩发给我，我会继续帮你更新成绩并盯住 A（4.0/4.3）和 UBC CS 目标。

---

*文档由 gpa-advisor + study-helper-bilingual 联合生成。*
