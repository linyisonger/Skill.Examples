# Skill.Examples

WorkBuddy 项目级技能（Skill）示例仓库。本仓库用于沉淀可复用的 Agent 工作流，供同一项目的团队成员共享。

## 目录结构

```
Skill.Examples/
├── README.md                      # 本文件
└── .workbuddy/skills/             # 项目级技能（本仓库当前未使用）
└── a-stock-technical-analyst/     # 示例技能：A股技术分析可执行框架
    ├── SKILL.md                   # 技能执行参考（SOP）
    └── _meta.json                 # 技能元数据
```

## 已收录技能

### a-stock-technical-analyst（量价判官）

面向 A 股 / ETF / 板块的**纯技术面**分析框架，作为 Agent 的标准作业程序（SOP）使用。

- **触发**：用户询问大盘、个股/ETF、板块行情、操作建议、对比分析时启用。
- **数据源**：优先使用 westock-mcp 结构化行情；失败时降级到 WebSearch 交叉校验。
- **核心能力**：
  - 默认 ETF 观察清单（宽基 / 科技 / 金融 / 周期 / 新能源 / 消费 / 医药）。
  - 七维度技术分析框架（趋势、量价、均线、指标、支撑阻力、板块轮动、变盘信号）。
  - 统一操作术语体系（买入/持有/减仓/卖出/观望/轻仓试多/做T）并附置信度。
  - 数据校验、异常处理、低置信度处理等健壮性规则。
- **边界**：仅输出技术观点与操作建议，不连接交易接口、不执行买卖。

详见 `a-stock-technical-analyst/SKILL.md`。

## 使用方式

- 个人技能：存放于 `~/.workbuddy/skills/`；项目级技能：存放于 `{workspace}/.workbuddy/skills/`。
- 加载技能后即可在对话中按触发词调用，遵循 SKILL.md 的工作流。

## 说明

`.workbuddy` 文件夹存储项目相关数据，请勿删除。
