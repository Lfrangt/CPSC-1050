# 快速排序 Quicksort 详解 | Quicksort Detailed Guide

**双向导航 · Bidirectional Navigation**

> 💡 **使用提示：** 在 **Markdown 预览** 中打开此文件（右键 → Open Preview，或 `Cmd+Shift+V`），点击目录和导航链接即可跳转。

---

<a id="toc"></a>
## 📑 目录 | Table of Contents

| # | 中文 | English | 跳转 |
|:--|:-----|:--------|:-----|
| 1 | [核心思想](#sec1) | [Core Idea](#sec1) | ⬇ |
| 2 | [分治三步](#sec2) | [Divide-Conquer-Combine](#sec2) | ⬇ |
| 3 | [关键概念](#sec3) | [Key Concepts](#sec3) | ⬇ |
| 4 | [伪代码](#sec4) | [Pseudocode](#sec4) | ⬇ |
| 5 | [分割过程详解](#sec5) | [Partition Process](#sec5) | ⬇ |
| 6 | [完整追踪示例](#sec6) | [Full Trace Example](#sec6) | ⬇ |
| 7 | [图解流程](#sec7) | [Visual Flow](#sec7) | ⬇ |
| 8 | [要点总结](#sec8) | [Summary](#sec8) | ⬇ |

---

<a id="sec1"></a>
## 1. 核心思想 | Core Idea

**中文：**  
Quicksort 是 **分治（Divide-and-Conquer）** 算法：选一个 **pivot（枢轴）**，把数组分成"小于 pivot"和"大于等于 pivot"两部分，对左右分别**递归**排序。当区间只有 0 或 1 个元素时停止（base case）。

**English:**  
Quicksort divides the array using a **pivot**, recursively sorts each part, and stops when a segment has 0 or 1 element.

**关键点：** 分 → 治 → （无需显式）合

[↑ 返回目录](#toc) · [→ 下一节](#sec2)

---

<a id="sec2"></a>
## 2. 分治三步 | Divide-Conquer-Combine

| 步骤 | 英文 | 中文 | 说明 |
|:----|:-----|:-----|:-----|
| **Divide** | 分 | 选 pivot，按 pivot 分割成左右两部分 | |
| **Conquer** | 治 | 对左右**递归**调用 Quicksort | |
| **Combine** | 合 | pivot 已在正确位置，左右排好即整体有序，**无需显式合并** | |

[↑ 返回目录](#toc) · [← 上一节](#sec1) · [→ 下一节](#sec3)

---

<a id="sec3"></a>
## 3. 关键概念 | Key Concepts

### Pivot（枢轴 / 分割值）
- 用来分割的"基准"元素
- 常见选法：**第一个**、**最后一个**、**中间**元素（教材多用第一个）

### splitPoint（分割点）
- 分割完成后 pivot 所在的下标
- 左边都 < pivot，右边都 ≥ pivot

### first, last
- 当前处理区间的**左边界**和**右边界**

[↑ 返回目录](#toc) · [← 上一节](#sec2) · [→ 下一节](#sec4)

---

<a id="sec4"></a>
## 4. 伪代码 | Pseudocode

```
Quicksort(first, last)
    IF (first < last)                          // 至少 2 个元素才继续
        Select splitVal from data[first..last] // 选 pivot（如取第一个）
        Split(splitVal)                        // 分割，得到 splitPoint
        Quicksort(first, splitPoint - 1)       // 递归排序左半
        Quicksort(splitPoint + 1, last)        // 递归排序右半
    // first ≥ last 时 base case，直接返回
```

**Base case：** `first ≥ last` → 区间 0 或 1 个元素 → 已有序，返回。

[↑ 返回目录](#toc) · [← 上一节](#sec3) · [→ 下一节](#sec5)

---

<a id="sec5"></a>
## 5. 分割过程详解 | Partition

以 **pivot = 第一个元素** 为例，目标：左边 < pivot，中间 pivot，右边 ≥ pivot。

### 示例：`[6, 2, 9, 4, 7]`，pivot = 6

| 步骤 | 操作 | 状态 |
|:----|:-----|:-----|
| 初态 | pivot = 6 | [6, 2, 9, 4, 7] |
| 分割 | 2 < 6，放到前面 | [2, 6, 9, 4, 7] |
| | 4 < 6，放到前面 | [2, 4, 6, 9, 7] |
| 完成 | 6 在 index 2 | 左 [2, 4]，右 [9, 7] |

**下一步：** `Quicksort(0, 1)` 对 [2, 4]；`Quicksort(3, 4)` 对 [9, 7]。

[↑ 返回目录](#toc) · [← 上一节](#sec4) · [→ 下一节](#sec6)

---

<a id="sec6"></a>
## 6. 完整追踪示例 | Full Trace

**输入：** [6, 2, 9, 4, 7]

```
Quicksort(0, 4)  →  pivot=6, 分割得 [2,4] | 6 | [9,7]
    ├─ Quicksort(0, 1)  [2, 4]
    │     pivot=2 → [] | 2 | [4]  →  已有序
    │
    └─ Quicksort(3, 4)  [9, 7]
          pivot=9 → [7] | 9 | []  →  已有序

最终：[2, 4, 6, 7, 9]
```

[↑ 返回目录](#toc) · [← 上一节](#sec5) · [→ 下一节](#sec7)

---

<a id="sec7"></a>
## 7. 图解流程 | Visual Flow

```
原始: [6, 2, 9, 4, 7]
         │
         ▼ pivot=6
    ┌────┴────┐
 [2,4]  ←6→  [9,7]
    │           │
    ▼           ▼ pivot=9
  [2,4]      [7] 9 []
    │
    ▼ pivot=2
  2 [4]
    │
    ▼ 合并后
[2, 4, 6, 7, 9]
```

[↑ 返回目录](#toc) · [← 上一节](#sec6) · [→ 下一节](#sec8)

---

<a id="sec8"></a>
## 8. 要点总结 | Summary

| 项目 | 内容 |
|:-----|:-----|
| **Base case** | `first ≥ last`（0 或 1 个元素） |
| **splitVal 选择** | 第一/最后/中间元素，影响性能不影响正确性 |
| **时间复杂度** | 平均 O(n log n)，最坏 O(n²) |
| **空间** | 递归栈 O(log n) 平均 |

[↑ 返回目录](#toc) · [← 上一节](#sec7)

---

**相关文件：** [Chapter 7 预习笔记](Chapter7_Algorithm_Design_Pre_Notes.md) · [Chapter 7 课堂答案](Chapter7_In_Class_Activity_Answers_Bilingual.md)
