# 📚 Chapter 3: Data Representation
# 第三章：数据表示

---

## 🎯 Chapter Goals | 本章目标

| English | 中文 |
|---------|------|
| Distinguish between **analog** and **digital** information | 区分**模拟**和**数字**信息 |
| Explain binary formats for **negative** and **floating-point** values | 解释**负数**和**浮点数**的二进制格式 |
| Describe **ASCII** and **Unicode** character sets | 描述 **ASCII** 和 **Unicode** 字符集 |
| Perform various types of **text compression** | 执行各种**文本压缩**方法 |
| Explain representation of **sound** | 解释**声音**的表示方法 |
| Explain how **RGB** values define a color | 解释 **RGB** 如何定义颜色 |
| Distinguish between **raster** and **vector** graphics | 区分**位图**和**矢量**图形 |
| Explain **video** compression | 解释**视频**压缩 |

---

## 1️⃣ Analog vs Digital | 模拟 vs 数字 ⭐⭐⭐

### Definitions | 定义

| Term 术语 | English | 中文 |
|-----------|---------|------|
| **Analog Data** | Continuous representation, analogous to actual information | 连续表示，类似于实际信息 |
| **Digital Data** | Discrete representation, breaks info into separate elements | 离散表示，将信息分成独立元素 |
| **Digitize** | Breaking data into pieces and representing them separately | 将数据分割成片段并分别表示 |

### Example | 例子

```
🌡️ Thermometer (温度计)
   - Analog: Mercury rises continuously (水银连续上升)
   - Digital: Shows discrete numbers like 36.5°C (显示离散数字)
```

### Why Binary? | 为什么用二进制？

| Reason 原因 | English | 中文 |
|-------------|---------|------|
| **Price** | Transistors are cheap to produce | 晶体管生产成本低 |
| **Reliability** | Transistors don't get jammed | 晶体管不会卡住 |

### Bit Representation | 位表示

```
1 bit  → 2 possibilities  (0, 1)           → 2¹ = 2
2 bits → 4 possibilities  (00, 01, 10, 11) → 2² = 4
n bits → 2ⁿ possibilities                   → 2ⁿ
```

---

## 2️⃣ Representing Negative Numbers | 负数表示 ⭐⭐⭐⭐⭐

### Three Methods | 三种方法

| Method 方法 | English | 中文 |
|-------------|---------|------|
| Signed-Magnitude | Sign bit + magnitude | 符号位 + 数值 |
| One's Complement | Invert all bits | 所有位取反 |
| **Two's Complement** | Invert all bits + add 1 | 所有位取反 + 加1 |

> ⚠️ **Most Important**: Two's Complement is used in computers!
> 
> ⚠️ **最重要**：计算机使用二进制补码（Two's Complement）！

---

### Signed-Magnitude 详解 | 符号-数值表示法

**概念**：最高位表示符号（0=正，1=负），其余位表示数值

```
+5 = 0 0000101  (最高位0表示正)
-5 = 1 0000101  (最高位1表示负)
     ↑
   符号位
```

**问题 Problems**:
1. **两个零**: +0 (00000000) 和 -0 (10000000) 
2. **运算复杂**: 加减法需要特殊处理

> ⚠️ 这就是为什么计算机不用 Signed-Magnitude，而用 Two's Complement！

---

### Overflow | 溢出 ⭐⭐⭐⭐

**定义**: 当计算结果超出可表示范围时发生溢出

**Definition**: Overflow occurs when the result cannot fit in the allocated bits

```
Example 例 (8-bit signed):
Range 范围: -128 to +127

  01111111  (+127)
+ 00000001  (+1)
──────────
  10000000  = -128 (WRONG! Should be +128)
  
这就是溢出！Result overflowed!
```

**检测溢出 Detecting Overflow**:
- 两个正数相加得到负数 → 溢出
- 两个负数相加得到正数 → 溢出

---

### Two's Complement | 二进制补码 ⭐⭐⭐⭐⭐

#### Formula | 公式

For k bits: **Negative(I) = 2ᵏ - I**

对于 k 位：**Negative(I) = 2ᵏ - I**

#### Easy Way (MUST KNOW!) | 简便方法（必须掌握！）

**Step 1**: Invert all bits (0→1, 1→0) | 第一步：所有位取反

**Step 2**: Add 1 | 第二步：加1

---

#### Example | 例题: Convert +2 to -2 (8 bits) | 把 +2 转成 -2（8位）

```
+2 = 00000010

Step 1 第一步: Invert 取反
      11111101

Step 2 第二步: Add 1 加1
      11111101
    +        1
    ──────────
      11111110

-2 = 11111110
```

✅ **Answer 答案: -2 in 8-bit two's complement = 11111110**

---

#### Two's Complement Table (4 bits) | 4位补码表

| Binary 二进制 | Decimal 十进制 | | Binary 二进制 | Decimal 十进制 |
|---------------|----------------|--|---------------|----------------|
| 0000 | 0 | | 1000 | -8 |
| 0001 | +1 | | 1001 | -7 |
| 0010 | +2 | | 1010 | -6 |
| 0011 | +3 | | 1011 | -5 |
| 0100 | +4 | | 1100 | -4 |
| 0101 | +5 | | 1101 | -3 |
| 0110 | +6 | | 1110 | -2 |
| 0111 | +7 | | 1111 | -1 |

> 🔑 **Key Observation**: The leftmost bit (MSB) indicates the sign!
> - 0 = positive (正数)
> - 1 = negative (负数)

---

#### Range of Two's Complement | 补码范围

For **n bits** | 对于 **n 位**:
- Minimum 最小值: **-2ⁿ⁻¹**
- Maximum 最大值: **+2ⁿ⁻¹ - 1**

| Bits 位数 | Range 范围 |
|-----------|------------|
| 4 bits | -8 to +7 |
| 8 bits | -128 to +127 |
| 16 bits | -32,768 to +32,767 |

---

#### Two's Complement Arithmetic | 补码运算

**Addition works normally! Subtraction = Add the negative!**

**加法正常运算！减法 = 加上负数！**

```
Example 例: -127 + 1 = -126

  10000001  (-127)
+ 00000001  (+1)
──────────
  10000010  (-126) ✓
```

---

## 3️⃣ Representing Real Numbers | 实数表示 ⭐⭐⭐⭐

### Concept | 概念

Real numbers have a **whole part** and a **fractional part**

实数有**整数部分**和**小数部分**

```
Examples 例: 104.32, 0.999, 357.0, 3.14159
```

### Radix Point | 基数点

| English | 中文 |
|---------|------|
| In decimal, it's called the "decimal point" | 在十进制中叫"小数点" |
| General term is "radix point" | 通用术语是"基数点" |

### Binary Fractions | 二进制小数

Positions to the right of the radix point:

基数点右边的位置：

| Position 位置 | Value 值 | Decimal 十进制 |
|---------------|----------|----------------|
| 2⁻¹ | 1/2 | 0.5 |
| 2⁻² | 1/4 | 0.25 |
| 2⁻³ | 1/8 | 0.125 |
| 2⁻⁴ | 1/16 | 0.0625 |

---

### Floating-Point Representation | 浮点数表示 ⭐⭐⭐⭐

#### Formula | 公式

```
R = ± mantissa × base^exponent
R = ± 尾数 × 基数^指数
```

| Component 组成 | English | 中文 |
|----------------|---------|------|
| **Sign** | + or - | 正或负 |
| **Mantissa** | The significant digits | 有效数字（尾数） |
| **Exponent** | Power of the base | 基数的幂次（指数） |

---

#### Examples | 例子

| Real Value 实数 | Floating-Point 浮点表示 |
|-----------------|-------------------------|
| 12001.00 | 12001 × 10⁰ |
| -120.01 | -12001 × 10⁻² |
| 0.12000 | 12000 × 10⁻⁵ |
| 155555000.00 | 15555 × 10³ |

---

### Scientific Notation | 科学计数法

Decimal point is kept to the right of the **leftmost digit**

小数点保持在**最左边数字**的右边

```
12001.32708 = 1.200132708 × 10⁴
            = 1.200132708E+4 (computer notation 计算机表示法)
```

---

### 作业题型：Sign, Mantissa, Exponent 表示 ⭐⭐⭐⭐

**题目**: How can 175.23 be represented as sign, mantissa, and exponent?

**如何用符号、尾数、指数表示 175.23？**

```
方法：把小数移除，记录移动位数

175.23 = 17523 × 10⁻²
         ↑        ↑
      mantissa  exponent
       (尾数)    (指数)

分解：
- Sign 符号: + (正数)
- Mantissa 尾数: 17523
- Exponent 指数: -2 (小数点向右移了2位)
```

**验算**: 17523 × 10⁻² = 17523 × 0.01 = 175.23 ✓

**其他例子**:
| 原数 | 表示形式 | 说明 |
|------|----------|------|
| 175.23 | 17523 × 10⁻² | 5位有效数字 |
| -0.00456 | -456 × 10⁻⁵ | 符号为负 |
| 3140000 | 314 × 10⁴ | 尾数314，指数4 |

---

### Converting Decimal Fractions | 十进制小数转换 ⭐⭐⭐⭐⭐ 

> ⚠️ **这是作业常考点！必须掌握！**

---

### 方法一：十进制小数 → 二进制 | Decimal Fraction → Binary

**核心方法：乘2取整，从上往下读**

**Method: Multiply by 2, take the integer part, read top to bottom**

```
步骤 Steps:
1. 用小数部分 × 2
2. 取结果的整数部分（0或1）作为二进制位
3. 用结果的小数部分继续 × 2
4. 重复直到达到要求的位数
5. 从上往下读取整数部分
```

---

#### 例题1 | Example 1: 0.50₁₀ → 二进制（5位小数）

```
0.50 × 2 = 1.00  → 取整数 1 ← 第1位
0.00 × 2 = 0.00  → 取整数 0 ← 第2位
0.00 × 2 = 0.00  → 取整数 0 ← 第3位
0.00 × 2 = 0.00  → 取整数 0 ← 第4位
0.00 × 2 = 0.00  → 取整数 0 ← 第5位

从上往下读：1, 0, 0, 0, 0

✅ 答案：0.50₁₀ = 0.10000₂
```

**验算 Verify**: 0.10000₂ = 1×2⁻¹ = 1×0.5 = 0.5 ✓

---

#### 例题2 | Example 2: 0.10₁₀ → 二进制（5位小数）

```
0.10 × 2 = 0.20  → 取整数 0 ← 第1位
0.20 × 2 = 0.40  → 取整数 0 ← 第2位
0.40 × 2 = 0.80  → 取整数 0 ← 第3位
0.80 × 2 = 1.60  → 取整数 1 ← 第4位
0.60 × 2 = 1.20  → 取整数 1 ← 第5位

从上往下读：0, 0, 0, 1, 1

✅ 答案：0.10₁₀ ≈ 0.00011₂
```

**验算 Verify**: 0.00011₂ = 1×2⁻⁴ + 1×2⁻⁵ = 0.0625 + 0.03125 = 0.09375 ≈ 0.10 ✓

> ⚠️ **注意**：大多数十进制小数无法用二进制精确表示！会有舍入误差。

---

#### 例题3 | Example 3: 0.74₁₀ → 二进制

```
0.74 × 2 = 1.48  → 1
0.48 × 2 = 0.96  → 0
0.96 × 2 = 1.92  → 1
0.92 × 2 = 1.84  → 1
0.84 × 2 = 1.68  → 1

✅ 答案：0.74₁₀ ≈ 0.10111₂
```

---

### 方法二：十进制小数 → 八进制 | Decimal Fraction → Octal

**核心方法：乘8取整，从上往下读**

**Method: Multiply by 8, take the integer part, read top to bottom**

```
步骤 Steps:
1. 用小数部分 × 8
2. 取结果的整数部分（0-7）作为八进制位
3. 用结果的小数部分继续 × 8
4. 重复直到达到要求的位数
5. 从上往下读取整数部分
```

---

#### 例题4 | Example 4: 0.50₁₀ → 八进制（5位小数）

```
0.50 × 8 = 4.00  → 取整数 4 ← 第1位
0.00 × 8 = 0.00  → 取整数 0 ← 第2位
0.00 × 8 = 0.00  → 取整数 0 ← 第3位
0.00 × 8 = 0.00  → 取整数 0 ← 第4位
0.00 × 8 = 0.00  → 取整数 0 ← 第5位

从上往下读：4, 0, 0, 0, 0

✅ 答案：0.50₁₀ = 0.40000₈
```

**验算 Verify**: 0.40000₈ = 4×8⁻¹ = 4×0.125 = 0.5 ✓

---

#### 例题5 | Example 5: 0.10₁₀ → 八进制（5位小数）

```
0.10 × 8 = 0.80  → 取整数 0 ← 第1位
0.80 × 8 = 6.40  → 取整数 6 ← 第2位
0.40 × 8 = 3.20  → 取整数 3 ← 第3位
0.20 × 8 = 1.60  → 取整数 1 ← 第4位
0.60 × 8 = 4.80  → 取整数 4 ← 第5位

从上往下读：0, 6, 3, 1, 4

✅ 答案：0.10₁₀ ≈ 0.06314₈
```

---

### 方法三：十进制小数 → 十六进制 | Decimal Fraction → Hexadecimal

**核心方法：乘16取整，从上往下读**

**Method: Multiply by 16, take the integer part, read top to bottom**

> 记住：10=A, 11=B, 12=C, 13=D, 14=E, 15=F

---

### 总结公式 | Summary Formula

| 目标进制 Target Base | 方法 Method |
|---------------------|-------------|
| 二进制 Binary (2) | 乘 2 取整 |
| 八进制 Octal (8) | 乘 8 取整 |
| 十六进制 Hex (16) | 乘 16 取整 |

**通用规则**：**乘以目标基数，取整数部分，从上往下读**

**General Rule**: **Multiply by target base, take integer part, read top to bottom**

---

### 二进制小数的权重表 | Binary Fraction Weights

| Position 位置 | 2⁻¹ | 2⁻² | 2⁻³ | 2⁻⁴ | 2⁻⁵ |
|---------------|------|------|------|------|------|
| Value 值 | 0.5 | 0.25 | 0.125 | 0.0625 | 0.03125 |
| Fraction 分数 | 1/2 | 1/4 | 1/8 | 1/16 | 1/32 |

---

## 4️⃣ Representing Text | 文本表示 ⭐⭐⭐

### Character Sets | 字符集

| Character Set 字符集 | Bits 位数 | Characters 字符数 | Description 描述 |
|----------------------|-----------|-------------------|------------------|
| **ASCII** | 7 bits | 128 | American Standard Code (美国标准码) |
| **Extended ASCII** | 8 bits | 256 | Includes special characters (包含特殊字符) |
| **Unicode** | 16+ bits | 65,536+ | International characters (国际字符) |

### ASCII Examples | ASCII 例子

| Character 字符 | Decimal 十进制 | Binary 二进制 |
|----------------|----------------|---------------|
| 'A' | 65 | 1000001 |
| 'a' | 97 | 1100001 |
| '0' | 48 | 0110000 |
| Space 空格 | 32 | 0100000 |

> 🔑 **Key Pattern**: 'a' - 'A' = 97 - 65 = 32
> 
> 小写字母 = 大写字母 + 32

---

## 5️⃣ Text Compression | 文本压缩 ⭐⭐⭐⭐

### Three Methods | 三种方法

---

### Method 1: Keyword Encoding | 关键字编码

Replace common words with symbols

用符号替换常用单词

```
Original 原文: "the" appears many times
Encoded 编码:  "#" replaces "the"

Example 例:
"the people and the government" 
→ "# people + # government"
```

#### Compression Ratio | 压缩比

```
Compression Ratio = Encoded Size / Original Size
压缩比 = 编码后大小 / 原始大小

Example 例: 596 / 656 = 0.9085 (saved 9.15% 节省9.15%)
```

---

### Method 2: Run-Length Encoding (RLE) | 游程编码 ⭐⭐⭐⭐

Replace repeated sequences with: **flag + value + count**

用 **标记 + 值 + 次数** 替换重复序列

```
Format 格式: *value count
* = flag 标记
value = repeated character 重复字符
count = number of repetitions 重复次数
```

#### Example | 例题

```
Original 原文: bbbbbbbbbbjjjklqqqqqq+++++

Encoded 编码: *b10jjjkl*q6*+5

Explanation 解释:
- *b10 = 'b' repeated 10 times (b重复10次)
- jjjkl = not worth encoding (不值得编码)
- *q6 = 'q' repeated 6 times (q重复6次)
- *+5 = '+' repeated 5 times (+重复5次)
```

> ⚠️ Only encode if repetition > 3 (saves space)
> 
> ⚠️ 只有重复超过3次才编码（才能节省空间）

---

#### 作业题详解 ⭐⭐⭐⭐

**题目**: Compress using RLE: `AAAABBBCCCCCCCDDDD hi there EEEEEEEEEFF`

**解答步骤**:

```
原文分析:
AAAA        → 4个A  → *A4 (编码)
BBB         → 3个B  → BBB (不编码，=3不划算)
CCCCCCC     → 7个C  → *C7 (编码)
DDDD        → 4个D  → *D4 (编码)
 hi there   → 保持原样
EEEEEEEEE   → 9个E  → *E9 (编码)
FF          → 2个F  → FF (不编码)

编码结果: *A4BBB*C7*D4 hi there *E9FF
```

**计算压缩比 Compression Ratio**:

```
Original 原始长度: 40 characters
Encoded 编码长度:  26 characters

Compression Ratio = 26/40 = 0.65 = 65%

节省了 35% 的空间！
```

**什么时候编码划算？When to encode?**

| 重复次数 | 原始 | 编码后 | 划算？ |
|----------|------|--------|--------|
| 2次 | AA (2字符) | *A2 (3字符) | ❌ 更长 |
| 3次 | AAA (3字符) | *A3 (3字符) | ➖ 一样 |
| 4次 | AAAA (4字符) | *A4 (3字符) | ✅ 节省1 |
| 10次 | AAAAAAAAAA (10字符) | *A10 (4字符) | ✅ 节省6 |

> 🔑 **规则**: 重复 **> 3** 次才编码！

---

### Method 3: Huffman Encoding | 霍夫曼编码 ⭐⭐⭐⭐

Use **fewer bits** for **common characters**

对**常用字符**使用**更少的位**

Use **more bits** for **rare characters**

对**稀有字符**使用**更多的位**

#### Key Property | 关键特性

**Prefix Code**: No character's bit string is a prefix of another

**前缀码**：任何字符的位串都不是另一个的前缀

```
Example 例:
'e' = 10      (common 常用)
'x' = 110110  (rare 稀有)
```

#### Decoding | 解码

Read left to right, bit by bit, match when found

从左到右逐位读取，匹配时记录

---

## 6️⃣ Representing Audio | 音频表示 ⭐⭐⭐

### How Sound Works | 声音原理

Sound = **air pressure waves** → vibrate eardrum → signals to brain

声音 = **气压波** → 振动耳膜 → 信号传到大脑

### Digitizing Audio | 数字化音频

| Step 步骤 | English | 中文 |
|-----------|---------|------|
| **Sampling** | Periodically measure the voltage | 周期性测量电压 |
| **Quantization** | Represent voltage as a number | 用数字表示电压 |

```
Higher sampling rate 更高采样率 = Better quality 更好质量
More bits per sample 更多位/样本 = Better accuracy 更高精度
```

### Audio Formats | 音频格式

| Format 格式 | Description 描述 |
|-------------|------------------|
| WAV | Uncompressed 未压缩 |
| MP3 | Compressed, uses Huffman + psychoacoustic model 压缩，使用霍夫曼+心理声学模型 |
| AIFF | Apple format 苹果格式 |
| FLAC | Lossless compression 无损压缩 |

> 🎵 **MP3**: Discards frequencies humans can't perceive (science!)
> 
> 🎵 **MP3**：丢弃人类无法感知的频率（科学！）

---

## 7️⃣ Representing Images & Graphics | 图像与图形表示 ⭐⭐⭐⭐

### Color Representation | 颜色表示

#### RGB Model | RGB 模型

Colors are defined by **Red, Green, Blue** values (0-255 each)

颜色由 **红、绿、蓝** 值定义（每个 0-255）

| RGB Value | Color 颜色 |
|-----------|------------|
| (255, 0, 0) | Red 红色 |
| (0, 255, 0) | Green 绿色 |
| (0, 0, 255) | Blue 蓝色 |
| (255, 255, 0) | Yellow 黄色 |
| (255, 255, 255) | White 白色 |
| (0, 0, 0) | Black 黑色 |

---

### Color Depth | 色深

| Term 术语 | Bits 位数 | Colors 颜色数 |
|-----------|-----------|---------------|
| **HiColor** | 16 bits | 65,536 |
| **TrueColor** | 24 bits | 16.7 million |

```
TrueColor: 8 bits × 3 (RGB) = 24 bits per pixel
真彩色：8位 × 3（RGB）= 每像素24位
```

---

### Image Terminology | 图像术语

| Term 术语 | English | 中文 |
|-----------|---------|------|
| **Pixel** | Picture element, a dot of color | 像素，一个颜色点 |
| **Resolution** | Number of pixels (e.g., 1920×1080) | 像素数量（如 1920×1080） |

---

### Raster vs Vector Graphics | 位图 vs 矢量图 ⭐⭐⭐⭐

| Feature 特性 | Raster 位图 | Vector 矢量 |
|--------------|-------------|-------------|
| **Storage** | Stores each pixel | Stores mathematical shapes |
| **存储方式** | 存储每个像素 | 存储数学形状 |
| **Scaling** | Loses quality when enlarged | Scales perfectly |
| **缩放** | 放大会失真 | 完美缩放 |
| **Best for** | Photos | Logos, diagrams |
| **适用于** | 照片 | 标志、图表 |
| **Formats** | BMP, GIF, PNG, JPEG | Flash, SVG |

---

### Raster Image Formats | 位图格式

| Format 格式 | Compression 压缩 | Best For 适用于 |
|-------------|------------------|-----------------|
| **BMP** | None/RLE | Simple images 简单图像 |
| **GIF** | Lossless, 256 colors | Animations, logos 动画、标志 |
| **PNG** | Lossless | Web graphics 网页图形 |
| **JPEG** | Lossy | Photos 照片 |

> 🔑 **Lossy vs Lossless**:
> - **Lossy 有损**: Some data lost, smaller file (如 JPEG)
> - **Lossless 无损**: No data lost, larger file (如 PNG)

---

## 8️⃣ Representing Video | 视频表示 ⭐⭐⭐

### Video Codec | 视频编解码器

**Codec** = **CO**mpressor / **DEC**ompressor

**编解码器** = **压缩器** / **解压器**

### Two Types of Compression | 两种压缩类型

| Type 类型 | English | 中文 |
|-----------|---------|------|
| **Temporal Compression** | Based on differences between consecutive frames | 基于连续帧之间的差异 |
| **时间压缩** | If frame hasn't changed much, don't duplicate | 如果帧变化不大，不重复存储 |
| **Spatial Compression** | Removes repetitive info within a frame | 移除帧内的重复信息 |
| **空间压缩** | Same as still image compression | 与静态图像压缩相同 |

```
Video 视频 = Many frames 多帧
Frame 帧 = One still image 一张静态图像

Temporal 时间: Compare frame 1 vs frame 2
Spatial 空间: Compress within frame 1
```

---

## 📝 Summary Table | 总结表

| Data Type 数据类型 | Representation 表示方法 |
|-------------------|-------------------------|
| Negative Numbers 负数 | Two's Complement 二进制补码 |
| Real Numbers 实数 | Floating Point (sign × mantissa × 2^exp) |
| Text 文本 | ASCII / Unicode |
| Text Compression 文本压缩 | Keyword, RLE, Huffman |
| Audio 音频 | Sampling + Quantization |
| Images 图像 | RGB pixels / Vector shapes |
| Video 视频 | Temporal + Spatial compression |

---

## 🔑 Key Formulas | 关键公式

| Formula 公式 | Description 描述 |
|--------------|------------------|
| Two's complement: Invert + Add 1 | 补码：取反 + 加1 |
| n-bit range: -2ⁿ⁻¹ to +2ⁿ⁻¹-1 | n位范围 |
| Compression ratio = New/Original | 压缩比 = 新/原 |
| TrueColor = 24 bits = 8×3 (RGB) | 真彩色 = 24位 |

---

## ⚠️ Common Exam Points | 常考点

1. **Two's Complement conversion** - 补码转换
2. **Floating-point representation** - 浮点数表示
3. **Run-Length Encoding** - 游程编码
4. **Compression ratio calculation** - 压缩比计算
5. **RGB color values** - RGB 颜色值
6. **Raster vs Vector** - 位图 vs 矢量
7. **Lossy vs Lossless compression** - 有损 vs 无损压缩

---

*Notes created: Jan 2026 | 笔记创建时间：2026年1月*

*Good luck with your preview! 预习加油！💪📚*
