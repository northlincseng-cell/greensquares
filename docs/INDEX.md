# My Green Squares (MGS) — Documentation Index

> **For AI agents:** Read this file first. It tells you what this project is, what documents exist, and what order to read them depending on the task.

## What Is This Project?

My Green Squares (MGS) is a consumer-facing sustainability platform where:

- **1 Green Square (GS) = 100g CO2e** of verified carbon reduction
- Priced at **£0.003** per GS to retailers
- Each GS requires **75%+ verified transition action** (not offsets) — staged progression to 80% → 85% → 90%
- Maximum **25% offsetting** permitted within a GS
- GS **expire after 12 months** — creating visible social consequences for stopping donations
- **Three tiers:** T1 retailer basket-value, T2 brand product-specific, T3 charity donations (Oxfam/WWF model)
- Built as a **CIC** (Community Interest Company) with statutory asset lock on conservation fund
- Offset project: **Verra VCS-1566** (Juma Reserve, REDD+)
- Stake in **C2050** (Ireland-registered D-MRV platform, claimed JP Morgan/KPMG/S&P partnerships — not independently verified)

## Platform Context

- **Deimos** — Separate C#/.NET platform for corporate energy transition verification. Feeds into MGS mass energy balance calculations.
- **Demo** — The root of this repo (`index.html`, `account.html`, `admin.html`, etc.) is a GitHub Pages demonstrator built in 18 hours using Claude on Antigravity. The demo contains dummy data — GS count and pricing shown are not production values.
- **Production stack** — Deimos is C#/.NET. Production MGS stack TBD but should be as close to deployable as possible.

## Repository Structure

```
greensquares/
├── index.html                    # Demo: Homepage
├── account.html                  # Demo: Member account page
├── admin.html                    # Demo: Admin dashboard
├── retailer-analytics.html       # Demo: Retailer analytics dashboard
├── consumer-app.html             # Demo: Consumer mobile app
├── epos-terminal.html            # Demo: EPOS terminal integration
├── map.html                      # Demo: Conservation project map
├── assets/                       # Demo: CSS, images, video, data
│
├── docs/                         # ← All documentation lives here
│   ├── INDEX.md                  # THIS FILE — start here
│   │
│   ├── architecture/             # Architecture specifications
│   │   ├── green-square-composition.md    # What a GS contains (the "anatomy")
│   │   └── lca-energy-system.md          # LCA & energy balance system architecture
│   │
│   └── research/                 # Deep research notes (numbered, sequential)
│       ├── 01_co2e_normalisation.md       # CO2e conversion factors and normalisation
│       ├── 02_carbon_tokens_fungibility.md # Carbon token fungibility mechanisms
│       ├── 03_c2050_un_harmonisation.md   # C2050 / UN harmonisation research
│       ├── 04_scope3_consumer_mapping.md  # Scope 3 to consumer action mapping
│       ├── 05_verification_traceability.md # Verification and anti-greenwashing
│       ├── 06_consumer_sustainability_currencies.md # Precedent schemes analysis
│       ├── 07_reewild_competitive_analysis.md # Reewild/PlanetPoints competitive analysis
│       ├── 08_lca_standards.md            # LCA standards (ISO 14040/44/14067, PEF, PAS 2050)
│       ├── 09_energy_balance_standards.md # Mass energy balance, ISO 50001, Deimos integration
│       ├── 10_lca_tools_databases.md      # LCA tools, platforms, databases, build vs buy
│       └── 11_incumbents_auditability.md  # Incumbent consultants & Big 4 audit requirements
```

## Reading Order by Task

### "I'm building the Green Square calculation engine"
1. `docs/architecture/green-square-composition.md` — What a GS contains
2. `docs/research/01_co2e_normalisation.md` — How CO2e conversions work
3. `docs/research/04_scope3_consumer_mapping.md` — How Scope 3 maps to consumer actions
4. `docs/architecture/lca-energy-system.md` — Full system architecture (Section 3: Two Engines)

### "I'm building the Deimos energy balance engine"
1. `docs/architecture/lca-energy-system.md` — Full system architecture (Sections 3, 5, 9)
2. `docs/research/09_energy_balance_standards.md` — Mass energy balance standards, MHHS, REGOs
3. `docs/research/08_lca_standards.md` — LCA standards context

### "I'm building the product LCA / carbon footprint system"
1. `docs/architecture/lca-energy-system.md` — Full system architecture (Sections 3, 4, 5)
2. `docs/research/08_lca_standards.md` — ISO 14040/44/14067, PEF, GHG Protocol
3. `docs/research/10_lca_tools_databases.md` — Tools, APIs, databases, build vs buy
4. `docs/research/11_incumbents_auditability.md` — What auditors need

### "I'm building the audit trail and compliance layer"
1. `docs/architecture/lca-energy-system.md` — Section 6: Auditability Architecture
2. `docs/research/11_incumbents_auditability.md` — Big 4 requirements, ISSA 5000
3. `docs/research/05_verification_traceability.md` — Verification frameworks

### "I'm building the consumer app or retailer dashboard"
1. `docs/architecture/green-square-composition.md` — What consumers see and interact with
2. `docs/research/06_consumer_sustainability_currencies.md` — Precedent schemes
3. `docs/research/07_reewild_competitive_analysis.md` — Competitive landscape
4. Review the demo HTML files in the repo root for current UI patterns

### "I'm building the blockchain/tokenisation layer"
1. `docs/research/02_carbon_tokens_fungibility.md` — Token design and fungibility
2. `docs/research/03_c2050_un_harmonisation.md` — C2050 and UN carbon market context
3. `docs/research/05_verification_traceability.md` — Verification chain design

### "I need the full picture"
Read `docs/architecture/lca-energy-system.md` first — it synthesises everything.

## Key Design Constraints (Non-Negotiable)

These rules come from the founder and must be respected in all builds:

1. **1 GS = 100g CO2e** — not 0.45kg, not 1kg. The demo shows 0.45kg — that is wrong and must be corrected.
2. **75% minimum transition action** — offsets cannot exceed 25% of a GS.
3. **Staged progression** — thresholds increase from 75% → 80% → 85% → 90%.
4. **No double-dipping** — a corporate like Nestlé can use their offset inside a GS, but commercial terms must be agreed. One credit cannot back two claims.
5. **12-month expiry** — GS expire. If a donor stops, their GS count visibly declines. This is the retention mechanic.
6. **Physical primacy** — Deimos must weight physically metered energy data above contractual paper claims (unbundled REGOs get zero credit).
7. **GS pricing is £0.003 each** — demo data showing other prices is dummy data.
8. **Every GS must be promotable** — the corporate providing the GS can promote the relevant message as they see fit. GS must contain what they're promoting that week. Keep GS fresh and relevant.
9. **Social + environmental, not just carbon** — every GS project has social and environmental benefits. That's what makes every Green Square different.

## API Integration Architecture (for builders)

The production system uses a layered API approach:

```
[MGS Platform]
    ├── Product PCFs ────→ CarbonCloud API (food carbon footprints)
    ├── Agriculture ─────→ Cool Farm Tool API (crop/dairy)
    ├── Scope 1/2/3 ─────→ Climatiq Enterprise API (DEFRA+EXIOBASE+EPA)
    ├── UK Statutory ────→ DEFRA flat file (self-hosted, free)
    ├── Advanced LCA ────→ openLCA IPC (gRPC, self-hosted, ecoinvent)
    ├── Grid carbon ─────→ National Grid ESO Carbon Intensity API (free)
    ├── EAC verification → Ofgem REGO Registry
    └── MHHS data ───────→ Elexon / supplier data feeds
```

Estimated API cost: £1,000–5,000/month at startup scale.

## Version History

| Date | Change | Author |
|------|--------|--------|
| March 2026 | Initial demo built (18 hours, Claude on Antigravity) | Founder |
| March 2026 | Research notes 01–07 added (GS composition deep research) | Perplexity Computer |
| March 2026 | Research notes 08–11 added (LCA & energy balance research) | Perplexity Computer |
| March 2026 | Architecture specs added (composition model + LCA/energy system) | Perplexity Computer |
