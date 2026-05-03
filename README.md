# Bundle Proposition — Data-Backed Product Bundle Intelligence

> **Turn billing data into sales-ready "Good / Better / Best" bundle recommendations — powered by Apriori association mining, MinHash clustering and heroicness scoring.**

---

## What this is

This project analyses real billing data to answer the question every sales team asks but rarely answers with data:

*"Which products should we pitch together — and in what order?"*

The pipeline mines actual customer purchase patterns, clusters accounts into bundle archetypes, identifies the **Hero product** that anchors each archetype, and outputs a structured **Good / Better / Best recommendation tree** per customer segment — complete with confidence scores, lift ratios, and a sales story for each tier.

The interactive dashboard (`index.html`) presents every output from the pipeline as a clean, mobile-friendly interface — no server required, open it directly in any browser.

---

## Live demo

Open `index.html` directly in your browser — no build step, no server, no dependencies to install.

[View the live project here] (https://steveyeongg.github.io/Bundle-Proposition/)

---

## Dashboard pages

| Page | What it shows |
|---|---|
| **Overview** | Pipeline summary, all 14 output files, key metrics |
| **Part 1–2 · Billing** | Raw billing rows, account-level product bundles, product penetration |
| **Part 3 · Apriori** | Top association rules by lift, heroicness leaderboard, revenue by product |
| **Part 4 · Archetypes** | Bundle cluster distribution, archetype-rule match table |
| **Part 5 · GBB Bundles** | Interactive Good/Better/Best recommendation trees per archetype |

---

### Key concepts

**Hero product** — the single product that most frequently appears as an antecedent in association rules *and* is present in ≥50% of accounts in its archetype. The door-opener the sales rep leads with.

**Hotness score** — composite metric: `0.20 × Count + 0.20 × Coverage + 0.20 × Confidence + 0.20 × Lift + 0.20 × Zhang's metric`. Measures whether a bundle rule is frequent, strong, and commercially scalable.

**Tier logic**
- **Good** — Hero + 1 add-on with highest Confidence + Coverage. Safe, fast close.
- **Better** — Good + 3 add-ons with highest Lift + Zhang's metric. Designed to be the default self-selection via anchoring/compromise effect. Marked *Most Popular*.
- **Best** — Better + 2 stretch add-ons ranked by average revenue per account. Aspirational/decoy tier that makes Better look like a bargain.

---

## Python dependencies

```
pandas
numpy
mlxtend
scikit-learn
openpyxl
hashlib (stdlib)
```

---

## Author

**Steve Yeong** · Pricing & Commercial Analytics  
Version: April 2026
