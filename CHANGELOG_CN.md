[English](CHANGELOG.md) | [简体中文](CHANGELOG_CN.md)

# 更新日志 — 海军条约拓展

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
