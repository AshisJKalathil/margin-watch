# Margin Watch

Live WIP, margin and cash control for home builders. This is a working demo
that starts with a fictional 60-job Adelaide builder.

Live demo: https://ashisjkalathil.github.io/margin-watch/

## Files

- `engine.js`: the calculation engine in plain JavaScript (no DOM). It holds
  the demo data generator, CSV import with flexible column matching
  (including Xero line-level bill exports), WIP, margin and leakage
  analysis, a 13-week cash forecast, business-health indicators and
  supplier-bill checks. It also runs in Node:
  `node -e 'const MW=require("./engine.js"); console.log(MW.analyse(MW.generate()).totals)'`
- `app.html`: the screens.
- `build.py`: puts `engine.js` inside `app.html` to make `index.html`.
- `index.html`: the built page that GitHub Pages serves.
- `sample-data/`: the eight demo tables as CSV. Use them as templates for a
  real builder's exports.

## AI features

The AI buttons (owner brief, explain a job, scan site notes, drafts, Ask and
reading a bill) need a hosted AI service and show "not available" on this
site. Every other part of the demo works here.

## Using real data

Export the eight tables (jobs, schedule, estimate, purchase orders, supplier
bills, variations, stage claims, site notes) as CSV and drop them on the
"Your data" tab. Files are read in the browser only and never uploaded.
Keep all amounts consistently ex-GST.

Build: `python3 build.py`
