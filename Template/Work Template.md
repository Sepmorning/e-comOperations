---
type: work-log
date: {{date:YYYY-MM-DD}}
weekday: {{date:dddd}}
status: active
tags:
  - work/log
  - status/daily
---

# 📅 {{date:YYYY-MM-DD}} {{date:dddd}}工作日志

---
 `dice: [[励志格言]]|line`
## 📅 今日常规日程

<%*
// 1. 获取今天的星期名称（例如："星期二"）
const days = ["星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"];
const todayName = days[new Date().getDay()];

// 2. 读取“每周计划日程”文件的内容（请确保这个文件名和你的源文件名完全一致）
const sourceFile = app.metadataCache.getFirstLinkpathDest("每周计划日程", "");

if (sourceFile) {
    const content = await app.vault.read(sourceFile);
    const lines = content.split("\n");
    
    let isTodaySection = false;
    let tasks = [];
    
    // 3. 解析文件，提取今天对应的列表项
    for (let line of lines) {
        if (line.startsWith("## ")) {
            if (line.includes(todayName)) {
                isTodaySection = true;
                continue;
            } else if (isTodaySection) {
                break; // 遇到了下一个星期的标题，结束读取
            }
        }
        
        // 如果在今天的区域内，并且是列表项（以 - 或 * 开头）
        if (isTodaySection && (line.trim().startsWith("- ") || line.trim().startsWith("* "))) {
            let taskText = line.replace(/^[\s-*]+/, "").trim();
            tasks.push(`- [ ] ${taskText}`); // 转换为真正的 Markdown 待办语法
        }
    }
    
    // 4. 将任务作为真正的文本输出到日记里
    if (tasks.length > 0) {
        tR += tasks.join("\n");
    } else {
        tR += `💡 今天 (${todayName}) 没有安排固定日程。`;
    }
} else {
    tR += "❌ 未找到【每周计划日程】文件，请检查文件名是否正确。";
}
-%>

---
## ⏰ 时间块深度执行

- **08:40 - 09:30 | 📥 启动仪式**
	- [ ] 查收并清理骁晖、纯粹和慧慧鱼美国站邮件消息
	- [ ] 跟踪物理信息并更新记录FBA表格
- **09:30 - 12:00 | 🚀 深度工作块 1 (Focus)**
	- [ ]  
- **13:30 - 17:30 | 🚀 深度工作块 2 (Focus)**
	- [ ] 
- **17:30 - 18:00 | 🏁 收尾与闭环**
	- [ ] 更新项目看板、填写复盘、规划明天的清单

---
## 📥 突发与琐碎事务收件箱

- [ ] [新任务/新想法1] (来自: 谁 | 截止日: )
- [ ] [新任务/新想法2]

---
## ✍️ 工作笔记、会议与灵感
### 笔记
- 
### 👥 会议/沟通记录

- 
### 💡 灵感/方法论沉淀
* 
---
## 📊结果交付与每日复盘 

### 1. 今日核心产出
- 
### 2. 关键业务指标/数据跟踪 
 - 
### 3. 日终三问
1. **今天有什么事情做得比昨天更好？**（哪怕是一个小习惯的改进）
   > 
2. **今天遇到了什么卡点/推进阻力？明天如何破局？**
   > 
3. **明天的核心 Top 1 任务是什么？**
   > 明天重点攻坚：

---
