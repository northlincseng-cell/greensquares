# My Green Squares (MGS)

**Consumer-facing sustainability platform where every Green Square represents verified carbon reduction.**

> **1 Green Square = 100g CO2e** — priced at £0.003 to retailers

## What Is This?

My Green Squares is a system that connects corporate carbon transition actions to consumer-visible sustainability units called "Green Squares". Unlike pure-offset schemes, each GS requires **75%+ verified transition action** (removing fossil fuels from the supply chain), with a maximum 25% permitted from offsets. GS thresholds progressively tighten: 75% → 80% → 85% → 90%.

The platform operates as a **CIC** (Community Interest Company) with a statutory asset lock on the conservation fund, using [Verra VCS-1566](https://registry.verra.org/app/projectDetail/VCS/1566) (Juma Reserve, REDD+) as the offset backing project.

## Demo

The root of this repo is a **GitHub Pages demonstrator** built in 18 hours using Claude on Antigravity.

**Live demo:** [https://northlincseng-cell.github.io/greensquares/](https://northlincseng-cell.github.io/greensquares/)

| Page | Description |
|------|-------------|
| `index.html` | Homepage |
| `map.html` | Conservation project map |
| `admin.html` | Admin dashboard |
| `retailer-analytics.html` | Retailer analytics |
| `account.html` | Member account page |
| `epos-terminal.html` | EPOS terminal integration |
| `consumer-app.html` | Consumer mobile app |

> **Note:** The demo contains dummy data. GS counts, pricing, and the 0.45kg CO2e figure shown are placeholder values — not production figures.

## Documentation

All project documentation lives in [`docs/`](./docs/INDEX.md).

**Start with [`docs/INDEX.md`](./docs/INDEX.md)** — it explains the project, lists every document, and provides reading orders by task (building the GS engine, the Deimos energy balance, the LCA system, the audit layer, the consumer app, etc.).

### Architecture Specifications
- [Green Square Composition Model](./docs/architecture/green-square-composition.md) — What a GS contains (the "anatomy")
- [LCA & Energy Balance System](./docs/architecture/lca-energy-system.md) — Full system architecture (705 lines, 72 citations)

### Research Notes (01–11)
Sequential deep research covering CO2e normalisation, carbon token fungibility, C2050/UN harmonisation, Scope 3 consumer mapping, verification traceability, precedent schemes, competitive analysis, LCA standards, energy balance standards, LCA tools/databases, and incumbent consultant/auditability analysis.

See [`docs/INDEX.md`](./docs/INDEX.md) for the full list and recommended reading order.

## Platform Architecture

```
MGS Ecosystem
├── My Green Squares (MGS)     — Consumer platform (this repo)
├── Deimos                     — C#/.NET corporate energy transition verification
└── Conservation Fund (CIC)    — Statutory asset-locked fund
```

**Deimos** is the separate C#/.NET platform that verifies corporate energy transition claims. It feeds mass energy balance calculations into MGS and is the gatekeeper for the 75% transition threshold.

## Three Tiers

| Tier | Model | Example |
|------|-------|---------|
| T1 | Retailer basket-value | Tesco adds GS to full basket at checkout |
| T2 | Brand product-specific | Nestlé embeds GS in specific SKU price |
| T3 | Charity donations | Oxfam/WWF direct donation model |

## Key Design Constraints

1. **1 GS = 100g CO2e** — fixed, non-negotiable
2. **75%+ transition action** — offsets capped at 25%
3. **No double-dipping** — one credit cannot back two claims
4. **12-month expiry** — GS expire, creating visible social consequences for stopping
5. **Physical primacy** — Deimos weights metered energy data above contractual paper claims
6. **Every GS is promotable** — corporates can promote their GS message; keep GS fresh and relevant
7. **Social + environmental** — every project has both dimensions; that's what makes each GS different

## Tech Stack

- **Demo:** Static HTML/CSS/JS (GitHub Pages)
- **Deimos:** C#/.NET
- **Production MGS:** TBD — target near-deployable from demonstrator
- **LCA APIs:** CarbonCloud, Cool Farm Tool, Climatiq Enterprise, DEFRA, openLCA, National Grid ESO

## License

Proprietary. All rights reserved.
