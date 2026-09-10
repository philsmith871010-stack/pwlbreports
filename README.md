# PWLBreports

The published site. Treasury management strategies, outturns and monitoring
reports built to the liability benchmark framework in CIPFA's 2026 consultation.

**This repo holds output, not source.** The tool is built from `builder/src/*`
in the private `pwlbtoday-tms` repo by `builder/build.py`; nothing here is
edited by hand.

| File | What it is |
|---|---|
| `index.html` | the landing page (`site/pwlbreports.html` in the source repo) |
| `pwlbreports-tool.html` | the tool itself, one self-contained file |
| `market-latest.json` | the rate snapshot the tool fetches from its own origin |

## market-latest.json

The tool ships with a rate snapshot compiled into it, and on load it fetches
this file and takes it **only if it is at least as current**. So the file is a
safe thing to overwrite: a stale or malformed one changes nothing, and the page
falls back to what it was built with.

That is the hook for live rates. Nothing writes it on a schedule yet — it is
published as a copy of the snapshot the tool was built from.
