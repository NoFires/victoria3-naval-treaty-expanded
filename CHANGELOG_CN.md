[English](CHANGELOG.md) | [简体中文](CHANGELOG_CN.md)

# 更新日志 — 海军条约拓展

## [v0.2.0] - 2026-11-21

### 新增
- **条约机构**：全球海军限武条约拆分为概览条目与三个机构条目（条约理事会、舰队合规、海军外交），各项决策按机构归类，以带真实按钮的政令卡片呈现。
- **概览面板**：五级配额阶梯、本国元首与会议主席国元首头像、条约其他条目的目录（原版日志卡片，点击即可打开），以及未钉选时显示的“钉选到概览”按钮。
- **入约邀请**（`nte_global.15`）：条约成立时邀请其余所有符合条件的列强，日后新晋列强各收到一次邀请。AI 会权衡对主席国的态度、海军法律、战略、财政压力、战争与海军优势。
- **地图模式**：按缔约国地位着色并标出双边条约；双边条约地图模式。
- **条约氛围**：稳定度高/低时为缔约国施加和睦/紧张修正。
- **双边条约**：配额进度条与期满事件（续约、放宽至 75% 或任其失效）。
- 中英文日志文本改写为叙事风格。

### 调整
- **只能通过日志退约**：外交界面不能再退出条约，须使用日志按钮或在会议上离席。
- **退约不再终结条约**：只有成员全部退出或稳定度归零时条约才会解散。
- **AI 更守约**：AI 入约后至少留 5 年，只在真正承压时启动升级条款，退约权重大幅降低。
- 条约分组改为主题分组（不再位于“附加日志条目”），概览条目默认钉选并以弹窗提示。

### 修复
- 条约解散后概览条目永远不关闭的问题；相关脚本报错一并消除。
- 条约条目的参与国列表、重复的参与国、孤立表决比较报错、利益集团本地化数据报错，以及续约变量未设置导致的闪退。

## [v0.1.1] - 2026-11-14

### 修复
- **真实吨位引擎（`common/script_values/nte_ship_values.txt`）**：
  - 为全部 `is_ship_type` 判定补全 `ship_type:ship_type_*` 作用域前缀。
  - 补全全部 22 种舰船（含浅水重炮舰、岸防铁甲舰、铁甲巡防舰等）的吨位映射，并显式豁免无武装运输船（`ship_type_early_troop_ship` / `ship_type_troop_ship`，计为 `0` 吨）。
- **GUI 与 VFS 贴图修复（`gui/frontend/frontend_dlc.gui`、`common/alert_types/nte_alerts.txt`、`common/scripted_progress_bars/nte_bars.txt`）**：
  - 将 `zz_nte_frontend_dlc.gui` 迁移覆盖 `gui/frontend/frontend_dlc.gui`，消除 `dlc_collection`/`dlc_button` 重复注册报错。
  - 将警戒与进度条中缺失的 `.dds` 路径替换为原版 `1.15.1` 已验证贴图。
- **观察者本地化与遥测清理**：
  - 将 `nte_btn_scrap_obsolete_hulls_desc` 中的 `GetPlayer` 替换为 `ROOT.GetCountry`。
  - 修复 `nte_bilateral_effects.txt` 中 `debug_log` 的无效 `[scope:...]` 括号语法，并清理 `nte_bilateral_strict_burden_paid` 临时变量。
- **AI 策略注入修复（`common/ai_strategies/zz_nte_ai_strategy.txt`）**：在 `INJECT:ai_strategy_default` 中恢复 `value = wanted_navy_size_script_value` 与全部 7 项原版/Overhaul 舰种权重基线，修复和平时期目标海军规模归零的问题。

### 调整与优化
- **日志进度条 UI 排版（`localization/english/nte_l_english.yml`、`localization/simp_chinese/nte_l_simp_chinese.yml`）**：精简 `nte_treaty_stability_bar` 与 `nte_personal_quota_bar` 的条内直显文字，避免左右重叠与右侧截断，将详细说明移至悬停提示（tooltip）。
- **《铁与蒸汽：海军大修》联动门控（`common/on_actions/zz_nte_overhaul_compat.txt`）**：为 `nte_global.10` 增加 `dreadnought_tech` 时代门控，避免木帆船时代误触超无畏舰质检事件。
- **AI 条约外交行动（`common/scripted_buttons/nte_scripted_buttons.txt`）**：优化拆船、封存、自动扶梯、海军假日、潜艇议定书与虚报吨位的 AI 决策权重。
- **文档**：新增 `AGENTS.md`，同步 `README.md` 并新增 `README_CN.md`，与 Steam 创意工坊 `v0.1.1` 介绍保持一致。

## [v0.1.0] - 2026-11-14

### 新增
- **《海军条约拓展》**面向 Victoria 3（`1.15.*`）的首个早期测试版 Demo 发布。
- 包含真实吨位核算引擎、锁定阶梯配额（`5:5:3:1.75:1.75:1.35`）的全球海军限武条约、唯一主席国联机同步结算、可战争强迫的双边限武条约、多维透明 AI 接受度及完整中英双语本地化。
