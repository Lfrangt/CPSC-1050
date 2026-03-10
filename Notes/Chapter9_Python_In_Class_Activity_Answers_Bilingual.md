# CPSC 1050 Chapter 9 Python – 课堂练习答案（中英双语）
# Chapter 9 Python In-Class Activity – Bilingual Answers

---

## Question 1 | 第 1 题

**题目 (Full question):**  
Name two tools that can be used to write and run Python code.

**题目（中文）：**  
说出两种可以用来编写和运行 Python 代码的工具。

---

**答案 / Answer**

**中文：**  
例如：**VS Code**（代码编辑器/IDE）、**repl.it**（在线环境）、**Python IDLE**、**Jupyter Notebook**、**PyCharm** 等。任选两个即可。

**English:**  
e.g. **VS Code** (editor/IDE), **repl.it** (online), **Python IDLE**, **Jupyter**, **PyCharm**. Any two are acceptable.

---

## Question 2 | 第 2 题

**题目 (Full question):**  
What is the purpose of the Python interpreter?

**题目（中文）：**  
Python 解释器（interpreter）的作用是什么？

---

**答案 / Answer**

**中文：**  
解释器负责**逐行读取并执行** Python 源代码：把人类可读的代码翻译成机器能执行的指令，并立即运行。不事先编译成单独的可执行文件（与“编译型”语言相对）。

**English:**  
The interpreter **reads and executes** Python source code line by line—translating human-readable code into instructions the machine can run. It does not compile to a separate executable first (unlike compiled languages).

---

## Question 3 | 第 3 题

**题目 (Full question):**  
What is the difference between concatenation and arithmetic operations in Python?

**题目（中文）：**  
在 Python 中，拼接（concatenation）和算术运算（arithmetic operations）有什么区别？

---

**答案 / Answer**

**中文：**  
- **拼接 (Concatenation)**：针对**字符串 (string)**，用 `+` 把多个字符串**首尾相连**成新字符串，如 `"Hello" + " " + "World"` → `"Hello World"`。  
- **算术运算 (Arithmetic)**：针对**数字**（整数、浮点数），用 `+` `-` `*` `/` 等做数学计算，如 `3 + 5` → `8`。  
- 若对数字和字符串混用 `+` 会报错（type error），需先转换类型（如 `str(3)` 或 `int("5")`）。

**English:**  
- **Concatenation**: For **strings**—`+` joins strings end-to-end (e.g. `"Hello" + "World"` → `"HelloWorld"`).  
- **Arithmetic**: For **numbers** (int/float)—`+`, `-`, `*`, `/` perform math (e.g. `3 + 5` → `8`).  
- Mixing number and string with `+` causes a type error; use type conversion first.

---

## Question 4 | 第 4 题

**题目 (Full question):**  
What does `int("42")` do in Python?

**题目（中文）：**  
在 Python 中，`int("42")` 的作用是什么？

---

**答案 / Answer**

**中文：**  
**类型转换 (type conversion)**：把**字符串** `"42"` 转换成**整数** `42`，结果是整数类型，可以参与算术运算。

**English:**  
**Type conversion**: Converts the **string** `"42"` to the **integer** `42`, so you can use it in arithmetic.

---

## Question 5 | 第 5 题

**题目 (Full question):**  
What is the difference between if, elif, and else in Python?

**题目（中文）：**  
在 Python 中，if、elif 和 else 有什么区别？

---

**答案 / Answer**

**中文：**  
- **if**：第一个条件；若为 True，执行对应块，后面的 elif/else 不再判断。  
- **elif**：在 if 为 False 时再判断；可写多个，按顺序判断，第一个为 True 的会执行。  
- **else**：前面所有 if/elif 都为 False 时执行，**不需要再写条件**，每个 if 结构最多一个 else。

**English:**  
- **if**: First condition; if True, run its block and skip the rest.  
- **elif**: Checked only when the previous if (and earlier elifs) are False; can have multiple.  
- **else**: Runs when all if/elif conditions are False; no condition; at most one per if-structure.

---

## Question 6 | 第 6 题

**题目 (Full question):**  
What does `range(4)` do in a for loop?

**题目（中文）：**  
在 for 循环中，`range(4)` 表示什么？

---

**答案 / Answer**

**中文：**  
`range(4)` 生成从 **0 到 3** 的整数序列（共 4 个数：0, 1, 2, 3），不包含 4。  
在 `for i in range(4):` 中，循环会**执行 4 次**，`i` 依次取 0、1、2、3。

**English:**  
`range(4)` produces the integers **0, 1, 2, 3** (4 values; 4 is excluded).  
In `for i in range(4):`, the loop runs **4 times** with `i` = 0, 1, 2, 3.

---

## Question 7 | 第 7 题

**题目 (Full question):**  
How many times will the following loop execute?  
`for i in range(2, 7, 2): print(i)`

**题目（中文）：**  
下面的循环会执行几次？  
`for i in range(2, 7, 2): print(i)`

---

**答案 / Answer**

**中文：**  
`range(2, 7, 2)` 表示从 2 开始、步长为 2、小于 7 的整数：**2, 4, 6**（共 3 个）。  
所以循环体 `print(i)` **执行 3 次**，依次输出 2、4、6。

**English:**  
`range(2, 7, 2)` gives start=2, step=2, stop=7 (exclusive): **2, 4, 6** — three values.  
The loop runs **3 times**, printing 2, then 4, then 6.

---

## Question 8 | 第 8 题

**题目 (Full question):**  
What happens if we use elif without an if statement?

**题目（中文）：**  
如果没有 if 语句而直接使用 elif，会怎样？

---

**答案 / Answer**

**中文：**  
会报**语法错误 (SyntaxError)**。`elif` 和 `else` 必须紧跟在某个 `if`（或前一个 `elif`）之后，不能单独出现；Python 要求条件分支从 `if` 开始。

**English:**  
You get a **SyntaxError**. `elif` (and `else`) must follow an `if` (or previous `elif`); they cannot stand alone. A conditional block must start with `if`.

---

## Question 9 | 第 9 题

**题目 (Full question):**  
In Python, `==` is used for \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ while `=` is used for \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_.

**题目（中文）：**  
在 Python 中，`==` 用于 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ ，而 `=` 用于 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ 。

---

**答案 / Answer**

**中文：**  
- `==` 用于**比较/判断相等 (comparison / equality)**。  
- `=` 用于**赋值 (assignment)**，把右边的值赋给左边的变量。

**English:**  
- `==` is used for **comparison / equality checking**.  
- `=` is used for **assignment** (giving a value to a variable).

---

## Question 10 | 第 10 题

**题目 (Full question):**  
The `if` statement in Python requires a \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ at the end of the condition.

**题目（中文）：**  
Python 的 `if` 语句在条件末尾需要一个 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ 。

---

**答案 / Answer**

**中文：**  
**冒号 (colon)** `:` 。条件写完后必须加冒号，下一行缩进写条件成立时要执行的代码块。

**English:**  
A **colon** `:`. The condition must end with `:`, and the block that runs when the condition is true is indented on the next line(s).

---

## Question 11 | 第 11 题

**题目 (Full question):**  
The function used to convert a string "42" into an integer is \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_.

**题目（中文）：**  
把字符串 "42" 转换成整数所用的函数是 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ 。

---

**答案 / Answer**

**中文：**  
**`int()`** 。例如 `int("42")` 得到整数 `42`。

**English:**  
**`int()`**. e.g. `int("42")` returns the integer `42`.

---

## Question 12 | 第 12 题

**题目 (Full question):**  
A loop that continues until a condition is false is called a \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ loop.

**题目（中文）：**  
一直执行到条件为假才停止的循环叫做 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ 循环。

---

**答案 / Answer**

**中文：**  
**while** 循环。格式：`while condition:` ，先判断条件，为 True 则执行块，再判断，直到条件为 False 才退出。

**English:**  
A **while** loop. Syntax: `while condition:` — it keeps running the block while the condition is True, and stops when the condition becomes False.

---

## Question 13 | 第 13 题

**题目 (Full question):**  
In Python, indentation is used to indicate a \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ block.

**题目（中文）：**  
在 Python 中，缩进用来表示一个 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ 块。

---

**答案 / Answer**

**中文：**  
**代码块 (code block)** 或 **语句块 (statement block)**。同一缩进级别的连续语句属于同一个块（如 if、for、while 后面的 body）。

**English:**  
A **code block** (or **statement block**). Lines with the same indentation form one block (e.g. the body of an `if`, `for`, or `while`).

---

## Question 14 | 第 14 题

**题目 (Full question):**  
(a) Find 2 syntax errors in the code.  
(b) What happens if the user enters a number instead of a name?

Code:
```python
name input("What is your name? ")
print("Hello" + name)
if len(name) > 5:
    print("You have a long name!")
else:
    print("Nice to meet you!")
```

**题目（中文）：**  
(a) 找出代码中的 2 处语法错误。  
(b) 如果用户输入的是数字而不是名字，会怎样？

---

**答案 / Answer**

**中文：**  
**(a) 两处语法错误：**  
1. 第一行：`name input(...)` 错误——**缺少赋值号 `=`**，应改为 `name = input("What is your name? ")`。  
2. 第二行：`"Hello" + name` 中间**缺少空格**，若希望显示 "Hello 名字"，应写成 `"Hello " + name` 或 `"Hello" + " " + name`。（若题目只要求“语法错误”，通常第一处必写；第二处也可视为缺少 `if` 后的**冒号**——若原题 if 行没有 `:`，则缺少冒号是第二处语法错误。常见标准答案：① 缺少 `=` ② if 条件后缺少 `:`。）

**(b) 用户输入数字：**  
`input()` 始终返回**字符串**，所以即使用户输入 `123`，`name` 也是 `"123"`。`len(name)` 对字符串有效，得到长度 3；`"Hello" + name` 仍是字符串拼接，会输出 `Hello123`。**不会**因输入是数字而报类型错误；若题目强调“输入数字”，可以答：行为上会把数字当作普通字符串处理，没有类型错误。

**English:**  
**(a) Two syntax errors:**  
1. First line: **missing `=`** — should be `name = input("What is your name? ")`.  
2. Either: missing space in `"Hello" + name` (so output has no space), or **missing colon `:`** after `if len(name) > 5` (if the original code had no colon).  

**(b) User enters a number:**  
`input()` always returns a **string**, so e.g. `123` becomes `"123"`. `len(name)` works (e.g. 3), and `"Hello" + name` is string concatenation (e.g. `"Hello123"`). No type error; the number is just treated as a string.

---

## Question 15 | 第 15 题

**题目 (Full question):**  
Why do we use indentation in Python?

**题目（中文）：**  
为什么在 Python 中要使用缩进？

---

**答案 / Answer**

**中文：**  
Python 用缩进来**界定代码块**，而不是像 C/Java 那样用大括号 `{}`。同一缩进表示同一层级（如都属于同一个 if 或 for），这样结构清晰，也强制写出易读的格式。

**English:**  
Indentation **defines code blocks** in Python (instead of braces `{}` in C/Java). Same indentation = same block (e.g. body of one `if` or `for`), so structure is clear and code stays readable.

---

## Question 16 | 第 16 题

**题目 (Full question):**  
What is the difference between a `while` loop and a `for` loop?

**题目（中文）：**  
`while` 循环和 `for` 循环有什么区别？

---

**答案 / Answer**

**中文：**  
- **while**：先判断**条件**，为 True 就执行一次块，再判断，直到条件为 False；**次数不固定**，由条件决定。  
- **for**：遍历一个**序列**（如列表）或 **range**，**次数通常已知**，每次取一个元素或一个索引。  
- 若已知次数或要遍历序列，常用 `for`；若“一直做到某条件不满足”，用 `while`。

**English:**  
- **while**: Repeats while a **condition** is True; **number of iterations** can be unknown.  
- **for**: Iterates over a **sequence** or **range**; **number of iterations** is usually fixed (e.g. once per element).  
- Use `for` when you have a known sequence/count; use `while` when you “repeat until a condition becomes false”.

---

## Question 17 | 第 17 题

**题目 (Full question):**  
What will `print(10 // 3)` output? Explain why.

**题目（中文）：**  
`print(10 // 3)` 会输出什么？请解释原因。

---

**答案 / Answer**

**中文：**  
输出 **3**。  
`//` 是**整数除法（floor division）**：只保留商的整数部分，舍去小数。10 ÷ 3 = 3.333…，整数部分为 3，所以 `10 // 3` 的结果是 `3`。

**English:**  
It prints **3**.  
`//` is **integer (floor) division**: it gives the quotient and drops the remainder. 10 ÷ 3 = 3.333…, so the integer part is **3**.

---

## Question 18 | 第 18 题

**题目 (Full question):**  
For the code below, identify the issues. No code fixing needed.

**(a)**  
```python
x = 10
if x = 10:
```

**(b)**  
```python
name = input("Enter your name: ")
if name == "";
print("Hello, " + name)
```

**(c)**  
```python
"Hello" * "3"
```

**题目（中文）：**  
指出下面代码中的问题。不需要修改代码。  
(a)(b)(c) 三段分别指出问题。

---

**答案 / Answer**

**中文：**  
- **(a)** `if x = 10:` 用了**一个等号 `=`**。在条件里应使用**比较运算符 `==`** 判断相等；`=` 是赋值，在 if 条件中会报 **SyntaxError**（或非法语法）。  
- **(b)** 两处问题：① `if name == ""` 末尾用了**分号 `;`**，应为**冒号 `:`**，否则 **SyntaxError**。② `print("Hello, " + name)` **缩进错误**：应缩进到 if 块内，否则不属于该 if，逻辑错误（且若上一行缺冒号，还会引发语法错误）。  
- **(c)** `"Hello" * "3"`：`*` 可以用于**字符串 × 整数**（重复字符串），但不能**字符串 × 字符串**。这里 `"3"` 是字符串，会报 **TypeError: can't multiply sequence by non-int of type 'str'**。

**English:**  
- **(a)** In `if x = 10:` the **single `=`** is assignment. In a condition you must use **`==`** for equality; using `=` here causes a **SyntaxError**.  
- **(b)** ① Use **colon `:`** after the condition, not semicolon `;` — otherwise **SyntaxError**. ② The **`print` line must be indented** under the `if` so it is part of the if-block; otherwise logic is wrong (and with the wrong punctuation you get syntax errors).  
- **(c)** `*` can do string × integer (repeat), but not string × string. `"3"` is a string → **TypeError** (can't multiply sequence by non-int of type 'str').

---

## Question 19 | 第 19 题

**题目 (Full question):**  
Write a simple Python program that:  
(a) Asks the user to enter a number between 3 and 6 (representing sides of a shape).  
(b) If the user enters 3, print "That's a Triangle!"; 4 → "That's a Square or Rectangle!"; 5 → "That's a Pentagon!"; 6 → "That's a Hexagon!"  
(c) If they enter a number outside the range, print "Sorry, I don't know that shape!"

**题目（中文）：**  
编写一个简单的 Python 程序：  
(a) 让用户输入 3 到 6 之间的数字（表示图形的边数）。  
(b) 若输入 3 输出 "That's a Triangle!"；4 → "That's a Square or Rectangle!"；5 → "That's a Pentagon!"；6 → "That's a Hexagon!"  
(c) 若输入超出范围，输出 "Sorry, I don't know that shape!"

---

**答案 / Answer**

**中文：**  
用 `input()` 读入字符串，用 `int()` 转成整数，再用 `if` / `elif` / `else` 按 3、4、5、6 和“其他”分别输出即可。

**English:**  
Read with `input()`, convert with `int()`, then use `if`/`elif`/`else` for 3, 4, 5, 6 and the default message.

**参考代码 / Sample code（行末中文注释）：**
```python
sides = input("Enter number of sides (3-6): ")   # 提示用户输入边数
sides = int(sides)                               # 将字符串转为整数
if sides == 3:                                   # 3 条边 → 三角形
    print("That's a Triangle!")
elif sides == 4:                                 # 4 条边 → 正方形或矩形
    print("That's a Square or Rectangle!")
elif sides == 5:                                 # 5 条边 → 五边形
    print("That's a Pentagon!")
elif sides == 6:                                 # 6 条边 → 六边形
    print("That's a Hexagon!")
else:                                            # 超出 3–6 范围
    print("Sorry, I don't know that shape!")
```

---

## 快速命令 / Quick Commands

- 需要 **Chapter 9 选择题练习**：说「生成 Chapter 9 Python 的 quiz」
- 有**作业或代码**要批改：说「批改这份作业」或「帮我看看这段代码」
- 需要**查漏补缺**：说「根据 Ch9 笔记帮我查漏补缺」
