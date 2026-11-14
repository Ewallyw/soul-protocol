# SOUL v5.0 — 智能体作业规程包

可放置于**任意位置**的分层智能体规程体系：不依赖安装路径、文件命名或特定 harness。各 agent（Magpie 资源库统一调配，或各 harness 自行注入）指向本包根目录的 `SOUL.md` 即可。

## 结构

```
SOUL.md            宪法层——每次会话全量常驻（含 §T 执行期触发表）
soul/rules/        12 规则组——intent/process 常驻，其余命中信号词才读
soul/references/   4 文件——模板/案例/术语/交付前自检，条款指向时才读
```

## 部署到某个 harness

1. 把本包放到任意目录（保持 `SOUL.md` 与 `soul/` 相对结构不变）。
2. 让 harness 的规程文件（AGENTS.md / CLAUDE.md 等）**包含或指向** `SOUL.md` 全文。
3. 引导层兜底（可选）：若无文件注入机制，至少内联 SOUL.md 的三法则+九门禁+复述默认开。

## Magpie 统一调配

Magpie 资源库 →「指令」写入本引导内容，各 agent 由 Magpie 统一分发；本包位置变化时只需更新指令中的包路径。

## 加载契约

- `SOUL.md` 每次会话全文常驻
- `soul/rules/intent.md`、`soul/rules/process.md` 常驻（always）
- 其余 `soul/rules/*.md`：命中 SOUL.md §T 触发表信号词时读取
- `soul/references/*.md`：仅在条款指向时读取

## 版本历史

- v5.1-full（full-inline-v5.1 分支）：全量单文件 AGENTS.md（宪法层+12规则组内联，≈99KB），分层加载架构退役
- v5.0-layered（tag）：分层版（SOUL.md 常驻 + rules/ 按信号加载 + references/ 按需），已被全量方案取代

## 治理

规程修改走 `soul/rules/meta.md` M 组流程。版本演进以 SOUL.md 内版本行与变更记录为准。
