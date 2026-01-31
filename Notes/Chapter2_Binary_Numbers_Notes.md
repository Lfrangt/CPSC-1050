# 📚 Chapter 2: Binary Values and Number Systems
# 第二章：二进制与数字系统

---

## 🎯 Why Learn This? | 为什么要学？

| English | 中文 |
|---------|------|
| Computers only understand 0s and 1s (voltage levels) | 计算机只认识0和1（电压高低） |
| Learning binary = learning computer's "native language" | 学二进制 = 学计算机的"母语" |
| Base conversion = "translation" between humans and computers | 进制转换 = 人类和计算机之间的"翻译" |

---

## 1️⃣ Positional Notation | 位置计数法 ⭐⭐⭐

### Core Concept | 核心概念

Each position has a **weight** = base^position

每个位置都有一个**权重** = 基数的幂次

```
Position (位置):    ...  3rd     2nd     1st     0th
                        第3位   第2位   第1位   第0位
Weight (权重):      ...  base³   base²   base¹   base⁰
```

> ⚠️ **Important**: Position starts from **0** on the right!
> 
> ⚠️ **注意**：位置从右边的 **0** 开始数！

### Example | 例子：Decimal 642

```
    6       4       2
    ↓       ↓       ↓
Position: 2       1       0
Weight:  10²     10¹     10⁰
       = 100   = 10    = 1

Calculation: 6×100 + 4×10 + 2×1 = 600 + 40 + 2 = 642
计算过程：   6×100 + 4×10 + 2×1 = 600 + 40 + 2 = 642
```

### 🔑 Key Rule | 关键规则

**A base-N number system can only use digits from 0 to N-1**

**基数为N的进制，只能使用 0 到 N-1 的数字**

| Base 进制 | Radix 基数 | Available Digits 可用数字 |
|-----------|------------|---------------------------|
| Binary 二进制 | 2 | 0, 1 |
| Octal 八进制 | 8 | 0, 1, 2, 3, 4, 5, 6, 7 |
| Decimal 十进制 | 10 | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 |
| Hexadecimal 十六进制 | 16 | 0-9, A, B, C, D, E, F |

---

## 2️⃣ Binary Basics | 二进制基础 ⭐⭐⭐⭐⭐

### Binary ↔ Decimal Table (MUST MEMORIZE!) | 对照表（必背！）

| Binary 二进制 | Decimal 十进制 | | Binary 二进制 | Decimal 十进制 |
|---------------|----------------|--|---------------|----------------|
| 0 | 0 | | 1000 | 8 |
| 1 | 1 | | 1001 | 9 |
| 10 | 2 | | 1010 | 10 |
| 11 | 3 | | 1011 | 11 |
| 100 | 4 | | 1100 | 12 |
| 101 | 5 | | 1101 | 13 |
| 110 | 6 | | 1110 | 14 |
| 111 | 7 | | 1111 | 15 |

### Powers of 2 (MUST MEMORIZE!) | 2的幂次表（必背！）

| 2⁰ | 2¹ | 2² | 2³ | 2⁴ | 2⁵ | 2⁶ | 2⁷ | 2⁸ | 2⁹ | 2¹⁰ |
|----|----|----|----|----|----|----|-----|-----|-----|------|
| 1 | 2 | 4 | 8 | 16 | 32 | 64 | 128 | 256 | 512 | 1024 |

### Storage Units | 存储单位

| Unit 单位 | Definition 定义 | Exam Point 考点 |
|-----------|-----------------|-----------------|
| **bit (位)** | 1 binary digit (0 or 1) 一个二进制数字 | Smallest unit 最小单位 |
| **Byte (字节)** | **8 bits** | ⚠️ Often tested! 常考！ |
| **Word (字)** | Depends on CPU (32/64 bits) 取决于CPU | |

### 📝 Example | 例题

**Q: How many bytes in `1100100110000110`?**

**问：`1100100110000110` 有多少字节？**

```
Total bits 总位数 = 16
1 Byte = 8 bits
Answer 答案: 16 ÷ 8 = 2 Bytes
```

---

## 3️⃣ Base Conversion | 进制转换 ⭐⭐⭐⭐⭐

### Method 1: Other Base → Decimal | 其他进制 → 十进制

**Formula 公式**: Multiply each digit by its weight, then sum up

**公式**：每位数字 × 权重，然后求和

---

#### Example 1 | 例题1: Binary → Decimal | 二进制 → 十进制

**Convert `110101₂` to decimal | 把 `110101₂` 转成十进制**

```
Position 位置:  5    4    3    2    1    0
Digit 数字:     1    1    0    1    0    1
Weight 权重:   2⁵   2⁴   2³   2²   2¹   2⁰
             = 32 = 16  = 8  = 4  = 2  = 1

Calculation 计算: 1×32 + 1×16 + 0×8 + 1×4 + 0×2 + 1×1
               = 32 + 16 + 0 + 4 + 0 + 1
               = 53₁₀
```

✅ **Answer 答案: 110101₂ = 53₁₀**

---

#### Example 2 | 例题2: Octal → Decimal | 八进制 → 十进制

**Convert `1314₈` to decimal | 把 `1314₈` 转成十进制**

```
Position 位置:  3      2     1     0
Digit 数字:     1      3     1     4
Weight 权重:   8³     8²    8¹    8⁰
             = 512  = 64  = 8   = 1

Calculation 计算: 1×512 + 3×64 + 1×8 + 4×1
               = 512 + 192 + 8 + 4
               = 716₁₀
```

✅ **Answer 答案: 1314₈ = 716₁₀**

---

#### Example 3 | 例题3: Hexadecimal → Decimal | 十六进制 → 十进制

**Convert `DC₁₆` to decimal | 把 `DC₁₆` 转成十进制**

> Remember 记住: D = 13, C = 12

```
Position 位置:  1       0
Digit 数字:     D       C
              = 13    = 12
Weight 权重:   16¹     16⁰
             = 16    = 1

Calculation 计算: 13×16 + 12×1 = 208 + 12 = 220₁₀
```

✅ **Answer 答案: DC₁₆ = 220₁₀**

---

#### Example 4 | 例题4: Octal with Decimal Point | 带小数的八进制

**Convert `352.25₈` to decimal | 把 `352.25₈` 转成十进制**

> ⚠️ Positions right of decimal point are negative: -1, -2, -3...
> 
> ⚠️ 小数点右边的位置是负数：-1, -2, -3...

```
Position 位置:   2    1    0   .   -1      -2
Digit 数字:      3    5    2   .    2       5
Weight 权重:    8²   8¹   8⁰      8⁻¹     8⁻²
              = 64 = 8  = 1    = 0.125  = 0.015625

Calculation 计算: 3×64 + 5×8 + 2×1 + 2×0.125 + 5×0.015625
               = 192 + 40 + 2 + 0.25 + 0.078125
               = 234.328₁₀
```

✅ **Answer 答案: 352.25₈ = 234.328₁₀**

---

### Method 2: Decimal → Other Base | 十进制 → 其他进制

**Steps 步骤**:
1. Divide by target base | 除以目标基数
2. Record remainder | 记录余数
3. Use quotient to continue | 用商继续除
4. Read remainders **bottom to top** | 余数**从下往上**读

---

#### Example 1 | 例题1: Decimal → Binary | 十进制 → 二进制

**Convert `77₁₀` to binary | 把 `77₁₀` 转成二进制**

```
77 ÷ 2 = 38 ... remainder 余 1  ↑
38 ÷ 2 = 19 ... remainder 余 0  │
19 ÷ 2 = 9  ... remainder 余 1  │  Read bottom to top
9  ÷ 2 = 4  ... remainder 余 1  │  从下往上读
4  ÷ 2 = 2  ... remainder 余 0  │
2  ÷ 2 = 1  ... remainder 余 0  │
1  ÷ 2 = 0  ... remainder 余 1  ← Start here 从这里开始
```

✅ **Answer 答案: 77₁₀ = 1001101₂**

---

#### Example 2 | 例题2: Decimal → Octal | 十进制 → 八进制

**Convert `11327₁₀` to octal | 把 `11327₁₀` 转成八进制**

```
11327 ÷ 8 = 1415 ... remainder 余 7  ↑
1415  ÷ 8 = 176  ... remainder 余 7  │
176   ÷ 8 = 22   ... remainder 余 0  │ Read bottom to top
22    ÷ 8 = 2    ... remainder 余 6  │ 从下往上读
2     ÷ 8 = 0    ... remainder 余 2  ← Start here
```

✅ **Answer 答案: 11327₁₀ = 26077₈**

---

### Method 3: Binary ↔ Octal (Group by 3) | 二进制 ↔ 八进制（3位一组）⭐⭐⭐⭐

**Why 3? Because 2³ = 8 | 为什么是3？因为 2³ = 8**

#### Binary → Octal | 二进制 → 八进制

**Convert `110001101110₂` to octal | 把 `110001101110₂` 转成八进制**

```
Group by 3 from right 从右往左每3位一组:
110 | 001 | 101 | 110

Convert each group 每组转换:
110 = 6
001 = 1
101 = 5
110 = 6
```

✅ **Answer 答案: 110001101110₂ = 6156₈**

---

#### Octal → Binary | 八进制 → 二进制

**Convert `771₈` to binary | 把 `771₈` 转成二进制**

```
Each octal digit → 3 binary digits 每个八进制数字转3位二进制:
7 = 111
7 = 111
1 = 001
```

✅ **Answer 答案: 771₈ = 111111001₂**

---

### Method 4: Binary ↔ Hexadecimal (Group by 4) | 二进制 ↔ 十六进制（4位一组）⭐⭐⭐⭐

**Why 4? Because 2⁴ = 16 | 为什么是4？因为 2⁴ = 16**

#### Hex Conversion Table (MUST MEMORIZE!) | 十六进制对照表（必背！）

| Hex | Binary 二进制 | | Hex | Binary 二进制 |
|-----|---------------|--|-----|---------------|
| 0 | 0000 | | 8 | 1000 |
| 1 | 0001 | | 9 | 1001 |
| 2 | 0010 | | A (10) | 1010 |
| 3 | 0011 | | B (11) | 1011 |
| 4 | 0100 | | C (12) | 1100 |
| 5 | 0101 | | D (13) | 1101 |
| 6 | 0110 | | E (14) | 1110 |
| 7 | 0111 | | F (15) | 1111 |

---

#### Binary → Hexadecimal | 二进制 → 十六进制

**Convert `1011010011₂` to hex | 把 `1011010011₂` 转成十六进制**

```
Group by 4 from right 从右往左每4位一组 (pad with 0 不够补0):
  10 | 1101 | 0011
0010 | 1101 | 0011

Convert each group 每组转换:
0010 = 2
1101 = D
0011 = 3
```

✅ **Answer 答案: 1011010011₂ = 2D3₁₆**

---

#### Hexadecimal → Binary | 十六进制 → 二进制

**Convert `C4₁₆` to binary | 把 `C4₁₆` 转成二进制**

```
Each hex digit → 4 binary digits 每个十六进制数字转4位二进制:
C = 1100
4 = 0100
```

✅ **Answer 答案: C4₁₆ = 11000100₂**

---

#### Example: Hex → Octal (Indirect) | 十六进制 → 八进制（间接转换）

**Convert `BABA₁₆` to octal | 把 `BABA₁₆` 转成八进制**

```
Step 1 第一步: Hex → Binary (4 bits each) 十六进制 → 二进制
B = 1011
A = 1010
B = 1011
A = 1010
BABA₁₆ = 1011101010111010₂

Step 2 第二步: Binary → Octal (3 bits each) 二进制 → 八进制
  1 | 011 | 101 | 010 | 111 | 010
001 | 011 | 101 | 010 | 111 | 010

001 = 1
011 = 3
101 = 5
010 = 2
111 = 7
010 = 2
```

✅ **Answer 答案: BABA₁₆ = 135272₈**

---

## 4️⃣ Binary Arithmetic | 二进制运算 ⭐⭐⭐⭐

### Binary Addition | 二进制加法

| Addition 加法 | Result 结果 | Note 说明 |
|---------------|-------------|-----------|
| 0 + 0 | 0 | |
| 0 + 1 | 1 | |
| 1 + 0 | 1 | |
| 1 + 1 | **10** | Write 0, carry 1 写0进1 |
| 1 + 1 + 1 | **11** | Write 1, carry 1 写1进1 |

---

#### Example | 例题: Binary Addition | 二进制加法

**Calculate `00010011 + 00111110` | 计算 `00010011 + 00111110`**

```
Carry 进位:   1 1 1 1 1 1 0 0
              0 0 0 1 0 0 1 1   (19₁₀)
            + 0 0 1 1 1 1 1 0   (62₁₀)
            ─────────────────
              0 1 0 1 0 0 0 1   (81₁₀) ✓
```

**Verification 验算**: 19 + 62 = 81 ✓

---

### Binary Subtraction (Borrowing) | 二进制减法（借位）

| Subtraction 减法 | Result 结果 | Note 说明 |
|------------------|-------------|-----------|
| 0 - 0 | 0 | |
| 1 - 0 | 1 | |
| 1 - 1 | 0 | |
| 0 - 1 | **1** | Borrow 1 (=2) 借1当2 |

---

#### Example | 例题: Binary Subtraction | 二进制减法

**Calculate `1010111 - 0111011` | 计算 `1010111 - 0111011`**

```
Borrow 借位:  0 1 2 2 0 2 1
              1 0 1 0 1 1 1     (87₁₀)
            - 0 1 1 1 0 1 1     (59₁₀)
            ─────────────────
              0 0 1 1 1 0 0     (28₁₀) ✓
```

**Verification 验算**: 87 - 59 = 28 ✓

---

## 5️⃣ Important Formulas | 常考公式 ⭐⭐⭐

### 1. Max value of n-bit binary number? | n位二进制数最大是多少？

**Answer 答案: 2ⁿ - 1**

Example 例: 4-bit max 4位最大 = 2⁴ - 1 = 15 = `1111₂`

---

### 2. k-digit hex = how many binary bits? | k位十六进制数有多少位二进制？

**Answer 答案: k × 4**

Example 例: 3-digit hex 3位十六进制 = 3 × 4 = 12 binary bits 位二进制

---

### 3. Largest 3-digit hex? Decimal value? | 十六进制最大的3位数？十进制是多少？

```
Largest 3-digit hex 最大3位十六进制 = FFF₁₆

To decimal 转十进制:
15×16² + 15×16¹ + 15×16⁰
= 15×256 + 15×16 + 15×1
= 3840 + 240 + 15
= 4095₁₀
```

---

## 6️⃣ Common Mistakes | 易错点总结 ⚠️

| Mistake 易错点 | Correct Way 正确做法 |
|----------------|----------------------|
| Position starts from 1 位置从1开始 | ❌ Position starts from **0**! 位置从**0**开始！ |
| Confuse bits and bytes 混淆bit和byte | ✅ **8 bits = 1 Byte** |
| Binary→Octal use 4 bits 二转八用4位 | ❌ Binary→Octal: **3 bits**, Binary→Hex: **4 bits** |
| Group from left 从左往右分组 | ❌ Group from **right**! 从**右往左**分组！ |
| Forget A-F values 忘记A-F的值 | ✅ A=10, B=11, C=12, D=13, E=14, F=15 |
| Forget to reverse remainders 忘记倒着写余数 | ✅ Read remainders **bottom to top** 从下往上读！ |

---

## 📝 Quick Reference Card | 速查卡

```
┌──────────────────────────────────────────────────────────┐
│  Other → Decimal: Multiply weights, sum up               │
│  其他 → 十进制：乘权重，加起来                            │
│                                                          │
│  Decimal → Other: Divide by base, read bottom-up         │
│  十进制 → 其他：除基数，倒着写                            │
│                                                          │
│  Binary ↔ Octal: Group by 3 | 二 ↔ 八：3位一组          │
│  Binary ↔ Hex: Group by 4   | 二 ↔ 十六：4位一组        │
│                                                          │
│  1 Byte = 8 bits                                         │
│  n-bit binary max = 2ⁿ - 1 | n位二进制最大值 = 2ⁿ - 1   │
│  k-digit hex = k×4 binary bits | k位十六进制 = k×4位二进制│
└──────────────────────────────────────────────────────────┘
```

---

## 🧠 Classic Joke | 经典笑话

> "There are only **10** types of people in the world: those who understand binary and those who don't."
> 
> "世界上只有 **10** 种人：懂二进制的和不懂的。"
> 
> (Because binary 10 = decimal 2 😄)
> 
> （因为二进制的 10 = 十进制的 2 😄）

---

*Notes created: Jan 6, 2026 | 笔记创建时间：2026年1月6日*

*Good luck with your quiz! 测验加油！💪📚*
