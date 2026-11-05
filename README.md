<p align="center"><img src="assets/banner.svg" alt="Team Capacity Tracker" width="100%"></p>

<p align="center">
<img src="https://img.shields.io/badge/stack-Apps_Script_·_HTML_Service_·_Sheets-5B3A3A?style=flat-square">
<img src="https://img.shields.io/badge/data-fictional-FBE3EC?style=flat-square">
<a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb"><img src="https://img.shields.io/badge/Portfolio-Nae_Kitakado-F4B4CD?style=flat-square"></a>
</p>

<p align="center"><a href="https://naekitakadoportfolio.github.io/team-capacity-tracker/"><img src="https://img.shields.io/badge/%E2%96%B6%20Try%20the%20live%20demo-5B3A3A?style=for-the-badge" alt="Live demo"></a></p>

# Team Capacity Tracker

Shows how much creative capacity a team really has, how output is trending by pipeline, and who the top performers are over a rolling window. Toggle departed editors to see phantom capacity disappear.

> **Portfolio rebuild.** This is a from-scratch recreation of a production system I designed and run, rebuilt with **fictional data** and no client names, code or branding. The live demo runs entirely in the browser.

## The problem
Managers assigned creative holds without a reliable view of editor capacity. Departed editors still showed up as available because of status gaps, substring field matching inflated output numbers, and triggers ran in the wrong timezone.

## Impact in production
A trusted capacity view: phantom capacity removed, output metrics cleaned up, quarter-over-quarter comparisons by pipeline, and rolling Best Bets windows to guide assignments.

## What it demonstrates
| Capability | How |
|---|---|
| Capacity modeling | Editors × weekly capacity vs assigned load |
| Data integrity | Departed-editor exclusion, exact field matching |
| Trend analysis | Quarter-vs-quarter output by pipeline |
| Rolling metrics | Configurable Best Bets window |
| Feasibility audits | Discovery script to check data before building |

## Production architecture
WebApp.gs + Dashboard.html · time-driven trigger in the correct timezone · project-tool API → Sheets snapshot · Discovery.gs for data feasibility audits

## Try it
Open the **[live demo](https://naekitakadoportfolio.github.io/team-capacity-tracker/)** or run `index.html` locally. No install needed.

---
<p align="center"><sub>Built by <b>Nae Kitakado</b>, AI Automation Consultant · <a href="https://www.linkedin.com/in/nae-k-203194265">LinkedIn</a> · <a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb">Portfolio</a> · open to retainer &amp; part-time consulting</sub></p>
