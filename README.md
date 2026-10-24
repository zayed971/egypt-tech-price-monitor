# egypt-tech-price-monitor

A price collector for computers and tech in Egypt, with some coverage of the UAE, Saudi Arabia and the US (new and used). It scrapes public shop pages, stores every price it sees in SQLite, exports CSV/JSON, flags deals, and can send alerts to Telegram.

It was **built for my own PC purchase in October 2026**: find a PC or laptop build, plus discounted parts, under 70,000 EGP. I bought my PC, so the experiment is closed. The code and the results are published here in case they are useful to someone else. See [RESULTS.md](RESULTS.md) for what it found.

Status: finished, not maintained. Shops change their sites often, so expect some adapters to break.

## What it does

- Collects listings from about 50 Egyptian shops (Shopify, WooCommerce, sitemap and plain-HTML adapters), three Egyptian price aggregators, and a few UAE, Saudi and US retailers.
- Classifies each listing (laptop, PC, CPU, GPU, RAM, SSD, monitor, accessories and so on) and parses specs from the title (RAM size and type, GPU model, storage and similar). Missing facts stay empty; nothing is invented.
- Keeps price history in SQLite, evaluates simple rules (`rules.json`: five price targets and an 8% drop in 24 hours) and an exchange-rate baseline (`references.json`).
- Estimates what an imported item would cost in EGP (`egypt-deals import-check`, template: `import-quote.example.json`).
- Optional Telegram alerts (`TELEGRAM_BOT_TOKEN` and `TELEGRAM_CHAT_ID` in `.env`, see `.env.example`).
- Is polite by design: honours robots.txt, rate limits per host, no logins, no CAPTCHA solving.

## Shops covered

The full list with adapters and URLs is in [`sources.json`](sources.json). Egyptian retailers include Compumarts, Alfrensia, Ennap, Kimo Store, Egypt Laptop, El Badr, Raya Shop, 2B, AHW Store, Sigma Computer, More Shopping, DokkanTech, Softlink, Dream 2000, Elyamama, King Tech, Technology Valley, B.TECH, Jumia, Amazon.eg, Noon and many smaller computer shops. Aggregators: Qarenly, EGPrices, Pricena. UAE, Saudi and US sources are in `global_sources_seed.csv` and the `global_*` modules.

How many of them actually worked in the October 2026 run is in [`results/report.md`](results/report.md) (source coverage section) and [`results/sources-in-listings-export.csv`](results/sources-in-listings-export.csv). Several shops were blocked or failed in that run.

## Install and run

Needs Python 3.11 or newer.

Linux / macOS:

```bash
git clone <this repo> && cd tech-monitor
python3 -m venv .venv
.venv/bin/pip install -e '.[test]'
.venv/bin/pytest -q                      # offline tests, fixtures only
.venv/bin/egypt-deals run                # small default run (4 pages per source)
.venv/bin/egypt-deals run --sources compumarts,kimo --max-pages 12
.venv/bin/egypt-deals run --scope hardware --max-pages 150 --max-details 100 --cache-ttl 0   # big run
.venv/bin/egypt-deals export             # rebuild CSV/JSON/reports from the database
```

Windows: run `Setup-Windows.cmd` once (creates `.venv`, installs the package), then `Start-Monitor.cmd`. Or use the same commands as above with `.venv\Scripts\python.exe -m egypt_deals.cli ...`.

Useful commands: `run`, `watch` (long-running scheduler), `export`, `notify`, `fx` (refresh USD/EGP), `telegram-setup`, `import-check --quote-file my-quote.json`.

Output goes to `data/` (created on first run): `deals.sqlite3`, `listings.csv/json`, `report.md`, `hardware/`, `laptop-review/` and so on. `scripts/` holds the one-off analysis scripts used during the experiment (deal scan, top-10 verification, laptop review, store payment-method check). Some of them expect extra local tools (an optional LLM CLI); they are optional and read their settings from environment variables.

## How the data is organised

| Where | What |
| --- | --- |
| `egypt_deals/` | the package: adapters, model, storage, rules, hardware classifier, reports |
| `scripts/` | runners and analysis scripts |
| `tests/` | offline tests with small HTML/JSON fixtures |
| `sources.json`, `rules.json`, `references.json` | shop list, alert rules, spec and exchange-rate references |
| `results/` | the reports and small result tables of the October 2026 run (about 15 MB) |
| GitHub Release assets | the large datasets, compressed with xz (listings, hardware tables, fresh listings, candidate lists), with `SHA256SUMS.txt` |

Main columns of the listing tables: `store, source, url, observed_at, raw_title, price_egp, old_price_egp, currency, stock, condition, mpn, sku, alert_eligible`, plus parsed specs. `price_egp` is the advertised price converted to EGP; `stock` is what the shop page said. Variants (for example Shopify sizes) are separate rows.

## Limits

- Scraping breaks when shops change their pages. Several adapters were already failing in the October 2026 run.
- The prices are a **snapshot from 2026-10-05 to 2026-10-09**. They are not current.
- The sample is bounded by page limits and is not the whole Egyptian market. Coverage gaps are listed in `results/hardware/coverage-and-gaps.json`.
- "In stock" is what a shop feed said, not a checkout guarantee. Used listings are asking prices.
- Private marketplace data (Facebook Marketplace, Dubizzle, OpenSooq, Haraj, Reddit) and seller details were removed from the published data. The Facebook Marketplace collector and the browser-driven collectors (for shops that refuse plain requests) are not published; the plain-HTTP collectors remain.
- No warranty of any kind. Check prices on the shop's own page before buying.

## License

Code: MIT. Data: see the data note in [LICENSE](LICENSE). Author: zayed971.
