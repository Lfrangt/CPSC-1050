# CPSC 1050 Lab Ch 6 - 答案与教学 / Answers and Teaching

---

## Question 1: 测试计划 / Test Plan

### 程序逻辑分析 / Program Logic Analysis

伪代码执行顺序：
1. 读取 num1, num2, num3
2. Load num1 → Add num3 → Sub num2
3. 结果存入 answer 并输出

**公式 / Formula:** `answer = num1 + num3 - num2`

---

### 测试计划表 / Test Plan Table

| Reason for Test Case | Input Values (num1, num2, num3) | Expected Output | Observed Output |
|----------------------|----------------------------------|-----------------|-----------------|
| 正常正数 / Normal positive numbers | 10, 5, 3 | 8 | (填写实测值) |
| 边界值：零 / Boundary: zero | 0, 0, 0 | 0 | (填写实测值) |
| 负数测试 / Negative numbers | -5, 3, 10 | 2 | (填写实测值) |
| 大数测试 / Large numbers | 100, 50, 25 | 75 | (填写实测值) |

---

### 计算验证 / Calculation Verification

| 测试用例 | 计算过程 | 预期结果 |
|---------|---------|---------|
| (10, 5, 3) | 10 + 3 - 5 = 8 | 8 ✓ |
| (0, 0, 0) | 0 + 0 - 0 = 0 | 0 ✓ |
| (-5, 3, 10) | -5 + 10 - 3 = 2 | 2 ✓ |
| (100, 50, 25) | 100 + 25 - 50 = 75 | 75 ✓ |

---

### 教学要点 / Teaching Points

- **Load-Add-Sub 顺序**：先 Load 第一个数，再 Add/Sub 其他数，顺序决定结果
- **测试用例选择原则**：应覆盖正常值、边界值（0）、负数、大数
- **Reason for Test Case**：说明为什么选这组输入（如 "验证负数运算"）

---

## Question 2: 温度判断流程图 / Temperature Flowchart

### 判断标准 / Criteria

| 温度范围 | 输出 |
|---------|------|
| > 30°C | Hot |
| 20°C ≤ temp ≤ 29°C | Warm |
| < 20°C | Cold |

---

### 流程图伪代码 / Flowchart Pseudocode

```
START
  Read temperature
  IF temperature > 30 THEN
    Write "Hot"
  ELSE IF temperature >= 20 AND temperature <= 29 THEN
    Write "Warm"
  ELSE
    Write "Cold"
  END IF
END
```

---

### 流程图结构示意 / Flowchart Structure (Text Diagram)

```
        ┌─────────┐
        │  START  │
        └────┬────┘
             │
             ▼
        ┌─────────────┐
        │ Read temp   │
        └──────┬──────┘
               │
               ▼
        ┌──────────────┐
        │ temp > 30?   │
        └──┬───────┬───┘
          Yes     No
           │       │
           ▼       ▼
      ┌────────┐  ┌──────────────────┐
      │ "Hot"  │  │ 20 ≤ temp ≤ 29?  │
      └────────┘  └──┬───────────┬───┘
                     Yes        No
                      │          │
                      ▼          ▼
                 ┌────────┐  ┌────────┐
                 │ "Warm" │  │ "Cold" │
                 └────────┘  └────────┘
```

---

### 教学要点 / Teaching Points

- **边界值注意**：20 和 29 是 inclusive（包含），所以用 `>=` 和 `<=`
- **判断顺序**：先判断 >30，再判断 20–29，最后 else 为 <20
- **流程图符号**：椭圆=起止，矩形=处理，菱形=判断

---

## Question 3: 四次考试成绩平均（无循环）/ Four Test Average (No Loops)

### 题目要求 / Requirements

- 输入：3 次期中考试 + 1 次期末考试
- 期末权重为普通考试的 2 倍
- 只用顺序操作，不用循环

### 权重计算 / Weight Calculation

- 普通考试权重各为 1，期末权重为 2
- 总权重 = 1 + 1 + 1 + 2 = 5
- 平均 = (term1 + term2 + term3 + final×2) / 5

---

### 伪代码 / Pseudocode

```
Read term1
Read term2
Read term3
Read final

Set total = term1 + term2 + term3 + (final * 2)
Set average = total / 5

Write average
```

---

### 教学要点 / Teaching Points

- **加权平均**：final 乘 2 表示其权重是其他考试的两倍
- **顺序操作**：每个 Read 和 Set 都是顺序执行，没有重复结构

---

## Question 4: 十五次考试成绩平均（用循环）/ Fifteen Test Average (With Loop)

### 题目要求 / Requirements

- 输入：14 次普通考试 + 1 次期末考试
- 期末权重为普通考试的 2 倍
- 用循环输入并求和

### 权重计算 / Weight Calculation

- 14 次普通考试权重各为 1，期末权重为 2
- 总权重 = 14 + 2 = 16
- 平均 = (sum_of_14_regular + final×2) / 16

---

### 伪代码 / Pseudocode

```
Set sum = 0
Set count = 1

WHILE count <= 14
  Read score
  Set sum = sum + score
  Set count = count + 1
END WHILE

Read final
Set total = sum + (final * 2)
Set average = total / 16

Write average
```

---

### 教学要点 / Teaching Points

- **循环用途**：用 WHILE 重复 14 次 Read 和累加，避免写 14 行相同代码
- **计数器**：count 从 1 到 14，控制循环次数
- **总权重**：14×1 + 2 = 16，所以除以 16

---

## 总结 / Summary

| 题目 | 核心概念 |
|-----|---------|
| Q1 | 测试计划、等价类划分、边界值 |
| Q2 | 流程图、条件分支、边界值判断 |
| Q3 | 加权平均、顺序伪代码 |
| Q4 | 循环、累加器、计数器 |
