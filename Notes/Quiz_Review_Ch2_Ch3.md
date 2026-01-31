# 🎯 CPSC 1050 Quiz Review - Chapter 2 & 3
# 测验复习速查表 (English-Chinese Bilingual 中英双语)

---

# 📖 Key Terms / 关键术语速查

| English 英文 | 中文 | Example 例子 |
|--------------|------|--------------|
| Binary | 二进制 | Base 2 |
| Decimal | 十进制 | Base 10 |
| Octal | 八进制 | Base 8 |
| Hexadecimal (Hex) | 十六进制 | Base 16 |
| Bit | 位 | 0 or 1 |
| Byte | 字节 | 8 bits |
| Convert | 转换 | Convert 45 to binary |
| Remainder | 余数 | 45÷2=22 remainder 1 |
| Quotient | 商 | 45÷2=22 |
| Carry | 进位 | 1+1=10 (carry 1) |
| Borrow | 借位 | 0-1 needs borrow |
| Two's Complement | 二进制补码 | For negative numbers |
| Signed | 有符号 | Can be + or - |
| Unsigned | 无符号 | Only positive |
| Mantissa | 尾数 | 3.14 in 3.14×10³ |
| Exponent | 指数 | 3 in 3.14×10³ |
| Floating Point | 浮点数 | Numbers with decimals |
| Radix Point | 基数点 | The "." in 3.14 |
| ASCII | ASCII码 | Character encoding |
| Compression | 压缩 | Make file smaller |
| Run-Length Encoding (RLE) | 游程编码 | AAAA → *A4 |
| Lossless | 无损 | No data lost |
| Lossy | 有损 | Some data lost |
| Raster Graphics | 位图/光栅图 | Stores pixels |
| Vector Graphics | 矢量图 | Stores shapes |
| Pixel | 像素 | Picture element |
| Resolution | 分辨率 | 1920×1080 |
| Sampling | 采样 | For audio digitization |
| Quantization | 量化 | Convert to numbers |

---

# ⚡ CHAPTER 2: Binary Values & Number Systems
# 第二章：二进制与数字系统

---

## 🔢 Must Memorize Tables / 必背表格

### Powers of 2 / 2的幂次
| 2⁰ | 2¹ | 2² | 2³ | 2⁴ | 2⁵ | 2⁶ | 2⁷ | 2⁸ |
|----|----|----|----|----|----|----|-----|-----|
| 1 | 2 | 4 | 8 | 16 | 32 | 64 | 128 | 256 |

### Hexadecimal Values / 十六进制对照
| A | B | C | D | E | F |
|---|---|---|---|---|---|
| 10 | 11 | 12 | 13 | 14 | 15 |

### Storage Units / 存储单位
```
1 Byte = 8 bits ⭐ MUST KNOW!
1 KB (Kilobyte) = 1024 Bytes
1 MB (Megabyte) = 1024 KB
```

---

## 📐 Conversion Methods / 进制转换方法

### Method 1: Other Base → Decimal / 其他进制 → 十进制
**Multiply by weight, then sum / 乘权重求和**

```
Question: Convert 1101₂ to decimal
题目：把 1101₂ 转成十进制

Answer:
1×2³ + 1×2² + 0×2¹ + 1×2⁰
= 8 + 4 + 0 + 1
= 13₁₀
```

### Method 2: Decimal → Other Base / 十进制 → 其他进制
**Divide by base, read remainders bottom-up / 除基取余，从下往上读**

```
Question: Convert 45 to binary / 把45转成二进制
Show your steps / 写出步骤

Answer:
45 ÷ 2 = 22  remainder 1  ↑
22 ÷ 2 = 11  remainder 0  │
11 ÷ 2 = 5   remainder 1  │ Read bottom to top
5  ÷ 2 = 2   remainder 1  │ 从下往上读
2  ÷ 2 = 1   remainder 0  │
1  ÷ 2 = 0   remainder 1  ←

45₁₀ = 101101₂
```

### Method 3: Binary ↔ Octal / 二进制 ↔ 八进制
**Group by 3 bits (from right) / 3位一组（从右往左）**

```
Question: Convert 110001101₂ to octal
Answer:
110 | 001 | 101
 6     1     5
= 615₈
```

### Method 4: Binary ↔ Hexadecimal / 二进制 ↔ 十六进制
**Group by 4 bits (from right) / 4位一组（从右往左）**

```
Question: Convert 10101011₂ to hexadecimal
Answer:
1010 | 1011
  A     B
= AB₁₆
```

---

## ➕ Binary Arithmetic / 二进制运算

### Addition Rules / 加法规则
```
0 + 0 = 0
0 + 1 = 1
1 + 0 = 1
1 + 1 = 10 (write 0, carry 1) ⭐
         (写0，进1)
1 + 1 + 1 = 11 (write 1, carry 1)
```

### Subtraction Rules (Borrowing) / 减法规则（借位）
```
0 - 0 = 0
1 - 0 = 1
1 - 1 = 0
0 - 1 = 1 (borrow 1 from left, borrowed 1 = 2) ⭐
         (向左借1，借来的1当2用)
```

---

## 📊 Key Formulas / 重要公式

| Formula 公式 | Meaning 含义 |
|--------------|--------------|
| Max value of n-bit binary = **2ⁿ - 1** | n位二进制最大值 |
| k-digit hex = **k × 4** binary bits | k位十六进制=k×4位二进制 |
| Number of bytes = **total bits ÷ 8** | 字节数=总位数÷8 |

**Example Question 例题:**
```
Q: How many bytes are in 1100100110000110?
   这个数有多少字节？
A: 16 bits ÷ 8 = 2 Bytes
```

---

# ⚡ CHAPTER 3: Data Representation
# 第三章：数据表示

---

## ➖ Representing Negative Numbers / 负数表示

### Two's Complement / 二进制补码 ⭐⭐⭐ VERY IMPORTANT!

**Method: Invert all bits + Add 1 / 方法：取反 + 加1**

```
Question: Represent -5 using 8-bit two's complement
题目：用8位补码表示 -5

Answer:
Step 1: Write +5 in binary
        +5 = 00000101

Step 2: Invert all bits (0→1, 1→0)
        取反: 11111010

Step 3: Add 1
        加1:  11111010
            +        1
            ──────────
              11111011

-5 = 11111011
```

### Range of n-bit Signed Binary / n位有符号二进制范围
```
Minimum value 最小值: -2^(n-1)
Maximum value 最大值: +2^(n-1) - 1

8-bit signed range 8位有符号范围: -128 to +127
```

### How to tell positive or negative? / 如何判断正负？
```
Look at the leftmost bit (MSB = Most Significant Bit):
看最左边的位（最高有效位）：

0 = Positive 正数
1 = Negative 负数
```

**Common Question 常见题目:**
```
Q: If the system used signed binary, would 150 be representable?
   Explain why or why not.
   如果系统使用有符号二进制，150能被表示吗？解释原因。

A: No, 150 cannot be represented.
   不能。
   
   In 8-bit signed binary, the range is -128 to +127.
   8位有符号二进制的范围是 -128 到 +127。
   
   150 > 127, so it exceeds the maximum positive value.
   150 > 127，所以超出了最大正数值。
```

---

## 📱 Floating Point / 浮点数

### Formula / 公式
```
R = ± mantissa × base^exponent
R = ± 尾数 × 基数^指数
```

**Example Question 例题:**
```
Q: A number is represented in scientific notation as 3.14×10³.
   Identify the mantissa and exponent.
   
   一个数用科学计数法表示为 3.14×10³。
   找出尾数和指数。

A: Mantissa 尾数 = 3.14
   Exponent 指数 = 3
   (Base 基数 = 10)
```

---

## 🔤 Character Encoding / 字符编码

### ASCII Values / ASCII值 ⭐ MUST MEMORIZE!

| Character 字符 | ASCII Value |
|----------------|-------------|
| 'A' | 65 |
| 'Z' | 90 |
| 'a' | 97 |
| 'z' | 122 |
| '0' | 48 |
| '9' | 57 |
| Space 空格 | 32 |

**Key Pattern 规律:**
```
Lowercase = Uppercase + 32
小写 = 大写 + 32

Example: 'a' = 'A' + 32 = 65 + 32 = 97
```

**Example Question 例题:**
```
Q: The string "Data" is stored using ASCII standard.
   Write the ASCII decimal value for each character.
   
   字符串"Data"用ASCII标准存储。
   写出每个字符的ASCII十进制值。

A: D = 68
   a = 97
   t = 116
   a = 97
```

---

## 🗜️ Compression Methods / 压缩方法

### Run-Length Encoding (RLE) / 游程编码 ⭐ OFTEN TESTED!

**Format: *character count / 格式：*字符 次数**
**Only encode repetitions > 3 / 只编码重复超过3次的**

```
Q: Compress "AAAABBBCCDAA" using Run-Length Encoding.
   用游程编码压缩 "AAAABBBCCDAA"。

A: AAAA = 4 times → *A4 (encode, >3 重复>3次，编码)
   BBB  = 3 times → BBB (don't encode, only 3 不编码)
   CC   = 2 times → CC (don't encode 不编码)
   D    = 1 time  → D (don't encode 不编码)
   AA   = 2 times → AA (don't encode 不编码)

   Result 结果: *A4BBBCCDAA
```

### Compression Ratio / 压缩比
```
Compression Ratio = Encoded size / Original size
压缩比 = 编码后大小 / 原始大小

The smaller, the better! 越小越好！
```

### Lossless vs Lossy Compression / 无损 vs 有损压缩

| Lossless 无损 | Lossy 有损 |
|---------------|------------|
| No data is lost 不丢失数据 | Some data is permanently discarded 永久丢弃数据 |
| Original can be perfectly reconstructed 可完美恢复 | Cannot recover original 无法恢复原始 |
| Larger file size 文件较大 | Smaller file size 文件较小 |
| Examples: PNG, FLAC | Examples: JPEG, MP3 |

---

## 🎨 Image Representation / 图像表示

### RGB Color Model / RGB颜色模型
```
(R, G, B) - Each value 0-255 每个值0-255

(255, 0, 0)   = Red 红色
(0, 255, 0)   = Green 绿色
(0, 0, 255)   = Blue 蓝色
(255, 255, 0) = Yellow 黄色
(0, 0, 0)     = Black 黑色
(255,255,255) = White 白色
```

### Color Depth / 色深
```
HiColor = 16 bits (5+5+5 or 5+6+5)
TrueColor = 24 bits (8 bits × 3 RGB) ⭐
```

### Raster vs Vector Graphics / 位图 vs 矢量图

| Feature | Raster Graphics 位图 | Vector Graphics 矢量图 |
|---------|----------------------|------------------------|
| Storage 存储 | Stores individual pixels 存储像素 | Stores mathematical shapes 存储数学形状 |
| Scaling 缩放 | Loses quality when enlarged 放大失真 | Scales perfectly 完美缩放 |
| Best for 适用于 | Photos 照片 | Logos, diagrams 标志、图表 |
| Formats 格式 | BMP, GIF, PNG, JPEG | SVG, Flash |

---

## 🎵 Audio Representation / 音频表示

### Digitizing Audio / 数字化音频

```
Q: What is the purpose of sampling when digitizing audio signals?
   数字化音频信号时，采样的目的是什么？

A: Sampling periodically measures the voltage of an analog 
   audio signal at regular intervals to convert it into 
   discrete digital values.
   
   采样是以固定间隔周期性地测量模拟音频信号的电压，
   将其转换为离散的数字值。
```

---

## 🎬 Video Compression / 视频压缩

| Type 类型 | Description 描述 |
|-----------|------------------|
| **Temporal Compression 时间压缩** | Based on differences between consecutive frames 基于连续帧之间的差异 |
| **Spatial Compression 空间压缩** | Removes repetitive information within a frame 移除帧内的重复信息 |

---

# 📝 Common Question Types / 常见题型

## Type 1: Base Conversion / 进制转换
```
Q: Convert the decimal number 45 to its binary equivalent.
   Show your steps.
```

## Type 2: Binary Arithmetic / 二进制运算
```
Q: Add the following binary numbers: 1011 + 0111
Q: Subtract: 1010 - 0011
```

## Type 3: Two's Complement / 补码
```
Q: Using 8-bit signed binary, represent the decimal number -6.
Q: Would 150 be representable in 8-bit signed binary? Explain.
```

## Type 4: Run-Length Encoding / 游程编码
```
Q: Compress "AAAABBBCCDAA" using Run-Length Encoding.
Q: Explain why RLE works well for this example.
```

## Type 5: ASCII Values / ASCII值
```
Q: Write the ASCII decimal value for each character in "Data".
```

## Type 6: Floating Point / 浮点数
```
Q: Identify the mantissa and exponent in 3.14×10³.
```

## Type 7: Digital vs Analog / 数字 vs 模拟
```
Q: List two advantages of using digital representation over 
   analog representation.
```

## Type 8: Graphics / 图形
```
Q: Explain the difference between raster graphics and vector 
   graphics in terms of how they store image data.
```

## Type 9: Compression Types / 压缩类型
```
Q: What is the difference between lossless and lossy compression?
```

---

# ⚠️ Common Mistakes / 易错点

| ❌ Wrong 错误 | ✅ Correct 正确 |
|--------------|----------------|
| Position starts from 1 | Position starts from **0** 位置从0开始 |
| Group bits from left | Group bits from **right** 从右往左分组 |
| 8 bits = 1 bit | **8 bits = 1 Byte** |
| Two's complement = just invert | Two's complement = **invert + add 1** 取反+1 |
| Encode all characters in RLE | Only encode **repetitions > 3** 只编码重复>3次 |
| 8-bit signed max = 255 | 8-bit signed max = **127** |

---

# 🚀 Last Minute Review / 考前快速复习

```
✓ Powers of 2: 1, 2, 4, 8, 16, 32, 64, 128, 256
✓ Hex: A=10, B=11, C=12, D=13, E=14, F=15
✓ 1 Byte = 8 bits
✓ Two's complement = Invert + Add 1
✓ 8-bit signed range: -128 to +127
✓ ASCII: A=65, a=97, lowercase = uppercase + 32
✓ RLE: Only encode repetitions > 3
✓ TrueColor = 24 bits
✓ Raster = pixels, Vector = shapes
✓ Lossless = no data lost, Lossy = data discarded
```

---

# 🔑 Key English Phrases for Quiz / 考试常见英文表达

| 看到这个... | 意思是... |
|-------------|-----------|
| "Convert X to binary" | 把X转成二进制 |
| "Show your steps" | 写出步骤 |
| "Using 8-bit unsigned binary" | 用8位无符号二进制 |
| "Using 8-bit signed binary" | 用8位有符号二进制 |
| "Would X be representable?" | X能被表示吗？ |
| "Explain why or why not" | 解释原因 |
| "Identify the mantissa and exponent" | 找出尾数和指数 |
| "Compress using RLE" | 用游程编码压缩 |
| "What is the ASCII value?" | ASCII值是多少？ |
| "List two advantages" | 列出两个优点 |
| "Explain the difference between" | 解释...的区别 |
| "In terms of" | 从...方面来说 |

---

*Good luck on your quiz! 测验加油！💪🍀*
