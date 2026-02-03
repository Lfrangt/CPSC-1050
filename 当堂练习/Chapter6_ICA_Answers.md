# CPSC 1050 Chapter 6 - In-Class Activity 答案

---

## Question 1: Programming Languages Analogy | 编程语言类比

**Explain why we need programming languages using an analogy from everyday life.**

**Answer:**

**Analogy: Programming languages are like recipes for a chef.**

- **Machine language** = Raw ingredients in their most basic form (flour, eggs, water) — the chef (CPU) can use them directly, but it's tedious and error-prone to work with.
- **Assembly language** = Simple cooking instructions like "mix," "bake," "stir" — easier to read than raw ingredients, but still very detailed.
- **High-level language** = A full recipe in plain English: "Make a chocolate cake" — one instruction accomplishes many steps.

Just as we need recipes to communicate cooking instructions clearly, we need programming languages to communicate instructions to computers in a way that humans can write and understand, and that can be translated into the binary signals the computer actually executes.

---

**中文：** 编程语言就像厨师的食谱。机器语言是原始食材，汇编语言是简单指令（搅拌、烘烤），高级语言是完整食谱（“做一个巧克力蛋糕”）。我们需要编程语言，就像需要食谱一样，用人类能理解的方式把指令传达给计算机，再转换成计算机能执行的二进制信号。

---

## Question 2: Language Choice for Online Store Orders | 在线商店订单处理的语言选择

**Would you choose high-level language, assembly, or machine language? Justify your answer with examples.**

**Answer:**

**I would choose a high-level language** (e.g., Python, Java, JavaScript).

**Justification:**

1. **Readability & maintainability:** Processing orders involves complex logic (inventory checks, payment validation, shipping calculations). High-level code like `total = price * quantity` is easy to read and modify.
2. **Development speed:** Building an online store requires many features quickly. High-level languages have libraries (e.g., for databases, web frameworks) that speed up development.
3. **Portability:** The same code can run on different servers without rewriting.
4. **Why NOT assembly/machine:** Assembly and machine language are used for low-level tasks (device drivers, embedded systems). For business logic like order processing, they would be unnecessarily slow to write and nearly impossible to maintain.

**Example:** In Python: `order_total = sum(item.price * item.quantity for item in cart)` — one line. In assembly, this would require dozens of instructions.

---

**中文：** 选择高级语言。原因：可读性强、开发效率高、可移植性好。订单处理涉及复杂业务逻辑，高级语言更合适。汇编和机器语言适合底层任务，不适合电商应用。

---

## Question 3: Shortest Route Algorithm | 最短路径算法

**Outline an algorithm in plain English for how the app might determine the best route for delivery drivers.**

**Answer:**

1. **Get inputs:** Collect the driver's current location, the list of delivery addresses, and any constraints (e.g., time windows, vehicle capacity).
2. **Build a map:** Represent all locations (warehouse, stops) as points and roads as connections with distances (or travel times).
3. **Calculate distances:** For each pair of locations, compute the distance or estimated travel time (using road network data or GPS).
4. **Find the shortest route:** Use an algorithm (e.g., Dijkstra's or a route optimization algorithm) to find the order of stops that minimizes total distance or time.
5. **Apply constraints:** Check that the route respects delivery windows and capacity limits. If not, adjust the order.
6. **Output the route:** Display the ordered list of stops with directions (e.g., "Stop 1: 123 Main St, then Stop 2: 456 Oak Ave...").

---

**中文：** ① 获取输入（当前位置、配送地址列表、约束条件）② 构建地图（地点和道路）③ 计算各点间距离或时间 ④ 用算法（如 Dijkstra）找最短路径 ⑤ 检查约束并调整 ⑥ 输出有序配送路线。

---

## Question 4: Self-Checkout System Design (IPO) | 自助结账系统设计

**Identify: Input, Process, Output**

**Answer:**

| Component | Description |
|-----------|-------------|
| **Input** | Product barcode/QR code (scanned), quantity, payment method (card/cash), loyalty card ID (optional), bagging sensor data |
| **Process** | Look up product price from database; calculate subtotal; apply discounts/coupons; add tax; process payment (validate card, count cash); update inventory; print receipt |
| **Output** | Display item names and prices on screen; total amount; receipt; change (if cash); confirmation message |

---

**中文：** 输入：条形码、数量、支付方式、会员卡。处理：查价、计算小计、折扣、税费、支付验证、更新库存。输出：屏幕显示、收据、找零、确认信息。

---

## Question 5: Customer Loyalty Points Pseudocode | 会员积分伪代码

**Write pseudocode for:**
1. Ask for customer's name
2. Ask how many purchases they made
3. Multiply purchases by 10 to calculate points
4. Display the customer's total points

**Answer:**

```
Start
  Write "Enter your name: "
  Read customerName
  Write "How many purchases did you make? "
  Read numberOfPurchases
  Set totalPoints to numberOfPurchases * 10
  Write customerName + ", your total points are: " + totalPoints
End
```

---

## Question 6: Coffee Machine Control Structures | 咖啡机控制结构

**What types of control structures (sequence, decision-making, looping) for each scenario?**

| Scenario | Control Structure | Reason |
|----------|-------------------|--------|
| **Selecting coffee size** | **Decision-making** | User chooses one option (small/medium/large) from multiple choices based on their selection |
| **Adding sugar or milk** | **Decision-making** | User selects yes/no or amount — different paths based on choice |
| **Refilling water when it runs low** | **Decision-making** (or **Looping** + Decision) | Check *if* water level is low → trigger refill. Could also use a loop that repeatedly checks water level until it's sufficient |

---

**中文：** 选择咖啡大小 → 决策（多选一）；加糖/奶 → 决策（是/否或数量）；水位低时加水 → 决策（条件判断）或 循环+决策（持续检测直到加满）。

---

## Question 7: Assembly Instructions Analysis | 汇编指令分析

**What does this program do?**

```
LOD A
SUB B
JNG END
STO C
END STP
```

**Answer:**

- **LOD A** — Load the value at memory location A into the accumulator
- **SUB B** — Subtract the value at B from the accumulator (result: A - B)
- **JNG END** — If the result is negative or zero, jump to END (stop)
- **STO C** — Store the accumulator value into memory location C (only if A - B > 0)
- **END STP** — Stop the program

**Summary:** The program computes **max(A - B, 0)**. If A > B, it stores (A - B) in C. If A ≤ B, it does nothing and stops (C is unchanged). This is equivalent to finding the positive difference between A and B.

---

**中文：** 程序计算 max(A - B, 0)。若 A > B，将 (A - B) 存入 C；若 A ≤ B，直接停止，C 不变。相当于求 A 和 B 的正差值。

---

## Question 8: Programming Error | 编程错误

**A program calculates `area = length × width` but was written as `area = length + width`.**
- **What type of error is this?**
- **How would you identify and fix it?**

**Answer:**

**Type of error: Logical error (逻辑错误)**

- The code runs without crashing (no syntax error).
- The output is wrong because the formula is incorrect.

**How to identify:**
1. **Testing:** Run with known values (e.g., length=5, width=4). Expected area=20, but program outputs 9 → error found.
2. **Code review:** Carefully read the formula and compare to the mathematical definition.
3. **Debugging:** Use a debugger to inspect variable values during execution.

**How to fix:** Change `area = length + width` to `area = length * width` (use multiplication, not addition).

---

**中文：** 这是逻辑错误。程序能运行但结果错误。识别方法：用已知数据测试（如 5×4=20，程序输出 9 则出错）、代码审查、调试器。修复：将 `+` 改为 `*`。

---

## Question 9: Software Testing - Login System | 登录系统测试用例

**List three different test cases for an online login system.**

**Answer:**

| Test Case | Input | Expected Result |
|------------|-------|-----------------|
| **1. Valid login** | Correct username + correct password | User is logged in and redirected to dashboard |
| **2. Invalid password** | Correct username + wrong password | Error message: "Invalid password" or "Login failed"; user remains on login page |
| **3. Empty fields** | Username or password left blank | Error message: "Please enter username and password"; form is not submitted |

**Additional useful test cases:**
- **Invalid username:** Wrong username → "User not found" or "Invalid credentials"
- **SQL injection / security:** Malicious input (e.g., `' OR '1'='1`) → System rejects or sanitizes input
- **Lockout after failed attempts:** Multiple wrong passwords → Account temporarily locked

---

**中文：** ① 正确用户名+正确密码 → 登录成功 ② 正确用户名+错误密码 → 显示错误，留在登录页 ③ 用户名或密码为空 → 提示必填，不提交。

---

## Question 10: ATM Withdrawal Flowchart | ATM 取款流程图

**Draw a simple flowchart for withdrawing money from an ATM.**

**Answer (Text-based representation):**

```
[Start] 
    ↓
[Insert Card]
    ↓
[Enter PIN]
    ↓
<PIN correct?> ——No——→ [Display "Invalid PIN"] → [End]
    |Yes
    ↓
[Select "Withdraw"]
    ↓
[Enter Amount]
    ↓
<Amount valid? (≤ balance, ≤ daily limit)> ——No——→ [Display "Invalid amount"] → [End]
    |Yes
    ↓
[Dispense Cash]
    ↓
[Update Account Balance]
    ↓
[Print Receipt]
    ↓
[End]
```

**Symbols used:**
- **Oval:** Start/End
- **Parallelogram:** Input/Output (Insert card, Enter PIN, Enter amount, Display messages, Dispense cash, Print receipt)
- **Rectangle:** Process (Update balance)
- **Diamond:** Decision (PIN correct? Amount valid?)
- **Arrows:** Flow direction

---

**中文：** 流程图步骤：开始 → 插卡 → 输入 PIN → 判断 PIN 是否正确 → 选择取款 → 输入金额 → 判断金额是否有效 → 出钞 → 更新余额 → 打印凭条 → 结束。

---

*End of Answers | 答案结束*
