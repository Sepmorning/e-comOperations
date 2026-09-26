---
type: amazon-index
tags: [amazon/index]
---

# 🛍️ Listing 与转化

> [!info] 收录范围
> 页面内容、卖点、图片、变体与站点同步。通用操作步骤另见 SOP。

[[亚马逊运营/00_运营总览|🧭 返回运营总览]]

---

```dataview
LIST
FROM "亚马逊运营/01_Listing"
WHERE file.path != this.file.path
SORT file.name ASC
```
