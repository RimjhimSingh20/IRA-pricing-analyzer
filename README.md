# MarketAccess.ai — IRA Strategy Suite

A healthcare consulting analytics platform for navigating CMS drug price negotiation under the Inflation Reduction Act. Built as a portfolio piece targeting market access roles at firms like Avalere Health, ZS Associates, and IQVIA.

**Live site:** https://rimjhimsingh20.github.io/IRA-pricing-analyzer/

---

## Tools

### 1. IRA Negotiation Risk Analyzer
Assess a drug's probability of CMS selection using a 6-factor weighted scoring model.
- Medicare Part D spend, market exclusivity, MTEP eligibility, indication breadth, orphan drug modifier, unmet medical need
- Risk score 0–100 with tiered output (Low / Moderate / High)
- Payer strategy recommendations and PDF export

### 2. CMS Outcome Simulator
Model the financial impact of IRA negotiation across all statutory discount tiers.
- Three scenarios: Statutory Ceiling, Analyst Base Case, CMS Aggressive
- Calibrated to 2024 CMS negotiated prices (avg 64% discount)
- Biologic vs. small molecule toggle with drug-type-specific ranges
- 5-year revenue trajectory chart with 2% annual volume growth

### 3. HEOR Value Dossier Generator
Generate structured AMCP-format health economics and outcomes research packages.
- 16-input form across clinical, economic, and evidence dimensions
- ICER positioning chart, payer readiness score, evidence gap analysis
- AMCP dossier checklist with 11 sections and submission readiness %

### 4. Model Validator
Retrospective validation of the simulator's Analyst Base Case against 2024 CMS published prices.
- All 10 drugs from the inaugural Medicare negotiation cycle pre-loaded
- Per-drug prediction error, RMSE (12.5pp), MAE (10.4pp)
- Animated bar chart (predicted vs. actual), outlier analysis for Imbruvica and Januvia
- Biologic systematic bias analysis with recalibration recommendation

---

## Technical Stack

| Layer | Technology |
|-------|-----------|
| UI framework | React 18 (UMD CDN) |
| Templating | Babel Standalone (JSX in-browser) |
| Styling | Tailwind CSS (Play CDN) |
| Charts | SVG + CSS animations (no charting library) |
| Hosting | GitHub Pages (static, no build step) |
| Fonts | Inter (Google Fonts) |

No Node.js, no build step, no dependencies to install. Each tool is a single self-contained HTML file.

---

## Statutory Framework

| Reference | Description |
|-----------|-------------|
| IRA § 1191–1198 | Medicare drug price negotiation authority |
| IRA § 1192(d) | MTEP eligibility thresholds (9yr small molecule / 13yr biologic) |
| IRA § 1194 | Maximum Fair Price (MFP) calculation methodology |
| IRA § 1194(c)(1)(B) | Statutory discount tier floors: 25% / 35% / 60% |

---

## Project Structure

```
ira-drug-analyzer/
├── index.html            # Landing page — suite overview and tool cards
├── analyzer.html         # IRA Negotiation Risk Analyzer
├── cms-simulator.html    # CMS Outcome Simulator
├── heor-dossier.html     # HEOR Value Dossier Generator
└── model-validator.html  # Model Validator (2024 CMS retrospective)
```

---

## Data Sources

- CMS Medicare Drug Price Negotiation Program — Initial Negotiated Prices for 2026 (August 2024)
- FDA Orange Book and Purple Book (approval dates)
- IRA § 1191–1198 statutory text
- AMCP Format for Formulary Submissions v4.1
