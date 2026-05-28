---
title: "Markdown 基本语法笔记"
date: 2026-05-28
draft: false
tags: ["Markdown", "笔记", "教程"]
categories: ["博客搭建"]
summary: "记录我常用的 Markdown 语法，方便自己随时查阅。"
---

# Markdown 基本语法笔记

这是我整理的马可down语法，方便写博客时快速参考。

## 1. 标题

用 `#` 表示标题级别：

```markdown
# 一级标题
## 二级标题
### 三级标题
---
title: "Markdown 基本语法笔记"
date: 2026-05-28
draft: false
tags: ["Markdown", "笔记", "教程"]
categories: ["博客搭建"]
summary: "记录我常用的 Markdown 语法，方便自己随时查阅。"
---

# Markdown 基本语法笔记

这是我整理的 Markdown 语法，方便写博客时快速参考。

## 1. 标题

用 `#` 表示标题级别：

```markdown
# 一级标题
## 二级标题
### 三级标题
2. 强调
markdown
*斜体*  或  _斜体_
**加粗**
***加粗斜体***
效果：斜体，加粗，加粗斜体。

3. 列表
无序列表：

markdown
- 项目一
- 项目二
  - 子项目（缩进两个空格）
有序列表：

markdown
1. 第一步
2. 第二步
4. 链接与图片
markdown
[文字](https://example.com)
![替代文本](图片URL)
5. 代码
行内代码：`code`

代码块：
```python
print("Hello")
```

6. 引用
markdown
> 这是一段引用。
这是一段引用。

7. 表格
markdown
| 标题1 | 标题2 |
|-------|-------|
| 内容1 | 内容2 |
8. 任务列表
markdown
- [x] 已完成
- [ ] 未完成
9. 转义特殊字符
用反斜杠 \ 转义：\*不是斜体\*
