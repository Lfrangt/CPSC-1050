# Chapter 4: Gates In-Class Activity - Bilingual Answers
# 第四章：门电路课堂活动 - 双语答案

---

## Question 1: Gate Behavior Table
## 问题1：门行为表

**Question | 问题：**  
Complete the table below by describing the behavior of each gate.  
完成下表，描述每个门的行为。

**Answer | 答案：**

| Gate<br>门 | Number of Inputs<br>输入数量 | Behavior<br>行为 |
|:-----------|:---------------------------|:-----------------|
| **NOT** | 1 | **English:** Accepts one bit and returns its opposite value<br>**中文：** 接受一个位并返回其相反值 |
| **AND** | 2 or more<br>2个或更多 | **English:** Produces 1 if both inputs are 1<br>**中文：** 如果两个输入都是1则输出1 |
| **OR** | 2 or more<br>2个或更多 | **English:** Produces 1 if at least one input is 1<br>**中文：** 如果至少一个输入是1则输出1 |
| **XOR** | 2 | **English:** Produces 1 if inputs are different (opposite)<br>**中文：** 如果输入不同（相反）则输出1 |
| **NAND** | 2 or more<br>2个或更多 | **English:** Produces 0 if both inputs are 1 (inverse of AND)<br>**中文：** 如果两个输入都是1则输出0（AND的反） |
| **NOR** | 2 or more<br>2个或更多 | **English:** Produces 1 if both inputs are 0 (inverse of OR)<br>**中文：** 如果两个输入都是0则输出1（OR的反） |

---

## Question 2: Boolean Expression Representation Methods
## 问题2：布尔表达式表示方法

**Question | 问题：**  
Complete the table below to describe the different ways Boolean expressions can be used to represent the behavior of gates and circuits.  
完成下表，描述布尔表达式可用于表示门和电路行为的不同方式。

**Answer | 答案：**

| Method<br>方法 | Description<br>描述 |
|:--------------|:-------------------|
| **Boolean Expressions<br>布尔表达式** | **English:** Similar to algebraic operations. Easy to understand and manipulate mathematically.<br>**中文：** 类似于代数运算。易于理解和数学操作。 |
| **Logic Diagrams<br>逻辑图** | **English:** Drawn diagrams that represent gates, inputs, and outputs. Shows the flow of signals through the circuit.<br>**中文：** 绘制的图表，表示门、输入和输出。显示信号通过电路的流动。 |
| **Truth Tables<br>真值表** | **English:** Visual representation showing each possible input combination and its corresponding output.<br>**中文：** 可视化表示，显示每个可能的输入组合及其对应的输出。 |

---

## Question 3: OR Gate Design
## 问题3：OR门设计

**Question | 问题：**  
You are designing a circuit with an OR gate. The inputs to the gate are A and B. Write the Boolean expression for the OR gate and create its truth table.  
您正在设计一个带有OR门的电路。门的输入是A和B。写出OR门的布尔表达式并创建其真值表。

**Answer | 答案：**

**Logic Diagram | 逻辑图：**
```
    A ────┐
          ├── OR ──> X
    B ────┘
```

**Boolean Expression | 布尔表达式：**
```
X = A + B
```

**Truth Table | 真值表：**
```
A | B | X
--|---|--
0 | 0 | 0
0 | 1 | 1
1 | 0 | 1
1 | 1 | 1
```

**Explanation | 解释：**

**English:**  
The OR gate produces an output of 1 if at least one input is 1. Only when both inputs are 0 does the output become 0.

**中文：**  
OR门在至少一个输入为1时产生输出1。只有当两个输入都为0时，输出才为0。

---

## Question 4: XOR Gate Unique Behavior
## 问题4：XOR门的独特行为

**Question | 问题：**  
Explain the unique behavior of an XOR gate.  
解释XOR门的独特行为。

**Answer | 答案：**

**English:**  
The XOR (Exclusive OR) gate has a unique behavior: it produces an output of 1 **only when the inputs are different** (one is 0 and the other is 1). When both inputs are the same (both 0 or both 1), the output is 0.

**中文：**  
XOR（异或）门有一个独特的行为：它**仅在输入不同时**（一个是0，另一个是1）产生输出1。当两个输入相同时（都是0或都是1），输出为0。

**Truth Table | 真值表：**
```
A | B | A XOR B
--|---|---------
0 | 0 |    0
0 | 1 |    1
1 | 0 |    1
1 | 1 |    0
```

**Key Characteristics | 主要特征：**

**English:**  
- Output is 1 when inputs differ
- Output is 0 when inputs are the same
- Useful for binary addition (sum bit)
- Can be used for parity checking

**中文：**  
- 输入不同时输出为1
- 输入相同时输出为0
- 用于二进制加法（和位）
- 可用于奇偶校验

**Boolean Expression | 布尔表达式：**
```
A XOR B = A'·B + A·B'
```

**Detailed Explanation | 详细解释：**

**English:**  
The XOR gate's unique behavior can be summarized as: "different inputs produce 1, same inputs produce 0." This is different from:
- **OR gate:** Produces 1 when at least one input is 1 (so 1 OR 1 = 1)
- **XOR gate:** Produces 0 when both inputs are 1 (so 1 XOR 1 = 0)

The XOR gate is "exclusive" because it excludes the case where both inputs are 1.

**中文：**  
XOR门的独特行为可以总结为："输入不同时输出1，输入相同时输出0"。这与以下不同：
- **OR门：** 当至少一个输入为1时产生1（所以1 OR 1 = 1）
- **XOR门：** 当两个输入都是1时产生0（所以1 XOR 1 = 0）

XOR门是"异或"的，因为它排除了两个输入都是1的情况。

---

## Question 5: Combinational vs Sequential Circuits
## 问题5：组合电路与时序电路

**Question | 问题：**  
What is a combinational circuit, and how does it differ from a sequential circuit? Provide an example of each.  
什么是组合电路，它与时序电路有何不同？请为每种电路提供一个例子。

**Answer | 答案：**

### Combinational Circuit | 组合电路

**Definition | 定义：**

**English:**  
A **combinational circuit** is a digital circuit whose output depends **only on the current input values**. It has no memory and does not store any previous state.

**中文：**  
**组合电路**是一种数字电路，其输出**仅取决于当前输入值**。它没有记忆功能，不存储任何先前状态。

**Characteristics | 特征：**
- ✅ No memory | 无记忆
- ✅ Output changes immediately with input | 输出随输入立即改变
- ✅ Can be described completely by a truth table | 可以用真值表完全描述
- ✅ No feedback paths | 无反馈路径
- ✅ No clock signal needed | 不需要时钟信号

**Example | 例子：**

**English:**  
**Half Adder** - Adds two 1-bit binary numbers. The output (Sum and Carry) depends only on the current values of inputs A and B. If you change the inputs, the output changes immediately without any delay or memory of previous states.

**中文：**  
**半加器** - 将两个1位二进制数相加。输出（和与进位）仅取决于输入A和B的当前值。如果改变输入，输出会立即改变，没有任何延迟或对先前状态的记忆。

**Other Examples | 其他例子：**
- Multiplexers (MUX) | 多路复用器
- Decoders | 译码器
- Encoders | 编码器
- Full Adder | 全加器

---

### Sequential Circuit | 时序电路

**Definition | 定义：**

**English:**  
A **sequential circuit** is a digital circuit whose output depends on **both the current input values and the previous state** (history) of the circuit. It has memory capability.

**中文：**  
**时序电路**是一种数字电路，其输出取决于**当前输入值和电路的前一个状态**（历史）。它具有记忆能力。

**Characteristics | 特征：**
- ✅ Has memory | 有记忆
- ✅ Output depends on current input + past state | 输出取决于当前输入 + 过去状态
- ✅ Usually requires a clock signal | 通常需要时钟信号
- ✅ Contains storage elements (flip-flops) | 包含存储元件（触发器）
- ✅ Has feedback paths | 有反馈路径

**Example | 例子：**

**English:**  
**D Flip-Flop** - A basic storage element that stores 1 bit of information. The output Q depends on the input D, but only updates at the clock edge (rising or falling edge). It remembers the previous value until the next clock cycle. This memory capability allows it to store information over time.

**中文：**  
**D触发器** - 一个基本的存储元件，存储1位信息。输出Q取决于输入D，但仅在时钟边沿（上升沿或下降沿）更新。它记住先前的值直到下一个时钟周期。这种记忆能力允许它随时间存储信息。

**Other Examples | 其他例子：**
- Counters | 计数器
- Registers | 寄存器
- Memory (RAM) | 内存（RAM）
- State Machines | 状态机

---

### Comparison Table | 对比表

| Feature<br>特征 | Combinational Circuit<br>组合电路 | Sequential Circuit<br>时序电路 |
|:----------------|:----------------------------------|:------------------------------|
| **Output Dependency<br>输出依赖** | Current inputs only<br>仅当前输入 | Current inputs + past state<br>当前输入 + 过去状态 |
| **Memory<br>记忆** | ❌ No<br>无 | ✅ Yes<br>有 |
| **Clock Signal<br>时钟信号** | Not needed<br>不需要 | Usually needed<br>通常需要 |
| **Storage Elements<br>存储元件** | None<br>无 | Flip-flops, registers<br>触发器、寄存器 |
| **Feedback<br>反馈** | No<br>无 | Yes<br>有 |
| **Description Method<br>描述方法** | Truth table<br>真值表 | State table, state diagram<br>状态表、状态图 |
| **Examples<br>例子** | Adders, Multiplexers, Decoders<br>加法器、多路复用器、译码器 | Counters, Registers, Memory<br>计数器、寄存器、内存 |

---

### Visual Comparison | 视觉对比

**Combinational Circuit | 组合电路：**
```
Inputs ──> [Logic Gates] ──> Output
         (no memory)
```

**Sequential Circuit | 时序电路：**
```
Inputs ──> [Logic Gates] ──> Output
              ↑      ↓
              └──────┘
          (feedback with memory)
```

---

## Question 6: Half Adder vs Full Adder
## 问题6：半加器与全加器的区别

**Question | 问题：**  
What is the difference between a half adder and a full adder? Provide the Boolean expressions for both.  
半加器和全加器有什么区别？请提供两者的布尔表达式。

**Answer | 答案：**

### Half Adder (半加器)

**English:**  
A **half adder** is a combinational circuit that adds two 1-bit binary numbers. It has two inputs (A and B) and produces two outputs: a **Sum** and a **Carry**. The half adder cannot handle a carry-in from a previous addition.

**中文：**  
**半加器**是一个组合电路，用于将两个1位二进制数相加。它有两个输入（A和B），并产生两个输出：**和（Sum）**和**进位（Carry）**。半加器无法处理来自前一次加法的进位输入。

**Truth Table | 真值表：**
```
A | B | Sum | Carry
--|---|-----|-------
0 | 0 |  0  |   0
0 | 1 |  1  |   0
1 | 0 |  1  |   0
1 | 1 |  0  |   1
```

**Boolean Expressions | 布尔表达式：**
- **Sum = A XOR B** = **A ⊕ B**  
  **中文：** 和 = A 异或 B
- **Carry = A · B** = **AB**  
  **中文：** 进位 = A 与 B

---

### Full Adder (全加器)

**English:**  
A **full adder** is a combinational circuit that adds three 1-bit binary numbers. It has three inputs: two addends (A and B) and a carry-in (Cin). It produces two outputs: a **Sum** and a **Carry-out (Cout)**. The full adder can handle a carry-in from a previous addition, making it suitable for multi-bit addition.

**中文：**  
**全加器**是一个组合电路，用于将三个1位二进制数相加。它有三个输入：两个加数（A和B）和一个进位输入（Cin）。它产生两个输出：**和（Sum）**和**进位输出（Cout）**。全加器可以处理来自前一次加法的进位输入，因此适用于多位加法。

**Truth Table | 真值表：**
```
A | B | Cin | Sum | Cout
--|---|-----|-----|-----
0 | 0 |  0  |  0  |  0
0 | 0 |  1  |  1  |  0
0 | 1 |  0  |  1  |  0
0 | 1 |  1  |  0  |  1
1 | 0 |  0  |  1  |  0
1 | 0 |  1  |  0  |  1
1 | 1 |  0  |  0  |  1
1 | 1 |  1  |  1  |  1
```

**Boolean Expressions | 布尔表达式：**
- **Sum = A XOR B XOR Cin** = **A ⊕ B ⊕ Cin**  
  **中文：** 和 = A 异或 B 异或 Cin
- **Cout = AB + (A XOR B) · Cin** = **AB + (A ⊕ B) · Cin**  
  **中文：** 进位输出 = AB + (A 异或 B) · Cin  
  **或者 | Or:** **Cout = AB + ACin + BCin**  
  **中文：** 进位输出 = AB + ACin + BCin

---

### Key Differences | 主要区别

| Feature | 特性 | Half Adder | 半加器 | Full Adder | 全加器 |
|---------|------|------------|--------|------------|--------|
| **Inputs | 输入** | 2 (A, B) | 2个 | 3 (A, B, Cin) | 3个 |
| **Carry-in | 进位输入** | ❌ No | 无 | ✅ Yes | 有 |
| **Use Case | 用途** | Least significant bit addition | 最低位加法 | All bit positions | 所有位位置 |
| **Implementation | 实现** | Simpler | 更简单 | More complex | 更复杂 |

---

## Question 7: Multiplexer
## 问题7：多路复用器

**Question | 问题：**  
What is a multiplexer, and how do its control signals determine the output? Provide a practical example.  
什么是多路复用器，控制信号如何决定输出？请提供一个实际例子。

**Answer | 答案：**

### What is a Multiplexer? | 什么是多路复用器？

**English:**  
A **multiplexer (MUX)** is a combinational circuit that selects one output from multiple inputs based on control signals (also called select signals). It acts like a digital switch that routes one of several input signals to a single output line.

**中文：**  
**多路复用器（MUX）**是一个组合电路，根据控制信号（也称为选择信号）从多个输入中选择一个输出。它就像一个数字开关，将多个输入信号中的一个路由到单个输出线。

### How Control Signals Work | 控制信号如何工作

**English:**  
The control signals (select lines) determine which input is passed to the output. For a 2-to-1 MUX, one select line (S) is needed. For a 4-to-1 MUX, two select lines (S₁, S₀) are needed. In general, for a 2ⁿ-to-1 MUX, n select lines are needed.

**中文：**  
控制信号（选择线）决定哪个输入被传递到输出。对于2选1多路复用器，需要一条选择线（S）。对于4选1多路复用器，需要两条选择线（S₁, S₀）。一般来说，对于2ⁿ选1多路复用器，需要n条选择线。

### 2-to-1 Multiplexer Example | 2选1多路复用器示例

**Truth Table | 真值表：**
```
S | I₀ | I₁ | Out
--|----|----|-----
0 |  0 |  0 |  0
0 |  0 |  1 |  0
0 |  1 |  0 |  1
0 |  1 |  1 |  1
1 |  0 |  0 |  0
1 |  0 |  1 |  1
1 |  1 |  0 |  0
1 |  1 |  1 |  1
```

**Boolean Expression | 布尔表达式：**
- **Out = S'·I₀ + S·I₁**  
  **中文：** 输出 = S'·I₀ + S·I₁

**English Rule:** When S=0, output = I₀; when S=1, output = I₁  
**中文规则：** 当 S=0 时，输出 = I₀；当 S=1 时，输出 = I₁

### Practical Example | 实际例子

**English:**  
**Example: Data Routing in a CPU**  
In a CPU, a multiplexer can be used to select which register's data should be sent to the ALU (Arithmetic Logic Unit). For instance:
- Input I₀: Data from Register A
- Input I₁: Data from Register B
- Select signal S: Determined by the instruction being executed
- Output: The selected register's data goes to the ALU

**中文：**  
**例子：CPU中的数据路由**  
在CPU中，多路复用器可用于选择哪个寄存器的数据应发送到ALU（算术逻辑单元）。例如：
- 输入 I₀：来自寄存器A的数据
- 输入 I₁：来自寄存器B的数据
- 选择信号 S：由正在执行的指令决定
- 输出：所选寄存器的数据进入ALU

---

## Question 8: Sequential Circuit
## 问题8：时序电路

**Question | 问题：**  
What is a sequential circuit, and how is it used to store information?  
什么是时序电路，它如何用于存储信息？

**Answer | 答案：**

### What is a Sequential Circuit? | 什么是时序电路？

**English:**  
A **sequential circuit** is a digital circuit whose output depends not only on the current input values but also on the previous state (history) of the circuit. Unlike combinational circuits, sequential circuits have memory capability and can store information.

**中文：**  
**时序电路**是一种数字电路，其输出不仅取决于当前输入值，还取决于电路的前一个状态（历史）。与组合电路不同，时序电路具有记忆能力，可以存储信息。

### Key Characteristics | 主要特征

**English:**  
1. **Memory Function | 记忆功能:** Sequential circuits contain storage elements (like flip-flops) that can remember previous states.
2. **State-Dependent Output | 状态相关输出:** The output depends on both current inputs and the stored state.
3. **Clock Signal | 时钟信号:** Most sequential circuits use a clock signal to synchronize state changes.
4. **Feedback | 反馈:** Sequential circuits often have feedback paths that feed output back as input.

**中文：**  
1. **记忆功能:** 时序电路包含可以记住先前状态的存储元件（如触发器）。
2. **状态相关输出:** 输出取决于当前输入和存储的状态。
3. **时钟信号:** 大多数时序电路使用时钟信号来同步状态变化。
4. **反馈:** 时序电路通常有反馈路径，将输出反馈作为输入。

### How It Stores Information | 如何存储信息

**English:**  
Sequential circuits store information using **flip-flops** (basic storage elements). Each flip-flop can store 1 bit of information (0 or 1). Multiple flip-flops can be combined to form **registers** that store multiple bits.

**中文：**  
时序电路使用**触发器**（基本存储元件）存储信息。每个触发器可以存储1位信息（0或1）。多个触发器可以组合形成**寄存器**，用于存储多位信息。

### Storage Process | 存储过程

**English:**  
1. **Input Data | 输入数据:** Data is provided to the circuit inputs.
2. **Clock Edge | 时钟边沿:** On a clock edge (rising or falling), the input data is captured.
3. **State Update | 状态更新:** The flip-flops update their stored values based on the inputs.
4. **Output | 输出:** The stored state becomes the new output, which persists until the next clock cycle.

**中文：**  
1. **输入数据:** 数据被提供给电路输入。
2. **时钟边沿:** 在时钟边沿（上升沿或下降沿），输入数据被捕获。
3. **状态更新:** 触发器根据输入更新其存储的值。
4. **输出:** 存储的状态成为新的输出，该输出持续到下一个时钟周期。

### Examples | 例子

**English:**  
- **Registers | 寄存器:** Store data temporarily (e.g., CPU registers)
- **Counters | 计数器:** Count clock pulses (e.g., program counter)
- **Memory | 内存:** Store large amounts of data (e.g., RAM)
- **State Machines | 状态机:** Control system behavior based on current state

**中文：**  
- **寄存器:** 临时存储数据（例如，CPU寄存器）
- **计数器:** 计数时钟脉冲（例如，程序计数器）
- **内存:** 存储大量数据（例如，RAM）
- **状态机:** 根据当前状态控制系统行为

---

## Question 9: Integrated Circuit (IC)
## 问题9：集成电路（IC）

**Question | 问题：**  
What is an integrated circuit (IC), and why is it important for modern computers?  
什么是集成电路（IC），为什么它对现代计算机很重要？

**Answer | 答案：**

### What is an Integrated Circuit? | 什么是集成电路？

**English:**  
An **Integrated Circuit (IC)** is a small semiconductor chip that contains many electronic components (transistors, resistors, capacitors, etc.) interconnected to form a complete electronic circuit. These components are fabricated on a single piece of semiconductor material (usually silicon).

**中文：**  
**集成电路（IC）**是一个小型半导体芯片，包含许多电子元件（晶体管、电阻、电容等），这些元件相互连接形成完整的电子电路。这些元件制造在单块半导体材料（通常是硅）上。

### Key Features | 主要特征

**English:**  
1. **Miniaturization | 小型化:** Thousands to billions of components in a tiny chip
2. **Efficiency | 效率:** Lower power consumption and faster operation
3. **Reliability | 可靠性:** Fewer connections mean fewer failure points
4. **Cost-Effectiveness | 成本效益:** Mass production makes ICs very affordable

**中文：**  
1. **小型化:** 在微小的芯片中包含数千到数十亿个元件
2. **效率:** 更低的功耗和更快的操作
3. **可靠性:** 更少的连接意味着更少的故障点
4. **成本效益:** 大规模生产使IC非常经济实惠

### Why It's Important for Modern Computers | 为什么对现代计算机很重要

**English:**  
1. **Performance | 性能:** ICs allow for extremely fast processing speeds. Modern CPUs contain billions of transistors on a single chip, enabling complex computations in nanoseconds.

2. **Size Reduction | 尺寸减小:** Without ICs, computers would be enormous. ICs enable laptops, smartphones, and other portable devices.

3. **Power Efficiency | 能效:** ICs consume much less power than discrete components, making battery-powered devices possible.

4. **Cost Reduction | 成本降低:** Mass production of ICs has dramatically reduced the cost of computing devices, making them accessible to everyone.

5. **Complexity | 复杂性:** ICs allow for incredibly complex circuits (like entire CPUs) to be manufactured reliably and consistently.

**中文：**  
1. **性能:** IC使处理速度极快。现代CPU在单个芯片上包含数十亿个晶体管，能够在纳秒内完成复杂计算。

2. **尺寸减小:** 没有IC，计算机将非常庞大。IC使笔记本电脑、智能手机和其他便携设备成为可能。

3. **能效:** IC比分立元件消耗的功率少得多，使电池供电设备成为可能。

4. **成本降低:** IC的大规模生产大大降低了计算设备的成本，使每个人都能使用。

5. **复杂性:** IC使极其复杂的电路（如整个CPU）能够可靠且一致地制造。

### Evolution | 发展历程

**English:**  
- **SSI (Small-Scale Integration) | 小规模集成:** 10-100 components
- **MSI (Medium-Scale Integration) | 中规模集成:** 100-1,000 components
- **LSI (Large-Scale Integration) | 大规模集成:** 1,000-10,000 components
- **VLSI (Very Large-Scale Integration) | 超大规模集成:** 10,000-1,000,000 components
- **ULSI (Ultra Large-Scale Integration) | 特大规模集成:** >1,000,000 components (modern CPUs)

**中文：**  
- **SSI (小规模集成):** 10-100个元件
- **MSI (中规模集成):** 100-1,000个元件
- **LSI (大规模集成):** 1,000-10,000个元件
- **VLSI (超大规模集成):** 10,000-1,000,000个元件
- **ULSI (特大规模集成):** >1,000,000个元件（现代CPU）

---

## Question 10: DeMorgan's Theorems
## 问题10：德摩根定理

**Question | 问题：**  
State DeMorgan's Theorems  
陈述德摩根定理

**Answer | 答案：**

### DeMorgan's Theorems | 德摩根定理

**English:**  
DeMorgan's Theorems are two fundamental laws in Boolean algebra that describe how to distribute the NOT operation over AND and OR operations.

**中文：**  
德摩根定理是布尔代数中的两个基本定律，描述了如何将NOT运算分配到AND和OR运算上。

### Theorem 1 | 定理1

**English:**  
**The complement of a sum equals the product of the complements.**  
**NOT (A OR B) = NOT A AND NOT B**

**中文：**  
**和的补等于补的积。**  
**非（A 或 B）= 非A 与 非B**

**Mathematical Notation | 数学符号：**
- `(A + B)' = A' · B'`
- `(A ∨ B)' = A' ∧ B'`

**Truth Table Verification | 真值表验证：**
```
A | B | A+B | (A+B)' | A' | B' | A'·B'
--|---|-----|--------|----|----|-------
0 | 0 |  0  |   1    | 1  | 1  |   1
0 | 1 |  1  |   0    | 1  | 0  |   0
1 | 0 |  1  |   0    | 0  | 1  |   0
1 | 1 |  1  |   0    | 0  | 0  |   0
```

### Theorem 2 | 定理2

**English:**  
**The complement of a product equals the sum of the complements.**  
**NOT (A AND B) = NOT A OR NOT B**

**中文：**  
**积的补等于补的和。**  
**非（A 与 B）= 非A 或 非B**

**Mathematical Notation | 数学符号：**
- `(A · B)' = A' + B'`
- `(AB)' = A' + B'`
- `(A ∧ B)' = A' ∨ B'`

**Truth Table Verification | 真值表验证：**
```
A | B | A·B | (A·B)' | A' | B' | A'+B'
--|---|-----|--------|----|----|-------
0 | 0 |  0  |   1    | 1  | 1  |   1
0 | 1 |  0  |   1    | 1  | 0  |   1
1 | 0 |  0  |   1    | 0  | 1  |   1
1 | 1 |  1  |   0    | 0  | 0  |   0
```

### Memory Tips | 记忆技巧

**English:**  
- **Break the bar, change the sign:** When you break the NOT bar over an operation, change AND to OR (or vice versa).
- **NOT (A OR B) = NOT A AND NOT B**
- **NOT (A AND B) = NOT A OR NOT B**

**中文：**  
- **打破横线，改变符号：** 当你在运算上打破NOT横线时，将AND改为OR（或反之）。
- **非（A 或 B）= 非A 与 非B**
- **非（A 与 B）= 非A 或 非B**

### Applications | 应用

**English:**  
DeMorgan's Theorems are used to:
- Simplify Boolean expressions
- Convert between AND-OR and NAND-NOR implementations
- Design logic circuits more efficiently

**中文：**  
德摩根定理用于：
- 简化布尔表达式
- 在AND-OR和NAND-NOR实现之间转换
- 更高效地设计逻辑电路

---

## Question 11: Simplify Using DeMorgan's Theorems
## 问题11：使用德摩根定理简化

**Question | 问题：**  
Simplify the Boolean expression (A·B)'·(C+D)' using DeMorgan's Theorems.  
使用德摩根定理简化布尔表达式 (A·B)'·(C+D)'。

**Answer | 答案：**

### Step-by-Step Solution | 逐步解答

**Given Expression | 给定表达式：**
```
(A·B)'·(C+D)'
```

### Step 1: Apply DeMorgan's Theorem to (A·B)' | 步骤1：对 (A·B)' 应用德摩根定理

**English:**  
According to DeMorgan's Theorem 2: `(A·B)' = A' + B'`

**中文：**  
根据德摩根定理2：`(A·B)' = A' + B'`

**Result | 结果：**
```
(A' + B')·(C+D)'
```

### Step 2: Apply DeMorgan's Theorem to (C+D)' | 步骤2：对 (C+D)' 应用德摩根定理

**English:**  
According to DeMorgan's Theorem 1: `(C+D)' = C'·D'`

**中文：**  
根据德摩根定理1：`(C+D)' = C'·D'`

**Result | 结果：**
```
(A' + B')·(C'·D')
```

### Step 3: Final Simplified Expression | 步骤3：最终简化表达式

**English:**  
The expression can be written as: `(A' + B')·(C'·D')`

**中文：**  
表达式可以写成：`(A' + B')·(C'·D')`

**Final Answer | 最终答案：**
```
(A·B)'·(C+D)' = (A' + B')·(C'·D')
```

### Verification | 验证

**English:**  
We can verify this is correct by checking that both expressions produce the same truth table.

**中文：**  
我们可以通过检查两个表达式是否产生相同的真值表来验证这是正确的。

**Truth Table | 真值表（部分验证）：**
```
A | B | C | D | (A·B)' | (C+D)' | Original | Simplified
--|---|---|---|--------|--------|----------|-----------
0 | 0 | 0 | 0 |   1    |   1    |    1     |     1
0 | 0 | 0 | 1 |   1    |   0    |    0     |     0
0 | 0 | 1 | 0 |   1    |   0    |    0     |     0
0 | 0 | 1 | 1 |   1    |   0    |    0     |     0
0 | 1 | 0 | 0 |   1    |   1    |    1     |     1
1 | 0 | 0 | 0 |   1    |   1    |    1     |     1
1 | 1 | 0 | 0 |   0    |   1    |    0     |     0
1 | 1 | 1 | 1 |   0    |   0    |    0     |     0
```

Both expressions produce the same output, confirming the simplification is correct.  
两个表达式产生相同的输出，确认简化是正确的。

---

**End of Answers | 答案结束**

---

**Note | 注意：**  
These answers are comprehensive bilingual explanations for the in-class activity questions. Use them as a study reference.  
这些答案是课堂活动问题的全面双语解释。请将它们用作学习参考。
