# Chapter 9: Python — 本周 Quiz 练习
# Chapter 9: High-Level Programming (Python) — This Week's Quiz Practice

**范围 Scope:** 仅 Chapter 9 知识点 | Only Ch9 topics  
**题型 Format:** 全选择题 All Multiple Choice · 中英双语 Bilingual

---

## 1. 工具与概念 / Tools & Concepts

**Q1.** Which of the following is a tool that can be used to write and run Python code?  
**以下哪种可以用来编写和运行 Python 代码？**

A) Microsoft Word  
B) **repl.it**  
C) PowerPoint  
D) Excel  

<details>
<summary>Answer / 答案</summary>
**B** — repl.it 是在线 Python 环境；VS Code、IDLE、Jupyter 等也可。  
repl.it is an online Python environment; VS Code, IDLE, Jupyter are also valid.
</details>

---

**Q2.** What is the purpose of the Python **interpreter**?  
**Python 解释器（interpreter）的作用是什么？**

A) To compile code into a single executable file / 把代码编译成一个可执行文件  
B) **To read and execute source code line by line / 逐行读取并执行源代码**  
C) To delete bugs automatically / 自动删除 bug  
D) To convert Python to Java / 把 Python 转成 Java  

<details>
<summary>Answer / 答案</summary>
**B** — 解释器逐行读取并执行代码，不先编译成单独可执行文件。  
Interpreter reads and executes code line by line; it does not compile to a separate executable first.
</details>

---

**Q3.** This course uses **Python 3**. Which statement is true?  
**本课使用 Python 3。以下哪句正确？**

A) Python 3 is fully backwards compatible with Python 2.  
B) **Python 3 is not backwards compatible with older versions. / Python 3 与旧版不兼容。**  
C) Python 3 can only run on Windows.  
D) Python 3 is the same as Java.  

<details>
<summary>Answer / 答案</summary>
**B** — Python 3 与 Python 2 等旧版不兼容。  
Python 3 is not backwards compatible with Python 2.
</details>

---

## 2. 输入输出与变量 / Input, Output & Variables

**Q4.** What does `input("Your name? ")` return in Python 3?  
**在 Python 3 中，input("Your name? ") 返回什么？**

A) An integer / 整数  
B) **A string / 字符串**  
C) A float / 浮点数  
D) None  

<details>
<summary>Answer / 答案</summary>
**B** — `input()` 始终返回字符串；若要数字需用 `int()` 或 `float()` 转换。  
input() always returns a string; use int() or float() to convert to number.
</details>

---

**Q5.** Which line correctly stores user input in a variable?  
**哪一行能正确把用户输入存到变量里？**

A) `user = "input"`  
B) **`user = input()`**  
C) `input = user`  
D) `user := input()`  

<details>
<summary>Answer / 答案</summary>
**B** — `user = input()` 把用户输入的内容赋给变量 `user`。  
user = input() assigns the user's input to the variable user.
</details>

---

**Q6.** In Python, `age = 12` but we write `print(Age)`. What happens?  
**在 Python 中，若写了 age = 12 却用 print(Age)，会怎样？**

A) It prints 12.  
B) **An error, because Python is case-sensitive. / 报错，因为 Python 区分大小写。**  
C) It prints "Age".  
D) It prints nothing.  

<details>
<summary>Answer / 答案</summary>
**B** — 变量名区分大小写；`Age` 和 `age` 是不同变量。  
Variable names are case-sensitive; Age and age are different.
</details>

---

## 3. 类型与类型转换 / Types & Type Conversion

**Q7.** What is the result of `int("42")`?  
**int("42") 的结果是？**

A) `"42"`  
B) **`42` (integer)**  
C) `42.0`  
D) Error / 报错  

<details>
<summary>Answer / 答案</summary>
**B** — `int()` 把字符串转为整数，得到 42。  
int() converts the string to integer 42.
</details>

---

**Q8.** To use a number from `input()` in arithmetic, we should:  
**要把 input() 得到的数用于算术运算，应该：**

A) Use it directly: `x = input()` then `x + 1`.  
B) **Convert it: e.g. `x = int(input())` or `x = float(input())`. / 先转换，如 int(input()) 或 float(input())。**  
C) Use `number(x)`.  
D) Python does this automatically.  

<details>
<summary>Answer / 答案</summary>
**B** — input() 返回字符串，做数学前要用 int() 或 float() 转换。  
input() returns a string; convert with int() or float() before math.
</details>

---

**Q9.** Which of the following is a **Boolean** value in Python?  
**以下哪个是 Python 中的布尔值？**

A) `"True"`  
B) **`True`**  
C) `1`  
D) `yes`  

<details>
<summary>Answer / 答案</summary>
**B** — 布尔类型是 `True` 和 `False`（首字母大写）。  
Boolean values are True and False (capitalized).
</details>

---

## 4. 字符串运算 / String Operations

**Q10.** What does `"Hi" + "!"` produce?  
**"Hi" + "!" 的结果是？**

A) Error  
B) **`"Hi!"`**  
C) `"Hi" "!"`  
D) `2`  

<details>
<summary>Answer / 答案</summary>
**B** — 字符串的 `+` 是拼接 (concatenation)。  
+ for strings is concatenation → "Hi!".
</details>

---

**Q11.** What is the result of `"ab" * 3`?  
**"ab" * 3 的结果是？**

A) `"ab3"`  
B) **`"ababab"`**  
C) Error  
D) `6`  

<details>
<summary>Answer / 答案</summary>
**B** — 字符串 `*` 整数表示重复该字符串若干次。  
String * int repeats the string → "ababab".
</details>

---

**Q12.** What is the difference between **concatenation** and **arithmetic** `+` in Python?  
**Python 中拼接（concatenation）和算术的 + 有什么区别？**

A) They are the same.  
B) **Concatenation joins strings; arithmetic + adds numbers. / 拼接连接字符串；算术 + 对数字做加法。**  
C) Concatenation only works with lists.  
D) Arithmetic + only works with strings.  

<details>
<summary>Answer / 答案</summary>
**B** — 对字符串用 + 是拼接；对数字用 + 是加法。混用会报错，需先转换类型。  
+ for strings = concatenation; + for numbers = addition. Mixing causes type error.
</details>

---

## 5. 条件与语法 / Conditionals & Syntax

**Q13.** In Python, `==` is used for \_\_\_\_\_ and `=` is used for \_\_\_\_\_.  
**在 Python 中，== 用于 \_\_\_\_\_ ，= 用于 \_\_\_\_\_ 。**

A) assignment; comparison  
B) **comparison (equality); assignment / 比较（相等）；赋值**  
C) both mean the same  
D) printing; input  

<details>
<summary>Answer / 答案</summary>
**B** — `==` 判断相等；`=` 是赋值。  
== checks equality; = assigns a value.
</details>

---

**Q14.** The `if` statement in Python must end with a \_\_\_\_\_ before the indented block.  
**Python 的 if 语句在条件后、缩进块前必须以 \_\_\_\_\_ 结尾。**

A) semicolon `;`  
B) **colon `:` / 冒号**  
C) comma `,`  
D) period `.`  

<details>
<summary>Answer / 答案</summary>
**B** — 条件后必须加冒号 `:`，下一行缩进写代码块。  
Condition must end with colon : ; next line(s) indented form the block.
</details>

---

**Q15.** What happens if we use `elif` without a preceding `if`?  
**如果没有前面的 if 而单独写 elif，会怎样？**

A) It runs normally.  
B) **SyntaxError. / 语法错误。**  
C) It is treated as `if`.  
D) It is ignored.  

<details>
<summary>Answer / 答案</summary>
**B** — `elif` 和 `else` 必须跟在 `if`（或前一个 `elif`）之后，不能单独出现。  
elif and else must follow an if (or previous elif); they cannot stand alone.
</details>

---

**Q16.** Which can **not** be used as a variable name in Python?  
**以下哪个不能作为 Python 变量名？**

A) `user_name`  
B) `count2`  
C) **`print`**  
D) `my_var`  

<details>
<summary>Answer / 答案</summary>
**C** — `print` 是内置函数/关键字，用作变量名会覆盖原有功能，应避免。  
print is a built-in; using it as a variable name shadows the built-in and should be avoided.
</details>

---

## 6. 循环与 range / Loops & range

**Q17.** What values does `range(4)` produce?  
**range(4) 产生哪些值？**

A) 1, 2, 3, 4  
B) 1, 2, 3  
C) **0, 1, 2, 3**  
D) 0, 1, 2, 3, 4  

<details>
<summary>Answer / 答案</summary>
**C** — range(n) 从 0 到 n-1，不包含 n。  
range(n) gives 0 through n-1, not including n.
</details>

---

**Q18.** How many times does `for i in range(5):` run the loop body?  
**for i in range(5): 的循环体会执行几次？**

A) 4  
B) **5**  
C) 6  
D) 0  

<details>
<summary>Answer / 答案</summary>
**B** — range(5) 产生 0,1,2,3,4，共 5 次。  
range(5) yields 0,1,2,3,4 — 5 iterations.
</details>

---

**Q19.** What does `range(2, 7, 2)` produce?  
**range(2, 7, 2) 产生什么？**

A) 2, 4, 6, 8  
B) 2, 4, 6, 7  
C) **2, 4, 6**  
D) 2, 3, 4, 5, 6  

<details>
<summary>Answer / 答案</summary>
**C** — range(start, stop, step)：从 2 开始、步长 2、小于 7，即 2, 4, 6。  
range(2,7,2) → start 2, step 2, stop 7 (exclusive) → 2, 4, 6.
</details>

---

**Q20.** How many times is "hello" printed?  
**"hello" 会被打印几次？**

```python
for i in range(0):
    print("hello")
```

A) 1  
B) **0**  
C) Infinite  
D) Error  

<details>
<summary>Answer / 答案</summary>
**B** — range(0) 没有元素，循环体执行 0 次。  
range(0) has no elements; loop runs 0 times.
</details>

---

## 7. 算法与调试 / Algorithm & Debugging

**Q21.** What is the recommended approach before writing code?  
**写代码前建议先做什么？**

A) Run the program immediately.  
B) **Design the algorithm first (e.g. in comments). / 先设计算法（如在注释里）。**  
C) Copy from the internet.  
D) Use only one variable.  

<details>
<summary>Answer / 答案</summary>
**B** — 算法优先：先在注释里想清楚步骤，再翻译成代码。  
Algorithm-first: design steps (e.g. in comments), then translate to code.
</details>

---

**Q22.** Finding and fixing errors in a program is called \_\_\_\_\_.  
**找出并修复程序中的错误叫做 \_\_\_\_\_ 。**

A) compiling  
B) **debugging / 调试**  
C) concatenation  
D) indentation  

<details>
<summary>Answer / 答案</summary>
**B** — 程序错误叫 bug；找出并消除 bug 叫 debugging。  
Program errors = bugs; finding and fixing them = debugging.
</details>

---

## 答案速查 / Answer Key

| Q  | Ans | Topic |
|----|-----|--------|
| 1  | B   | Tools (repl.it) |
| 2  | B   | Interpreter |
| 3  | B   | Python 3 |
| 4  | B   | input() returns string |
| 5  | B   | Storing input |
| 6  | B   | Case-sensitive |
| 7  | B   | int() |
| 8  | B   | Type conversion for input |
| 9  | B   | Boolean |
| 10 | B   | String concatenation |
| 11 | B   | String repetition * |
| 12 | B   | Concatenation vs arithmetic |
| 13 | B   | == vs = |
| 14 | B   | Colon after if |
| 15 | B   | elif needs if |
| 16 | C   | Keywords (print) |
| 17 | C   | range(4) |
| 18 | B   | range(5) → 5 times |
| 19 | C   | range(2,7,2) |
| 20 | B   | range(0) → 0 times |
| 21 | B   | Algorithm-first |
| 22 | B   | Debugging |

---

**复习建议：** 重点记牢 `input()`→字符串、`int()`/`float()` 转换、`==` 与 `=`、`if` 后冒号与缩进、`range(n)` 与 `range(start, end, step)`、字符串 `+` 和 `*`。  
**Review:** Remember input()→string, int()/float(), == vs =, colon and indentation after if, range(), string + and *.
