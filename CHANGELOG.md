[English](CHANGELOG.md) | [简体中文](CHANGELOG_CN.md)

# Changelog — Naval Treaty Expanded

## [v0.2.0] - 2026-11-21

### Added
- **Treaty offices**: the Global Naval Limitation Treaty is now an overview entry plus three office entries (Treaty Council, Fleet Compliance, Naval Diplomacy). Decisions are grouped by office and shown as decree cards with real buttons.
- **Overview widgets**: tier ladder of the five quota ranks, portraits of our ruler and the conference chair, a directory of the treaty's other entries (vanilla journal cards, click to open), and a pin-to-outliner button while unpinned.
- **Invitations to accede** (`nte_global.15`): when the treaty is founded every other eligible Great Power is invited; powers that rise later get one invitation of their own. The AI weighs its attitude to the chair, navy law, strategy, fiscal pressure, war and naval superiority.
- **Map modes**: treaty members by standing, with bilateral treaty stripes; bilateral treaty map mode.
- **Treaty climate**: concord / strain modifiers on members while stability is high / low.
- **Bilateral treaty**: quota progress bar, expiry event (renew, ease to 75%, or let it lapse).
- Narrative rewrite of journal texts in both languages.

### Changed
- **Leaving only through the journal**: the treaty can no longer be withdrawn from in the diplomacy screen; use the journal button or a conference walkout.
- **The treaty survives withdrawals**: it dissolves only when no member is left or stability reaches 0.
- **AI members stay longer**: 5-year minimum membership for AI, escalator clause only under real pressure, much lower withdrawal weights.
- The treaty group is themed (no longer under "Additional Journal Entries"), the overview entry is pinned by default and announced with a popup.

### Fixed
- The overview entry stayed open forever after the treaty dissolved; it now closes, and the related script errors are gone.
- Participant list on the treaty entry, duplicate involved countries, isolation vote comparison errors, interest group loc data errors, and a crash from an unset renewal variable.

## [v0.1.1] - 2026-11-14

### Fixed
- **Real Tonnage Engine (`common/script_values/nte_ship_values.txt`)**:
  - Fixed all `is_ship_type` checks to use the required `ship_type:ship_type_*` scope prefix.
  - Added full 22-hull coverage (including `monitor`, `coastal_defense_ship`, `iron_frigate`, and modern hulls) and explicitly exempted unarmed `ship_type_early_troop_ship` and `ship_type_troop_ship` (`0` treaty tonnage).
- **GUI & VFS Assets (`gui/frontend/frontend_dlc.gui`, `common/alert_types/nte_alerts.txt`, `common/scripted_progress_bars/nte_bars.txt`)**:
  - Moved `zz_nte_frontend_dlc.gui` to `gui/frontend/frontend_dlc.gui` to cleanly override vanilla without duplicate `dlc_collection`/`dlc_button` registrations.
  - Replaced missing alert/progress-bar `.dds` texture paths with verified Vanilla `1.15.1` textures.
- **Observer-Safe Localization & Telemetry**:
  - Replaced `GetPlayer` with `ROOT.GetCountry` in `nte_btn_scrap_obsolete_hulls_desc`.
  - Fixed invalid `[scope:...]` `debug_log` formatting in `nte_bilateral_effects.txt` and added `nte_bilateral_strict_burden_paid` variable cleanup.
- **AI Strategy Injection (`common/ai_strategies/zz_nte_ai_strategy.txt`)**: Restored `value = wanted_navy_size_script_value` and all 7 Vanilla/Overhaul `ai_ship_category_*` base weights inside `INJECT:ai_strategy_default` so peacetime `wanted_navy_size` never collapses to zero.

### Changed & Improved
- **Journal Progress Bars UI (`localization/english/nte_l_english.yml`, `localization/simp_chinese/nte_l_simp_chinese.yml`)**: Shortened in-bar text on `nte_treaty_stability_bar` and `nte_personal_quota_bar` to prevent overlap/clipping, moving detailed explanations into `name`/hover tooltips.
- **Overhaul Co-Execution (`common/on_actions/zz_nte_overhaul_compat.txt`)**: Added `dreadnought_tech` era gate to `nte_global.10` so super-capital inspections do not fire prematurely in the wooden-sail era.
- **AI Treaty Decisions (`common/scripted_buttons/nte_scripted_buttons.txt`)**: Refined AI scoring for treaty buttons (`scrap`, `mothball`, `escalator`, `naval_holiday`, `submarine_protocol`, `falsify`).
- **Documentation**: Added `AGENTS.md`, synced `README.md`, and added `README_CN.md` to match Steam Workshop `v0.1.1`.

## [v0.1.0] - 2026-11-14

### Added
- Initial Early Demo release of **Naval Treaty Expanded** for Victoria 3 (`1.15.*`).
- Real tonnage calculation engine, locked `5:5:3:1.75:1.75:1.35` Global Naval Limitation Treaty with single-chair MP settlement, coercive/wargoal Bilateral Naval Limitation Treaty, multi-factor AI acceptance, and full English/简体中文 localization.
