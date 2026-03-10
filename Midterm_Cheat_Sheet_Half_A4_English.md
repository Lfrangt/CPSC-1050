# CPSC 1050 Midterm Half-Page A4 Cheat Sheet
> Feb 26 Thu, 90min, closed-book; **half-page handwritten** allowed. Types: MCQ / Fill-in / Short answer / Tracing. Print single-sided at 8–9pt or hand-copy.

---

## Ch 2 Binary & Number Systems

- **Positional weight** = base^position (right to left: 0,1,2…) | **Base N:** digits 0 to N−1
- **2⁰~2⁸** = 1,2,4,8,16,32,64,128,256 | **1 Byte = 8 bits** (memorize)
- **Hex A–F** = 10,11,**12**,13,14,15 → **C=12, B=11** (common on quizzes)
- **n bits → 2ⁿ distinct values**; **min bits for N items** = ⌈log₂N⌉ (e.g. 6 items → 3 bits)
- **→Decimal:** sum by weight | **Decimal→other base:** divide by base, **remainders read bottom-up**
- **Bin↔Oct** group by 3 bits | **Bin↔Hex** group by 4 bits (pad left with 0s)
- **Hex ordering:** by **numeric value** (same as decimal). Compare by converting to decimal or by **most significant digit** first; in one digit **0<1<…<9<A<B<C<D<E<F**
- **Binary add/subtract:** 1+1=10 carry; 0−1 borrow 2

---

## Ch 3 Data Representation

- **Analog** continuous / **Digital** discrete
- **Two's complement:** invert + 1. **n-bit range:** −2ⁿ⁻¹ ~ 2ⁿ⁻¹−1 (8-bit: −128~127)
- **Overflow:** result **doesn't fit** in allotted space (not radix point or mixed types)
- **Signed-magnitude:** **two representations of zero** → **unnecessary complexity** (not wasted memory)
- **Floating point:** value = **mantissa × base^exponent**; decimal→binary: **×2 take integer**, read top-down
- **Radix point** = “decimal point” in non-decimal bases
- **Compression:** **Huffman** = variable-length, frequent chars shorter; **run-length** = repeated runs (not “word replacement”)
- **Quiz traps:** resolution by pixel count, **not** color depth (F); JPEG for photos, GIF for line art (don’t swap); **Unicode** > 65,000 chars; RGB models human perception

---

## Ch 4 Gates & Circuits

- **NOT** 0↔1 | **AND** all 1→1 | **OR** any 1→1 (**inclusive OR**) | **XOR** different→1 (OR vs XOR differ only when A=B=1)
- **NAND** AND then NOT (bubble on **output**, doesn’t negate inputs) | **NOR** OR then NOT. **Universal gates:** NAND, NOR
- **Boolean:** **identity** A·1=A; **associative** (AB)C=A(BC); **De Morgan's** (A+B)'=A'B', (AB)'=A'+B'
- **Truth table** = all input combos and outputs; **gate** = device that performs basic ops on signals; **transistor** = switch
- **Half adder:** Sum=A⊕B, Carry=AB | **Full adder:** Sum=A⊕B⊕Cin
- **Combinational** no memory | **Sequential** has memory, needs clock
- **Inversion bubble** = small circle on gate symbol for NOT

---

## Ch 5 Computing Components

- **von Neumann:** CPU + memory + I/O, connected by **bus** (carries **address, data, control**)
- **CPU:** **ALU** + **CU** (**IR is in CU**) + **registers**
- **PC (Program Counter)** = **address of next instruction** (not the instruction or data) | **IR (Instruction Register)** = **current instruction being executed**
- **Fetch-decode-execute:** fetch **next instruction** from memory
- **RAM** main memory, **volatile**; **ROM** **non-volatile**; **both are random access**
- **Addressability** = **bits per** addressable unit (e.g. 8-bit = 1 byte)
- **Secondary storage:** **optical** CD/DVD (**not** magnetized particles); **magnetic** HDD, tape
- **Cache** L1/L2/L3; **pipelining** instruction stages; **task-level parallelism** multiple processors on different tasks

---

## Ch 6 Low-Level & Pseudocode

- **Execution order:** **machine language** (CPU runs directly) ← **assembly** (**assembler** translates) ← **high-level** (compiler)
- **Assembly** uses **mnemonics**; **loader** = loads **machine language** program into memory
- **Pseudocode:** Get/Read, Set/←, Write/Print; IF/ELSE watch ranges (e.g. **0 < x ≤ 10** print B)
- **Tracing:** WHILE/FOR by hand (e.g. product×count; **nested loops** count = product of levels, watch count++ from −1 → final = product−1); **PC order** repeats same instruction in loops
- **IPO** Input→Process→Output | **Flowchart:** oval start/end, rectangle process, diamond decision, parallelogram I/O

**Pseudocode — three complete examples:**

**(1) IF/ELSE (branching):**
```
Read x
IF (x > 10)
    Print 'A'
ELSE IF (x > 0)
    Print 'B'
ELSE
    Print 'C'
END IF
```
*(Range for B: 0 < x ≤ 10. AND/OR: IF (a >= 20 AND a <= 30) …)*

**(2) WHILE loop:**
```
Set count to 1
Set product to 1
WHILE (count < 5)
    Set product to product * count
    Set count to count + 1
END WHILE
Display "Product is " + product
```
*(Result: 24. Multiple inputs: Read a, b)*

**(3) FOR loop (nested):**
```
Set count to 0
FOR i = 1 To 2
    FOR j = 1 To 3
        Set count to count + 1
    End For
End For
Display "Count is " + count
Return count
```
*(6 times. array: list[i]; record: item.name)*

---

## Ch 7 Problem Solving & Algorithms

- **Sequential search** from **start** one by one (not from middle); **binary search** list **must be sorted**, **divide and conquer**, mid=(first+last)/2, < → last=mid−1, > → first=mid+1; **comparison count** by hand (each step halves)
- **Selection sort** each pass pick smallest unsorted, swap with current position
- **Bubble sort** compare/swap adjacent, one max sinks per pass
- **Insertion sort** keep prefix sorted, insert next in correct place
- **Quicksort** pick **pivot**, partition <pivot and ≥pivot, **recurse** on sides; based on **recursion**
- **Recursion:** **base case** return directly; **general case** call self (smaller size); need **at least** both
- **Array** = homogeneous collection; **record** = heterogeneous, access by name
- **Top-down design:** main module most abstract; **abstract step** = detail not fully specified

---

## Quick Reference & Common Mistakes

| Question | Answer |
|----------|--------|
| What does PC hold? | **Address of next instruction** (not instruction/data) |
| What does IR hold? Where? | **Current instruction**; in **Control Unit** |
| Addressability? | **Number of bits** per addressable location |
| How does CD store data? | **Optical** (not magnetized particles) |
| What does bus carry? | **Address, data, control** |
| RAM/ROM volatile? | RAM **volatile**, ROM **non-volatile**; both **random access** |
| Hex C = ? 11 = ? | **C=12, B=11** |
| n bits → how many values? | **2ⁿ** |
| Two representations of zero? | **Signed-magnitude**; causes **unnecessary complexity** |
| OR vs XOR? | Differ only when **A=B=1** (OR=1, XOR=0) |

**Good luck!**
