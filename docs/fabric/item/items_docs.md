---
title: 物品文档
date: 2023/10/18
---

物品是你物品栏中占据一个一个格子的内容。它们可以在右击的时候执行操作，食用，或生成实体。以下是整个 `Item`（物品）类与其相关部件的简介。
如果你需要一个可以边做边学的例子，请见我们添加物品的教程。

## 物品设置

`Item` 的构造方法需要一个 `Item.Settings` 的实例，这个类定义物品的诸多行为，例如堆叠数量、耐久度、是否可食用等等。以下是所有可用的方法：

