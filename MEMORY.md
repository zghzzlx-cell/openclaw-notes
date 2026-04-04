# MEMORY.md - 长期记忆（分层结构）

> **使用规则**：L1层每次session必载，L2层每次session读取，L3层按需检索。
> **更新时间**：每日23:00自动更新，L2层每日覆盖写入。

---

## L1 身份层（≤200 tokens，永久核心）

- **名称**：小管家 | **版本**：OpenClaw 2026.4.3
- **定位**：商业管理公司副总经理首席数字助理
- **用户**：副总经理（分管综合部、财务部），称呼"领导"
- **公司**：商业管理公司，2026年营收目标7000万，预算偏差≤10%
- **当前重点**：Q2绩效管理（4/1）、Q3搬迁（B2-2）、商户清退争议
- **领导飞书ID**：oc_a36ab500916298d83062f33a23d976f1

### 团队架构（九部）
| 部门 | 角色 | 技能 |
|------|------|------|
| 战略部 | 参谋/战略顾问 | competitive-intelligence-market-research |
| 资财部 | 资财精算师 | afrexai-lease-analyzer |
| 法务部 | 合规法务官 | afrexai-regulatory-compliance |
| IT部 | 数字化专家 | api-gateway |
| 财务部 | 预算管控官 | afrexai-budget-planner |
| 美工部 | 文档美化官 | tiangong-wps-word/ppt-automation |
| 架构部 | 架构炼金师 | skill-security-audit-v2 |
| 安全审核部 | 安全审核官 | skill-security-audit-v2 |
| 行政部 | 行政运营官 | n8n-workflow-automation |
| 人事部 | 人才战略官 | 待安装 |

### 综合部4人
姜玲（综合经理）、汤凤燕（HR主管）、孙章雪（行政专员）、姚凯凯（信息化主管）、财务经理（待确认）

### 关键约定（永久生效）
1. **安全优先**：技能安装前必须过安全审核
2. **文件规范**：新建文档/表格，必须开编辑权限后发飞书
3. **决策模式**：问题→选项→用户决策→执行
4. **行动纪律**：不等催促，直接执行，结论先行

---

## L2 工作状态层（≤500 tokens，每日更新）

### 新架构系统（2026.4.3 升级 v2）
| 系统 | 文件 | 状态 | 核心功能 |
|------|------|------|---------|
| Turn Budget & 压缩 | scripts/turn_budget.py | ✅ | 轮次预算+超过15轮自动压缩 |
| Permission Denial追踪 | scripts/permission_denials.py | ✅ | 所有拒绝操作记录(含原因/是否自动阻止) |
| 结构化输出 | scripts/structured_output.py | ✅ | JSON Schema验证(绩效方案/合同/预算) |
| 工具路由评分 | scripts/tool_router.py | ✅ | Token权重匹配+中文分词 |
| 分层Agent调度 | scripts/agent_layer.py | ✅ | 5层Agent模式(general/plan/explore/verification) |
| 上下文压缩 | scripts/context_compaction.py | ✅ | hot/warm/cold三层记忆 |
| 流式事件系统 | scripts/event_stream.py | ✅ | 异步事件流(message_delta/stop/tool_match) |
| 能力地图审计 | scripts/capability_audit.py | ✅ | 能力地图+P0/P1差距追踪 |

### 2026.4.3 能力升级(第二弹)
| 系统 | 文件 | 状态 | 核心功能 |
|------|------|------|---------|
| Hook系统 | scripts/tool_hook.py | ✅ | PreToolUse/PostToolUse，exit码契约(0=Allow/2=Deny/N=Warn) |
| 增量压缩 | scripts/incremental_compaction.py | ✅ | 增量合并+pending work推断+文件提取+structured summary |
| 结构化任务 | scripts/task_manager.py | ✅ | pending→in_progress→completed状态机，支持优先级/截止日期/标签 |
| 指令文件发现 | scripts/claw_instructions.py | ✅ | CLAW.md链式发现(hash去重/字符预算/继承覆盖) |

### 分层Agent模式
- `general_purpose` → 通用执行（默认）
- `plan` → 任务规划拆解（关键词：怎么规划/如何计划/拆解）
- `explore` → 代码库探索（关键词：搜索/查找/分析代码）
- `verification` → 结果验证（关键词：验证/检查/审核）
- `guidance` → 教学引导（关键词：如何/怎么/解释）

### Cron健康状态
| Cron | 状态 | 备注 |
|------|------|------|
| 每日技能巡检(00:00) | ok | |
| 我的工作日报(08:00) | ok | |
| 每日计划确认(08:30) | ok | |
| 每日完成确认(16:30) | ok | |
| 每日系统复盘(23:00) | ok | |

### 当前P0待办
- Q2绩效启动（4/1截止）
- 财务经理人选（待确认）
- team-daily IT部 timeout修复

---

## L3 知识库层（按需检索，不自动加载）

### 核心脚本索引
- `scripts/turn_budget.py` — Turn预算+自动压缩
- `scripts/permission_denials.py` — 权限拒绝日志
- `scripts/structured_output.py` — JSON Schema输出
- `scripts/tool_router.py` — Token权重工具路由（含中文分词）
- `scripts/agent_layer.py` — 分层Agent调度器
- `scripts/context_compaction.py` — 三层记忆压缩
- `scripts/event_stream.py` — 异步事件流
- `scripts/capability_audit.py` — 能力地图审计
- `scripts/tool_hook.py` — Hook系统（Pre/Post Tool + exit码契约）
- `scripts/incremental_compaction.py` — 增量压缩（pending work推断+文件提取+结构化摘要）
- `scripts/task_manager.py` — 任务状态机（pending→in_progress→completed）
- `scripts/claw_instructions.py` — CLAW.md链式发现（继承覆盖+hash去重）

### 飞书文件总索引
见 memory/feishu-files-index.md

### Claude Code/claw-code 研究笔记
见 memory/claude-code-analysis.md（2026.4.3）

---

### Cron 部署状态
| 任务 | Crontab | 状态 |
|------|---------|------|
| 每日复盘 | `0 23 * * * python3 scripts/daily_review_cron.py` | ✅ 已配置 |
| 报告输出 | `memory/daily-reviews/latest.json` | ✅ 每日生成 |
| 飞书推送 | `scripts/send_review.py` | ⚠️ 需配置 lightclawbot API key |

### lightclawbot 配置（如需开启飞书推送）
```json
// ~/.openclaw/openclaw.json channels段
"lightclawbot": {
  "enabled": true,
  "apiKeys": ["<your-api-key>"]
}
```
然后运行: `python3 scripts/send_review.py <api_key>`

---

*最后更新：2026-04-03 01:05 CST*
*claw-code源码分析 + 全量部署完成*

### 2026-04-05 [语音系统调试]
- 飞书语音自动模式：发语音→文字+原生语音；发文字→仅文字。实现方案：Python脚本调用Feishu API发Opus格式原生语音，关闭全局tts.auto。

### 2026-04-05 [工作流规则确定]
- 多部门协同任务工作流规则：每个任务有截止时间+每日计划；深夜任务先提议用户同意才执行；提前≥24小时立即通知；每日8:00报告；技术类自主判断，专业类用户审核。

### 2026-04-05 [安全规范]
- Token安全规范：openclawmp Token用完即删，不在文件系统留存。从会话记录获取。

### 2026-04-05 [平台确认]
- 水产市场接入：openclawmp CLI安装成功，网址openclawmp.stepfun.com，与ClawHub是两个不同生态。

## M-FLOW AI记忆架构学习 (2026-04-05)

### 核心论文
《19岁，常青藤辍学，这群中国年轻人重构了AI记忆》— 量子位 2026-04-03
心流元素团队 M-FLOW：https://github.com/FlowElement-ai/m_flow

### 关键洞察
1. 图路由Bundle Search替代平坦向量检索
2. 四层倒锥结构：Entity(锥尖) → FacetPoint → Topic → Episode(锥底)
3. 检索哲学：一条强证据链就足以证明相关性，取路径最小代价
4. 跨文档实体桥接：共享Entity节点自动关联不同文档
5. 指代消解：区分"他"和"它"

### 与我的架构对比
| 维度 | M-FLOW | 我 |
|------|--------|-----|
| 检索 | 图路由 | 向量 |
| 结构 | 四层倒锥 | 三层 |
| 关联 | 自动桥接 | 双向链接 |

### 能力差距
- 图路由检索（需向量库Milvus）
- 指代消解（需NLP模型）
- 毫秒级响应（当前依赖LLM）

### 已执行改进
- Obsidian双向链接（模拟跨文档关联）
