# AGENTS.md — Naval Treaty Expanded（海军条约拓展）开发规范

## 1. 环境与目标版本
- **游戏版本**：Victoria 3 **1.15.***（目标基线 `1.15.1`）
- **原版游戏路径**：`C:\Program Files (x86)\Steam\steamapps\common\Victoria 3\game`（或本地 Steam 安装目录下的 `game` 目录）
- **Mod 开发根目录**：当前工作目录
- **上传与加载建议**：打包或配置游戏加载 / Steam 创意工坊上传目录时，仅需包含 `.metadata`、`common`、`dlc`、`events`、`gui`、`localization` 与 `thumbnail.png`，避免将 `.git`、工程文档或本地索引一并上传。
- **联机兼容性**：严禁使用导致联机 OOS 的非确定性状态或本地玩家专属逻辑分支（UI 文本除外）。

## 2. 核心设计约束
- **先逆向原版、再写脚本**：任何条约字段、触发器、修正名、外交动作或本地化概念（`[concept_*]`）必须先查阅原版 `game/common/` 或 `game/localization/`，禁止凭空猜写（例如：`has_treaty_alliance_with` / `has_treaty_defensive_pact_with` 的参数是 `TARGET =`，而非 `who =` 或 `target =`；原版海军概念是 `[concept_fleet]`，不存在 `concept_navy`）。
- **增量注入与隔离命名空间**：
  - 全部自建脚本、变量、事件、修正与按钮统一使用 `nte_*` / `gnl_*` 前缀；
  - 对原版 `ai_strategies` 等使用 `INJECT:` 增量注入，避免整文件覆盖；
  - 不直接覆写 `right_click_menu.gui` 等巨型原版 UI 文件。
- **零 `error.log` 容忍度**：
  - 所有 `remove_modifier` 必须先做 `has_modifier` 检查，或统一调用 `nte_clear_all_global_modifiers` / `nte_clear_all_bilateral_modifiers`；
  - 严禁在 `can_ratify` 等不支持条约实例选项的作用域访问 `scope:article_options`。
- **多人联机确定性**：
  - 全局条约配额分配、修订表决、违约脉冲、孤立制裁与主席国交接统一由唯一主席国（`global_var:global_gnl_chair_country`）在月度/年度脉冲中确定性执行。
- **数值平衡与无白嫖机制**：
  - 所有日志外交按钮（退约、造假、潜艇议定书、情报互换、拆船、封存）必须具备真实的战略取舍或外交影响力/建造效率代价，禁止无成本刷分；
  - AI 接受度采用多维透明化 `desc` 分解，财政压力结合 `military_expenses_share`、财政赤字与黄金储备缓冲（`scaled_gold_reserves`）计算。
- **与 `Iron & Steam: Naval Overhaul` 联动**：
  - 兼容桥接通过 `common/on_actions/zz_nte_overhaul_compat.txt` 与 `dlc/dlc_nte_overhaul/`、`gui/zz_nte_frontend_dlc.gui` 实现，任何加载顺序下不产生硬依赖或报错。

## 3. 提交与改动前校验
- 每次修改脚本或本地化文件后，必须校验：
  1. 修改的 `.txt` 与 `.yml` 文件保留 **UTF-8 with BOM**（`.metadata/metadata.json` 保持有效 JSON）；
  2. 所有脚本文件大括号 `{}` 配对平衡；
  3. `localization/simp_chinese/nte_l_simp_chinese.yml` 与 `localization/english/nte_l_english.yml` 键名 100% 对等（`ZH_ONLY=0`、`EN_ONLY=0`）。
