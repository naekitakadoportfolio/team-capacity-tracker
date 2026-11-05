<p align="center"><img src="assets/banner.svg" alt="Team Capacity Tracker" width="100%"></p>

<p align="center">
<img src="https://img.shields.io/badge/stack-Apps_Script_·_HTML_Service_·_Sheets-14384E?style=flat-square">
<img src="https://img.shields.io/badge/data-fictional-89CDE7?style=flat-square">
<a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb"><img src="https://img.shields.io/badge/Portfolio-Nae_Kitakado-1D4C93?style=flat-square"></a>
</p>

<p align="center"><a href="https://naekitakadoportfolio.github.io/team-capacity-tracker/"><img src="https://img.shields.io/badge/%E2%96%B6%20Try%20the%20live%20demo-14384E?style=for-the-badge" alt="Live demo"></a></p>

# Team Capacity Tracker

A multi-page capacity planner for creative teams. It shows true weekly editor capacity, lets managers assign holds on a board with over-capacity warnings, tracks output by pipeline quarter over quarter, ranks Best Bets over a rolling window, and runs data audits that catch phantom capacity and over-counted metrics.

> **Portfolio rebuild.** A from-scratch recreation of a production system I designed and run. It uses **fictional people and data**, with no client names, code or branding.

## ✨ Features
- **Overview:** editors counted, weekly capacity, assigned load, open holds, utilisation bars and a needs-attention list
- **Weekly board:** columns per editor, move holds between editors, over-capacity confirmation, create new holds (validated)
- **Editors:** edit capacity, add editors (duplicate and range checks), mark departed (their holds return to Unassigned automatically)
- **Pipeline output:** quarter picker, change per pipeline and a grouped SVG chart
- **Best Bets:** rolling-window slider, average pace, utilisation and 8-week sparklines
- **Data audit:** phantom-capacity detector with one-click fix, substring vs exact field-match check, trigger timezone check
- **Settings:** snapshot timezone and time, exclude departed editors, default window
- **Activity log**, persisted state, light/dark theme

## 🧭 Try it
1. Open the **[live demo](https://naekitakadoportfolio.github.io/team-capacity-tracker/)**. Dan has departed but still holds work.
2. Open *Data audit* → **Fix now**, then look at the *Weekly board*
3. Move a hold onto a full editor to see the capacity warning

## 🏗 Production architecture
| Layer | Production | This demo |
|---|---|---|
| Data | Project-tool API → daily Sheets snapshot | Seeded editors & holds |
| Jobs | Time-driven trigger in the team's timezone | Settings page |
| Discovery | `Discovery.gs` feasibility audits before building metrics | Data audit page |
| UI | `WebApp.gs` + `Dashboard.html` | Static SPA |

## 📁 Project structure
```
team-capacity-tracker/
├── index.html        # built app (shell + app code, single file)
├── src/
│   ├── app.js        # views, state seed, business logic
│   └── app.json      # title, navigation, theme, storage key
├── assets/banner.svg # README banner
├── README.md
└── LICENSE
```

## 🚀 Run locally
No build step is needed to run it. Open `index.html`, or serve the folder:
```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```
`index.html` is generated from `src/` by a small shared shell (hash router, persisted state, modals, toasts, light/dark theme).

## 🧩 Implementation notes
- `counted()` excludes departed editors when the setting is on, which removes phantom capacity
- Pipeline metrics use exact field matching, because substring matching double-counts variants like "UGC Remix"
- Best Bets average = the last *n* weeks of each editor's history ÷ *n*

## 🗺 Roadmap
- Drag-and-drop on the board
- Holiday-aware capacity per editor
- Forecast of next week's open holds from the intake rate

---
<p align="center"><sub>Built by <b>Nae Kitakado</b>, AI Automation Consultant · <a href="https://www.linkedin.com/in/nae-k-203194265">LinkedIn</a> · <a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb">Portfolio</a> · open to retainer &amp; part-time consulting</sub></p>
