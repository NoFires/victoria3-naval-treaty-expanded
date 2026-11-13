# Naval Treaty Expanded (`v0.1.0` Early Demo)

> **⚠️ Early Playable Demo (`v0.1.0`):** This mod is currently in an **early playable demo** stage. Core ship tonnage calculation, global multilateral naval treaties, bilateral coercive disarmament treaties, and AI acceptance mechanics are functional, while long-term 1836–1936 AI balance, mid/late-game pacing, and additional flavor events are still under active development. Feedback, bug reports, balance suggestions, and pull requests are warmly welcome!

**Naval Treaty Expanded** is a naval arms limitation and maritime diplomacy expansion for **Victoria 3 (`1.15.*`)**. Inspired by the Washington and London Naval Treaties, it introduces a real ship tonnage engine, a locked-tier global multilateral naval treaty, and enforceable bilateral disarmament treaties.

## Companion Mod

- **[Iron & Steam: Naval Overhaul](https://steamcommunity.com/sharedfiles/filedetails/?id=3726415174)** — Official companion mod, fully compatible in any load order with automatic super-capital detection, construction events, and joint menu badge.

## Current Features (`v0.1.0`)

- **Real Tonnage & Naval Doctrine Engine**: Calculates treaty tonnage from ship era, power projection, and hit points. Capital ships and cruisers count toward quotas; destroyers and submarines are exempt. Integrates with `Jeune École` (0.72× cruiser tonnage) and `Diplomatic Navy` (+15% voting weight).
- **Global Naval Limitation Treaty**: Unlocks with International Relations for Great & Major Powers, assigning locked `5 : 5 : 3 : 1.75 : 1.75 : 1.35` quota tiers with map coloring, stability & quota bars, weighted quota revisions (`-15%` to `+15%`), isolation sanctions (75% vote), Escalator Clause, Naval Holidays, mothballing, scrapping, Submarine Protocol, and covert tonnage falsification.
- **Bilateral Naval Limitation Treaty**: Coercive disarmament pact (supports diplomatic play wargoal enforcement) capping target tonnage relative to the enforcer (`60%` default; adjustable to `30% / 50% / 60% / 75%` via post-signing diplomatic note), backed by a 3-stage ultimatum & punitive play chain.
- **Transparent AI Acceptance**: Multi-factor AI evaluation tied to diplomatic attitude, naval combat power ratio, naval fiscal pressure (budget share × fiscal distress cushioned by gold reserves), naval laws, diplomatic strategies, rank disparity, and treaty binding period.
- **Localization & MP**: Full **English** and **简体中文** localization; single-chair settlement architecture for multiplayer synchronization.

## Contributing

Contributions are very welcome! Whether you want to help with:
- 1836–1936 observer balance & AI pacing tests
- New flavor events, journal actions, or conference mechanics
- Localization improvements or compatibility patches with other mods

Feel free to open an **Issue** or submit a **Pull Request** at [NoFires/victoria3-naval-treaty-expanded](https://github.com/NoFires/victoria3-naval-treaty-expanded)!
