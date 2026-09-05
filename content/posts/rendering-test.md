---
title: "页面渲染测试"
date: 2026-09-05T16:00:00+08:00
draft: false
description: "用一篇小文章检查图片、Markdown、代码和 LaTeX 的显示效果。"
summary: "用一篇小文章检查图片、Markdown、代码和 LaTeX 的显示效果。"
tags:
  - 渲染测试
  - Markdown
  - LaTeX
categories:
  - Notes
math: true
ShowToc: true
TocOpen: true
ShowCodeCopyButtons: true
---

这是一篇临时的渲染测试文章，之后可以删除。它会集中展示博客最常用的内容类型。

## 1. 图片

图片使用仓库中的本地 SVG，同时测试图片标题和替代文本是否正常。

![一个用于测试本地图片渲染的抽象图形，包含绿色山形、圆形和文字标签](/images/rendering-grid.svg "Local SVG rendering test")

*图 1：本地 SVG 图片。正式文章可以替换为 PNG、WebP 或照片。*

## 2. Markdown 基础元素

这里有 **粗体**、*斜体*、~~删除线~~、`行内代码`，以及一个指向 [个人主页](/) 的链接。

> 好的技术笔记不只记录结论，也记录自己是怎样抵达结论的。

### 列表

- 研究问题
- 实验设置
  - 数据
  - 方法
  - 评价指标

1. 先提出一个足够具体的问题
2. 再写下可以验证的假设
3. 最后记录失败的尝试

- [x] 写下问题
- [x] 做一个最小实验
- [ ] 用真实数据复现

### 表格

| 项目 | 状态 | 备注 |
| --- | --- | --- |
| 图片 | 正常 | 使用本地 SVG |
| Markdown | 正常 | 标题、列表、表格 |
| LaTeX | 测试中 | 需要检查字体和换行 |

## 3. LaTeX 数学公式

行内公式应该和文字自然混排，例如损失函数可以写成 $L(\theta) = \frac{1}{n}\sum_{i=1}^{n}(f_\theta(x_i)-y_i)^2$。

也支持保留反斜杠的写法：\\(E=mc^2\\)。在 Markdown 中需要写成两个反斜杠，避免被 Markdown 当成转义符。

块级公式应该单独居中显示：

$$
\mathrm{Attention}(Q,K,V)=\mathrm{softmax}\left(\frac{QK^\top}{\sqrt{d_k}}\right)V
$$

也可以写带编号的公式：

$$
\nabla_\theta J(\theta)=\frac{1}{m}\sum_{i=1}^{m}\nabla_\theta\ell\bigl(f_\theta(x_i),y_i\bigr)\tag{1}
$$

## 4. 代码块

```python
from dataclasses import dataclass


@dataclass
class Note:
    title: str
    tags: list[str]


note = Note("Rendering test", ["markdown", "latex"])
print(note.title)
```

## 5. 一个较长的段落

文章页的重点是阅读体验。正式写作时，可以把背景、方法、结果和局限性拆成清晰的章节；如果文章很长，右上角目录会帮助读者定位。代码、图片和公式之间应该留有足够的呼吸空间，而不是把所有内容压缩成一张信息密度过高的卡片。
