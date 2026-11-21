[English](README.md) | [简体中文](README_CN.md)

# Naval Treaty Expanded `[Early Demo v0.2.0]`

[![Steam Workshop](https://img.shields.io/badge/Steam%20Workshop-3838936983-1b2838?logo=steam)](https://steamcommunity.com/sharedfiles/filedetails/?id=3838936983)
[![Victoria 3](https://img.shields.io/badge/Victoria%203-1.15.*-blue)](https://store.steampowered.com/app/529340)
[![Multiplayer](https://img.shields.io/badge/Multiplayer-Synchronized-brightgreen)](#version-info)

> **⚠️ Early Demo Notice (`v0.2.0`):** This mod is currently in an **early playable demo** stage. The core real tonnage calculation engine, global multilateral arms limitation treaty, war-enforceable bilateral disarmament treaty, and AI diplomatic acceptance system are all functional, while long-campaign 1836–1936 AI balance, mid-to-late-game pacing, and additional flavor events are still being actively tuned. Bug reports, balance suggestions, and direct collaboration are very welcome!

**Naval Treaty Expanded** is a naval arms limitation and maritime diplomacy expansion for **Victoria 3 (`1.15.*`)**. Inspired by the historical Washington and London Naval Treaties, it introduces a real ship tonnage engine, a locked-tier global multilateral naval treaty, and coercive bilateral disarmament treaties—turning naval arms races into a strategic contest balancing quotas, diplomacy, and fiscal capacity.

**Load Order:** Recommended after foundational framework mods (such as Community Mod Framework) and before major total-conversion mods. Fully compatible with **[Iron & Steam: Naval Overhaul](https://steamcommunity.com/sharedfiles/filedetails/?id=3726415174)** in any load order.

---

## Open-Source Collaboration — Join Us on GitHub!

This project is open source on GitHub, and **players and fellow modders are warmly invited to collaborate**! Whether you want to help with AI acceptance and quota numerical balancing, 1836–1936 observer-mode stress tests, flavor events and journal actions, localization polish, or compatibility patches for other mods, your help is welcome:

- **GitHub Repository**: <https://github.com/NoFires/victoria3-naval-treaty-expanded>
- Feel free to open an **Issue**, balance discussion, or **Pull Request**!

---

## Compatibility

This mod uses additive injection (`INJECT:`) and isolated namespaces (`nte_*` / `gnl_*`), and does not alter vanilla ship types or the Ship Designer UI—minimizing conflicts with other mods.

- **[Iron & Steam: Naval Overhaul](https://steamcommunity.com/sharedfiles/filedetails/?id=3726415174)** — Official companion mod, fully compatible with deep built-in strategic synergy (see below).
- Adds standalone diplomatic treaty articles, journal entries, alert notifications, and bilingual localization; safely compatible with most economy, politics, and UI overhaul mods.

---

## Current Features (`v0.2.0 Demo`)

### Real Tonnage & Naval Doctrine Engine
- Measures naval size by **real treaty tonnage** calculated from ship era, naval power projection, and hull hit points (`HP`), rather than raw ship counts.
- Capital ships (Ships of the Line to Super-Dreadnoughts) and Cruisers (Frigates to Aircraft Carriers) count toward treaty quotas; Destroyers and Submarines are exempt.
- Integrates deeply with naval laws: **`Jeune École`** grants a `0.72×` cruiser tonnage reduction, and **`Diplomatic Navy`** grants a `+15%` treaty council voting weight bonus.

### Global Naval Limitation Treaty (Locked Tiered Quotas)
- Once International Relations technologies are unlocked, Great and Major Powers can sign the Global Naval Limitation Treaty via diplomatic treaty and activate a shared Journal Entry.
- Assigns **`5 : 5 : 3 : 1.75 : 1.75 : 1.35`** quota tiers based on naval strength at signing and locks the top two tier slots to prevent late-joining powers from crowding out existing signatories.
- Built-in transparent multi-factor AI acceptance (naval combat power ratio, military fiscal strain cushioned by gold reserves, naval laws, diplomatic strategies, mutual trust, etc.), fully adapted for Victoria 3 `1.15` journal map coloring, status hover tooltips, and dual progress bars (**Global Treaty Stability** and **Personal Quota Usage**).
- All global calculations, quota allocations, revision votes, and chair succession are settled deterministically by a single Chair country, ensuring full multiplayer synchronization.

### Journal Diplomacy & Treaty Compliance Mechanics
- **Weighted Revisions & Sanction Votes**: Signatories can propose continuous `-15%` to `+15%` limit revisions based on real fleet weight and diplomatic clout, or vote (`75%` threshold) to impose diplomatic isolation sanctions on treaty violators.
- **Escalator Clause**: When a major non-signatory naval power expands above `80%` of the second-tier quota, signatories can invoke the Escalator Clause to temporarily raise limits by `20%` and accelerate capital shipbuilding.
- **Naval Holiday, Mothballing & Scrapping**: Supports calling a 3-year "Naval Holiday", peacetime mothballing of reserve fleets (`-18%` treaty tonnage and `-20%` upkeep at the cost of power projection and capital ship construction speed), and scrapping obsolete battleships for industrial/shipyard conversion.
- **Submarine Protocol & Covert Falsification**: Spend diplomatic influence to sign the London Submarine Protocol to curb convoy raiding and gain prestige, or risk "Tonnage Falsification" to conceal `12%` of reported tonnage—facing severe sanctions if exposed during intelligence exchanges or inspections.

### Bilateral Naval Limitation Treaty (Coercive & War-Enforceable)
- A coercive and humiliating unilateral disarmament pact: defaults to capping the target's fleet tonnage at **`60%`** of the enforcer's, with a post-signing diplomatic note allowing the enforcer to choose between **`30% / 50% / 60% / 75%`** restriction tiers (varying diplomatic cost and relations impact).
- Available as a **Diplomatic Play Wargoal** to enforce terms on defeated rivals at war's end.
- Non-compliant targets enter a 3-month grace period with slowed capital ship construction; if relations remain hostile and the target refuses to back down, a 3-stage ultimatum and punitive diplomatic play event chain triggers.

### Synergy with Iron & Steam: Naval Overhaul
- Purpose-built to pair with **[Iron & Steam: Naval Overhaul](https://steamcommunity.com/sharedfiles/filedetails/?id=3726415174)**.
- When both mods are enabled together, dynamically raises super-capital inspection thresholds, links ship completion notifications, and displays a joint compatibility badge on the main menu.
- Because real tonnage scales with hull `HP` and power projection, 10-slot high-tier ship modifications in **Iron & Steam: Naval Overhaul** translate directly into a genuine strategic choice between **"individual ship quality vs. total fleet tonnage"**.
- Treaty-exempt escort destroyers and submarines (paired with snorkels, hydrophones, and Jeune École) become decisive asymmetric tools for treaty-restricted powers and smaller maritime states to break blockades.

---

## Version Info

- **Current Version**: `v0.2.0` (Early Demo)
- **Supported Languages**: English, 简体中文 (Full bilingual localization)
- **Multiplayer**: Fully `multiplayer_synchronized = true`
- **Game Version**: Victoria 3 **`1.15.*`**
- **Steam Workshop**: <https://steamcommunity.com/sharedfiles/filedetails/?id=3838936983>
- **GitHub Repository**: <https://github.com/NoFires/victoria3-naval-treaty-expanded>
