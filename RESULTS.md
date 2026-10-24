# Results of the October 2026 experiment

This file summarises what the price monitor found. Every number below is quoted from a report or table in [`results/`](results/); the file is named next to it. Anything I inferred myself is marked **(inference)**. Prices are advertised prices in EGP, without delivery, as shown by the shops on the dates given. They are a snapshot, not current prices.

The goal was a PC or laptop build, plus discounted parts, with a budget of 70,000 EGP. The buyer was in Egypt (the city was removed from the published files).

## 1. Size and dates

- **Dates:** listing observations run from 2026-10-05 to 2026-10-09 (`observed_at` in the listings export). The main collection run started 2026-10-09 19:59 UTC and finished 20:34 UTC (`run-manifest.json`). Page-level verification of the shortlists was done on 2026-10-05 and 2026-10-06 (`laptop-review/review.md`, `laptop-vs-desktop.md`, `ram-top10`, `screen-top10`).
- **Extracted listings:** 87,224 (`report.md`); 30,273 of them were eligible for price alerts. The published copy of the listings export has 83,693 rows, because 3,531 private-marketplace rows (Facebook Marketplace, Dubizzle, OpenSooq, Haraj, Reddit) were removed.
- **Hardware table:** 68,422 hardware offer rows across all stock states, of which 23,306 were eligible in-stock retailer offers (`hardware/report.md`). Per category, for example: laptop 9,542 (1,533 eligible), GPU 5,202 (752), SSD 3,441 (502), monitor 3,521 (1,000), RAM 2,445 (463), PSU 1,820 (593).
- **Catalogue run of 2026-10-05:** 22,218 unique priced retailer products, 10,558 of them marked in stock, from 8 shops (`catalog-counts.json`).
- **Shops:** `report.md` lists 81 source entries: 41 `ok`, 13 `blocked_or_failed`, 8 `works` (US shops), 3 `wall`, 1 `no_data` and 15 `n/a` (marketplaces and some UAE/Saudi sources). The hardware report covers 50 Egyptian sources, 39 `ok` and 11 `blocked_or_failed`. The published listings export has 66 source ids (`sources-in-listings-export.csv`); the aggregator Qarenly contributes dozens of sub-stores. Failed or blocked in the last run: B.TECH, Jumia, Raya, Sigma (listing feed), Egypt Laptop, Technology Valley, El Badr, Elyamama, Dubizzle, Noon (robots.txt) and a few more. Their rows come from earlier or partial collections.
- **Currencies in the listings export:** 78,042 EGP, 2,248 AED, 1,749 USD, 1,651 SAR, 3 unknown rows.

## 2. Best deals per category

New, advertised prices. Stock was checked on the shop's own page only for the shortlisted items, on the dates given in section 5 and 6 and in the source files.

| Category | Pick | EGP | Shop | Source file |
| --- | --- | ---: | --- | --- |
| Value laptop (plugged-in 3D work) | Lenovo LOQ 15ARP9, Ryzen 7 7435HS, RTX 4060 8GB, 12GB DDR5, 512GB | 54,499 | Sigma Computer | `laptop-review/review.md` |
| Cheaper laptop | Lenovo LOQ 15IAX9E, i5-12450HX, RTX 4050 6GB, 8GB, 512GB | 45,499 | Sigma Computer | `laptop-review/review.md` |
| Laptop at the ceiling | Lenovo LOQ 15IRX10, i7-14700HX, RTX 5060, 16GB DDR5, 512GB (DOS, no Windows) | 69,499 | Sigma Computer | `report.md`, `alerts.json` |
| Laptop, 1TB | Gigabyte A16, i7-13620H, RTX 5060, 16GB, 1TB | 64,900 | Compumarts | `laptop-review/review.md` |
| Laptop, 100W RTX 5060 | MSI Cyborg 15 Max, i7-13620H, RTX 5060, 16GB, 512GB | 65,499 | Compumarts | `laptop-review/review.md` |
| Used laptop (CAD) | Dell Precision 3581, i7-13800H, RTX A500 4GB, 16GB, 512GB | 35,500 | Kimo Store | `laptop-review/review.md` |
| Desktop tower | i5-14400F / RTX 5060, 16GB DDR4, 256GB NVMe | 44,200 | Softlink | `laptop-vs-desktop.md` |
| Desktop tower | Ryzen 5 5600 / RTX 5060 8GB, 16GB DDR4, 256GB NVMe | 45,700 | Elyamama | `laptop-vs-desktop.md` |
| Desktop tower, 16GB GPU | Ryzen 5 7600X / RTX 5060 Ti 16GB, 16GB DDR5, 500GB | 66,666 | Compumarts | `laptop-vs-desktop.md` |
| Budget tower | Super Nova V6, Ryzen 5 5500 / RTX 3050 6GB, 8GB DDR4, 256GB SATA | 25,500 | Compumarts | `top10/shortlist.md` |
| GPU (standalone) | EVGA RTX 3060 XC 12GB | 12,400 | Egypt Laptop | `laptop-vs-desktop.md`; later **withdrawn as out of stock** in `top10/shortlist.md` |
| Laptop RAM (16GB DDR5) | Acer SD200 16GB DDR5-5600 SO-DIMM | 9,500 | Compumarts | `ram-top10/shortlist.md` |
| Desktop RAM (32GB DDR4) | Lexar THOR 32GB (2x16) DDR4-3200 | 11,900 | Softlink | `ram-top10/shortlist.md` |
| SSD (1TB NVMe) | KLEVV CRAS C715 1TB Gen3 | 5,699 | Alfrensia | `top10/shortlist.md` |
| SSD (1TB NVMe) | Crucial E100 1TB | 7,300 | not named in the file | `laptop-vs-desktop.md` |

The editorial "top 10" (`top10/shortlist.md`, checked 2026-10-06) mixes laptops, towers, the GPU (withdrawn), RAM and an SSD. It says of itself that it is "an editorial shortlist from the current collection, not a benchmark ranking or a claim to the entire Egyptian market".

Workstation totals from that file: the i5-14400F / RTX 5060 tower plus the 32GB DDR4 kit and 1TB NVMe SSD comes to **61,799 EGP** in advertised parts; the Ryzen 5 5500 / RTX 3050 tower with the same memory and storage to **43,099 EGP**. Neither includes monitor, peripherals, delivery, fitting or a Windows license.

### Laptop review (2026-10-05)

`laptop-review/review.md` reviewed 248 distinct eligible, in-stock retailer products (212 new, 36 used), out of 1,824 variant offers / 1,731 distinct retailer products across all stock states. Its recommendation: start with the 54,499 EGP LOQ RTX 4060 for value when plugged in; compare the 65,499 EGP MSI Cyborg 15 Max and the 69,499 EGP LOQ i7-14700HX / RTX 5060 if more headroom justifies the cost. It states that no Blender or Rhino benchmark results were collected, so these are specification-based candidates.

A refresh on 2026-10-09 (`laptop-review/summary.json`) counted 5,259 under-budget variant rows (5,087 unique products, all stock states). Of these, 1,107 variant rows / 1,075 unique products were eligible and in stock (932 new, 123 used, 20 refurbished).

### Alerts (`alerts.json`)

The original file had 11 alerts; the published copy has 10, because one alert about a Dubizzle listing was removed. Rules that fired: `ddr5-laptop-16` (16GB DDR5 laptop stick at or below 10,000 EGP; cheapest 9,300 EGP at Dar El Computer, then 9,500 at Compumarts), `loq-14700hx-5060` (69,499 EGP at Sigma) and `drop-24h` (price drops of 9.1% to 34.4% within 24 hours, for example a Razer BlackShark V2 X headset from 4,620 to 3,030 EGP at AHW Store).

From `report.md`, best verified price against each target:

- LOQ i7-14700HX / RTX 5060: 69,499 EGP (target 70,000), met.
- 16GB DDR5 laptop stick: 9,300 EGP (target 10,000), met.
- 32GB DDR5 desktop kit: 22,500 EGP at El Badr (target 21,000), **not met**.
- Used RTX 3060 12GB (target 13,000) and used 5600X / RTX 3060 full PC (target 32,000): **no verified eligible listing**.

## 3. Laptop versus desktop (`laptop-vs-desktop.md`, checked 2026-10-06)

Stated decision: "local buying is the best-supported option currently; a cheaper delivered overseas deal has not been verified. Desktop offers now deserve equal attention: for work at a fixed desk, they provide clear upgrade and GPU-memory advantages. A laptop remains attractive when portability and an included screen matter."

- Three verified towers: 44,200 (Softlink), 45,700 (Elyamama) and 66,666 EGP (Compumarts), all reported in stock on 6 October.
- With 32GB RAM and a 1TB SSD swapped in, the Softlink tower is **62,500 EGP** and the Elyamama tower **64,000 EGP**, before peripherals and delivery.
- The 66,666 EGP tower has 16GB GPU memory against 8GB in the shortlisted RTX 4060/5060 laptops, but only 16GB system RAM.
- The report says "No matched Blender/Rhino measurements were obtained, so no percentage speed advantage is claimed." Nothing in the data settles which is faster for rendering. **(inference)** On price for the GPU class, the towers win clearly in this data; the laptop wins on portability and an included screen.

## 4. Import versus local (`import-comparison.md`, `laptop-vs-desktop.md`)

- Conclusion: "The local shortlist currently favors buying in Egypt." No cheaper delivered Amazon US offer was verified. No destination-specific Amazon US checkout was obtained (direct Amazon.com access returned HTTP 500).
- Exchange-rate baseline: 1 USD = 52.24751 EGP (provider quote 2026-10-05T00:02:31+00:00).
- All-in break-even (item + shipping + import charges): LOQ i7-14700HX / RTX 5060 at 69,499 EGP = $1,330.19 (with an illustrative 3% card fee: $1,291.44); 16GB DDR5 laptop stick at 9,500 EGP = $181.83; 32GB DDR5 desktop kit at 25,875 EGP = $495.24. `laptop-vs-desktop.md` gives about $1,013 to beat the 54,499 EGP laptop and $1,291 to beat the 69,499 EGP one. These are calculations, not live offers; the 3% fee and 10% saving are scenarios.
- One verified US example: Newegg's Crucial CT16G56C46S5 16GB DDR5-5600 laptop RAM showed $274.95, about 14,365 EGP before shipping and import costs, against 9,500 EGP locally for the Acer module. Different brands, and no Egypt delivery quote.
- `registry/egypt_import_rules.md` and `registry/*.jsonl` hold the research notes on import rules and on shops in Egypt, the Gulf and elsewhere.

## 5. RAM picks (`ram-top10/shortlist.md`, checked 2026-10-06, 15:26-15:27 Egypt time)

| # | RAM | For | EGP | Shop |
| --- | --- | --- | ---: | --- |
| 1 | Acer SD200 16GB DDR5-5600 | Laptop | 9,500 | Compumarts |
| 2 | PNY 16GB DDR5-4800 | Laptop | 9,550 | Compumarts |
| 3 | TEAMGROUP Elite 32GB (1x32) DDR4-3200 | Laptop | 9,750 | Compumarts |
| 4 | Crucial 16GB DDR4-3200 | Laptop | 5,550 | Kimo Store |
| 5 | Crucial 8GB DDR4-3200 | Laptop | 2,550 | Kimo Store |
| 6 | Lexar THOR 32GB (2x16) DDR4-3200 | Desktop | 11,900 | Softlink |
| 7 | Acer Predator Vesta II 32GB (2x16) DDR5-6000 CL36 | Desktop | 22,500 | El Badr |
| 8 | HIKSEMI Hiker 16GB DDR4-3200 | Desktop | 5,500 | Compumarts |
| 9 | Acer UD200 16GB DDR5-4800 | Desktop | 9,500 | El Badr |
| 10 | Crucial 8GB DDR4-3200 UDIMM | Desktop | 2,650 | El Badr |

Lowest observed new RAM prices across the whole table (`hardware/report.md`): DDR5 16GB DIMM 9,500 (Acer, El Badr); DDR5 16GB SODIMM 9,300 (Acer, Dar El Computer); DDR5 32GB DIMM 16,300 (Acer, Dar El Computer); DDR5 32GB SODIMM 20,500 (KLEVV, Sigma); DDR4 16GB DIMM 4,999 (Kingston, Square Tech); DDR4 32GB DIMM 11,000 (Crucial, Softlink). The report warns that a 32GB total may be a kit and that unknown form factors are excluded. RAM fields missing in the data: capacity 142, DDR generation 105, form factor 844, module count 1178.

Upgrade cost (`laptop-review/review.md`): a 16GB DDR5 laptop stick is about 9,500 EGP, so the 69,499 EGP LOQ becomes 78,999 EGP with one extra stick, and the 54,499 EGP 12GB LOQ becomes 73,499 EGP if both modules are replaced with 16GB sticks.

## 6. Screen picks

Monitors (`screen-top10/shortlist.md`, checked 2026-10-06, 15:52 Egypt time), 27 inch unless noted:

| # | Monitor | Specs | EGP | Shop |
| --- | --- | --- | ---: | --- |
| 1 | ASUS ProArt PA278QGV | QHD IPS 120Hz, 95% DCI-P3 | 14,499 | Alfrensia |
| 2 | ViewSonic VA2708-4K-MHD | 4K IPS 60Hz | 10,999 | Compumarts |
| 3 | Samsung Odyssey G5 G50F | QHD IPS 180Hz | 8,888 | Compumarts |
| 4 | ASUS VA27AQ | QHD IPS 75Hz | 6,999 | El Badr |
| 5 | Gigabyte G27U | 4K IPS 160Hz | 16,899 | El Badr |
| 6 | MSI Modern MD272UPHW | 4K IPS 60Hz, USB-C 98W | 16,300 | El Badr |
| 7 | Philips 32E1N3500 (31.5 inch) | QHD IPS 100Hz | 9,150 | Compumarts |
| 8 | MSI PRO MP275Q | QHD IPS 100Hz | 8,199 | Compumarts |
| 9 | ViewSonic VA24E1-H (24 inch) | FHD IPS 120Hz | 3,999 | Compumarts |
| 10 | Gigabyte GO27Q24G | QHD WOLED 240Hz | 22,899 | Alfrensia |

Small screens under 27 inch (`small-screen-top10/shortlist.md`, checked 2026-10-06): new Full HD IPS monitors from 3,650 EGP (MSI PRO MP225, 21.5 inch, 100Hz, Compumarts) to 4,888 EGP (MSI PRO MP243L E14, Compumarts); used from 1,650 EGP (Fujitsu B24-8 TE Pro 24 inch and Dell U2312HM 23 inch, both Kimo Store, "Grade A original used"). These are advertised specifications, not measured colour accuracy.

## 7. Automatic deal flags (`deal_scan/`)

`scripts/deal_scan.py` flags listings that are far below the median of similar offers or marked down from a "was" price. The shortlist in the published copy has 167 rows (153 Egypt, 7 Saudi, 6 UAE, 1 US). An LLM pass (DeepSeek, no internet, titles only) gave 515 verdicts: 310 ok, 134 skip, 59 look, 12 unsure (`hermes_verdicts.jsonl`). The shortlist ages range from 1.6 to 44.3 hours at flag time.

**Treat these as unverified leads, not deals.** Many flags are artefacts of the matching: a "was" price of 8,888,008,888 on a monitor, bundles and different variants grouped together, and cheap accessories compared with pricier look-alikes. Examples that looked interesting at flag time: Xiaomi Sound Play speaker 3,599 EGP against a median of 30,999 for 5 other offers (Ennap); Gigabyte Z890 EAGLE WIFI7 motherboard 12,325 against a median of 35,020 (Compumarts); Ryzen 7 5800X3D at 18,499 marked down from 33,333 (Compumarts). **(inference)** Some of these are probably listing errors or mismatched products; none were checked at checkout.

## 8. What the data cannot tell you

- Whether any price held after the collection date. The monitor was set to watch until 2026-10-26, but no later data is included.
- Final cart price, delivery cost, warranty type (an `ED` model suffix does not prove official Egyptian warranty), installed RAM layout, GPU power limits and battery health. These stay empty in the data rather than being guessed.
- Benchmarks. None were run.
- Offline stores and private sellers. They were out of scope; the marketplace collectors were blocked (robots.txt, login walls) or are not published.

## 9. Data quality notes

- Several shops were failing during the final run, so their rows may be older than 2026-10-09.
- The same product can appear several times (Shopify variants, Sigma language pages, Qarenly aggregator copies of shop listings).
- Some shop pages hold conflicting prices (for example the Alfrensia Klevv 32GB DDR5 kit: 25,875 EGP visible against 22,499 in a duplicate structured-data block). The visible one was used.
- Spec parsing is title-based and sometimes wrong. The `quality_issues` column in the hardware tables lists what the pipeline itself flagged, such as power supplies priced under 1.5 EGP per watt.
