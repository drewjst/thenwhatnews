# HANDOFF — thenwhatnews
State:    spec
Next:     Design the autonomous pipeline slice: ingest, cluster into events, machine-made links, and a daily graph JSON that the mockup loads.
Blockers: none
Decisions this session:
- License is AGPL-3.0-only — it is OSI open source and makes anyone who runs a modified hosted copy publish their source — rejected: BSL/PolyForm (not open source), Apache/MIT (no protection against a closed hosted fork).
- research/ is gitignored and stays local — it holds business planning material, which never goes in a public repo — rejected: committing the packet alongside the mockup.
- The public repo holds only the fictional mockup, README, and license — a license protects the code, not the idea, so the plan stays private — rejected: publishing the full plan under a restrictive license.
- GitHub Pages serves index.html from the root of main, with .nojekyll — the mockup is one static file — rejected: a docs/ folder or a gh-pages branch.
- The product is autonomous news aggregation with machine-made correlation links — the owner stated this on 2026-11-21 — rejected: the packet's editor-reviewed, manually produced briefing, which both councils ruled on.
- The name is "Then What News", with the repo and page at `thenwhatnews` — the owner chose it on 2026-11-21 because a stranger understands it — rejected: "Ripple Atlas" (unclear, and it reads as the crypto company), "Aftermath Map", "Knock-on Map". Open: a USPTO search before any domain purchase.
- A link carries one of three labels: followed, related, or attributed — the software never states a cause in its own voice, which keeps political links safe to publish without an editor — rejected: one "caused" label that the model assigns.
Pointers: branch main · index.html (mockup) · https://drewjst.github.io/thenwhatnews/ · research/council-packet.md, research/council-first-move.md, research/council-name.md (all local only)
