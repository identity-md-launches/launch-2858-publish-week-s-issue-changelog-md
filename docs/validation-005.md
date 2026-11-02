# Issue 005 validation and design review

Complete for the stated publication scope, with the browser and reporting limitations below. This is a worker’s record of checks, not independent certification.

## Scope and authority

Publish issue 005 for **Monday 26 October 2026 00:00 UTC through Monday 2 November 00:00 UTC, end exclusive**, with publication date **2 November 2026**. The existing React/TypeScript/Vite paper, CSS, metadata, build configuration, manifest and lockfile are preserved. Its existing labels and behavior already meet the requested date, leader-scope and online wording. Issues 001–004 are unchanged; issue 001 already says 10 October.

The visual idea is an ordinary newspaper: warm newsprint, a gothic masthead, serif reporting and ruled columns, with restrained red editorial marks. The user’s requirement to “Keep the existing site's design, layout and code exactly as they are” controls any conflict with the probe’s house preferences. Changes are editorial data, notes, index/feed/export, documentation and an explicitly budgeted evidence allowlist.

## Requirement coverage

| Requirement | Result and evidence |
| --- | --- |
| Most recent full UTC week and publication date | Met: issue 005, 26 October–1 November; publication 2 November |
| Exact issue shape; three lead paragraphs; bounded lists | Met: content validator; two new stories, three findings, two answers |
| API sources, plain language, no prohibited story content | Met: source/prose validator and editorial review; watch source in `evidence/005.json` |
| Weekly numbers, comparison and seat ranking | Met with disclosed time/attribution limits: saved trail recalculates all values |
| Preserve earlier issue files | Met: files 001–004 compare byte for byte with the baseline |
| Every issue embedded; newest-first tabs and one Latest | Met: five embedded editions; five real tabs exercised offline |
| Publication date, Covering week, correct leader scope, workers online | Met: existing components; all five real editions checked |
| Glossary, sources switch, Visit links, meter, watch, disclaimer | Met: existing interactions and paper content retained |
| Static export, relative assets, source and lockfile | Met: production build and subpath browser checks; protected files unchanged |
| No network except Google Fonts; no external scripts or wallet | Met: observed resource requests and offline interaction checks |
| RSS and index include every issue | Met: generated index and feed; existing test compares root/export RSS |
| Responsive first screen and share metadata | Met: screenshots, five tested widths and metadata checks |
| Production build, typecheck, interactions, six-domain review | Met: results below; Safari and unavailable manual checks explicitly excluded |
| Design and installation documentation; size budget | Met: refreshed root documents and final integrity audit |

No feature is presented as live when it is fabricated. Figures are a dated issue snapshot; online has a visible snapshot footnote. External hosting after delivery is outside this local publication task.

## Reporting method and checks

API reads used custom `CHANGELOG.md/005` User-Agent headers. The main collector’s full value is recorded in `artifacts/005-counts.json`. A 33-page job scan yielded **15,673 unique records**; a 19-page answer scan yielded **8,932**. Each timestamp cursor overlaps by one millisecond and IDs are deduplicated; both scans exhausted the collection. Relevant two-week rows and page metadata are retained. The final overlapping page may contain an already-seen boundary record and no new ID.

All **566** job details with a last update in or after the current week were read, including jobs created earlier. Seven temporary rate-limit failures were retried with lower concurrency and all succeeded. Weekly leaders count accepted nodes with recorded seats, irrespective of parent job state. The trail contains **1,740** attributed nodes and **27** without a seat. Attributed counts include 31 nodes in blocked jobs. Ties use the lower seat number. The top three are Seat #1470 (15), Seat #2 (9), Seat #47 (9).

The original hourly endpoint and a request for 336 historical hours both returned only a rolling 24-hour series. The preserved paper’s `numbers.accepted` therefore continues to mean completed parent jobs dated by their last update, matching its “Completed jobs” label. The results are **553**, versus **847** in the previous week. The meter is `round(50 × 553 / 847) = 33`; completed jobs fell **35%**. The accepted-node ranking is a separate measure. Node updates are proxies for acceptance times; absent attribution and later record changes remain limitations.

The launches response contained 500 records, reaching back to 12 October, before both weeks. There were **60** live releases first recorded in the current week. There were **75** requests attested within it. The health snapshot at **2026-11-02 01:00:32.398 UTC** reported **1,042 connected workers**. It is not a weekly average or peak.

Selection read 400 newest publications, 100 audit publications and 100 workflows, plus launch records. All seven selected project/report records have publication times inside the week. Both answer records have attestation times inside it, agreement at or above quorum and decoded results matching the text. The health answer is about 98 out of 100; the checked hamster hour records zero wheel passes. Subjects of questions can predate the attestation week.

Project descriptions were cross-checked against README files at their delivered revisions. Audit findings were read from their API Markdown reports. The paper’s broad Moderate label covers two source Medium findings and one source Low finding affecting refunds in a practice game; that difference is retained in the story trail. It claims no real losses or subsequent repairs. No signature verification, independent security audit, reproduction of the external findings or third-party gameplay test is claimed.

## Findings and corrections

| Finding | Location, observation and correction | Recheck |
| --- | --- | --- |
| Outbound project aliases unavailable | `issues/005.json:14` and the other Visit fields: the selected `sites.imd.fun` aliases returned HTTP 404. The brief expressly permits Explorer. Visit links now use the exact project pages there. This is an external-service limit, not a paper rendering defect. | All four final Visit pages returned HTTP 200. API source links remain separate. |
| Jargon in an answer draft | `issues/005.json:61`, answer summary: the draft called periods “settled.” Replaced that with “Each period already had a completed record” and explained why zero was not filled in for missing data. | Final issue passed prose/schema validation and editorial review. |
| Unstated counting limits could mislead | `evidence/005.json:5`: the hourly response is only 24 hours; 27 accepted nodes lack seats; update times stand in for acceptance. The notes disclose the unit, period and missing attribution, following the existing paper’s approach. | Saved arithmetic passes; How we counted and ranking notes render with the issue. |

No new application defect was reproduced, and no application code change was necessary. Two early assertions in the supplemental scratch check were corrected: tab labels are read independently of adjacent dates, and the date-line check accounts for the inherited uppercase CSS. Those were test-comparison mistakes, not website defects. The final supplemental run passed all 31 checks.

## Better Interface coverage

The pinned workflow and core principles of all six domains were read before publication. Source review and rendered checks are distinguished here.

| Domain | Checked source and rendered states | Coverage limits |
| --- | --- | --- |
| Accessibility | `src/App.tsx:263` keyboard tab pattern, native controls, names/roles, glossary dialog and source switch; `src/styles.css:44` visible two-pixel focus outline. Keyboard navigation, Enter/Space disclosures, Escape and focus restoration passed. Focused tab/dialog screenshots were inspected. Automated accessibility scans found zero violations at 320, 390, 768, 1024, 1440 and in the open dialog. | No human screen-reader session or physical assistive-device test; not a claim of complete accessibility compliance. |
| Layout | `src/styles.css:54` page width and `:89` lead columns; breakpoints at `:209`, `:222`, `:250`. Mobile/desktop screenshots and five-width overflow checks passed. At 390 the masthead, latest edition, source switch and complete lead heading are above 844px. All five real tabs remain reachable offline. | Native browser zoom, RTL/localization and print rendering untested. The existing suite did test 200% text enlargement. |
| Writing | `issues/005.json`, `evidence/005.json`, and inherited labels in `src/App.tsx`. Stories explain what projects do and possible user effects in short prose. Unknown outcomes and snapshot limits are explicit. No worker is named outside Seat numbers. Empty-section and unknown-link fixture copy remains truthful. | External project claims were checked against delivered descriptions, not independently exercised. |
| Typography | `src/styles.css:12` font roles; `:86` lead heading, `:89` body columns, `:267` phone body. Three intended Google Font families loaded in Chromium. Actual content wraps without clipping at the five tested widths; numeric data keeps tabular figures. | Existing small tracked print labels, numerous size steps and four weights are preserved by the brief. Safari/font-loading transitions were not retested here. |
| Colors | `src/styles.css:3` existing semantic palette; real foreground/background pairs measured from six representative elements. Ink/paper 14.30:1; accent/paper 5.54:1; muted/paper 5.49:1; ink/panel 12.92:1; accent/panel 5.01:1; muted/panel 4.97:1. Labels and outlines accompany color states. | These are measured opaque pairs, not every composited/modal state. Forced colors untested. Only the existing light theme is shipped. |
| UI details | Native details, native dialog, source switch, tab selection and meter retained. Screenshots show square newspaper rules and the existing shaded panels. The probe found no border-plus-shadow surfaces, nested cards, gradient text, transition-all or endless animation under reduced motion. | Physical touch and browser animation-panel playback untested; there is no animated interaction sequence to slow down. Forms, wallets, transactions and alternate themes are not applicable. |

The wallet references were read and classified as not applicable: this is a newspaper, and the brief expressly excludes wallet connection. Existing Better Interface/Impeccable attribution and license texts remain in `docs/design-guidance-licenses.txt`.

## Design probe

The exact pinned probe ran against the production export, with results retained in `artifacts/005-taste.json`: **9 passed, 7 flagged**. Passing checks: render, targets, contrast, glyphs, slogans, repetition, chrome, motion and share metadata.

| Flag | Evidence and disposition |
| --- | --- |
| Layout | No horizontal scroll at 320, 390 or 1440 and no hidden text. Three paragraph-box intersections at 1440 arise from the bounding boxes of paragraphs fragmented across CSS columns (`src/styles.css:89`). The desktop image was inspected; a DOM Range check measured **zero overlapping text fragments between paragraphs**. No text-over-text defect was found. |
| Casing | 26 content boxes use inherited uppercase styling, including `.eyebrow` (`src/styles.css:56`), action labels (`:122`) and severity badges (`:133`). Preserved newspaper design. |
| Tracking | 28 content boxes exceed the probe’s tracking preference; `.eyebrow` uses `.11em`, actions `.065em`. Preserved newspaper design. |
| Eyebrows | 13 heuristic kicker detections, including severity labels and some adjacent-data false positives. Editorial kickers and labels are part of the preserved design. |
| Type sizes | 14 repeated sizes at both measured widths; 20 sizes including one-offs at 390, 19 at 1440. The existing scale is preserved. |
| Type faces | Three families pass the family limit; the existing 400/500/600/700 weights exceed the probe’s three-weight preference. No fonts or weights were added. |
| Copy budget | Probe counts 95 prose words on the first phone screen and 178 on desktop, above its house thresholds. This is an existing newspaper reading layout. The requested product and controls are visible on the first phone screen; the layout was preserved. |

The explicit preservation requirement takes precedence over the six styling/density preferences. They remain documented exceptions; the probe is not reported as an unqualified pass.

## Actual commands and outcomes

The dependency manifest and lockfile were used unchanged.

```sh
npm ci --cache /tmp/changelog-005-npm-cache --no-audit --no-fund
PLAYWRIGHT_BROWSERS_PATH=/tmp/changelog-005-browsers npx playwright install chromium webkit
npm run build
npm run typecheck
npm run check
PLAYWRIGHT_BROWSERS_PATH=/tmp/changelog-005-browsers npm test
PLAYWRIGHT_BROWSERS_PATH=/tmp/changelog-005-browsers node .imd/reads/skills/design-critic/scripts/taste.mjs --out test/scratch/taste
PLAYWRIGHT_BROWSERS_PATH=/tmp/changelog-005-browsers node test/scratch/check-edition.mjs
git diff --check
```

| Check | Actual result |
| --- | --- |
| Production build | Exit 0; five issues prepared, content validation passed, Vite export produced |
| Typecheck | Exit 0, `tsc --noEmit` |
| Content and saved evidence | Exit 0; issues 003–005 recalculated, 001–002 reported as lacking raw trails |
| Existing interaction suite | Exit 0; **58 checks** in Chromium **156.0.8078.4**, under `/preview/paper/` |
| Supplemental real-edition check | Exit 0; **31 checks**, all five real issues offline, dates/scopes/source preference correct |
| Automated accessibility | Zero violations at five widths and in the glossary dialog |
| Resources and console | Zero application errors or failed requests; only Google Fonts left the local origin |
| Offline/static behavior | External requests blocked, then browser offline; all five editions remain usable. Latest issue also readable with JavaScript disabled. |
| Probe | Ran successfully, nine checks passed and seven flags reviewed as above |
| Final Visit links | Four HTTP 200 responses from exact Explorer project records |

The first default browser-install attempt could not write its home cache; retrying with the writable `/tmp` browser path succeeded. The downloaded WebKit runtime could not launch because required host libraries were absent. The supplied browser MCP separately answered `Chromium distribution 'chrome' is not found at /opt/google/chrome/chrome`. It produced no preview or screenshot. Local Playwright Chromium supplied all current rendered evidence. No Chrome installation outside the allowed paths was attempted.

The full desktop page, 390px first screen, keyboard focus and glossary screenshots produced by the existing suite were inspected locally. The retained compact screenshots are `artifacts/005-screenshots/mobile-first-screen.jpg` (390×844) and `desktop.jpg` (1440×1100). The latter covers the desktop first screen; it is not described as a full-page image. The 89 combined checks and measurements are retained in `artifacts/005-interaction-results.json`.

## Remaining limits and completion

Current Safari/WebKit behavior, human screen-reader use, physical devices, native browser zoom, print and forced-colors rendering were not verified. API records can change after collection. Source evidence is not an independent security or signature certification. The required project aliases were unavailable; working Explorer links are used as expressly permitted. The existing RSS publication base is preserved and can be overridden at build time.

These limits are disclosed without changing the requested paper design. The static export, complete source and existing lockfile are delivered. Final path, integrity and size measurements follow.

## Final integrity and path budget

The final delivery contains **74 files, 7,278,883 bytes** (limit **8,388,608**). The production export contains **8 files, 382,357 bytes**. The final check parsed both RSS files, confirmed five entries newest first, and compared all five embedded issues exactly with their source JSON.

| Path group | Bytes used | Explicit allowance |
| --- | ---: | ---: |
| artifacts/003 | 3,479,347 | 3,670,016 |
| artifacts/004 | 1,944,202 | 2,097,152 |
| artifacts/005 | 926,068 | 1,048,576 |
| other | 929,266 | 1,572,864 |

Issue 005 uses **698,369 bytes of JSON** (limit 786,432) and **227,699 bytes of screenshots** (limit 262,144). No historical evidence was removed. The allowlist admits exactly four issue 005 JSON files and two JPEGs.

A byte comparison confirmed **44 baseline files unchanged**, including issues 001–004, all existing application/build/test sources, the manifest and lockfile, public assets, historical reporting artifacts and earlier edition notes. No submitted dependency/cache directory, symlink, submodule or package archive was found. Obsolete generated RSS assets were removed by the existing build; the current referenced RSS asset is included. `git diff --check` passed.
