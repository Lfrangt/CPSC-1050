# 📖 Chapter 9: High Level Programming - Python | 高级语言编程 - Python

**Source / 来源:** Ch9_HLL_Python_Pre.pdf & Ch9_HLL_Python_Post.pdf (Dr. Hazra Imran)

---

## 📖 1. What is Programming? | 什么是编程？

**中文：**
- 编程是把一个**大而复杂的任务**拆成越来越小的子任务，直到子任务简单到可以用**基本指令**完成。
- 基本指令包括：**输入 (Input)**、**输出 (Output)**、**数学运算 (Math)**、**条件 (Conditional)**、**重复 (Repetition)**。
- 流程：设计算法 → 用 Python 写代码 → 测试、部署、改进。

**English:**  
Programming is breaking a large, complex task into smaller subtasks until they are simple enough to be performed with basic instructions: Input, Output, Math, Conditional, Repetition. Flow: Design algorithm → Write in Python → Test, deploy, refine.

**关键概念 / Key Concepts:**
- **Programming (编程)** - 用基本指令完成复杂任务的过程
- **Algorithm (算法)** - 解决问题的步骤设计，应先于写代码

---

## 📖 2. Programming Language & Tools | 编程语言与工具

**中文：**
- 本课使用 **Python 3**；Python 3 与旧版**不兼容**。
- 本课**不是** Python 课，而是用 Python 作为工具讲授 CS 基础概念。
- 编程工具：代码编辑器 / IDE（如 **VS Code**、**repl.it**、Python IDLE、Jupyter、pip）。

**English:**  
We use Python 3; it is not backwards compatible. This is not a Python course—Python is a tool to teach fundamental CS concepts. Tools: code editors/IDEs (VS Code, repl.it, IDLE, Jupyter, pip).

**关键概念 / Key Concepts:**
- **IDE (Interactive Development Environment)** - 集成开发环境
- **repl.it** - 最容易上手的在线环境

---

## 📖 3. Algorithm-First Thinking | 算法优先思维

**中文：**
- 常见问题：学生还没想清楚就动手写代码。
- **建议：** 先在注释里**设计算法**，再把它**翻译成代码**。

**English:**  
Common issue: students write code before thinking. Pro tip: design the algorithm in comments first, then translate to code.

---

## 📖 4. First Python Program: Input & Output | 第一个程序：输入与输出

**中文：**
- **print()**：输出到屏幕。
- **input()**：从用户读取输入；可带提示信息，如 `input("What's your name?")`。
- 把输入存到**变量**，再用 **+** 做字符串拼接，如 `"Nice to meet you, " + user`。

**English:**  
`print()` outputs; `input()` reads user input (can include a prompt message). Store input in a variable; use `+` for string concatenation.

**示例 / Example（带行末中文注释，符合你的偏好）：**
```python
print("Hi, what's your name?")     # 问候用户
user = input()                      # 获取用户输入并赋给变量 user
print("Nice to meet you, " + user)  # 输出拼接后的字符串
```

---

## 📖 5. Syntax & Bugs | 语法与错误

**中文：**
- **语法规则 (Syntax rules)** 规定语句结构；违反则无法运行。
- 程序错误叫 **bug**；找出并消除 bug 叫 **debugging（调试）**。

**English:**  
Syntax rules govern structure; violations cause errors. Programming errors = bugs; finding and removing them = debugging.

---

## 📖 6. Types of Values & Type Conversion | 值的类型与类型转换

**中文：**
- **基本类型：** 字符串 (String)、整数 (Integer)、浮点数 (Floating Point)、布尔 (Boolean)、列表 (List)。
- **类型转换：** `int()`、`float()`、`str()` 等，如 `int("42")` → 42，`str(23.4)` → `'23.4'`。

**English:**  
Primitive types: strings, integers, floats, booleans, lists. Convert with `int()`, `float()`, `str()`.

| 英文 (English) | 中文 (Chinese) | 示例 (Example) |
|----------------|----------------|----------------|
| String | 字符串 | `"Hello"`, `'Hi'` |
| Integer | 整数 | `42`, `-4711` |
| Float | 浮点数 | `47.11`, `0.0` |
| Boolean | 布尔 | `True`, `False` |
| List | 列表 | `[22, 33, 56]` |

---

## 📖 7. Variables & Names | 变量与命名

**中文：**
- **变量 (Variable)**：一个名字，指向一个值；存在内存里供后续使用。
- 命名规则：以字母开头；可有数字、下划线；小写开头（惯例）；可用 camelCase 或下划线。**不能**有空格，**不能**用关键字。

**English:**  
A variable is a name that refers to a value. Names: start with letter, can have numbers/underscore, lowercase by convention; no spaces, no keywords.

**注意 / Note:** `age = 12` 与 `print(Age)` 会出错——Python **区分大小写**。

---

## 📖 8. Keywords | 关键字

**中文：**
- 关键字用于识别程序结构，**不能**作为变量名。例如 `print = 5` 会破坏 `print` 函数。

**English:**  
Keywords cannot be used as variable names (e.g. do not use `print` as a variable).

---

## 📖 9. Arithmetic & String Operations | 算术与字符串运算

**中文：**
- 算术运算符：`+` `-` `*` `/` `**`（乘方）。
- 字符串一般**不能**做数学运算；**例外**：`+`（拼接）、`*`（重复，如 `"a"*3` → `"aaa"`）。

**English:**  
Arithmetic: `+`, `-`, `*`, `/`, `**`. Strings: only `+` (concatenation) and `*` (repetition) are allowed.

---

## 📖 10. Indentation (Tab) | 缩进

**中文：**
- Python 对 **tab/缩进** 敏感，缩进有语法含义（尤其在 **if / for** 中）。

**English:**  
Indentation (tab) has meaning in Python—required for control structures.

---

## 📖 11. Selection (Conditional) | 选择（条件）

**中文：**
- **if / elif / else**：根据布尔表达式决定执行哪一块代码。
- 格式：`if` 后加**冒号**，下一行**缩进**；`elif` 可多次；`else` 最多一个。
- 比较用 **`==`**（相等），注意与赋值 `=` 区别。

**English:**  
`if` / `elif` / `else` with boolean expressions; colon after condition; indentation for block. Use `==` for equality.

**模板 / Template:**
```python
if <boolean expression>:    # 条件后必须有冒号，下一行缩进
    ...
elif <boolean expression>:  # 可选，可重复
    ...
else:                       # 可选，每个 if 最多一个 else
    ...
```

---

## 📖 12. Loops (Repetition) | 循环（重复）

**中文：**
- **作用：** 同一段代码重复执行多次，避免重复写多遍。
- **for 循环**：按**序列**或 **range** 重复固定次数。
- **range(n)**：0 到 n-1（不包含 n）。
- **range(start, end)**：start 到 **end-1**（**end 不包含**，即 Python 里的 **stop**）。
- **range(start, stop, step)**：从 start 开始、步长为 step、**小于 stop** 的整数；stop 不包含。例如 `range(2, 7, 2)` → 2, 4, 6。

**English:**  
Loops repeat a block without rewriting. `for` loops over a sequence or `range()`. `range(n)` → 0..n-1; `range(start, end)` → start..end-1 (**end** is exclusive, often called **stop**). `range(start, stop, step)` → start, start+step, ... up to but **not including** stop (e.g. `range(2, 7, 2)` → 2, 4, 6).

**格式 / Format:**
```python
for var in <sequence>:      # 或 for i in range(n):
    statement_1              # 缩进块
    statement_2
```

**示例 / Example:**
```python
for value in [22, 33, 56]:
    print(value)             # 依次输出 22, 33, 56
    print(value * 100)       # 再输出 2200, 3300, 5600

for i in range(3):
    do_something()          # 执行 3 次，i 依次为 0, 1, 2
```

---

## 📝 术语表 / Terminology Table

| 英文 (English) | 中文 (Chinese) | 定义 (Definition) |
|----------------|----------------|-------------------|
| Programming | 编程 | 用基本指令完成复杂任务的过程 |
| Algorithm | 算法 | 解决问题的步骤设计 |
| Variable | 变量 | 指向某个值的名字 |
| Syntax | 语法 | 规定语句结构的规则 |
| Bug / Debugging | 错误 / 调试 | 程序错误；查找并修复错误 |
| Conditional / Selection | 条件 / 选择 | if/elif/else 分支 |
| Loop / Repetition | 循环 / 重复 | for/while 重复执行 |
| Concatenation | 拼接 | 字符串用 + 连接 |
| Indentation | 缩进 | 用 tab/空格表示代码块 |

---

## 📝 本周学习建议 / This Week's Suggestions

1. **先练一个完整小程序**：按讲义做一遍 Greeting Chatbot（问名字、问喜欢的电影、评论），确保会用 `print`、`input`、变量、拼接。
2. **再练条件**：写“天气”程序：输入 sunny → 输出 Go swimming；rainy → Stay at home；用 `if/elif/else`。
3. **最后练循环**：用 `for i in range(n)` 和 `for x in [a,b,c]` 各写一个小例子。
4. **Quiz 准备**：本章 Quiz 很可能考：`input()`/`print()` 用法、变量命名规则、类型转换、`if/elif/else` 模板、`for` 与 `range()` 的含义。建议用「生成 Ch9 quiz」再练一轮选择题。

---

## 快速命令 / Quick Commands

- 需要**本章 Quiz 练习题**时可以说：「生成 Chapter 9 Python 的 quiz」或「Generate Ch9 quiz」
- 有**作业或代码**要批改时说：「批改这份作业」或「帮我看看这段代码」
- 需要**查漏补缺**时说：「根据 Ch9 笔记帮我查漏补缺」
