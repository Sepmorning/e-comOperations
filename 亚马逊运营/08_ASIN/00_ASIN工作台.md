---
type: asin-dashboard
tags: [amazon/index]
---

# 📦 ASIN 精细化运营工作台

> [!abstract] 一产品一档案，一站点一份记录
> Markdown 记录现状、行动、证据和复盘；Excel 负责日级明细与计算。[[亚马逊运营/00_运营总览|🧭 返回运营总览]]

## 🚀 创建第一份档案

1. 在 `亚马逊运营/08_ASIN` 下新建笔记，命名为 `品牌-US-ASIN-产品简称`，其他站点替换 US。
2. 打开命令面板，执行 **Templater: Open Insert Template modal**，选择 `ASIN精细化运营`。
3. 填写上方 `asin`、`marketplace`、`brand`、`product` 属性，设置 `review_date`。
4. 先填购买理由、当前一个主行动与经营基线，再把现有 Excel 明细表链接进来。无数据的栏目可以暂留空。

---

## 🎯 产品总览

```dataview
TABLE WITHOUT ID file.link AS "产品档案", asin AS "ASIN", marketplace AS "站点", brand AS "品牌", stage AS "阶段", priority AS "优先级", review_date AS "复查日期"
FROM "亚马逊运营/08_ASIN"
WHERE type = "asin"
SORT priority ASC, file.name ASC
```

## ⏰ 待复查

```dataview
TABLE WITHOUT ID file.link AS "产品", review_date AS "计划复查"
FROM "亚马逊运营/08_ASIN"
WHERE type = "asin" AND review_date AND date(review_date) <= date(today)
SORT review_date ASC
```

## ✅ 未完成行动

```dataview
TASK
FROM "亚马逊运营/08_ASIN"
WHERE !completed AND file.frontmatter.type = "asin"
GROUP BY file.link
```

> [!tip] 数据越多，越要分工
> 每个 ASIN 的周快照只保留关键数值；数千行的广告、订单和库存明细放 Excel。模板中的目标自行填写，不预设统一 ACOS 或利润阈值。


## 📖 单人运营使用指南

[[亚马逊运营/08_ASIN/ASIN精细化运营使用指南|如何建档、检查瓶颈、验证调整，以及与工作周记分工]]
