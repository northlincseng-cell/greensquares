# The Green Square: Anatomy of a Universal Sustainability Micro-Unit

## Executive Summary

The Green Square (GS) is a consumer-facing micro-unit of verified carbon reduction, defined as **1 GS = 100g CO2e**, priced at **£0.003** to retailers. At the tonne level, this equates to 10,000 GS per tonne CO2e and a nominal price of **£30/tCO2e** — positioning the unit at the premium end of today's voluntary carbon market, above average spot prices of ~$6/tCO2e but consistent with high-quality nature-based credits assessed at ~$13–26/tCO2e by [S&P Global Commodity Insights](https://www.spglobal.com/energy/en/news-research/latest-news/electric-power/100925-natural-carbon-capture-removal-credit-prices-hit-2025-low-on-supply-glut).

The GS works because it solves three problems simultaneously. First, it translates the abstract complexity of carbon accounting — Scope 3 categories, lifecycle assessments, emission factor databases — into a single collectible integer that consumers can earn, accumulate, and direct. Second, it creates a two-tier commercial model (retailer basket-value + brand product-specific) that generates revenue from the parties best positioned to pay (brands and retailers), not from consumers who have repeatedly demonstrated unwillingness to fund carbon at checkout. Third, it arrives at precisely the moment when the infrastructure to make it credible — [JP Morgan Kinexys blockchain tokenisation](https://www.jpmorgan.com/payments/newsroom/kda-blockchain-carbon-market-tokenization), the [first-ever Paris Agreement carbon credits](https://unfccc.int/news/un-carbon-market-approves-first-ever-issuance-of-credits-under-the-paris-agreement) (February 2026), and reformed verification standards — has become operational for the first time.

The key design decisions that define the GS are:

- **100g CO2e denomination**: calibrated to consumer-scale actions (a glass of milk ≈ 1.6 GS; a beef burger ≈ 30 GS; protecting 1 m² of rainforest per year = 10 GS)
- **Two-tier architecture**: Tier 1 (basket-value, retailer-funded, spend-based emission factors) and Tier 2 (product-specific, brand-funded, ISO 14067-compliant PCFs)
- **Collect-and-direct model**: consumers earn passively through shopping and actively choose conservation projects — fundamentally different from auto-offset at checkout
- **CIC conservation fund**: statutory asset lock prevents private extraction of conservation revenue
- **Verification stack**: Verra VCS → CIC → blockchain → consumer QR verification
- **£0.003 price point**: viable at micro-unit scale through batch blockchain processing and enterprise infrastructure

This report synthesises the scientific, commercial, regulatory, and technical evidence base for what each Green Square must contain.

---

## 1. The 100g CO2e Baseline — Scientific Foundation

### 1.1 Why 100g Is the Right Denomination

The 100g CO2e unit was not chosen arbitrarily. It occupies a specific position in the scale of consumer carbon actions that makes it uniquely functional. Too large a unit (1 kg, 1 tonne) renders most daily actions invisible — a consumer switching from dairy to oat milk would earn fractions of a unit. Too small (1g, 10g) creates unmanageably large numbers that lose meaning. At 100g, the Green Square maps onto consumer actions in integer-scale quantities that are simultaneously comprehensible and motivating.

| Consumer Action | CO2e Saving | Green Squares |
|---|---|---|
| One glass of oat milk instead of dairy (200ml) | ~140g | **1.4 GS** |
| One meal: chicken instead of beef (200g) | ~10,800g | **108 GS** |
| One domestic flight avoided (London–Edinburgh return) | ~62,000g | **620 GS** |
| Protecting 1 m² of tropical rainforest (annual) | ~1,000g | **10 GS** |
| Switching 1 kWh from UK grid to solar PV | ~164g | **1.64 GS** |
| Diverting 1 kg food waste from landfill to composting | ~570g | **5.7 GS** |

These figures derive from [DEFRA 2025 GHG Conversion Factors](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025), [IPCC AR6 lifecycle emission factors](https://www.ipcc.ch/report/ar6/wg3/chapter/chapter-6/), and [Poore & Nemecek's landmark 2018 food LCA meta-analysis](https://www.science.org/doi/10.1126/science.aaq0216). The 100g denomination ensures that a typical weekly grocery shop (£100) generates approximately **250–450 GS** — a quantity large enough to feel meaningful, granular enough to differentiate between product categories, and small enough that individual choices register on the counter.

The unit also scales elegantly upward. A corporate sponsor protecting 1 hectare of tropical rainforest generates 100,000 GS per year — a large but communicable number suitable for marketing campaigns. A brand switching 1 tonne of freight from air to sea saves 10,350 GS. The 100g denomination works across six orders of magnitude without losing legibility.

### 1.2 The Normalisation Framework

Every sustainability action, regardless of category, converts to Green Squares through a single normalisation pathway:

1. **Identify the activity and its measurable unit** — kWh, km, kg, m², £
2. **Identify the baseline emission factor** (EF_baseline) from a recognised database
3. **Identify the improved-scenario emission factor** (EF_improved) using the same database and system boundaries
4. **Calculate CO2e saving** = activity quantity × (EF_baseline − EF_improved), expressed in grams
5. **Calculate Green Squares** = CO2e saving ÷ 100
6. **Apply a confidence tier label** (Tier 1 verified, Tier 2 estimated high-confidence, Tier 3 estimated indicative)

This framework is deliberately method-agnostic. It accommodates supplier-specific primary data, industry-average LCA data, and spend-based EEIO factors — the same five calculation methods endorsed by the [GHG Protocol Scope 3 Standard](https://ghgprotocol.org/corporate-value-chain-scope-3-standard). The critical discipline is that every conversion must specify its source database, system boundary, and baseline counterfactual.

### 1.3 Key Emission Factor Sources

Four databases form the canonical reference set for GS calculations:

| Database | Coverage | Update Cycle | Primary Use |
|---|---|---|---|
| [DEFRA/DESNZ UK GHG Conversion Factors](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025) | UK electricity, fuels, transport, waste, water | Annual (2025 uses 2023 data) | UK energy/transport GS calculations |
| [US EPA Emission Factors Hub](https://www.epa.gov/climateleadership/ghg-emission-factors-hub) | US fuels, electricity, waste | Annual | US market GS calculations |
| [ecoinvent](https://ecoinvent.org/database/) | 26,000+ datasets: materials, energy, transport, agriculture | Version 3.9+ (IPCC 2021 factors) | Manufacturing/material switching |
| [IPCC AR6 WG3](https://www.ipcc.ch/report/ar6/wg3/chapter/chapter-6/) | Global lifecycle electricity generation factors | Per assessment cycle | Global energy benchmarks |

GWP values are standardised on **AR5 100-year** (CH4 = 28, N2O = 265), consistent with both DEFRA and EPA reporting frameworks. Mixing AR4 and AR5 values is explicitly prohibited within the GS methodology to prevent inconsistent comparisons.

### 1.4 Worked Examples Across Categories

**Energy transition — switching 1 kWh from coal to wind (global lifecycle):**

Coal lifecycle: 820 gCO2e/kWh ([IPCC AR6 median](https://www.ipcc.ch/report/ar6/wg3/chapter/chapter-6/)). Wind onshore lifecycle: 11 gCO2e/kWh. Saving = 809 gCO2e = **8.09 GS per kWh**.

**Manufacturing — switching 1 kg of virgin PET plastic to recycled PET:**

Virgin PET: ~2,750 gCO2e/kg ([EPA WARM](https://www.epa.gov/climateleadership/ghg-emission-factors-hub), [ecoinvent](https://ecoinvent.org/database/)). Recycled PET: ~230 gCO2e/kg. Saving = 2,520 gCO2e = **25.2 GS per kg switched**.

**Consumer purchasing — switching one 200g beef serving to lentils:**

Beef (dairy herd): ~33 kgCO2e/kg ([Poore & Nemecek](https://ourworldindata.org/grapher/ghg-per-kg-poore)). Lentils: ~0.9 kgCO2e/kg. Saving = 200g × (33 − 0.9)/1000 = 6,420 gCO2e = **64.2 GS per meal switch**.

**Land use — protecting 1 m² of tropical rainforest (annual sequestration):**

[MIT Climate Portal](https://climate.mit.edu/posts/supply-curve-forest-based-co2-removal) estimates tropical moist forest sequesters ~11 tCO2e/ha/year (3 tC/ha/year × 3.67). Per m²: 1,100 gCO2e/year. At 100g per GS: **11 GS per m² per year**. The MGS claim of 10 GS per m² per year is therefore **conservative and scientifically defensible**, sitting below the MIT median estimate.

**Transport — switching 1 tonne of freight 1,000 km from air to sea:**

Air freight: ~1,054 gCO2e/tonne-km ([Climate Action Accelerator](https://climateactionaccelerator.org/solutions/sea_freight/)). Sea container: ~10 gCO2e/tonne-km ([Climatiq](https://www.climatiq.io/blog/accuracy-freight-emissions-calculations)). Saving = 1,000 × (1,054 − 10) = 1,044,000 gCO2e = **10,440 GS per consignment**.

### 1.5 Data Quality and Uncertainty Tiers

Every GS calculation carries an inherent uncertainty band. The GS specification requires explicit labelling:

| Tier | Data Source | Typical Uncertainty | GS Label |
|---|---|---|---|
| 1 | Primary supplier data, metered energy, ISO 14067-certified PCF | ±5–15% | "Verified" |
| 2 | Industry-average LCA (ecoinvent, Agribalyse, DEFRA defaults) | ±15–30% | "Estimated (high confidence)" |
| 3 | EEIO spend-based factors (EXIOBASE, USEEIO) | ±30–50%+ | "Estimated (indicative)" |

This tiering mirrors the [GHG Protocol's own data quality hierarchy](https://ghgprotocol.org/scope-3-calculation-guidance-2) and the [WRAP Data Quality Scoring Framework](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf) for UK food businesses. [Steubing et al. (2022)](https://www.climatiq.io/blog/science-behind-spend-based-emission-factors) found that spend-based factors can differ from LCA-based values by a factor of 2 in over 50% of cases — reinforcing that Tier 3 is acceptable only for initial screening, not product-level claims.

---

## 2. What Goes Into a Green Square — The Composition Model

### 2.1 Five Action Categories

Every Green Square traces its CO2e content to one of five action categories, each with established emission factor databases and calculation methodologies:

**Energy transition** — fossil-to-renewable switching. The most data-rich category. UK grid electricity at 0.209 kgCO2e/kWh ([DEFRA 2025](https://assets.publishing.service.gov.uk/media/6846b0870392ed9b784c0187/2025-GHG-CF-methodology-paper.pdf)) vs solar PV at 0.041–0.045 kgCO2e/kWh lifecycle ([IPCC AR6](https://www.ipcc.ch/report/ar6/wg3/chapter/chapter-6/)) provides a clear delta. GS should use lifecycle factors (not combustion-only) to be conservative and defensible.

**Manufacturing and supply chain** — material switching, process efficiency, logistics mode changes. Based on [ecoinvent](https://ecoinvent.org/database/) cradle-to-gate factors and [ISO 14067:2018](https://www.iso.org/standard/71206.html) product carbon footprints. Packaging material switching alone spans enormous ranges: virgin aluminium at 8–16 kgCO2e/kg vs recycled aluminium at ~0.5 kgCO2e/kg.

**Consumer purchasing behaviour** — food choice, product selection, delivery mode. The [Poore & Nemecek (2018)](https://www.science.org/doi/10.1126/science.aaq0216) meta-analysis (38,700 farms, 119 countries) provides the most comprehensive baseline. Food product emissions span a 100:1 range from beef (60–100 kgCO2e/kg) to peas (~1 kgCO2e/kg). Transport typically accounts for only [6–10% of food's lifecycle emissions](https://ourworldindata.org/food-choice-vs-eating-local), though a 2022 Nature Food study found this may be 3.5–7.5× higher for refrigerated fresh produce.

**Land use and conservation** — avoided deforestation (REDD+), reforestation, peatland restoration, rewilding. Based on Verra VCS project data, [IPCC AR4/AR6 forest carbon models](https://www.ipcc.ch/site/assets/uploads/2018/02/ar4-wg3-chapter9-1.pdf), and [WRI Global Forest Watch](https://www.wri.org/insights/forests-absorb-twice-much-carbon-they-emit-each-year) flux data. The critical distinction here is between **carbon stock** (stored carbon, typically 35–147 kgCO2e/m² in tropical forest) and **annual sequestration rate** (active uptake, ~1.1 kgCO2e/m²/year).

**Waste diversion** — landfill avoidance, recycling, composting. Based on [EPA WARM model](https://www.epa.gov/climateleadership/ghg-emission-factors-hub) and [DEFRA waste factors](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025). Food waste diverted from landfill to composting saves ~0.57 kgCO2e/kg (5.7 GS/kg).

### 2.2 How Scope 3 Maps Into the Two-Tier System

The [GHG Protocol Corporate Value Chain Standard](https://ghgprotocol.org/corporate-value-chain-scope-3-standard) defines 15 Scope 3 categories. For food retail, [Scope 3 represents ~97–98% of total emissions](https://www.wwf.org.uk/sites/default/files/2022-11/WWF-Whats-in-Store-for-our-Planet-the-Impact-of-UK%20Shopping-Baskets-on-Climate-and-Nature-2022-v1.pdf), with Category 1 (Purchased Goods and Services) alone accounting for [55–77% of total Scope 3](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf). The two-tier GS system maps directly onto this reality:

| Scope 3 Category | % of Retail Scope 3 | MGS Tier | Mechanism |
|---|---|---|---|
| **1 — Purchased Goods & Services** | 55–77% | **Tier 2** (brand-funded PCF) | Brand provides ISO 14067 PCF per GTIN; GS calculated per product |
| **4 — Upstream Transport** | 5–10% | Embedded in Tier 2 PCF | Included in cradle-to-gate product footprint |
| **9 — Downstream Transport** | 5–8% | Background factor | Customer travel; not directly in basket GS |
| **11 — Use of Sold Products** | 3–8% | Tier 2 (non-food) | Relevant for appliances, electronics |
| **12 — End-of-Life** | 5–8% | Packaging factor in Tier 2 | Recyclable vs single-use packaging differential |
| **All others (2,3,5–8,13–15)** | <5% combined | Operational overhead | Not allocated to consumer baskets |

The insight is structurally important: **a well-designed Tier 2 system that captures Category 1 PCFs captures the overwhelming majority of a product's true climate impact**. This makes the Tier 2 product-level GS the scientific backbone of the scheme, while Tier 1 basket-value GS serves as the engagement layer and entry point.

### 2.3 The Tier 1 / Tier 2 Architecture

**Tier 1 — Basket-value (retailer-funded)**

The retailer pays £0.003 per GS issued across all purchases. GS are calculated using spend-based or category-average emission factors applied at the EPOS department level. The GHG Protocol [explicitly endorses spend-based methods](https://ghgprotocol.org/sites/default/files/2022-12/Chapter1.pdf) as a valid Scope 3 calculation approach when supplier-specific data is unavailable.

Calibration data from [Climatiq's EXIOBASE factors](https://www.climatiq.io/data/emission-factor/9e0ebb95-ed59-49e9-8c0a-290f0975ae77) gives a convenience store factor of 0.186 kgCO2e/USD (~0.24 kgCO2e/GBP), yielding approximately **2.4 GS per £1 spent**. Analysis of UK retailer Scope 3 disclosures ([M&S ESG Report 2024](https://corporate.marksandspencer.com/sites/marksandspencer/files/2024-06/ESG_Report_2024.pdf)) suggests major grocers operate at ~0.35–0.40 kgCO2e/£, or **3.5–4.0 GS per £1**.

A more scientifically robust approach is a **5-category Tier 1 rate structure** based on EPOS department codes:

| Sub-tier | Categories | Estimated GS per £ |
|---|---|---|
| T1-A (High intensity) | Beef, lamb, mutton | 15–40 |
| T1-B (Medium-high) | Poultry, pork, fish, dairy, cheese | 4–15 |
| T1-C (Medium) | Eggs, rice, processed food, frozen | 3–15 |
| T1-D (Low) | Vegetables, fruit, legumes, bread | 1–5 |
| T1-E (Non-food) | Household, personal care, textiles | 2–5 |

This is achievable because standard EPOS systems already hold department/category codes — the integration simply requires mapping retailer codes to MGS emission factor tiers.

**Tier 2 — Product-specific (brand-funded)**

The brand pays a premium to assign a specific GS value to individual SKUs, based on an [ISO 14067](https://www.iso.org/standard/71206.html) or [PAS 2050](https://ghgprotocol.org/sites/default/files/2022-12/GHG%20Protocol%20PAS%202050%20Factsheet.pdf)-compliant Product Carbon Footprint. Where a product has Tier 2 data, its specific GS value replaces the Tier 1 category average in the basket calculation. This creates a direct commercial incentive: brands with genuinely lower-carbon products can demonstrate superiority at the point of sale, while brands invest in PCF certification to control their GS narrative.

The GTIN-to-PCF linkage is technically feasible today. The [BRC Mondra Coalition](https://www.mondra.com) (including Tesco, M&S, Sainsbury's, Ocado, Aldi, Lidl) is already building systematic product-level PCF data integrated with Oracle ERP systems. Pioneers like [Oatly](https://www.oatly.com/oatly-who/sustainability-plan/climate-footprint-product-label) (using [CarbonCloud's ISO 14067-aligned platform](https://carboncloud.com)) and [Quorn](https://www.quorn.co.uk/carbon-footprint) (using Carbon Trust certification) have published on-pack carbon footprint data for years — providing ready-made Tier 2 reference values.

### 2.4 EPOS Integration Architecture

Standard retail EPOS systems record per-transaction: SKU/barcode (GTIN/EAN), product description, quantity, price, category/department code, timestamp, store ID, and promotions applied. Carbon footprint data is **not** present by default but can be introduced through three technical routes:

1. **Carbon data enrichment of product master records** — PCF values added as a field in the PIM/ERP product master; EPOS queries this field at checkout. [Mondra integrates with existing Oracle ERP systems](https://fooddigital.com/retail/scope-3-uk-food-retailers-unite-to-tackle-ghg-emissions) via this approach.

2. **Real-time API lookup at POS** — A carbon data API is queried using the GTIN at checkout. Higher latency but faster to deploy without ERP modifications. This mirrors how loyalty programme points engines already function.

3. **Category-level factor tables** — EPOS applies a department-level emission factor to purchase quantity or value. This is the Tier 1 approach, requiring minimal integration.

[Electronic Shelf Labels (Vusion/SES-imagotag)](https://www.vusion.com/products/sesimagotag/electronic-shelf-labels/) provide an additional display channel — [Uniware EPOS systems](https://www.uniware.co.uk/2024/07/02/carbon-label/) already support displaying kgCO2e data on self-service kiosks by integrating Klimato or Nutritics data.

---

## 3. Fungibility — Making Every GS Equal

### 3.1 How Existing Systems Solve Fungibility

The carbon market has spent three decades wrestling with the same problem the GS faces: how to make units from radically different activities — planting trees in Uganda, installing solar panels in Bangladesh, replacing cookstoves in Cambodia — interchangeable and consistently valued. Every major system converges on **abstraction through standardisation**: strip the unit back to a single common denominator (1 tonne CO2e), enforce rigorous methodology to ensure that denominator means the same thing regardless of source, and let independent verification create trust in the abstraction.

**Verra VCS** — The world's largest voluntary carbon crediting programme (2,579+ registered projects, 132+ countries, 1.3+ billion tonnes reduced or removed) achieves fungibility through the Verified Carbon Unit (VCU), where 1 VCU = 1 tCO2e regardless of project type. [Verra](https://verra.org/programs/verified-carbon-standard/) enforces this through 80+ approved methodologies, mandatory independent validation and verification by accredited VVBs, and a centralised registry that tracks every credit from issuance to retirement.

**Gold Standard** — [Founded by WWF in 2003](https://www.goldstandard.org), Gold Standard requires mandatory SDG impact assessment against at least 3 Sustainable Development Goals. Its credits trade at a 20–40% premium over VCS equivalents, demonstrating that the market does price quality differentials within the fungibility framework.

**CORSIA** — The aviation industry's Carbon Offsetting and Reduction Scheme for International Aviation creates a curated subset of eligible credits from approved programmes. It demonstrates that fungibility can coexist with quality tiers — not all credits are CORSIA-eligible, but all CORSIA-eligible credits are interchangeable within the scheme.

**The ICVCM Core Carbon Principles** — The [Integrity Council for the Voluntary Carbon Market](https://icvcm.org/core-carbon-principles/) has established 10 science-based principles as the global quality benchmark. Credits with the CCP label carry the highest achievable integrity signal. This creates a quality-gated fungibility layer: all CCP-labelled credits are interchangeable at the highest integrity tier.

### 3.2 The Quality-Gating Lesson from Blockchain Tokens

The Toucan Protocol / Base Carbon Tonne (BCT) experiment of 2021–2022 provided a critical negative lesson. Toucan enabled bridging of VCM credits to the Ethereum blockchain, creating tradeable tokens. The problem: by accepting any VCS credit without quality filtering, the pool was flooded with the cheapest, lowest-quality credits — primarily old-vintage renewable energy credits from China and India. The BCT price crashed from ~$7 to under $1 as quality arbitrage played out. [JP Morgan's research paper "Carbon Markets Reimagined"](https://www.jpmorgan.com/kinexys/documents/carbon-markets-reimagined-digital-assets.pdf) explicitly notes that blockchain alone "is not an authority on quality" and that "digital monitoring and connectivity with insurers and ratings agencies are required to improve project quality tracking."

The lesson for MGS: **fungibility without quality gating destroys value**. Every GS must be backed by credits meeting a defined quality threshold — not the lowest-cost available credit.

### 3.3 The MGS Approach: Methodology-Backed Abstraction

The GS achieves fungibility through a layered abstraction:

1. **All GS represent exactly 100g CO2e** — this is the common denominator, equivalent to 0.0001 VCUs
2. **All underlying credits must meet a quality floor** — CCP-eligible programme, reformed methodology (VM0048 for REDD+), or independent rating of B or above from [BeZero Carbon](https://bezerocarbon.com/insights/an-introduction-to-additionality-in-carbon-projects) or [Sylvera](https://sylvera.com)
3. **Metadata distinguishes without breaking fungibility** — each GS carries project ID, vintage, methodology, and verification body as attributes, but trades and accumulates as a uniform unit
4. **The CIC conservation fund is the aggregation layer** — individual consumer GS are pooled; the fund retires VCUs in batch, maintaining the 10,000:1 ratio

This mirrors how frequent-flyer miles work: all miles accumulate equally in the consumer's account regardless of whether they were earned on a short-haul domestic or long-haul international flight, but the underlying flight data is preserved as metadata.

### 3.4 The £30/tonne Pricing Position

At £0.003 per GS (100g CO2e), the implied tonne price is £30 (~$38). This pricing sits within the VCM landscape as follows:

| Credit Type | Current Price (per tCO2e) | GS-Equivalent Price (100g) | MGS Position |
|---|---|---|---|
| Low-quality avoidance | $2–5 | $0.0002–0.0005 | **6–15× premium** |
| Mid-quality nature-based ([Platts CNC](https://www.spglobal.com/energy/en/news-research/latest-news/electric-power/100925-natural-carbon-capture-removal-credit-prices-hit-2025-low-on-supply-glut)) | ~$13 | ~$0.0013 | **~3× premium** |
| High-quality removal (BBB+ rated, [Sylvera](https://sylvera.com)) | ~$26 | ~$0.0026 | **~1.5× premium** |
| Premium CDR forward contracts | $160–180 | $0.016–0.018 | **0.2× (below)** |

The £30/tonne position implies MGS is purchasing high-quality but not ultra-premium credits. This is commercially sustainable: the current market offers sufficient supply of CCP-eligible nature-based credits in the $15–30 range to support the scheme at scale. The premium over spot also creates a margin buffer against market volatility — if spot prices rise toward £30, MGS has already locked in its pricing to consumers.

---

## 4. Verification and Trust Architecture

### 4.1 The Verification Stack

MGS requires a five-layer verification architecture — each layer addresses a specific failure mode from the 2013–2015 greenwashing era and the 2023 VCM crisis (where the South Pole/Kariba scandal revealed that [two-thirds of Kariba's credits were fictitious](https://www.latimes.com/business/story/2025-10-17/majority-of-carbon-credits-from-tarnished-project-deemed-bogus) and VCM transaction volumes [fell 56% year-on-year](https://www.forest-trends.org/pressroom/report-the-voluntary-carbon-market-contracted-in-2023-driven-by-drop-off-in-transactions-for-redd-and-renewable-energy/)):

**Layer 1 — Project-level verification (Verra VCS / Gold Standard)**

The underlying tonne-scale credits are independently verified by accredited Validation/Verification Bodies (VVBs) against the relevant standard. [Verra operates a two-stage audit system](https://verra.org/programs/verified-carbon-standard/): validation (does the project meet all rules?) followed by verification (have the claimed outcomes actually been achieved?). VVBs must be accredited by an International Accreditation Forum member under the Multilateral Recognition Arrangement. Verra's VVB Performance Monitoring Programme uses 17 indicators across four categories and can suspend underperforming auditors.

Post-2023 reforms are material. [Verra's VM0048 REDD methodology](https://verra.org/program-notice/setting-the-standard-verras-revolutionary-new-redd-methodology/) now uses a **single, jurisdiction-wide deforestation dataset** set by Verra itself — removing the ability for project developers to self-select high-baseline reference regions that inflated earlier credits. [New additionality tools VT0008 and VT0009](https://verra.org/verra-releases-new-vcs-additionality-tools/) are specifically designed to meet ICVCM CCP requirements.

**Layer 2 — CIC conservation fund (statutory asset lock)**

Revenue flowing into the MGS conservation fund is held within a Community Interest Company — a UK legal entity with a [statutory asset lock](https://www.gov.uk/government/publications/community-interest-companies-how-to-form-a-cic/community-interest-companies-guidance-chapters) that cannot be removed from the Articles of Association. No assets can be transferred to ordinary limited companies or to individuals. The CIC Regulator (part of Companies House) has oversight, and annual CIC Reports are filed publicly. This is a structural prevention mechanism: conservation fund revenue **cannot** be extracted for private gain as a matter of law, not policy.

**Layer 3 — Blockchain traceability**

An immutable ledger maps each batch of VCU retirements to exactly 10,000 Green Square issuances. The optimal architecture is batch processing combined with individual lookup: GS sales are recorded in real-time in a secure database; at defined intervals, a batch of VCU retirements is executed via the Verra Registry; each batch is anchored on-chain with a cryptographic hash linking to the list of GS IDs it covers. This makes the per-unit blockchain cost effectively zero while preserving full auditability. Enterprise blockchain solutions (permissioned chains, Layer 2 rollups, or [Kinexys by JP Morgan](https://www.jpmorgan.com/insights/payments/blockchain-digital-assets/introducing-kinexys)) operate at < $0.001 per transaction, viable at the £0.003 GS price point.

**Layer 4 — Independent annual audit**

A published Verification Statement confirms: (a) the 10,000 GS : 1 VCU ratio is maintained; (b) no excess GS have been issued beyond VCU inventory; (c) VCU retirements on the Verra Registry match cumulative GS sales; (d) CIC assets are used for stated conservation purposes. This two-level audit structure — project-level VCS + aggregation-level independent audit — is substantially more rigorous than anything claimed by the bad actors of 2013–2015.

**Layer 5 — Consumer-facing transparency**

Each Green Square carries a unique ID that consumers can verify against the blockchain ledger, confirming it traces to a specific VCU retirement on the Verra Registry. The minimum viable implementation is a QR code on each GS certificate linking to a retirement proof page showing VCU serial number, project name, vintage year, and retirement date. Services like [Carbonmark](https://www.carbonmark.com/post/carbon-retirement-verification) and [ShiftCarbon](https://shiftcarbon.io/solutions/point-of-sale-integration) already provide this infrastructure as white-label APIs.

### 4.2 Anti-Greenwashing Framework

The UK regulatory environment has materially changed since MGS's 2013–2015 run. The [Competition and Markets Authority Green Claims Code](https://www.gov.uk/government/publications/green-claims-code-making-environmental-claims/environmental-claims-on-goods-and-services) sets six binding principles: claims must be truthful, clear, complete, fair in comparison, lifecycle-considered, and substantiated *before* publication. Under the [Digital Markets, Competition and Consumers Act (DMCCA) 2024](https://cse-net.org/uk-greenwashing-rules-2025-compliance-guide/), the CMA can now directly fine companies up to **10% of global turnover** for misleading environmental claims — without going to court. These powers have been active since 6 April 2025.

The [EU Green Claims Directive](https://environment.ec.europa.eu/topics/circular-economy-topics/green-claims_en) requires science-based proof, specification of claim scope, life-cycle significance, trade-off disclosure, and accredited certification. Even for a UK-based scheme, alignment with EU requirements provides substantial protection as UK regulators watch EU standards closely.

**Safe claims for MGS** (with appropriate evidence):

- "Each Green Square represents 100g CO2e reduction or avoidance, verified under the Verified Carbon Standard"
- "Our conservation fund is a Community Interest Company — by law, all assets must be used for community/environmental benefit"
- "You can verify your Green Square at [portal] to see the specific carbon project and VCU retirement that backs it"

**Claims to avoid** (high regulatory risk):

- "Carbon neutral" — requires whole lifecycle evidence; intense ASA/CMA scrutiny
- "Offsetting your emissions" — implies one-for-one replacement; may overstate permanence
- "Green" (unqualified) — vague; likely misleading under CMA Code Principle 1

### 4.3 The CIC Structure as Trust Architecture

The CIC is not merely a corporate structure choice — it is a **trust architecture decision** that addresses the precise failure modes of past greenwashing:

Many bad actors in the 2013–2015 era were ordinary limited companies with no legal constraints on how offset revenues were used. A CIC materially changes this through: the [statutory asset lock](https://www.harpermacleod.co.uk/insights/the-asset-lock-is-a-cic-the-right-structure-for-your-social-enterprise/) (assets must be retained for community purposes or transferred only to other asset-locked bodies); regulatory oversight from the CIC Regulator; annual public reporting at Companies House; and the impossibility of converting to a standard limited company without Regulator approval.

UK environmental CIC precedents include [9Trees CIC](https://www.9trees.org) (tree planting based on the "9 trees to balance the average UK citizen's annual carbon consumption" model) and multiple nature recovery and peatland restoration projects receiving UK government Landscape Recovery funding.

### 4.4 Additionality: How MGS Demonstrates Real Impact

The additionality question operates at two levels. **Project-level**: would the Juma Reserve forest (VCS-1566) still be standing without the REDD+ project? The Juma Sustainable Development Reserve covers [540,444.5 hectares in the State of Amazonas](https://www.reddprojectsdatabase.org/227-the-juma-sustainable-development-reserve-project/), under documented deforestation pressure from illegal logging and land conversion. The project is implemented by Fundação Amazonas Sustentável (FAS), holds both VCS and CCB (Climate, Community & Biodiversity) co-certification, and demonstrates additionality through financial viability analysis (conservation is not viable without carbon revenue), common practice analysis (conservation without payment is not common in the region), and barrier analysis (carbon finance overcomes structural barriers from illegal logging revenue).

A September 2025 [Climate Policy Initiative study](https://www.climatepolicyinitiative.org/publication/carbon-credits-in-the-amazon-new-methodology-for-assessing-project-additionality/) found that **77% of carbon credits from REDD projects in the Brazilian Amazon are additional** — meaning the majority represent genuine avoided deforestation. The Juma Reserve, being in a high-pressure deforestation zone, is in a category more likely to be within the additional 77%.

**Revenue-level additionality**: Do Green Square purchases provide marginal financial incentive that keeps projects viable? At the £0.003 per 100g price point, MGS mobilises conservation finance from millions of consumers who would never enter the institutional carbon market. Aggregate demand at micro-scale represents genuinely new money — a consumer spending £0.30 in a convenience transaction is not displacing a corporate credit purchase. The CIC structure locks this new money into conservation.

---

## 5. The C2050 Infrastructure Layer

### 5.1 What C2050 Brings

[C2050 (Climate Compliance 2050)](https://www.linkedin.com/posts/climate-compliance-2050_climatecompliance-environmentalinvestments-activity-7432060268320325632-dR3M) is an Ireland-registered startup positioning itself as a SaaS-based digital monitoring, reporting and verification (D-MRV) platform for evaluating and certifying carbon credits as high-quality, tradable financial assets. Its [stated methodology](https://www.ireland-portugal.com/members/c2050/) centres on territorial intelligence (geospatial data), legal/regulatory compliance mapping, real-time D-MRV, quality scoring, and financial asset structuring.

C2050 occupies precisely the gap that [JP Morgan's own research identifies](https://www.jpmorgan.com/kinexys/documents/carbon-markets-reimagined-digital-assets.pdf) as the missing piece: blockchain ensures standardised data structures and transparency, but does not evaluate whether a credit is genuinely additional or high-impact. C2050 claims to fill this quality evaluation role, feeding verified data into the tokenisation infrastructure.

### 5.2 JP Morgan Kinexys — Tokenisation at Registry Level

[Kinexys (formerly Onyx)](https://www.jpmorgan.com/payments/newsroom/kda-blockchain-carbon-market-tokenization), JP Morgan's blockchain unit founded in 2015, has processed over $1.5 trillion in transactions. On 2 July 2025, Kinexys announced a carbon credit tokenisation application with three testing partners: [S&P Global Commodity Insights](https://www.spglobal.com/en/press/press-release/sp-global-commodity-insights-exploratory-testing-with-jp-morgan), EcoRegistry (completed testing), and the International Carbon Registry (completed testing).

The Kinexys approach is **native tokenisation** — credits are minted directly on the KDA blockchain at the registry level, not bridged from external systems. Each token carries standardised metadata: vintage year, serial number, country, verification body, methodology, project type/ID, and certification standard. Key capabilities include fractionalization (tokens divided while maintaining full attribute traceability), delivery-versus-payment settlement, and bank-grade security.

For MGS, this means that a 100g CO2e Green Square can be technically represented as a fractional token on institutional-grade infrastructure. Commercial platforms are already dividing credits into 0.001 tCO2e units (1kg); a 100g unit (0.0001 tCO2e) is therefore [technically feasible on current blockchain infrastructure](https://www.tandfonline.com/doi/full/10.1080/19498241.2025.2611313). [Thailand's TrueMoney Wallet](https://www.carbonmark.com/post/building-with-blockchain-in-the-carbon-market-part-1) (20 million users, 2025) already enables consumer-facing sub-tonne carbon offsetting via Carbonmark integration.

### 5.3 S&P Global — Pricing and Benchmarking

S&P Global's role in the emerging architecture is threefold. Its **Platts price assessments** (including [Platts CNC](https://www.spglobal.com/energy/en/news-research/latest-news/electric-power/100925-natural-carbon-capture-removal-credit-prices-hit-2025-low-on-supply-glut) for nature-based removal credits) provide the global benchmark against which credit quality tiers are priced. Its **Environmental Registry and Meta Registry** (a registry-as-a-service platform that aggregates data from multiple existing registries) directly addresses the fragmentation problem. And its **Trucost** division provides environmental impact data for 20,000+ companies, enabling institutional investors to incorporate carbon holdings into portfolio accounting.

If GS eventually carry Trucost-compatible metadata, they become priceable within institutional investment portfolios — enabling structured financial products, ESG index inclusion, and green bond eligibility. S&P estimates VCM annual value at [up to $4 billion by 2030](https://www.spglobal.com/energy/en/news-research/blog/energy-transition/120325-how-does-the-voluntary-carbon-market-work), with significant growth through the 2030s.

### 5.4 KPMG — Enterprise Channel and Assurance

[KPMG's carbon market practice](https://kpmg.com/xx/en/our-insights/esg/integrity-issues-in-the-voluntary-carbon-markets.html) spans purchasing strategy, portfolio assessment, project documentation, assurance/verification, and Article 6 advisory. A 2025 KPMG paper on [Navigating Article 6](https://assets.kpmg.com/content/dam/kpmg/za/pdf/2025/Navigating%20Article%206%20of%20the%20Paris%20Agreement_Thought%20Leadership.pdf) outlines support for businesses generating credits compliant with the Paris Agreement Crediting Mechanism. KPMG's most plausible role in a C2050 arrangement would be as a **channel to enterprise clients** — introducing the D-MRV platform to corporates seeking to demonstrate high-quality carbon credit sourcing, and providing third-party assurance of D-MRV outputs.

### 5.5 Article 6 Alignment and the UN Harmonisation Path

The global carbon market is converging through four parallel streams: UN governance (Article 6.4), quality standards (ICVCM CCPs), infrastructure (Kinexys, World Bank CADT), and financial pricing (S&P Platts, MSCI). The [first-ever credits under the Paris Agreement Crediting Mechanism were issued in February 2026](https://unfccc.int/news/un-carbon-market-approves-first-ever-issuance-of-credits-under-the-paris-agreement) — a Myanmar clean-cooking project authorised by the Republic of Korea. This marks the transition from rulemaking to live operation.

In November 2025, [Singapore, Verra, and Gold Standard jointly published the Article 6.2 Crediting Protocol](https://verra.org/singapore-gold-standard-and-verra-publish-article-6-2-crediting-protocol/), establishing standardised procedures for governments to use VCM registries for Article 6.2. This embodies the "include rather than replace" principle: VCM infrastructure is being formally integrated into the UN compliance framework. Credits from CCP-eligible projects registered under Article 6.4 would carry the highest level of internationally recognised credentials.

For MGS, this convergence means that Green Squares backed by Article 6-aligned projects carry internationally recognised credentials rather than proprietary claims — precisely the credibility uplift the relaunch requires.

### 5.6 Due Diligence Notes on C2050's Public Profile

Transparency requires noting that C2050's public footprint is minimal as of March 2026: [15 LinkedIn followers](https://www.linkedin.com/posts/climate-compliance-2050_climatecompliance-environmentalinvestments-activity-7432060268320325632-dR3M), no press coverage found, website inaccessible at time of research. The claimed partnerships with JP Morgan, KPMG, and S&P cannot be independently confirmed from public sources. However, the functional role C2050 describes (D-MRV platform supporting Article 6 compliance) is precisely the gap identified in JP Morgan's own research. The due diligence position for MGS should treat C2050's institutional partnerships as **unverified but plausible**, and require documentary evidence of contractual relationships before material capital deployment.

---

## 6. Consumer Design — Simplicity Over Complexity

### 6.1 Lessons from Failed Sustainability Currencies

The landscape of consumer sustainability schemes is littered with instructive failures. The pattern is consistent across [Recyclebank](https://www.wastedive.com/news/recycle-track-systems-acquires-recyclebank/565572/) (4 million members at peak, now absorbed by RTS), [Joulebug](https://joulebug.com) (pivoted from consumer to B2B), [Pawprint](https://www.pawprint.eco) (same trajectory), [Yayzy](https://community.ibm.com/community/user/blogs/debbie-ardizone/2023/11/06/yayzy) (niche scale), and dozens of similar apps:

**Standalone app acquisition costs are prohibitive** — estimated at $50–$150+ CAC. No consumer carbon business generates sufficient per-user revenue to justify this. **Engagement cliffs at week 4–6** — carbon tracking apps show the same categories week after week, unlike financial or fitness tracking which generates new data daily. **Monetisation fails** — freemium carbon tracking has <2% premium conversion; offset commissions generate cents per user-month.

The programmes that survived pivoted to B2B (employer-funded). The programmes that scaled retained a B2B commercial anchor: [Cogo/NatWest](https://www.finextra.com/pressarticle/93671/300000-natwest-users-have-now-accessed-their-carbon-footprint-with-cogo-integration) (bank-funded, 500,000+ users); [AWorld](https://www.aworld.org) (corporate-funded, 1M+ users); [Reewild/PlanetPoints](https://www.mastercard.com/gb/en/news-and-trends/Insights/2025/planet-points-reewild-sustainable-consumption.html) (Mastercard-backed, showing 18.8% emission reduction in UCL pilot).

### 6.2 What Makes Collect-and-Direct Different from Auto-Offset

This is the most fundamental structural distinction in the market:

| Dimension | Auto-Offset (Cloverly, Stripe Climate, checkout opt-in) | Collect & Direct (MGS) |
|---|---|---|
| Consumer action | Passive or one-click at checkout | Active collection over time |
| Consumer agency | None — offset happens automatically | High — consumer chooses conservation project |
| Engagement depth | Single transaction; no return | Ongoing accumulation; growing investment |
| Emotional ownership | Zero | High — "my Green Squares, my conservation project" |
| Loyalty effect | None | Strong — directs repeat shopping behaviour |
| Consumer funding | Consumer pays extra | Brand/retailer funded — zero consumer cost |
| Greenwashing risk | High if credits are low-quality | Lower — conservation direction, not offset claim |

The collect-and-direct model taps into the same psychology that makes frequent flyer programmes endure: the value lies partly in the journey of accumulation, not just the moment of redemption. A [2023 scientific study](https://www.sciencedirect.com/article/pii/S2666188825009463) found that carbon labels combined with rewards significantly increase sustainable purchasing. [Research with 1,126 participants](https://www.sciencedirect.com/article/pii/S0950329323000071) showed that traffic-light labels (relative sustainability grading) increased choice of low-CO2 items while absolute kgCO2e numbers alone had no significant effect — but a positive reward mechanism like GS transforms carbon data from a warning into an incentive.

Critically, the collect-and-direct model eliminates the "willing to say I care but unwilling to pay extra" gap. Opt-in carbon offset at checkout converts at [1–5%](https://dataintelo.com/report/carbon-smart-e-commerce-checkout-offset-market). MGS costs the consumer nothing — Green Squares are funded by retailers and brands at £0.003 each.

### 6.3 The Social Sharing Imperative

Research consistently shows sustainability engagement scales when it becomes social. [Recyclebank's early pilots](https://en.wikipedia.org/wiki/Recyclebank) tripled participation through visible per-household recycling data. Gamification mechanics that drive collection behaviour include visible point balances (creating investment behaviour), streaks (loss aversion), leaderboards (social comparison), badges (status signalling), and — critically — **directionality** (choosing where points go), which transforms passive earning into active agency.

A [2024 PwC survey of 20,000 consumers](https://www.strategy-business.com/article/A-better-way-to-market-sustainable-products) found willingness to pay 9.7% above average for sustainably produced goods. [NYU Stern CSB data](https://www.strategy-business.com/article/A-better-way-to-market-sustainable-products) shows sustainability-marketed products grew at 2.3× the rate of conventional items (12.3% vs 5.3% annually, 2019–2024). The commercial case is clear — but only if the scheme is brand-funded and frictionless.

### 6.4 How the Demo Already Implements Best Practices

The [live MGS demo](https://northlincseng-cell.github.io/greensquares/) demonstrates several architecturally significant features: a consumer-facing homepage with collect-and-share mechanics; a Leaflet.js satellite map of Amazon conservation projects (making conservation direction geographically tangible); a full admin dashboard with two-tier campaign management; retailer analytics with conversion funnels and ROI metrics; consumer account with conservation project direction across four regions (Amazon, Borneo, Kenya, Scotland); an EPOS terminal with live GS calculation and API webhook; and a consumer mobile app with QR scan, history, and impact visualisation.

Key best-practice implementations: the EPOS integration shows real-time GS calculation at point of sale (matching the [Reewild/PlanetPoints UCL pilot model](https://www.ucl.ac.uk/sustainable/news/2025/feb/earn-rewards-sustainable-choices-campus-reewilds-new-planetpoints-loyalty-programme)); the satellite map provides specific project disclosure (not vague "we support conservation"); the QR scan enables the consumer verification layer; and the two-tier campaign management implements the Tier 1/Tier 2 architecture at admin level.

### 6.5 Gaps and Opportunities in the Current Demo

Based on the research findings, the demo could be strengthened in several areas: adding a consumer-facing GS balance counter with visual accumulation (the "Duolingo streak" mechanic); implementing the QR-to-registry verification chain (QR → GS ID → VCU serial number → Verra Registry retirement proof); adding social sharing of conservation direction choices; displaying per-product GS breakdowns in the basket (not just basket totals); and integrating the 5-category Tier 1 rate structure rather than a flat GS/£ rate. The conservation project selection could also be enhanced with real-time satellite imagery showing forest integrity — a D-MRV feature that C2050's platform is designed to provide.

---

## 7. Critical Design Decisions and Risks

### 7.1 Double-Counting Prevention

Double-counting is the existential risk for any carbon micro-credit system. The prevention architecture operates across four layers:

**Registry level**: VCUs are retired on the [Verra Registry](https://verra.org/programs/verified-carbon-standard/) under a single account controlled by the MGS CIC. Once retired, a VCU serial number cannot be reused — enforced by Verra's infrastructure.

**Aggregation ledger**: A blockchain (or secure database with audit trail) enforces the 10,000:1 mapping. A smart contract cannot mint more GS than the VCU inventory supports.

**Article 6 corresponding adjustments**: Under the Paris Agreement, credits used internationally require the host country to make a "corresponding adjustment" to its national inventory — preventing the same reduction from being counted by both the project country and the buyer country. [The ICVCM](https://icvcm.org/article-6-of-the-paris-agreement-and-the-integrity-councils-work/) states that both CCPs and Article 6 are needed to ensure governments and corporates deliver high-integrity climate finance. If underlying MGS projects are Article 6.4-registered, this highest-level double-counting prevention is automatically enforced.

**Public verification**: Consumers can independently verify that their GS traces to a retired VCU — creating a crowd-sourced audit layer where any discrepancy between GS claims and registry retirements would be immediately visible.

### 7.2 Price Stability at £0.003 When Carbon Markets Fluctuate

VCM spot prices have ranged from ~$2/tCO2e (low-quality avoidance) to $160+/tCO2e (premium removals) in 2025. Total VCM market value was approximately [$1.04 billion in 2025](https://www.spglobal.com/energy/en/news-research/blog/energy-transition/120325-how-does-the-voluntary-carbon-market-work) with projections of [$7–35 billion by 2030](https://www.spglobal.com/energy/en/news-research/blog/energy-transition/120325-how-does-the-voluntary-carbon-market-work) (MSCI estimates). The £30/tonne MGS price includes a margin buffer above current mid-quality spot (~$13 Platts CNC) but could face compression if compliance market integration (Article 6.4, EU ETS linkage) drives prices upward.

Mitigation strategies: forward purchasing of VCUs to lock in supply at known prices; diversification across multiple project types and vintages; and periodic review of the £0.003 GS price with transparent communication if adjustment is needed. The price stability is also inherently protected by the CIC structure — the conservation fund does not need to generate shareholder returns, removing the profit margin pressure that would amplify price sensitivity.

### 7.3 Verification Costs at Micro-Unit Scale

Every tonne-based standard, every registry, and every blockchain protocol was designed for 1,000 kg units, not 100g units. The per-unit verification overhead for a £0.003 product must be near-zero. The batch processing architecture solves this: individual GS sales are recorded off-chain; VCU retirements are executed in daily or weekly batches; each batch is anchored on-chain with a single hash. [A 2024 PwC report](https://pmc.ncbi.nlm.nih.gov/articles/PMC12924408/) confirms tokenisation can achieve up to 85% cost reduction in clearing and settlement. Enterprise blockchain transactions cost <$0.001 each; batch processing reduces the effective per-GS blockchain cost to a fraction of a penny.

The [new Verra registry](https://verra.org/verra-registry-transition/) (developed with S&P Global, announced August 2025) will feature "transaction-ready APIs that allow for automated transfers and retirements of units, replacing manual processes" — the infrastructure MGS needs for automated high-volume retirement.

### 7.4 The Category Whitelist Question

Should every product category earn GS, or only categories with defensible emission factor data? The research suggests a staged approach:

**Phase 1 (launch)**: Tier 1 GS available for all FMCG categories using the 5-tier rate structure, clearly labelled as "estimated (indicative)." Tier 2 available only for brands with ISO 14067-compliant PCFs.

**Phase 2 (maturity)**: Expand Tier 2 coverage as more brands submit PCF data. Introduce category exclusions for products where emission factors are too uncertain (some processed foods, complex multi-ingredient products). The [WRAP Scope 3 Protocols](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf) identify five minimum categories (1, 4, 9, 11, 12) covering ≥67% of food retail Scope 3 — these should define the priority coverage.

### 7.5 Regulatory Evolution

The regulatory landscape is tightening rapidly:

- **UK**: [DMCCA 2024](https://cse-net.org/uk-greenwashing-rules-2025-compliance-guide/) gives CMA direct fining powers (10% of global turnover) for misleading green claims, active since April 2025. The [January 2026 CMA supply chain guidance](https://www.tlt.com/insights-and-events/insight/navigating-green-claims-cma-guidance-for-supply-chain-actors) establishes shared liability — retailers bear responsibility for GS claims even though they originate from MGS.
- **EU**: [EU CSRD](https://environment.ec.europa.eu/topics/circular-economy-topics/green-claims_en) requires large companies to report Scope 3; the Green Claims Directive mandates accredited certification of environmental claims and five-year review cycles.
- **France**: [Eco-Score regulation](https://www.vaayu.tech/insights/french-ecoscore-explained) (Decree no.2025-957, effective October 2025) introduces mandatory environmental labelling for consumer products — a potential Tier 2 requirement accelerator.

MGS's design — with specific quantified claims, named verification standards, CIC structure, and blockchain audit trail — is architecturally aligned with where regulation is heading. The risk is not that regulation will invalidate the model, but that it may require enhancements (e.g., mandatory third-party certification of GS claims, which the verification stack already supports).

---

## 8. Recommended Green Square Specification

### 8.1 Formal Specification Table

| Parameter | Specification |
|---|---|
| **Unit name** | Green Square (GS) |
| **Denomination** | 1 GS = 100g CO2e (0.0001 tCO2e) |
| **Retail price** | £0.003 per GS (to retailers/brands) |
| **Consumer cost** | £0.00 (brand/retailer funded) |
| **Implied tonne price** | £30/tCO2e (~$38/tCO2e) |
| **Underlying asset** | Verified Carbon Unit (VCU) from ICROA-endorsed programme |
| **Quality floor** | CCP-eligible programme; VM0048+ for REDD; or BeZero/Sylvera rating ≥ B |
| **Aggregation ratio** | 10,000 GS : 1 VCU (1 tonne) |
| **Conservation fund** | Community Interest Company (CIC) with statutory asset lock |
| **Verification standard** | Verra VCS (primary), Gold Standard, Plan Vivo (secondary) |
| **Emission factor sources** | DEFRA 2025, EPA 2024, ecoinvent 3.9+, IPCC AR6 |
| **GWP standard** | AR5 100-year (CH4=28, N2O=265) |
| **Tier 1 methodology** | Spend-based EEIO or category-average emission factors per EPOS department |
| **Tier 2 methodology** | ISO 14067:2018 or PAS 2050:2011 Product Carbon Footprint |
| **Blockchain infrastructure** | Batch processing on enterprise/consortium chain; Kinexys-compatible |
| **Consumer verification** | QR code → GS ID → VCU serial number → Verra Registry retirement proof |
| **Audit frequency** | Annual (aggregation ratio, registry reconciliation, CIC report) |
| **Update cycle** | Annual emission factor refresh (aligned with DEFRA publication) |

### 8.2 Metadata Fields Per Green Square

Each GS carries the following metadata, either directly encoded (for Tier 2) or inherited from the aggregation batch (for Tier 1):

| Field | Description | Source |
|---|---|---|
| `gs_id` | Unique Green Square identifier | MGS platform |
| `gs_tier` | 1 (basket-value) or 2 (product-specific) | MGS platform |
| `gs_co2e_g` | Always 100 | Fixed |
| `gs_issue_date` | ISO 8601 timestamp of issuance | MGS platform |
| `gs_retailer_id` | Issuing retailer identifier | EPOS integration |
| `gs_product_gtin` | GTIN/EAN of product (Tier 2 only) | EPOS integration |
| `gs_pcf_source` | PCF data source (e.g., "CarbonCloud ISO14067") | Tier 2 brand submission |
| `gs_data_tier` | 1 (verified), 2 (high-confidence), 3 (indicative) | Emission factor quality |
| `vcu_project_id` | Verra Registry project ID (e.g., VCS-1566) | VCU linkage |
| `vcu_serial` | VCU serial number | Verra Registry |
| `vcu_vintage` | Credit vintage year | Verra Registry |
| `vcu_methodology` | VCS methodology (e.g., VM0048) | Verra Registry |
| `vcu_retirement_date` | Date of VCU retirement | Verra Registry |
| `blockchain_hash` | Batch anchoring hash | Blockchain ledger |
| `consumer_project` | Consumer-directed conservation project | MGS consumer account |

### 8.3 The Lifecycle of a Green Square

**Stage 1 — Creation**: A VCU is acquired by the MGS CIC from a CCP-eligible project. The VCU enters the CIC's holding account on the Verra Registry. 10,000 GS are authorised against each VCU.

**Stage 2 — Award**: A consumer purchases goods at a participating retailer. The EPOS integration calculates GS earned (Tier 1 category-average or Tier 2 product-specific). GS are credited to the consumer's MGS account in real-time.

**Stage 3 — Direction**: The consumer reviews their GS balance and directs accumulated GS to a conservation project of their choice (Amazon, Borneo, Kenya, Scotland). This direction is logged in the consumer account and aggregated at the CIC level.

**Stage 4 — Retirement**: At defined intervals, the CIC executes a batch VCU retirement on the Verra Registry corresponding to accumulated GS issued. The batch is anchored on-chain. Each GS is linked to the batch retirement hash and the corresponding VCU serial numbers.

**Stage 5 — Verification**: The consumer can scan a QR code to view their GS verification chain: GS ID → batch hash → VCU serial number → Verra Registry retirement record → project documentation. The annual independent audit confirms the integrity of the entire chain.

### 8.4 Integration Points

The full GS lifecycle requires integration across five systems:

```
EPOS (retailer)
  → MGS API (GS calculation engine)
    → Consumer Account (MGS platform)
      → Verra Registry API (VCU retirement)
        → Blockchain Ledger (batch anchoring)
          → Consumer Verification Portal (QR → proof chain)
```

The EPOS integration passes transaction data (SKUs, quantities, prices, department codes) to the MGS API, which returns GS earned per item and per basket. The MGS platform manages consumer accounts, GS balances, and conservation direction. The Verra Registry API (expected to be transaction-ready following the S&P Global partnership) executes batch retirements. The blockchain ledger anchors each batch with a cryptographic hash. The verification portal enables consumer-facing transparency by linking GS IDs to retirement proof.

Existing infrastructure makes each integration point achievable: [Mondra/Oracle ERP integration](https://fooddigital.com/retail/scope-3-uk-food-retailers-unite-to-tackle-ghg-emissions) for EPOS-to-PCF linkage; [ShiftCarbon](https://shiftcarbon.io/solutions/point-of-sale-integration) or [Carbonmark](https://www.carbonmark.com/post/carbon-retirement-verification) for registry API retirement; [Kinexys](https://www.jpmorgan.com/payments/newsroom/kda-blockchain-carbon-market-tokenization) or Polygon L2 for blockchain anchoring. The MGS platform and consumer verification portal are proprietary builds demonstrated in the [live demo](https://northlincseng-cell.github.io/greensquares/).

---

## Conclusion

The Green Square is not merely a loyalty token with environmental branding. It is a scientifically grounded micro-unit of verified carbon reduction, calibrated to consumer-scale actions, priced at the premium end of the voluntary carbon market, and designed to be traceable from point-of-sale through to registry retirement. Its composition draws on the established emission factor databases (DEFRA, EPA, ecoinvent, IPCC AR6), the most widely used carbon crediting standards (Verra VCS, Gold Standard, ICVCM Core Carbon Principles), and the emerging institutional infrastructure (JP Morgan Kinexys, S&P Global, Article 6 PACM) that is transforming carbon markets from fragmented voluntary pledges into standardised, auditable financial instruments.

The 2026 relaunch arrives at a structural inflection point: the [first Paris Agreement credits have been issued](https://unfccc.int/news/un-carbon-market-approves-first-ever-issuance-of-credits-under-the-paris-agreement), blockchain tokenisation is being tested at institutional scale with [bank-grade infrastructure](https://www.jpmorgan.com/kinexys/documents/carbon-markets-reimagined-digital-assets.pdf), reformed verification methodologies address the baseline gaming that destroyed VCM credibility, and UK/EU regulators are punishing vague green claims while rewarding specific, substantiated ones. The Green Square's architecture — CIC asset lock, two-tier emission factor model, batch blockchain traceability, consumer verification portal — is purpose-built for this regulatory environment.

The competitive landscape reinforces the timing. Neither [Tesco Clubcard nor Sainsbury's Nectar](https://yougov.com/en-gb/articles/50083-what-britons-want-out-of-loyalty-programmes-in-2024) has integrated a sustainability reward mechanic. [Reewild/PlanetPoints](https://www.mastercard.com/gb/en/news-and-trends/Insights/2025/planet-points-reewild-sustainable-consumption.html) — the closest competitor — offers eco-loyalty points but not conservation project direction, blockchain verification, or UN harmonisation alignment. The checkout offset market ($1.42 billion in 2024, [projected $5.74 billion by 2033](https://dataintelo.com/report/carbon-smart-e-commerce-checkout-offset-market)) demonstrates appetite but converts at only 1–5% because it asks consumers to pay. MGS converts at the rate of shopping itself, because the consumer cost is zero.

What each Green Square contains is ultimately simple: 100 grams of verified CO2e reduction, backed by a retired carbon credit, held in a legally protected conservation fund, traceable on a blockchain ledger, and directed by a consumer to a named conservation project. The complexity lies not in the unit but in the infrastructure required to make that simplicity trustworthy. This report demonstrates that the infrastructure now exists.
