# CHANGELOG.md

An unofficial weekly newspaper about the IMD swarm, written for ordinary readers.

Issue **005**, published **2 November 2026**, covers **26 October 00:00 to 2 November 00:00 UTC, end exclusive**: the complete Monday–Sunday week of 26 October–1 November. The lead is Wheelworks, a browser puzzle inspired by a real hamster’s activity. Two new-project stories, three security findings, two signed answers and a world-simulation preview complete the issue.

The finished static export is in [dist/](dist/). All **five** editions and their reporting notes are embedded at build time. Only No. 005 is tagged Latest. Application source, styles, layout, metadata, configuration, dependencies and lockfile are unchanged. Issues 001–004 are byte-identical to the supplied files; issue 001 already has its correct 10 October publication date.

## Install, preview and rebuild

Use Node.js **22.12 or newer** and the committed npm lockfile:

```sh
npm ci
npm run dev
```

For the production export:

```sh
npm run typecheck
npm run build
npm run check
npm run preview
```

Open the URL printed by Vite. Serve `dist/` over HTTP, including under a hosting subpath. The build uses relative asset URLs and regenerates `issues/index.json`, root RSS and the RSS inside the export. It pre-renders the latest paper and embeds every issue and reporting note in `dist/index.html`. Rebuilding needs no IMD connection, credentials or assignment inputs.

The latest paper is readable before JavaScript. Tabs, source visibility and glossary explanations use JavaScript. During reading, the page requests only local assets and Google Fonts. It has no API calls, external scripts, trackers, analytics, wallet connection or persistent browser storage. Visit and Source links navigate when selected. Reading and primary interactions work with external requests blocked.

RSS lists every issue newest first, with publication dates and `#noN` links. The existing publication address in `scripts/content.mjs` is preserved; set `PAPER_SITE_URL` when rebuilding for another known address.

## Check the interactions

```sh
npx playwright install chromium
npm test
```

The existing suite starts and closes a temporary preview under a nested path. It checks production content, source visibility, glossary focus, keyboard tabs, history, disclosures, responsive reflow, enlarged text, offline reading, metadata, embedded data and RSS. Disposable archive fixtures check empty sections and unknown links; fixtures never enter the export.

`PLAYWRIGHT_BROWSERS_PATH` selects a writable browser-download directory; `PLAYWRIGHT_CHROMIUM_EXECUTABLE` can select an existing binary. Tests write results to ignored `artifacts/` paths. The historical `scripts/test-rendering.mjs` contains issue 004/date assertions; it was preserved and was **not** treated as an issue 005 test.

For this issue, installation used `npm ci --cache /tmp/changelog-005-npm-cache --no-audit --no-fund`. Browser downloads used `PLAYWRIGHT_BROWSERS_PATH=/tmp/changelog-005-browsers`. Dependencies, browsers, caches and disposable fixtures are excluded from delivery.

## Reporting and evidence

Public API requests supplied a custom `CHANGELOG.md/005` User-Agent. The main collector used `CHANGELOG.md/005 (public weekly newspaper; factual archive research)`. Reporting is start-inclusive and end-exclusive, in UTC.

| Measure | Issue 005 |
| --- | ---: |
| Completed jobs | 553 |
| Live launches first recorded during the week | 60 |
| Answers signed during the week | 75 |
| Workers online at reporting time | 1,042 |
| Swarm-o-Meter | 33/100 |

The meter compares 553 completed jobs with the preceding week’s 847: **35% fewer**. Its formula is `round(50 × current / previous)`, capped at 100; equal weeks score 50.

As in the existing paper, `numbers.accepted` counts **completed jobs by their last recorded update**, matching the preserved “Completed jobs” label. `/steps/hourly` supplied only a rolling 24-hour series, even with longer-period parameters. It cannot establish a weekly contribution total. “How we counted” explains this limit and the job-based measure.

The weekly ranking separately counts accepted nodes with a seat and an update time within the week, including nodes in blocked jobs: **Seat #1470 (15), Seat #2 (9), Seat #47 (9)**. There were 1,740 attributed contributions and 27 accepted nodes without a seat. Missing attribution remains a ranking limitation. Update times stand in for acceptance times; these are contributions, not distinct jobs. Online is the connected-worker count from `/health` at **01:00:32 UTC on 2 November**, not a weekly total.

Research scanned **15,673 unique jobs** and **8,932 unique answer requests** to exhaustion, overlapping timestamp boundaries and deduplicating IDs. It read all **566** relevant job details; seven rate-limited reads succeeded on retry. The 500-row launches response extends before both reporting weeks. Selection also read 400 publications, 100 audit publications and 100 workflows.

[005-counts.json](artifacts/005-counts.json) preserves relevant rows, pagination and arithmetic. [005-story-evidence.json](artifacts/005-story-evidence.json) records dated publications, audit excerpts, answer decoding and project-documentation checks. [evidence/005.json](evidence/005.json) holds the notes embedded in the paper. `npm run check` recalculates issues 003–005 from saved trails; issues 001–002 remain unverified from raw trails.

Every story has an API source; the watch source is in its reporting note. Project descriptions were cross-checked against documentation at the delivered revision. Selected projects’ required `sites.imd.fun` aliases returned 404, and the alternate gateways tested failed TLS. All four Visit links therefore use the permitted public Explorer project pages, each checked with an HTTP 200 response. Third-party gameplay was not independently exercised.

Selection omits spam, offensive material, copycat projects and financial speculation. Audit stories describe possible user consequences without claiming real harm or shipped repairs. Signed answers report public attestations; signatures and underlying claims were not independently certified.

## Actual validation

Production build, TypeScript and content/evidence checks passed. The existing Chromium suite passed **58 checks**; an additional scratch check passed **31**, covering all five real editions offline, dates, weekly/all-time headings, source preference, first-screen controls and desktop text fragments. Automated accessibility scans reported **zero violations** at five widths and in the glossary. There were no application console errors or failed resources. Google Fonts loaded directly in Chromium.

The pinned design probe ran on the export: **9 of 16 checks passed**. Six flags concern inherited newspaper styling or density that the brief requires preserving. The layout flag is a paragraph bounding-box heuristic across columns; screenshots and a text-fragment measurement found no actual text overlap. No horizontal scrolling or hidden text was reported. The 390px first screen visibly contains the paper, Latest tab, source switch and lead headline.

The supplied browser MCP could not start because its configured Chrome executable was absent. Local Playwright Chromium supplied rendered checks and screenshots. WebKit could not start because host libraries were missing. Safari, physical devices, human screen-reader use, native zoom, print and forced-colors rendering remain unverified. Text enlargement is not native zoom.

See [docs/validation-005.md](docs/validation-005.md) for actual commands, six-domain Better Interface coverage, findings, exceptions and limitations. [005-interaction-results.json](artifacts/005-interaction-results.json), [005-taste.json](artifacts/005-taste.json) and the [mobile](artifacts/005-screenshots/mobile-first-screen.jpg) and [desktop](artifacts/005-screenshots/desktop.jpg) screenshots retain current results. These are worker-side observations, not independent certification. Earlier validation documents remain historical records.

## Submission budget

The exact artifact allowlist in `.gitignore` budgets **6.5 MiB**: **3.5 MiB** for retained issue 003 files, **2 MiB** for retained issue 004 files and **1 MiB** for issue 005. Issue 005 allows **0.75 MiB JSON** and **0.25 MiB screenshots** across six named paths. All other submitted paths share **1.5 MiB**. No historical evidence is removed. The complete submission must stay below **8,388,608 bytes**; actual sizes are in the validation note.

Source, the existing manifest and lockfile, complete static export, runtime assets and notices are included. Dependencies and caches are ignored at every depth. No submodule, package archive or dependency mirror is delivered.

## Add another edition

1. Gather the latest complete Monday–Sunday UTC week with a distinct User-Agent.
2. Add the next numbered issue and reporting note. Preserve earlier issues; `date` is publication day and `week` is the coverage period.
3. Save compact dated evidence, including accepted nodes and recorded seats within the week. Missing `leadersScope` means all-time.
4. Rebuild, typecheck and check interactions, evidence, export assets and submission size. Tabs, Latest, index and RSS are generated from every issue.

The implemented visual system is in [DESIGN.md](DESIGN.md). Guide attribution and licenses remain in [docs/design-guidance-licenses.txt](docs/design-guidance-licenses.txt); runtime notices are included in `dist/`.
