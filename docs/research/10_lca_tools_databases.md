# LCA Tools, Platforms & Emission Factor Databases
## Research Report for My Green Squares (MGS)

**Date:** March 2026  
**Purpose:** Inform build/buy/integrate decision for product-level carbon footprints (retail FMCG) and corporate energy balance.  
**Platform context:** C#/.NET SaaS, startup budget, UK-based.

---

## Executive Summary

MGS sits at a critical intersection: LCA tools built for expert consultants are overkill and expensive, while generic carbon accounting platforms lack the product-level food/FMCG granularity required. The most viable path for a startup is a **layered integration strategy**: use the **Climatiq API** or **CarbonCloud API** for product-level food carbon footprints, combine with **free DEFRA factors** for energy/corporate scope, and progressively build proprietary logic on top. Full build-from-scratch is inadvisable without significant LCA domain expertise. Full commercial LCA licensing (SimaPro, GaBi) is cost-prohibitive for a SaaS product and contractually restrictive on sub-licensing.

---

## 1. Open-Source LCA Tools

### 1.1 OpenLCA (GreenDelta)

| Attribute | Detail |
|-----------|--------|
| Language | Java (desktop application) |
| License | Mozilla Public License 2.0 (free) |
| Current version | 2.6.1 (released February 2026) |
| Database compatibility | ecoinvent, Agribalyse, USLCI, ELCD, GaBi, many others via Nexus |
| API | **IPC server exposing REST and gRPC — explicitly supports C#, Python, JS/TS** |
| Embedded use | Confirmed possible: GreenDelta themselves do this; other commercial applications built on the Java API or gRPC |
| Standards | ISO 14040, 14044, 14067, EN 15804, ISO 21930 |

**API details:** OpenLCA's IPC (Inter-Process Communication) server runs as a local/server process exposing REST and gRPC endpoints. The [olca-ipc Python package](https://github.com/GreenDelta/olca-ipc.py) is the reference client. C# support is listed explicitly on the [features page](https://www.openlca.org/features/). The API allows external applications to:
- Run LCA calculations against loaded databases
- Create/update product systems and processes
- Retrieve impact results, contribution trees, and Sankey data
- Perform Monte Carlo and parameter sensitivity analyses

**SaaS embedding considerations:** OpenLCA runs as a desktop GUI application — to embed it in a SaaS context, you run it headless as a calculation server. GreenDelta's commercial `onlineLCA` product does exactly this (openLCA models served via web interface). Multiple commercial deployments confirmed via community forum. **Key limitation:** the openLCA process must be running; it is not a pure library you compile into your code.

**Licensing note for SaaS:** OpenLCA itself is open source and free. However, any database (e.g., ecoinvent) loaded into it requires its own license. The tool itself places no SaaS restriction.

**Cost:** Free tool. ecoinvent licence from ~CHF 1,650/year (single user). Developer licence required for embedding ecoinvent in a product (price on request).

---

### 1.2 Brightway2 / Brightway 2.5

| Attribute | Detail |
|-----------|--------|
| Language | Python |
| License | BSD (open source, commercial use permitted) |
| Current version | Brightway 2.5 (stable, February 2025 on PyPI) |
| Database compatibility | ecoinvent (via `bw2io`), USLCI, any EcoSpold2/ILCD/SimaPro CSV format |
| API | Pure Python library — call directly from Python code |
| GUI | Activity Browser (separate open-source project) |
| Active development | Yes — Brightway 2.5 active as of 2025, with cloud computing capabilities added |

**Capabilities:**
- Full process-based LCA: build product systems, run characterisation, contribution analysis
- Monte Carlo uncertainty analysis
- Custom LCIA methods
- Time-explicit modelling
- Highly scriptable/automatable — ideal for batch processing thousands of products

**Integration with C#/.NET:** Not directly callable from C#. Would require:
1. A Python microservice (FastAPI/Flask) exposing Brightway calculations via REST, called from C#
2. Or Python.NET (`pythonnet`) interop (complex, not recommended for production)

**Commercial use:** BSD licence permits commercial use freely. No restrictions on SaaS deployment.

**Suitability for MGS:** Excellent for a Python-based calculation microservice feeding a C#/.NET front-end. The most flexible open-source option for food/FMCG LCA — Brightway's data structure accommodates any supply chain topology.

---

### 1.3 Activity Browser

| Attribute | Detail |
|-----------|--------|
| Language | Python (PyQt GUI on top of Brightway2) |
| License | LGPL (open source) |
| Purpose | Desktop GUI for Brightway2 databases |
| Integration value | Low for SaaS embedding — it's a desktop tool |

Activity Browser provides a graphical interface to Brightway2 databases. Useful for analysts building/validating LCA models, but not directly embeddable in a web application. Its value to MGS is in the **model-building and validation phase** rather than production.

---

### 1.4 pylcaio / LCAIO

| Attribute | Detail |
|-----------|--------|
| Language | Python |
| License | Open source (GitHub: MaximeAgez/pylcaio) |
| Purpose | Hybrid PLCA + MRIO (Input-Output) databases |
| Database support | ecoinvent 3.5–3.9 + EXIOBASE 3.7+ |

**What it does:** Hybridises process-based LCA (ecoinvent) with multi-regional input-output tables (EXIOBASE) to fill truncation gaps in upstream supply chains. The resulting hybrid database can be exported to Brightway2.

**Relevance to MGS:** High value for corporate-level energy balance and Scope 3 emissions — IO tables capture macro-economic supply chains that process-LCA misses. Last significant update was 2022; development appears to have slowed. Requires both ecoinvent and EXIOBASE licences.

---

### 1.5 C#/.NET LCA Libraries

**No purpose-built, production-ready C#/.NET LCA library exists in open source.** The LCA ecosystem is dominated by Java (openLCA), Python (Brightway2), and Matlab. Options for MGS:

| Approach | Description | Complexity |
|----------|-------------|------------|
| **openLCA gRPC via C#** | Call openLCA's IPC server from C# using generated gRPC stubs | Medium — requires running openLCA server process |
| **Python microservice** | Brightway2 wrapped in a REST API, called from C# | Low-medium — well-understood microservice pattern |
| **Build native C# engine** | Implement matrix-based LCA maths directly in C# | High — requires deep LCA domain expertise |
| **Call external API** | Climatiq, CarbonCloud, etc. — pure HTTP from C# | Low — standard REST integration |

The GreenDelta API documentation ([openLCA-ApiDoc](https://github.com/GreenDelta/openLCA-ApiDoc)) contains C# examples for the gRPC client. This is the most direct path to native C# integration with a full LCA engine.

---

## 2. Commercial LCA Platforms

### 2.1 SimaPro (PRé Sustainability)

| Attribute | Detail |
|-----------|--------|
| Type | Desktop/cloud LCA software |
| Version | SimaPro Craft 10.2 (includes ecoinvent 3.11) |
| Pricing | Expert: €6,100/year (first user); Power: €7,800/year |
| Extra users | Expert: €5,000/user/year; Power: €6,300/user/year |
| Databases included | ecoinvent v3, Agri-footprint, Industry data 2.0, USLCI, EU/Danish IO |
| API | **Synergy add-on** provides cloud/API integration layer |
| Target | LCA experts, consultants, academia, R&D teams |
| Standards | ISO 14040/44, 14067, EN 15804, PEF |

**Synergy (API layer):** SimaPro Synergy adds a cloud layer enabling multi-user collaboration and API integration. Pricing not publicly stated — enterprise quote. The Synergy API is REST-based and allows embedding SimaPro calculations into other systems.

**Licensing for SaaS sub-licensing:** PRé does not permit SaaS resale of SimaPro calculations without a separate commercial agreement. Not suitable for MGS to resell as a product.

**Assessment:** Industry standard for expert LCA practitioners. Too complex and expensive for a startup to license as a back-end calculation engine. Better used by MGS's own LCA team to build and validate reference models.

**Sources:** [SimaPro Plans](https://simapro.com/plans/), [Order Form PDF](https://simapro.se/wp-content/uploads/2025/08/2025.3-Order-form-SimaPro-plans-for-business-subscription.pdf)

---

### 2.2 GaBi / Sphera

| Attribute | Detail |
|-----------|--------|
| Type | Enterprise LCA + risk management platform |
| Database | 20,000+ datasets; 1,000+ pre-built models |
| Pricing | ~$15,000–$17,000/year (Vendr data); enterprise custom |
| API | ERP/PLM integration available; "LCA Automation" for portfolio footprinting |
| Target | Large enterprises, automotive, chemicals, consumer goods |
| Cloud/on-premise | Both available |

**LCA Automation:** Sphera's flagship feature for large companies calculating footprints across entire product portfolios, with ERP and PLM integration. Designed for enterprises managing thousands of products.

**Assessment:** Far beyond startup budget. Requires specialist GaBi expertise. Not API-first. Best in class for manufacturing enterprises — not relevant for MGS's current stage.

**Sources:** [Sphera LCA page](https://sphera.com/solutions/product-stewardship/life-cycle-assessment-software-and-data/), [Vendr pricing data](https://www.vendr.com/marketplace/sphera)

---

### 2.3 One Click LCA

| Attribute | Detail |
|-----------|--------|
| Type | Cloud SaaS LCA platform |
| Primary focus | Construction (EPDs, building LCA) — expanding to manufacturing/products |
| Pricing (Product LCA) | Business / Expert / Power Pack tiers — contact for pricing |
| API | REST API available for data import (CSV/Excel/API) |
| Database | World's largest EPD database; ecoinvent integration |
| Standards | EN 15804, ISO 14040, 14067, 21930; LEED, BREEAM, DGNB |
| Cloud | Yes — fully cloud |

**Food/FMCG relevance:** Primarily construction-focused. Has a Product Carbon Footprint tool, but food/agriculture data coverage is limited compared to food-specific platforms. API integration available but focused on BIM/construction workflows.

**Assessment:** Not relevant for MGS's food FMCG focus. Worth monitoring as it expands into manufacturing.

**Sources:** [One Click LCA EPD/Product Pricing](https://oneclicklca.com/en-us/pricing/product-lca-and-epd-pricing)

---

### 2.4 Ecochain (Helix)

| Attribute | Detail |
|-----------|--------|
| Type | Cloud SaaS LCA platform, SME-oriented |
| Pricing | Professional: from **€290/month** (€3,480/year); Business: from €417/month; Enterprise: custom |
| Database | ecoinvent 3.11 included; Agri-footprint add-on |
| API | API available for BOM import (CSV/Excel/API); enterprise tier for automation |
| Standards | ISO 14040/44, ISO 14067, PEF |
| Target | SMEs to enterprises in manufacturing, food, packaging |
| Cloud | Yes |

**Key value proposition:** Bulk product LCA at scale — claims <€50/product LCA at scale, vs €10,000+ for consultants. "Verify once" model for EPDs. API import of Bills of Materials.

**Assessment for MGS:** The most accessible commercial LCA platform at startup-friendly pricing. The Professional tier at €290/month gives access to a full LCA tool with ecoinvent. API integration is available but the platform is designed for businesses running their own LCAs, not for embedding into a third-party SaaS product. White-labelling not apparent.

**Sources:** [Ecochain Pricing](https://ecochain.com/pricing/)

---

### 2.5 Mondra

| Attribute | Detail |
|-----------|--------|
| Type | AI-powered food/agri LCA SaaS platform |
| Pricing | Not publicly disclosed; enterprise-grade; SaaS and DaaS options on "Comply" tier |
| API | Yes — "out-of-the-box API integrations to PLM and PIM vendors"; DaaS tier available |
| Database | Large verified food/beverage emissions factors database; global and national variants |
| Technology | "Hypermodelling" AI generates thousands of product PCFs from BOM data; farm-level primary data from 400K+ representative farms |
| Clients | Tesco, Sainsbury's, ASDA, Waitrose, Starbucks, Nando's — 85% of UK grocery retailers |
| Funding | £3.6M pre-Series A (Feb 2024) |
| Standards | GHG Protocol, ISO 14067, GSTA, CSRD, SBTi, CBAM |
| Focus | UK/EU food & beverage; retail-supplier collaboration |

**How Mondra builds their platform:** AI-powered digital twins of food product supply chains. Ingests existing specification data (BOM, recipe data from PLM/PIM systems). Applies farm-level primary data fused with benchmarks from 400K+ representative farms. Runs automated LCAs at portfolio scale. Key differentiator: the platform connects retailers, brand owners, and suppliers in a shared ecosystem, enabling supplier data contribution.

**API/DaaS:** Mondra offers Data as a Service on their Comply tier — emissions factors database available as a feed. API integrations confirmed with PLM/PIM systems (Manufacture 2030 partnership announced June 2024). This represents the closest competitor model to what MGS could build — and a potential data source.

**Assessment for MGS:** Mondra is a direct competitor in the UK food sector. Their DaaS offering could be relevant if MGS wants to license food emission factors rather than source them independently. The API integration model is directly analogous to what MGS needs to build.

**Sources:** [Mondra.com](https://www.mondra.com), [Net Zero Compare](https://netzerocompare.com/software/mondra)

---

### 2.6 CarbonCloud

| Attribute | Detail |
|-----------|--------|
| Type | Food product carbon footprint SaaS + API |
| Pricing | Not publicly disclosed — contact for API pricing |
| API | **Yes — REST API explicitly offered** for database integration |
| Database | Thousands of food product climate footprints, farm-to-shelf; biophysical model |
| Methodology | Scope 3 footprints, ISO 14067, GHG Protocol; FLAG and non-FLAG breakdown |
| Technology | AI-powered mapping from BOM data |
| Focus | Food and beverage — all categories |
| Cloud | Yes |

**API specifics:** CarbonCloud's API provides access to thousands of pre-calculated food product climate footprints. Designed for developers to integrate food carbon data into their own systems. The API page explicitly invites integration: "Superpower your system with thousands of high-fidelity climate footprints from all parts of the food system."

**Assessment for MGS:** **One of the highest-value integration options for product-level food footprinting.** If MGS needs pre-calculated food product footprints without building from scratch, CarbonCloud's API is a strong candidate. Pricing not public — requires direct sales engagement. The biophysical model provides scientifically robust results comparable to LCA consultancy.

**Sources:** [CarbonCloud API](https://carboncloud.com/api/), [CarbonCloud PCF](https://carboncloud.com/solutions/product-carbon-footprint/)

---

### 2.7 Umberto (iPoint)

| Attribute | Detail |
|-----------|--------|
| Type | Process modelling/material flow analysis + LCA |
| Pricing | Enterprise — quote required |
| Target | Manufacturing, industrial ecology, chemical industry |
| API | Not API-first; enterprise integrations possible |

**Assessment for MGS:** Specialist tool for process/flow modelling. Not relevant for retail FMCG food footprinting.

---

## 3. Enterprise Carbon Accounting Platforms

### 3.1 Sustain.Life

| Attribute | Detail |
|-----------|--------|
| Type | Cloud SaaS ESG/carbon accounting |
| Pricing | From **~$3,000/year** (per feature) |
| Scope | Scope 1, 2, 3 corporate emissions |
| API | Basic integrations; not API-first |
| Target | SMEs to mid-market businesses |
| Focus | Corporate GHG reporting, not product-level LCA |

**Assessment for MGS:** Corporate-level only. Too basic for product-level FMCG footprints. Low relevance.

---

### 3.2 Watershed

| Attribute | Detail |
|-----------|--------|
| Type | Enterprise corporate carbon platform |
| Pricing | **$30,000–$150,000/year** (typical ~$79,000) — enterprise only |
| Scope | Scope 1, 2, 3; decarbonisation roadmaps; regulatory reporting |
| API | Enterprise data integrations; no public developer API |
| Target | Large enterprises with mature sustainability programmes |
| Focus | Corporate measurement + reporting, not product-level LCA |

**Assessment for MGS:** Price point completely outside startup budget. No public API. Not relevant.

**Sources:** [Vendr Watershed pricing](https://www.vendr.com/buyer-guides/watershed), [Dcycle Watershed guide](https://www.dcycle.io/blog/watershed-pricing/)

---

### 3.3 Persefoni

| Attribute | Detail |
|-----------|--------|
| Type | Enterprise carbon accounting + climate disclosure |
| Pricing | **Persefoni Pro: Free** (Scope 1–3, all 15 categories, CSRD/ISSB reporting); Advanced: custom enterprise pricing |
| Scope | Scope 1, 2, 3 corporate; financial disclosure focus |
| API | Enterprise integrations; no public developer API |
| Target | Large enterprises, financial institutions |
| Focus | Corporate GHG + financial regulatory disclosure |

**Assessment for MGS:** The free Pro tier is genuinely useful for MGS's own corporate carbon footprint reporting. Not suitable as an embedded back-end for product-level footprints.

**Sources:** [Persefoni Pricing](https://www.persefoni.com/pricing)

---

### 3.4 Normative

| Attribute | Detail |
|-----------|--------|
| Type | AI-powered corporate carbon accounting |
| Pricing | Essential: custom (enterprise); Premium: custom |
| Emission factors | 349,000+ emission factors in database |
| API | Supply chain integrations (procurement system connectors) |
| Target | Mid-market to enterprise, complex supply chains |
| Focus | Scope 3 supply chain; science-based targets |

**Assessment for MGS:** Large emission factor database (349K+ factors) is noteworthy. Primarily corporate, not product-level FMCG. Not directly relevant for MGS's core use case.

**Sources:** [Normative Pricing](https://normative.io/pricing/), [KEY ESG review](https://www.keyesg.com/article/best-carbon-accounting-software-platforms)

---

## 4. Emission Factor Databases

### 4.1 ecoinvent (v3.11+)

| Attribute | Detail |
|-----------|--------|
| Type | Process-based LCI/LCIA database |
| Coverage | 25,000+ datasets; manufacturing, agriculture, energy, transport, waste — global |
| Licensing | Annual subscription; multiple tiers |
| Single-user | ~CHF 1,650–2,000/year |
| Enterprise Standard | 5+ users; pricing on request |
| Developer | Software integration rights; sub-licensing LCIA scores to end users; pricing on request |
| API | **REST API in closed beta** (v0) — access to 25,000+ datasets, 600+ impact indicators |
| Download | Full database downloadable as ecoSpold2/ILCD/JSON-LD for licensees |
| Update frequency | Annual major versions (currently v3.11); minor updates during year |
| System models | Cut-off, APOS, Consequential |
| Format | EcoSpold2, ILCD, JSON-LD, XML, Excel |

**Developer licence for SaaS:** The Developer licence allows software tool providers to embed ecoinvent LCIA scores in their products and sub-license LCIA results to end users. The end user receives LCIA impact scores but not raw LCI inventory data. Pricing is negotiated separately — this is the critical licence type for MGS if building a product with ecoinvent as the background database.

**API status:** The [ecoinvent REST API](https://docs.api.ecoinvent.org) is in **closed beta** as of early 2026. Provides programmatic access to 25,000+ datasets and 600+ impact indicators. Breaking changes expected before commercial release. MGS should register interest — this would substantially simplify integration.

**Assessment for MGS:** ecoinvent is the gold standard background database. Without it, any LCA tool produces results of questionable quality. The Developer licence is the path for embedded use. The beta API is promising but not yet production-ready.

**Sources:** [ecoinvent Licenses](https://ecoinvent.org/licenses/), [ecoinvent Developer License](https://ecoinvent.org/licenses/developer/), [ecoinvent API Docs](https://docs.api.ecoinvent.org)

---

### 4.2 DEFRA/DESNZ UK GHG Conversion Factors

| Attribute | Detail |
|-----------|--------|
| Publisher | UK Department for Energy Security and Net Zero |
| Coverage | UK energy, transport, refrigerants, business travel, water, waste, materials — Scope 1, 2, 3 |
| Cost | **Free** — government publication |
| Update frequency | Annual (2025 edition published June 2025) |
| Formats | Excel condensed, Excel full set, flat file (CSV for automation) |
| API | **No REST API** — download only (flat file for automated processing) |
| Licence | Open Government Licence (OGLv3) — free commercial use |
| Food coverage | Limited — broad sector averages, not product-specific |

**Assessment for MGS:** **Essential and free.** DEFRA factors cover energy, transport, and business travel comprehensively. The flat file format supports automated ingestion. Critical for the corporate energy balance and Scope 1/2 reporting. Not sufficient for product-level food FMCG LCA on their own.

**Sources:** [DEFRA 2025 Conversion Factors](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025)

---

### 4.3 EPA GHG Emission Factors Hub

| Attribute | Detail |
|-----------|--------|
| Publisher | US Environmental Protection Agency |
| Coverage | US-focused; stationary combustion, mobile combustion, fugitive emissions |
| Cost | Free |
| Update frequency | Annual |
| API | No API — Excel download only |
| Relevance for UK | Low — US-specific factors; some global refrigerant data |

**Assessment for MGS:** Low relevance for UK-focused platform. Useful reference for US market expansion.

---

### 4.4 Agribalyse (ADEME, France)

| Attribute | Detail |
|-----------|--------|
| Publisher | ADEME (French environmental agency) |
| Coverage | **2,500+ food products** (processed and raw) + 200 agricultural raw materials — French production context |
| Cost | **Free and open source** (ETALAB licence) |
| Update frequency | Major versions; v3.2 current (2025) |
| API | No direct API — downloadable database in ecoinvent/ILCD/EcoSpold format |
| Access via | openLCA Nexus, SimaPro (requires SimaPro licence), direct download |
| Scope | Full LCA; 16 environmental indicators per product |
| Food detail | Ingredient-level; processing, packaging, transport stages |

**Assessment for MGS:** **Highly relevant and free.** 2,500 food products with full LCA profiles is substantial coverage. French production context limits direct UK applicability (transport assumptions, energy mix), but provides excellent proxy data for common food categories. Can be loaded directly into openLCA or Brightway2 for calculation. The combination of Agribalyse + DEFRA energy factors covers a large proportion of common FMCG food products without needing ecoinvent.

**Sources:** [Agribalyse Documentation](https://doc.agribalyse.fr/documentation-en/), [Agribalyse on openLCA Nexus](https://nexus.openlca.org/database/Agribalyse)

---

### 4.5 ELCD (European Life Cycle Database)

| Attribute | Detail |
|-----------|--------|
| Publisher | European Commission (JRC) |
| Coverage | Core industrial sectors: energy, transport, materials, waste treatment — EU context |
| Cost | **Free** |
| API | No — ILCD format download |
| Update frequency | Irregular; last major update 2012–2014; largely superseded |
| Status | Largely superseded by more current databases; maintained as reference |

**Assessment for MGS:** Limited value — outdated. Better alternatives exist (ecoinvent, Agribalyse). Useful as a free fallback for basic EU industrial processes.

---

### 4.6 Exiobase

| Attribute | Detail |
|-----------|--------|
| Type | Multi-Regional Environmentally Extended Input-Output (MRIO) table |
| Publisher | NTNU, TNO, CML Leiden consortium |
| Coverage | 163 industries × 200 products; global; monetary-based supply chains |
| Cost | EXIOBASE3: **Free** (CC BY-SA 4.0 on Zenodo) |
| API | No API — download from Zenodo |
| Formats | SUT/IOT matrices (CSV, HDF5) |
| Use case | Macro supply chain carbon intensity; spend-based emission factors; IO-LCA |

**Assessment for MGS:** Excellent for **corporate Scope 3 spend-based calculations** and filling gaps in process LCA upstream supply chains. The free CC BY-SA licence is very permissive for commercial use (attribution + share-alike). The pylcaio library enables hybridisation with ecoinvent. Key limitation: monetary-based (£/€ spend → emissions), so less precise than activity-based LCA for specific products.

**Sources:** [Exiobase.eu](https://exiobase.eu), [Zenodo EXIOBASE3](https://doi.org/10.5281/zenodo.3583070)

---

### 4.7 US LCI (NREL)

| Attribute | Detail |
|-----------|--------|
| Publisher | National Renewable Energy Laboratory (US DOE) |
| Coverage | US industrial and energy processes; manufacturing, fuels, materials |
| Cost | **Free** |
| Update frequency | Quarterly releases |
| Formats | JSON-LD, openLCA .zolca, ecoSpold2, ILCD |
| API | Available via [LCA Commons API](https://www.lcacommons.gov/lca-commons-api-guide) — public REST API |
| Access | lcacommons.gov; direct download |

**Assessment for MGS:** Moderate relevance. US-focused, but useful for products with US supply chains. The LCA Commons API is notable — a free public REST API for LCA data, worth exploring.

**Sources:** [US LCI Downloads (GitHub)](https://github.com/uslci-admin/uslci-content/blob/dev/docs/release_info/release-downloads.md)

---

### 4.8 Climatiq API

| Attribute | Detail |
|-----------|--------|
| Type | Aggregated emission factor API (multi-source) |
| Pricing | Free (Starter, non-commercial); **€2,000/year** (Data Pro, non-commercial); **Custom** (Enterprise, commercial licence) |
| Data sources | DEFRA, EPA, IPCC, Agribalyse, EXIOBASE 3.11+, ecoinvent (enterprise add-on), IEA, Carbon Minds, sustamize |
| API type | REST API |
| Commercial use | **Enterprise tier only** — Starter and Data Pro are non-commercial |
| Coverage | Scope 1, 2, 3; freight, travel, energy, PCF calculations |
| AI features | AI-powered activity mapping (beta/enterprise) |
| Certifications | ISO 27001, SOC 2 |

**API capabilities:**
- `/estimate` — calculate CO2e from activity data
- Freight, travel, energy calculations
- Product carbon footprint (PCF) calculations (beta)
- Emission factor search and export
- EXIOBASE-based spend factors

**Assessment for MGS:** **The most important third-party API option.** Climatiq aggregates DEFRA, EPA, ecoinvent, EXIOBASE and others behind a single REST API. Commercial use requires Enterprise tier (custom pricing). The API is developer-friendly, well-documented, and supports C# via standard HTTP. For corporate energy balance + Scope 1/2/3 reporting, Climatiq covers most use cases. **For food product-specific LCA, coverage is less deep than CarbonCloud or Agribalyse — it includes Agribalyse data but as a flat factor rather than full LCA calculation.**

**Sources:** [Climatiq Pricing](https://www.climatiq.io/pricing), [Climatiq API Docs](https://www.climatiq.io/docs)

---

### 4.9 GaBi Databases (Sphera)

| Attribute | Detail |
|-----------|--------|
| Coverage | 20,000+ datasets; extensive industrial sectors |
| Cost | Commercial — bundled with GaBi software; enterprise pricing |
| API | Via GaBi/Sphera LCA Automation product |
| Standalone | No — requires GaBi software licence |

**Assessment for MGS:** Not accessible without full GaBi licence ($15,000+/year). Not viable for startup.

---

### 4.10 IDEA (Japan)

| Attribute | Detail |
|-----------|--------|
| Publisher | AIST + JEMAI (Japan) |
| Coverage | ~3,800 processes covering all major Japanese economic sectors; food, manufacturing, energy |
| Cost | Pricing in Japanese only; from ~€2,000 in SimaPro |
| API | No public API |
| Relevance | Japanese supply chains; Asian manufacturing |

**Assessment for MGS:** Low immediate relevance for UK FMCG focus. Relevant if expanding to products with significant Asian supply chains.

---

### 4.11 Sustamize API

| Attribute | Detail |
|-----------|--------|
| Type | CO2e data API for Scope 3, PCF, ESG |
| Coverage | Products, materials, components — manufacturing focus |
| API | REST (JSON) |
| Integration | Available as add-on in Climatiq Enterprise |
| Focus | Manufacturing/industrial Scope 3 |

Available as a premium add-on via Climatiq Enterprise. Not the primary choice for food FMCG.

---

## 5. Food & Retail-Specific Platforms

### 5.1 Foundation Earth

| Attribute | Detail |
|-----------|--------|
| Type | Non-profit eco-labelling organisation |
| Model | Front-of-pack environmental scoring (A+ to G) for food products |
| Methodology | Open-source PEF-aligned LCA methodology (launched March 2023, developed with Blonk Sustainability) |
| Cost | Assessment fees per product (commercial partnership model) |
| API | No public API |
| Standards | EU PEF, GHG Protocol |
| Clients | Nestlé, Sainsbury's, M&S, Meatless Farm, many UK food brands |

**Methodology relevance:** Foundation Earth's [open-source LCA methodology](https://blonksustainability.nl/launch-of-foundation-earths-lca-methodology-for-evironmental-footprint-labelling) is publicly available and PEF-compliant. MGS could adopt this methodology framework for product footprinting rather than inventing its own. The A+ to G scoring is consumer-facing and widely recognised in UK retail — aligning with it would give MGS results directly comparable to on-shelf labels.

**Assessment for MGS:** **High strategic value as a methodology reference.** Not a data source or API to call. MGS should align its calculation methodology with Foundation Earth's open-source approach to ensure compatibility with UK retail labelling requirements.

---

### 5.2 Foodsteps

| Attribute | Detail |
|-----------|--------|
| Type | UK food/hospitality carbon footprint SaaS |
| Focus | Restaurants, caterers, food brands — product/recipe carbon labelling |
| Database | UK-specific food ingredients database (1,000+ ingredients) |
| Methodology | GHG Protocol, WRAP guidance; A–E traffic light labels |
| Integration | Recipe/menu management system API integrations |
| Clients | UK food businesses, hospitality |
| API | Integrations with recipe management systems (confirmed 2025) |

**Assessment for MGS:** Foodsteps is a direct competitor in the UK food carbon labelling space, though focused on hospitality/restaurants rather than retail FMCG. Their UK-specific ingredient database is a differentiator. Not a data source MGS can access externally — competitive intelligence.

---

### 5.3 My Emissions

| Attribute | Detail |
|-----------|--------|
| Type | UK food & drink carbon accounting SaaS |
| Focus | Food brands, manufacturers, foodservice — Scope 3 + product LCAs |
| Database | Built on DEFRA, WRAP, Food Data Transparency Partnership data |
| Coverage | Scope 1, 2, 3; product carbon footprints; carbon labelling |
| Pricing | Not publicly disclosed; described as "affordable" for food brands |
| Standards | GHG Protocol, WRAP, SBTi |
| API | Not publicly offered |
| UK context | Partners with DEFRA, WRAP — government-aligned methodology |

**Assessment for MGS:** Direct UK food sector competitor. Their database methodology (DEFRA + WRAP-aligned) represents the most credible UK-specific approach for retail FMCG. Not a data source accessible externally. Good case study for methodology alignment.

---

### 5.4 Cool Farm Tool

| Attribute | Detail |
|-----------|--------|
| Publisher | Cool Farm Alliance (non-profit) |
| Focus | Agricultural on-farm GHG, water, biodiversity |
| Coverage | Crop and dairy farm-level assessments |
| Pricing | Free basic; membership model for enhanced access |
| API | **Yes — Crop and Dairy API available** for embedding as calculation engine in third-party tools |
| Standards | GHG Protocol, ISO 14064 |

**API value:** The Cool Farm Tool's Crop and Dairy assessment APIs enable it to function as a calculation engine in third-party digital products. This is directly relevant for agricultural ingredient footprinting within FMCG products.

**Assessment for MGS:** **High value for agricultural ingredient footprinting.** The API would enable MGS to calculate farm-gate emissions for crop and dairy ingredients without building that methodology from scratch. Cool Farm Alliance membership required.

**Sources:** [Cool Farm Annual Report 2024 (PDF)](https://coolfarm.org/wp-content/uploads/2025/06/Cool-Farm_Annual-Report-2024_FINAL.pdf)

---

### 5.5 HowGood

| Attribute | Detail |
|-----------|--------|
| Type | Product sustainability ratings SaaS |
| Coverage | 1M+ food products assessed; 8 sustainability metrics |
| Methodology | Ingredient-level; GHG, water, land use, biodiversity, animal welfare, labour |
| Clients | Large food manufacturers, retailers |
| API | Via "Latis" platform — enterprise integration |
| Carbon methodology | Carbon Trust certified PCF methodology |
| Pricing | Enterprise — no public pricing |

**Assessment for MGS:** Strong data coverage for established food brands. Enterprise pricing likely outside startup budget. The Carbon Trust certified methodology is a quality signal. Not accessible as a simple API for a startup.

**Sources:** [HowGood Sustainability Ratings](https://www.howgood.com/methodology/product-sustainability-ratings)

---

## 6. API-First & Embeddable Options

### Summary: APIs Available for C#/.NET Integration

| API / Data Source | Type | Coverage | Pricing | Commercial Licence | Notes |
|-------------------|------|----------|---------|-------------------|-------|
| **Climatiq** | REST API | DEFRA, EPA, EXIOBASE, Agribalyse, ecoinvent (add-on), IEA | Free (non-commercial); €2K/yr Data Pro (non-commercial); **Enterprise custom** | Enterprise only | Best general-purpose; C# HTTP client straightforward |
| **CarbonCloud** | REST API | Thousands of food product footprints, farm-to-shelf | Not published | Assumed commercial | Best for food product PCFs; contact for pricing |
| **Cool Farm Tool** | REST API | Agricultural crop + dairy on-farm | Membership-based | Contact alliance | Farm-gate ingredients emissions |
| **Mondra** | REST API (DaaS) | Food/beverage emissions factors; PLM/PIM integrations | Enterprise | Contact | Direct competitor; may license DaaS |
| **ecoinvent** | REST API (beta) | 25,000+ datasets, 600+ impact indicators | Developer licence (custom) | Developer licence required | Closed beta; watch for commercial launch |
| **LCA Commons (NREL)** | REST API | US LCI data | Free | Open | US-focused; useful reference |
| **openLCA IPC** | gRPC/REST (local/server) | Any loaded database | Free (tool) + database licence | Open source tool | Best for self-hosted calculation engine |
| **Sustamize** | REST API | Products/materials Scope 3 | Via Climatiq Enterprise add-on | Enterprise | Manufacturing focus |

### Typical API Pricing Models

| Model | Example | Notes |
|-------|---------|-------|
| **Annual SaaS licence** | Climatiq €2,000/year | Fixed cost; volume-unlimited within tier |
| **Per call / per calculation** | Climatiq Enterprise (volume-based) | Scales with usage; predictable for low volume |
| **Per product** | CarbonCloud, HowGood (estimated) | Common for product footprint databases |
| **Enterprise flat fee** | Mondra DaaS | Negotiated; opaque pricing |
| **Free open access** | LCA Commons, DEFRA, Agribalyse | Download/API, no per-call cost |

### White-Labelling / Embedding

No major LCA platform offers explicit white-label options at startup pricing. The practical path to white-label is:

1. **License data via API** (Climatiq Enterprise, CarbonCloud) — no UI, pure data
2. **Build MGS's own calculation layer and UI** on top
3. **Present results under MGS brand** — this is the standard SaaS model

**Green Project Technologies** offers a [white-label carbon accounting platform](https://www.greenprojecttech.com/newsroom/white-label-press-release) for consulting firms — less relevant for MGS's product context but demonstrates the model exists.

### Databases That Can Be Downloaded and Self-Hosted

| Database | Format | Licence | Self-host permitted |
|----------|--------|---------|---------------------|
| Agribalyse | EcoSpold2/ILCD/JSON-LD | Open (ETALAB) | Yes — free |
| EXIOBASE3 | CSV/HDF5 matrices | CC BY-SA 4.0 | Yes — free |
| DEFRA factors | Excel/CSV flat file | OGL v3 | Yes — free |
| US LCI | JSON-LD/openLCA | Public domain | Yes — free |
| ELCD | ILCD | Free | Yes |
| ecoinvent | EcoSpold2/JSON-LD/ILCD | Paid licence | Yes — for licensees |
| Agri-footprint | ecoinvent-compatible | Commercial | No — requires licence |
| GaBi | Proprietary | Commercial | No |

---

## 7. Build vs Buy Analysis

### 7.1 What Does It Cost to Build a Basic LCA Engine from Scratch in C#/.NET?

**The core LCA calculation is matrix algebra.** A product's life cycle impact is computed as:

```
s = h * (I - A)^-1 * f
```

Where:
- `f` = functional unit (demand vector)
- `A` = technology matrix (process inputs/outputs)
- `I - A` = Leontief inverse
- `h` = characterisation matrix (emission factors → impact categories)
- `s` = impact score vector

This is straightforward numerical computing — solvable in C# with standard linear algebra libraries (MathNet Numerics, which is MIT licensed). The **maths is not the hard part.**

**The hard parts are:**

| Challenge | Difficulty | Cost/Time |
|-----------|------------|-----------|
| Building/sourcing the background database (A matrix) | Very High | Months to years without ecoinvent |
| Modelling the foreground product system correctly | High | Requires LCA domain expertise |
| Handling multi-functionality/allocation | High | Methodological decisions with regulatory implications |
| LCIA method implementation (ReCiPe, EF 3.1, GWP 100) | Medium | Several weeks |
| Data quality management and uncertainty | High | Often neglected; legally risky to omit |
| Keeping data current with annual database updates | Ongoing | Significant maintenance burden |
| ISO 14067/14040 compliance verification | High | External audit cost |

**Realistic build estimate for a minimal viable LCA engine (food FMCG):**

| Component | Approach | Cost estimate |
|-----------|----------|---------------|
| Calculation engine (C#) | MathNet Numerics + custom sparse matrix | 4–8 weeks dev; ~£20K–40K |
| Background database | ecoinvent Developer licence | £5K–15K/year |
| Food foreground data | Agribalyse (free) + manual curation | 8–12 weeks LCA expert time; £20K–50K |
| LCIA methods | Open implementations (GWP100 is simple) | 2–4 weeks dev |
| API wrapper for C# service | REST API layer | 2–4 weeks dev |
| **Total MVP** | | **£50K–120K + £5K–15K/year ongoing** |

**This is the minimum.** A production-quality, ISO-compliant product footprinting engine for retail FMCG needs ongoing LCA expertise, annual database updates, and third-party verification. Total cost of ownership over 3 years: £200K–400K equivalent.

---

### 7.2 Open-Source Acceleration Components

| Component | Source | What it provides |
|-----------|--------|-----------------|
| Sparse matrix solver | MathNet Numerics (C#, MIT) | LCA Leontief inverse calculation |
| Background database | Agribalyse (free) + US LCI (free) | 2,500+ food products; US materials |
| IO database | EXIOBASE3 (CC BY-SA) | Macro supply chain for Scope 3 |
| Energy factors | DEFRA flat file (OGL) | UK energy/transport/fuel |
| Calculation engine | openLCA via gRPC | Full LCA engine — avoids building maths |
| Python microservice | Brightway2 (BSD) | Alternative calculation back-end |

---

### 7.3 Minimum Viable Architecture Using Existing APIs

```
[MGS Platform (C#/.NET)]
        |
        |─── Product Carbon Footprint ──→ [CarbonCloud API]
        |                                  (food product PCFs)
        |
        |─── Agricultural Ingredients ──→ [Cool Farm Tool API]
        |                                  (crop/dairy farm-gate)
        |
        |─── Corporate Energy Balance ──→ [Climatiq Enterprise API]
        |    (Scope 1, 2, 3)               (DEFRA + EPA + EXIOBASE)
        |
        |─── UK Statutory Reporting ────→ [DEFRA flat file]
        |    (direct DEFRA factors)        (self-hosted, free)
        |
        |─── Advanced LCA (optional) ───→ [openLCA IPC server]
             (novel/custom products)        (self-hosted; ecoinvent)
```

**Monthly API cost estimate (startup scale):**
- Climatiq Enterprise: ~£500–2,000/month (estimate; custom pricing)
- CarbonCloud API: ~£500–3,000/month (estimate; contact required)
- Cool Farm Tool: membership fee (likely £500–2,000/year)
- DEFRA: free
- Total: **£1,000–5,000/month** for API-based approach

vs. **£5,000–15,000/month** equivalent for employing in-house LCA team + full software stack

---

### 7.4 How Competitors Build Their Platforms

#### Mondra
- **Data:** Largest internally verified food/beverage EF database; integrated farm-level primary data from 400K+ representative farms
- **Compute:** "Hypermodelling" AI generates product-level PCFs automatically from BOM/specification data
- **Integration:** API-first; connects to PLM/PIM systems (SAP, Infor, etc.)
- **Methodology:** GHG Protocol + ISO 14067 + GSTA standard
- **Stack:** Not disclosed; likely Python/ML for classification + custom LCA engine

#### CarbonCloud
- **Data:** Biophysical model developed over decades of academic research; continuously updated by in-house science team
- **Compute:** AI-powered ingredient matching from BOM; bulk calculation from uploaded ingredient lists
- **Integration:** REST API for third-party embedding
- **Methodology:** ISO 14067, GHG Protocol; FLAG/non-FLAG breakdown
- **Stack:** Not disclosed; academic origin (Chalmers University research lineage)

#### My Emissions
- **Data:** DEFRA + WRAP + Food Data Transparency Partnership — government-aligned, UK-specific
- **Compute:** Proprietary food emissions database; AI-assisted Scope 3 from procurement data upload
- **Methodology:** GHG Protocol + WRAP guidance; UK compliance focus
- **Stack:** Not disclosed; SaaS web platform

**Common architectural pattern:** All successful food carbon platforms are built on a **curated proprietary food ingredient/product database** layered over open or licensed background data (ecoinvent, Agribalyse, DEFRA). The calculation engine is less differentiating than the **data curation and methodology**.

---

### 7.5 Recommendation Matrix for MGS

| Use Case | Recommended Approach | Rationale |
|----------|---------------------|-----------|
| **Product-level food PCFs** | Integrate CarbonCloud API | Thousands of pre-calculated food footprints; scientific quality; fastest to market |
| **Agricultural ingredients** | Integrate Cool Farm Tool API | Best-in-class for farm-gate calculations; non-profit API |
| **Corporate Scope 1 & 2** | DEFRA flat file (self-hosted) | Free; UK-official; simple energy + fuel factors |
| **Corporate Scope 3** | Climatiq Enterprise API | Aggregates DEFRA, EXIOBASE, EPA behind single API |
| **Novel/custom products** | openLCA + Agribalyse (self-hosted) | Free tools; ecoinvent Developer licence if needed |
| **Long-term differentiation** | Build proprietary UK food EF database | Curate from Agribalyse + DEFRA + primary data |
| **LCA methodology standard** | Align with Foundation Earth open methodology | UK retail compliance; comparable to on-shelf labels |

---

## 8. Quick Reference: Decision Framework

```
Q1: Is it a standard food/grocery product?
  YES → CarbonCloud API (fastest, scientifically sound)
  NO  → Continue to Q2

Q2: Is it agricultural/crop/dairy at farm gate?
  YES → Cool Farm Tool API
  NO  → Continue to Q3

Q3: Is it a corporate energy balance / Scope 1-2?
  YES → DEFRA flat file (free, self-hosted)
  NO  → Continue to Q4

Q4: Is it Scope 3 spend-based?
  YES → Climatiq Enterprise (EXIOBASE factors)
  NO  → Continue to Q5

Q5: Is it a novel product requiring full process LCA?
  YES → openLCA + ecoinvent Developer licence + Agribalyse
  NO  → Raise with MGS LCA team
```

---

## 9. Competitive Landscape Summary

### UK Food Carbon Footprinting — Competitor Map

| Company | Focus | Data Source | Price Point | API |
|---------|-------|-------------|-------------|-----|
| Mondra | Retail/brand food | Proprietary + farm data | Enterprise | Yes (DaaS) |
| My Emissions | Food brands/foodservice | DEFRA/WRAP | SME/affordable | No |
| Foodsteps | Hospitality/restaurants | UK-specific DB | SME | Yes (recipe integrations) |
| CarbonCloud | All food sectors | Biophysical model | SME–Enterprise | **Yes** |
| HowGood | Large food brands | Proprietary (1M+ products) | Enterprise | Via Latis |
| Foundation Earth | Eco-labelling | PEF/open methodology | Per-assessment | No |
| MGS (target) | Retail FMCG + corporate | API integration | Startup → scale | TBD |

---

## 10. Sources

1. [openLCA Features](https://www.openlca.org/features/)
2. [openLCA API Forum](https://ask.openlca.org/4985/using-through-background-calculation-engine-without-openlca)
3. [olca-ipc Python package](https://github.com/GreenDelta/olca-ipc.py)
4. [Brightway 2.5 PyPI](https://pypi.org/project/brightway25/)
5. [Devera LCA Software Comparison 2025](https://www.devera.ai/resources/lca-software-comparison-in-2025-best-tools-ranking)
6. [SimaPro Plans](https://simapro.com/plans/)
7. [SimaPro Order Form 2025 (PDF)](https://simapro.se/wp-content/uploads/2025/08/2025.3-Order-form-SimaPro-plans-for-business-subscription.pdf)
8. [Sphera LCA Software](https://sphera.com/solutions/product-stewardship/life-cycle-assessment-software-and-data/)
9. [Vendr Sphera Pricing](https://www.vendr.com/marketplace/sphera)
10. [Ecochain Pricing](https://ecochain.com/pricing/)
11. [One Click LCA Product Pricing](https://oneclicklca.com/en-us/pricing/product-lca-and-epd-pricing)
12. [Mondra.com](https://www.mondra.com)
13. [Mondra – Net Zero Compare](https://netzerocompare.com/software/mondra)
14. [CarbonCloud API](https://carboncloud.com/api/)
15. [ecoinvent Licenses](https://ecoinvent.org/licenses/)
16. [ecoinvent Developer License](https://ecoinvent.org/licenses/developer/)
17. [ecoinvent API Docs (beta)](https://docs.api.ecoinvent.org)
18. [Climatiq Pricing](https://www.climatiq.io/pricing)
19. [DEFRA GHG Conversion Factors 2025](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025)
20. [Agribalyse Documentation](https://doc.agribalyse.fr/documentation-en/)
21. [Agribalyse on openLCA Nexus](https://nexus.openlca.org/database/Agribalyse)
22. [EXIOBASE3 (Zenodo)](https://doi.org/10.5281/zenodo.3583070)
23. [US LCI Database Downloads](https://github.com/uslci-admin/uslci-content/blob/dev/docs/release_info/release-downloads.md)
24. [Persefoni Pricing](https://www.persefoni.com/pricing)
25. [Watershed Pricing (Vendr)](https://www.vendr.com/buyer-guides/watershed)
26. [Foundation Earth Methodology](https://blonksustainability.nl/launch-of-foundation-earths-lca-methodology-for-evironmental-footprint-labelling)
27. [Foodsteps](https://www.foodsteps.earth)
28. [My Emissions](https://myemissions.co)
29. [HowGood Methodology](https://www.howgood.com/methodology/product-sustainability-ratings)
30. [Cool Farm Tool Annual Report 2024 (PDF)](https://coolfarm.org/wp-content/uploads/2025/06/Cool-Farm_Annual-Report-2024_FINAL.pdf)
31. [pylcaio (GitHub)](https://github.com/MaximeAgez/pylcaio)
32. [Normative Pricing](https://normative.io/pricing/)
33. [KEY ESG Carbon Platform Reviews](https://www.keyesg.com/article/best-carbon-accounting-software-platforms)
34. [Sustain.Life on GetApp](https://www.getapp.com/operations-management-software/a/emissions-management/)
35. [IDEA Japanese LCI (SimaPro)](https://simapro.com/products/idea-japanese-inventory-database/)
36. [Carbon Maps LCA Software 2025](https://www.carbonmaps.io/blog/lca-software)
