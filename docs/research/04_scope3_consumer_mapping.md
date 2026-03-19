# Scope 3 Emissions → Consumer Mapping
## Deep Research for My Green Squares (MGS) Platform

**Prepared:** March 2026  
**Purpose:** Scientific and commercial foundation for the MGS Green Squares (GS) award system — mapping GHG Protocol Scope 3 complexity into a consumer-facing unit of 100g CO2e per Green Square, at both basket-level (Tier 1, retailer-funded) and product-level (Tier 2, brand-funded).

---

## Table of Contents

1. [The 15 Scope 3 Categories — Retail/FMCG Deep Dive](#section-1)
2. [Product Carbon Footprints: Methodology and Data](#section-2)
3. [Retail EPOS Integration and SKU-Level Carbon Data](#section-3)
4. [Simplification Strategies and Consumer Research](#section-4)
5. [The Tier 1/Tier 2 Model: Scientific Defensibility](#section-5)
6. [Key Conclusions and Recommendations](#section-6)

---

## Section 1: The 15 Scope 3 Categories — Retail/FMCG Deep Dive {#section-1}

### Overview

The [GHG Protocol Corporate Value Chain (Scope 3) Standard](https://ghgprotocol.org/corporate-value-chain-scope-3-standard) provides the only internationally accepted method for companies to account for value chain emissions across 15 categories, divided into upstream (categories 1–8) and downstream (categories 9–15). For retail, [Scope 3 represents ~97–98% of total emissions](https://www.wwf.org.uk/sites/default/files/2022-11/WWF-Whats-in-Store-for-our-Planet-the-Impact-of-UK%20Shopping-Baskets-on-Climate-and-Nature-2022-v1.pdf), with approximately [80% upstream and 20% downstream in product value chains](https://www.mckinsey.com/capabilities/sustainability/our-insights/retailers-climate-road-map-charting-paths-to-decarbonized-value-chains).

For food/FMCG, [WRAP's 2024 Scope 3 Protocols for UK Food and Drink Businesses](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf) identifies five minimum recommended categories that together cover ≥67% of a food retailer's footprint: **Categories 1, 4, 9, 11, and 12**. Category 1 alone can represent up to **92–95%** of total Scope 3 for food processors.

---

### The 15 Categories in Detail

#### UPSTREAM CATEGORIES

---

**Category 1: Purchased Goods and Services**

- **Definition:** All upstream cradle-to-gate emissions from the extraction, production, and transport of goods and services purchased by the reporting company. This is the single most material category for virtually all food retailers and FMCG brands.
- **What it covers:** Agricultural production of food ingredients (animal and crop), packaging materials, cleaning products, office supplies, IT services. For a supermarket, this encompasses every ingredient in every product on its shelves.
- **Typical emission factors (retail/FMCG):**

| Food Category | kg CO2e / kg product (global avg, Poore & Nemecek 2018) |
|---|---|
| Beef (beef herd) | 99.5 |
| Lamb & Mutton | 39.7 |
| Dark chocolate | ~47 |
| Beef (dairy herd) | 33.3 |
| Coffee | ~29 |
| Farmed shrimp | 26.9 |
| Cheese | 24.0 |
| Farmed fish | ~14 |
| Pig meat | 12.3 |
| Poultry | 9.9 |
| Eggs | 4.7 |
| Rice | 4.5 |
| Tofu | 3.2 |
| Milk | 3.2 |
| Tomatoes | 2.1 |
| Oat milk (Oatly) | ~0.9 |
| Quorn mycoprotein | 0.79 |
| Peas | 0.98 |
| Bananas | 0.89 |

  *Source: [Poore & Nemecek (2018), Science](https://www.science.org/doi/10.1126/science.aaq0216), compiled via [Our World in Data](https://ourworldindata.org/grapher/ghg-per-kg-poore) and [Statista](https://www.statista.com/statistics/1201677/greenhouse-gas-emissions-of-major-food-products/)*

- **Green Squares expression:** A 300g pack of beef mince (4kg CO2e @ 33 kg CO2e/kg) = 40 GS. A 400g pack of chicken fillets (3.6 kg CO2e @ 9 kg CO2e/kg) = 36 GS. A 1L carton of oat milk (0.9 kg CO2e) = 9 GS. Category 1 is the primary driver of Tier 2 product GS calculations.
- **Data availability:** ★★★★☆ — Rich secondary databases exist (WRAP, Ecoinvent, Agribalyse, HESTIA). Supplier-primary data increasingly available via platforms like [Mondra](https://www.mondra.com), [CarbonCloud](https://carboncloud.com), and [Foundation Earth](https://www.foundation-earth.net). Variability can be large (e.g., beef ranges from 30 to 105 kg CO2e/kg depending on farming system).
- **Reliability rating:** Medium-high for averages; high uncertainty at individual product level without supplier data. [WRAP's Data Quality Scoring Framework](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf) rates supplier-specific PCF data as Tier 1 (best), spend-based EEIO as Tier 5 (lowest).

---

**Category 2: Capital Goods**

- **Definition:** Upstream emissions from the production of capital goods purchased by the company (equipment, vehicles, machinery, buildings, IT hardware).
- **What it covers:** Refrigeration units, store fit-out, vehicles, warehouse equipment. Typically a one-off investment, amortised over asset life.
- **Typical emission factors:** Refrigeration system ~1–5 tCO2e each; electric delivery vehicle ~15 tCO2e manufacture. Generally <2% of a retailer's total Scope 3.
- **Green Squares relevance:** Minimal for consumer-facing GS award. Relevant to MGS in terms of platform/terminal hardware carbon accounting (negligible at system level).
- **Data availability:** ★★★☆☆ — Engineering LCA data widely available; accounting records provide activity data.
- **Reliability rating:** Medium. Useful for completeness but not a priority for MGS.

---

**Category 3: Fuel and Energy-Related Activities (not in Scopes 1 or 2)**

- **Definition:** Well-to-tank emissions for fuels used in Scope 1; transmission and distribution (T&D) losses for Scope 2 electricity; extraction and processing of fuels before they are burned.
- **What it covers:** E.g., oil extracted and refined before being burned in delivery vans; T&D losses in the electrical grid before electricity reaches the store.
- **Typical emission factors:** UK electricity T&D losses ~0.019 kg CO2e/kWh (2025 Defra factors). Well-to-tank for diesel ~0.097 kg CO2e/litre.
- **Green Squares relevance:** Operational overhead not directly allocable to consumer baskets. Embedded within store-level energy allocation.
- **Data availability:** ★★★★★ — Defra publishes annual UK conversion factors. [2025 Defra factors available from GOV.UK](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025).
- **Reliability rating:** High. Well-established emission factors.

---

**Category 4: Upstream Transportation and Distribution**

- **Definition:** Third-party transport emissions from supplier to reporting company (inbound logistics). Includes road, rail, air, sea freight.
- **What it covers:** Ingredients transported from farms to factories; finished goods from factories/DCs to stores; cold chain logistics. For a major UK supermarket, this may represent 5–10% of Scope 3.
- **Typical emission factors:** HGV road freight ~0.089 kg CO2e/tonne-km (Defra 2025); air freight ~2.1 kg CO2e/tonne-km; sea freight ~0.012 kg CO2e/tonne-km.
- **Green Squares expression:** UK-imported strawberries via road: ~0.2 kg CO2e/kg at 2,000km = 2 GS/kg. Air-freighted Kenyan green beans: ~8 kg CO2e/kg = 80 GS/kg.
- **Data availability:** ★★★★☆ — Logistics providers increasingly report tonne-km data; Defra factors well-established. Tier 1 supplier transport often estimated.
- **Reliability rating:** Medium-high for distance-based methods; lower for aggregated logistics networks.

---

**Category 5: Waste Generated in Operations**

- **Definition:** Third-party disposal and treatment of waste generated in the company's own operations (stores, warehouses, offices) — not waste in the supply chain.
- **What it covers:** Food waste from store operations going to landfill or anaerobic digestion (AD); packaging waste; general commercial waste.
- **Typical emission factors:** Food to landfill ~0.64 kg CO2e/kg; food to AD ~-0.13 kg CO2e/kg (benefit); mixed commercial waste ~0.53 kg CO2e/kg (Defra 2025).
- **Green Squares relevance:** Operational retailer category; not directly linked to consumer basket value for Tier 1.
- **Data availability:** ★★★★☆ — Waste tonnage records standard in retail operations.
- **Reliability rating:** High for waste arisings; medium for fate/treatment mix.

---

**Category 6: Business Travel**

- **Definition:** Third-party transport emissions from employee business travel (flights, trains, taxis, car hire).
- **What it covers:** Buyer trips to supplier sites, trade shows, head office travel.
- **Typical emission factors:** Short-haul economy flight ~0.15 kg CO2e/passenger-km (2025 Defra); rail ~0.035 kg CO2e/passenger-km.
- **Green Squares relevance:** Negligible — represents <0.1% of retail Scope 3. Not relevant to basket-level calculations.
- **Data availability:** ★★★★★ — Expense reporting systems.
- **Reliability rating:** High.

---

**Category 7: Employee Commuting**

- **Definition:** Emissions from employees' home-to-work travel in non-company-owned vehicles.
- **What it covers:** Staff commuting to stores, warehouses, and head offices.
- **Typical emission factors:** UK average car commute ~0.17 kg CO2e/km; bus ~0.09 kg CO2e/km (Defra 2025). Large supermarkets employ 100,000+ staff.
- **Green Squares relevance:** Background operational overhead; ~0.2% of retail Scope 3.
- **Data availability:** ★★★☆☆ — Requires employee survey data; often estimated from workforce size and national commuting averages.
- **Reliability rating:** Medium.

---

**Category 8: Upstream Leased Assets**

- **Definition:** Operation of assets leased by the company and not included in Scope 1 or 2 (e.g., leased store premises where the landlord is responsible for energy).
- **What it covers:** Leased retail space, leased vehicles, leased cold storage.
- **Typical emission factors:** Varies by asset type and energy use.
- **Green Squares relevance:** Operational overhead; embedded in store-level apportionment.
- **Data availability:** ★★★☆☆ — Dependent on landlord energy data sharing.
- **Reliability rating:** Low-medium.

---

#### DOWNSTREAM CATEGORIES

---

**Category 9: Downstream Transportation and Distribution**

- **Definition:** Transport of products from the company's operations to the end consumer, where not paid for by the reporting company. For a retailer, this most critically includes **customer travel to and from the store**.
- **What it covers:** Final mile delivery (home delivery); customer journeys to stores; inter-store transfers not included in Cat 4. [WRAP](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf) identifies this as one of the minimum recommended categories for retailers.
- **Typical emission factors:** Average UK car trip to supermarket ~2–4 kg CO2e per trip (1.6km average distance, petrol car ~0.17 kg CO2e/km = 0.27 kg CO2e outbound; but full round trip with multiple passengers apportioned). Home grocery delivery van: ~0.05–0.2 kg CO2e per delivery slot.
- **Green Squares relevance:** Not directly applicable to basket-level GS award. Could be a factor in rewarding online vs in-store behaviour differentially. Per the BOPIS (Buy Online, Pick Up In Store) lifecycle analysis, [in-store retail and BOPIS show comparable per-basket carbon footprints of ~57 kg CO2e](https://www.sciencedirect.com/science/article/pii/S1361920926000830).
- **Data availability:** ★★★☆☆ — Customer travel data requires modelling from store location and catchment data.
- **Reliability rating:** Medium.

---

**Category 10: Processing of Sold Products**

- **Definition:** Emissions from downstream processing of intermediate products sold to business customers.
- **What it covers:** A flour miller selling flour to a bakery; the bakery's processing emissions fall in Cat 10 for the miller. For retailers selling direct to consumers (final products), this category is typically **not applicable**.
- **Green Squares relevance:** Not applicable for most retail contexts (selling finished goods to consumers).
- **Data availability:** N/A for final product retailers.
- **Reliability rating:** N/A.

---

**Category 11: Use of Sold Products**

- **Definition:** Direct and indirect use-phase emissions from the end use of goods sold by the company. The [GHG Protocol](https://ghgprotocol.org/sites/default/files/2022-12/Chapter11.pdf) distinguishes between direct use-phase emissions (product directly emits GHGs, e.g., fuel) and indirect use-phase emissions (product requires energy to operate).
- **What it covers for food retail:** Refrigeration energy used by consumers to store food; cooking energy (hobs, ovens, microwaves); energy for washing clothing/textiles.
  - A freezer running at home to store frozen goods: ~0.2 kWh/day × 0.2 kg CO2e/kWh = ~15 kg CO2e/year per freezer.
  - Cooking a 300g beef joint: electric oven ~1.56 kWh × 0.2 = ~0.31 kg CO2e.
- **For non-food FMCG:** Washing machine energy per cycle for clothing is significant — ~0.63 kWh × 0.2 = 0.13 kg CO2e per wash; over 50 washes per garment = 6.5 kg CO2e.
- **Green Squares relevance:** Important for non-food items (electronics, appliances, textiles). For perishable food, often negligible relative to production emissions (typically <5% of food's total lifecycle footprint). May be included in Tier 2 product GS calculations for electrically-operated products.
- **Data availability:** ★★★☆☆ — Product use profiles from industry standards; energy consumption from product specifications.
- **Reliability rating:** Medium. Requires assumptions about consumer use behaviour.

---

**Category 12: End-of-Life Treatment of Sold Products**

- **Definition:** Disposal and treatment of products sold by the company at the end of their lives, including packaging.
- **What it covers:** Consumer food waste going to landfill or household composting; product packaging waste (plastic, glass, cardboard recycling); textile disposal.
- **Typical emission factors:** Food waste to landfill ~0.64 kg CO2e/kg; mixed municipal waste to landfill ~0.58 kg CO2e/kg; cardboard recycled ~0.02 kg CO2e/kg; plastic incineration ~2.0 kg CO2e/kg.
- **Green Squares relevance:** [WRAP](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf) identifies this as a minimum required category for retailers. Often represents 5–10% of total Scope 3 for packaged food retailers. Could inform differential GS rates for products with recyclable vs single-use packaging.
- **Data availability:** ★★★☆☆ — Packaging mass/composition from product specs; waste fate estimated from national recycling rate statistics.
- **Reliability rating:** Medium.

---

**Category 13: Downstream Leased Assets**

- **Definition:** Operation of assets owned by the company and leased to third parties.
- **What it covers:** Franchise premises, equipment leased to concession holders.
- **Green Squares relevance:** Minimal for standard supermarket/FMCG context unless significant franchise operations. M&S reports this as 2% of Scope 3 via franchises.
- **Data availability:** ★★★☆☆.
- **Reliability rating:** Medium.

---

**Category 14: Franchises**

- **Definition:** Scope 1 and 2 emissions from franchise operations not included in the company's Scope 1 and 2.
- **What it covers:** Energy used by franchised outlets (e.g., a branded coffee franchise within a supermarket).
- **Green Squares relevance:** Negligible for most grocery retailers.
- **Data availability:** ★★★☆☆.
- **Reliability rating:** Medium.

---

**Category 15: Investments**

- **Definition:** Financed emissions — the Scope 1 and 2 emissions of companies in which the reporting organisation holds equity, debt, or project finance.
- **What it covers:** For a retailer with a financial services arm (e.g., Tesco Bank), this would include the financed emissions of loan portfolios.
- **Green Squares relevance:** Not applicable to retail operations for MGS basket calculations.
- **Data availability:** ★★☆☆☆ — Requires PCAF (Partnership for Carbon Accounting Financials) methodology.
- **Reliability rating:** Low-medium.

---

### Materiality Summary for Food Retail

Based on [CDP sector data](https://cdn.cdp.net/cdp-production/cms/guidance_docs/pdfs/000/003/504/original/CDP-technical-note-scope-3-relevance-by-sector.pdf), [WRAP protocols](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf), and [M&S ESG reporting](https://corporate.marksandspencer.com/sites/marksandspencer/files/2024-06/ESG_Report_2024.pdf):

| Category | % of Retail Scope 3 | MGS Relevance | Priority |
|---|---|---|---|
| 1 — Purchased goods | 55–77% | Core of Tier 2 product GS | **Critical** |
| 4 — Upstream transport | 5–10% | Embedded in product PCF | High |
| 9 — Downstream transport | 5–8% | Customer travel; optional | Medium |
| 11 — Use of sold products | 3–8% | Non-food products only | Medium |
| 12 — End-of-life | 5–8% | Packaging factor | Medium |
| 2, 3, 5–8, 13–15 | <5% combined | Background/operational | Low |

**Key insight for MGS:** Category 1 (purchased goods, i.e., product-level supply chain emissions) is the single most important driver. A well-designed Tier 2 system that captures Category 1 PCFs captures the overwhelming majority of a product's true climate impact.

---

## Section 2: Product Carbon Footprints — Methodology and Data {#section-2}

### What is a Product Carbon Footprint (PCF)?

A Product Carbon Footprint (PCF) is the quantification of greenhouse gas emissions generated throughout the supply chain of a specific product, expressed in kg CO2e, covering all six major GHGs (CO2, CH4, N2O, HFCs, PFCs, SF6). It is "usually expressed as a carbon intensity — e.g., kg CO2e per kg product, or kg CO2e per unit," per [CarbonChain](https://www.carbonchain.com/carbon-accounting/product-carbon-footprint).

A PCF is effectively the single-product application of Scope 3, and is the scientific foundation for Tier 2 Green Squares.

---

### ISO 14067:2018 — Carbon Footprint of Products

[ISO 14067:2018](https://www.iso.org/standard/71206.html) is the primary international standard specifying principles, requirements, and guidelines for the quantification and reporting of the carbon footprint of a product (CFP). It is consistent with the ISO 14040/14044 Life Cycle Assessment standards.

**Key methodological features:**

1. **Life Cycle Assessment (LCA) approach:** Systematically identifies and quantifies all GHG emissions at every stage of a product's lifecycle.
2. **System boundaries:** Typically "cradle-to-grave" (raw material extraction → manufacturing → distribution → use → end-of-life) or "cradle-to-gate" (up to point of sale), depending on scope.
3. **Functional unit:** A specific quantified description of the product's function (e.g., "1 kg of packaged chicken breast").
4. **Data hierarchy:**
   - Primary data (from the company's own operations and suppliers) — highest quality
   - Secondary data (industry databases, LCA databases like Ecoinvent, Agribalyse, HESTIA) — lower quality
5. **Allocation:** When a process produces multiple outputs (e.g., a beef carcass yields steak, mince, leather), emissions must be allocated between co-products.
6. **GWP100:** Global Warming Potential over 100 years (IPCC AR5/AR6 values).

**Limitations identified by [Decerna](https://www.decerna.co.uk/knowledge-base/life-cycle-assessment/iso-standards/iso-14067/):**
- Verification is **optional** under ISO 14067 (unlike Environmental Product Declarations which require mandatory third-party verification)
- No minimum data quality thresholds specified in the standard
- Methodological choices (system boundary, allocation method, recycling approach) can materially change results
- Only covers climate change — not water, biodiversity, land use

**Accuracy:** PCFs calculated to ISO 14067 typically carry uncertainty ranges of ±20–50% due to variability in supply chain data. [As Carbon Direct notes](https://www.carbon-direct.com/insights/carbon-footprint-data-collection-common-challenges-and-how-to-solve-them), 83% of companies struggle to access accurate emissions data from their supply chain, and self-reported supplier data carries risks of over- or under-reporting.

---

### PAS 2050:2011 — UK Standard for Product Carbon Footprinting

[PAS 2050](https://gicgrp.com/uk/audit-services/product-carbon-footprint-pas-2050/) was developed by BSI British Standards in 2008 (revised 2011), co-sponsored by the Carbon Trust and Defra. It was "the first consensus-based and internationally applicable standard on product carbon footprinting," per the [GHG Protocol PAS 2050 Factsheet](https://ghgprotocol.org/sites/default/files/2022-12/GHG%20Protocol%20PAS%202050%20Factsheet.pdf).

**Methodology:**
- Takes a **process LCA approach** (as opposed to EEIO/spend-based)
- Covers both B2B (business-to-business) and B2C (business-to-consumer) assessments
- System boundary: GHG emissions from production, transportation, storage, distribution, use, and disposal
- Allows **exclusions** based on materiality (<1% of total) provided at least 95% of the product's life cycle is included
- **Five steps:** Build process map → Check boundaries → Collect data → Calculate footprint → Check uncertainty

**Relationship to ISO 14067:** PAS 2050 and ISO 14067 are broadly harmonised — both use LCA methodology and the same GWP100 metrics. Minor differences exist in recycling approaches and reporting requirements. The [GHG Protocol Factsheet](https://ghgprotocol.org/sites/default/files/2022-12/GHG%20Protocol%20PAS%202050%20Factsheet.pdf) notes the two standards should give "results not expected to be significantly different" for most products.

**Practical difference for MGS:** ISO 14067 is now the dominant global standard; PAS 2050 is more prevalent among UK brands. Both are scientifically valid for Tier 2 GS calculations. MGS should accept either standard as an input methodology.

---

### What Data Do Brands Typically Have?

Based on research across multiple sources:

| Data Type | Availability | Quality |
|---|---|---|
| Own Scope 1+2 energy use | Near-universal | High |
| Tier 1 supplier data (direct inputs) | 40–60% of brands | Medium |
| Tier 2+ supplier data (raw materials) | 10–20% of brands | Low |
| Ingredient-level LCA (from databases) | Most brands via consultants | Medium |
| Full ISO 14067 certified PCF | ~15% of FMCG brands | High |
| Spend-only data (EEIO) | Universal fallback | Low |

According to [Carbon Direct](https://www.carbon-direct.com/insights/carbon-footprint-data-collection-common-challenges-and-how-to-solve-them), the key challenges are: (1) SME suppliers lack resources to measure emissions; (2) confidentiality concerns around sharing data; (3) fragmented data across multiple systems; (4) inconsistent methodologies across the supply chain.

**Industry response:** The [BRC Mondra Coalition](https://www.mondra.com) (including Tesco, M&S, Sainsbury's, Ocado, Aldi, Lidl) is working to establish a unified standard for product-level performance measurement across the UK food industry, using AI-powered LCA and a "living digital twin" for every product's carbon footprint.

---

### Accuracy of Product-Level CO2e Calculations

| Method | Typical Accuracy | Best For |
|---|---|---|
| Supplier-specific primary data | ±10–20% | Tier 2 brand claims |
| Industry-average LCA (Ecoinvent/Agribalyse) | ±30–50% | Tier 1 basket estimates |
| Spend-based EEIO | ±50–100%+ (factor of 2 or more) | Screening only |

[Steubing et al. (2022)](https://www.climatiq.io/blog/science-behind-spend-based-emission-factors) found that comparing EXIOBASE spend-based factors against Ecoinvent LCA, >50% of product footprints differed by a factor of 2. Spend-based methods are adequate for screening and Tier 1 basket estimation but are not appropriate for making specific product-level claims.

**MGS practical implication:** Tier 2 brands must provide LCA-based PCF data (ideally ISO 14067 compliant). Tier 1 basket calculations may use spend-based or category-average emission factors as a defensible starting point, with clear disclosure of methodology.

---

## Section 3: Retail EPOS Integration and SKU-Level Carbon Data {#section-3}

### What Product-Level Data Exists in Standard EPOS Systems?

A typical retail Electronic Point of Sale (EPOS) system records per-transaction:
- **SKU/barcode (GTIN/EAN)** — unique product identifier
- **Product description** — name, variant, size
- **Quantity** — units or weight sold
- **Price** — unit price, total price
- **Category/department code** — e.g., "Fresh Meat," "Dairy," "Bakery"
- **Timestamp** — date, time
- **Store ID / till ID**
- **Promotions applied**

What it does **not** contain by default:
- Carbon footprint data
- Ingredient composition
- Country of origin (sometimes in product master data)
- Packaging type/weight

The EPOS system links to a **Product Information Management (PIM)** system or **Enterprise Resource Planning (ERP)** system (e.g., SAP, Oracle), which holds richer product master data including weight, dimensions, supplier codes, and nutritional information. This is the integration point where carbon data can be introduced.

---

### How to Link SKUs to Carbon Footprint Data

There are three emerging technical approaches:

**1. Carbon data enrichment of product master records**  
Carbon footprint values (kg CO2e/kg or kg CO2e/unit) are added as a field in the PIM/ERP product master. At checkout, the EPOS queries this field and calculates GS for the basket.  
- Used by: Mondra integration with Oracle ERP, as referenced in their [BRC coalition work](https://www.mondra.com/blog/mondra-and-impactbuying-set-a-new-standard-for-product-level-carbon-data)
- [Mondra integrates with existing commercial retailer systems, notably those provided by Oracle](https://fooddigital.com/retail/scope-3-uk-food-retailers-unite-to-tackle-ghg-emissions)

**2. Real-time API lookup at POS**  
At checkout, a carbon data API is queried using the product GTIN. The API returns the PCF value, and the EPOS calculates the GS.  
- Faster to deploy without ERP changes; higher latency at checkout
- Similar to how loyalty programme points engines work today

**3. Category-level factor tables**  
EPOS applies a category-level emission factor to the purchase price or quantity, without product-specific PCF data. This is the Tier 1 approach.  
- E.g., "Fresh Meat" category = 8.5 kg CO2e/kg × weight sold = GS awarded

**4. Electronic Shelf Label (ESL) integration**  
[Vusion/SES-imagotag Electronic Shelf Labels](https://www.vusion.com/products/sesimagotag/electronic-shelf-labels/) integrate with POS systems and could display carbon label information directly on the shelf edge alongside price. [Uniware EPOS systems](https://www.uniware.co.uk/2024/07/02/carbon-label/) already support displaying kg CO2e data on self-service kiosks and order apps by integrating Klimato or Nutritics data.

---

### SKU Carbon Databases

| Platform | Coverage | Methodology | Access |
|---|---|---|---|
| [CarbonCloud ClimateHub](https://apps.carboncloud.com/climatehub) | 10,000+ US branded products; expanding to UK | Farm-to-shelf LCA | Free public; subscription for brand management |
| [Mondra](https://www.mondra.com) | UK/EU food supply chains; BRC coalition members | ISO 14067-aligned LCA | Commercial B2B |
| Foundation Earth | 500+ food products (UK, certified) | LCA, A+–G score | B2B partnership |
| Klimato | Food service/restaurant menus | LCA per dish | B2B subscription |
| WRAP UK Food/Drink EF database | Ingredient-level, ~400 food commodities | Consolidated LCA (Poore & Nemecek + Agribalyse + HESTIA) | Free download |

**For MGS integration:** The most commercially scalable route is:
1. For Tier 1: Apply category-level emission factors from WRAP/EEIO databases to EPOS department/category codes
2. For Tier 2: Require participating brands to provide certified PCF data (ISO 14067 or PAS 2050), submit via MGS data portal, map to GTIN, and inject into product master or real-time API

---

### Existing Examples of Carbon Labelling at Point of Sale

**Oatly**  
[Oatly was a pioneer](https://www.oatly.com/oatly-who/sustainability-plan/climate-footprint-product-label), launching carbon footprint labels in the UK in 2019 and US in 2023. Their label displays kg CO2e per kg product, calculated using [CarbonCloud's ISO 14067-aligned LCA platform](https://www.fooddive.com/news/oatly-debuts-carbon-footprint-labeling-on-us-products/641605/) from cradle-to-gate ("grower to grocer"). Values are recalculated annually. Example: Oatly Oat Drink ~0.3–0.9 kg CO2e/litre.

**Quorn**  
[Quorn displays carbon footprint labels](https://www.quorn.co.uk/carbon-footprint) showing kg CO2e per serving (calculated by the Carbon Trust to ISO 14067/PAS 2050). Example values: Quorn Mince = 0.16 kg CO2e/serving (300g pack ~1.29 kg CO2e/kg). [Full Carbon Trust comparison report (2022)](https://www.quorn.co.uk/assets/files/content/Carbon-Trust-Comparison-Report-2022.pdf) shows Quorn products range from 0.79–2.79 kg CO2e/kg, compared to 27–100 kg CO2e/kg for beef.

**Klimato / Eaternity (foodservice)**  
[Klimato partners with foodservice businesses](https://futuregreen.global/our-services/communications-and-marketing/menu-carbon-labelling/) to display per-dish carbon footprints at point of sale. Integrates with EPOS systems to display CO2e values on kiosks.

**Foundation Earth**  
[Foundation Earth](https://www.theconsumergoodsforum.com/race-to-zero-hub-resources/foundation-earth-eco-impact-labelling/) issues front-of-pack environmental labels on food products rating A+ to G, used by brands including Meatless Farm and others. LCA-based, recertified annually, covers carbon, water, biodiversity.

---

## Section 4: Simplification Strategies and Consumer Research {#section-4}

### How Existing Carbon Labels Simplify Complex Data

**Foundation Earth (A+ to G)**  
The [Foundation Earth eco-impact label](https://environmentallabels.co.uk/how-foundation-earth-is-disrupting-labelling-of-consumer-products/) uses a traffic-light scoring system (A+ to G) analogous to nutritional labels, with letter grades based on LCA scores covering carbon, water, biodiversity, and land use. By converting raw kg CO2e values into a comparative grade, it removes the need for consumers to understand absolute numbers. Re-certified yearly to enable improvement tracking.

**Eco-Score (France)**  
The [French Eco-Score (Coût Environnemental)](https://www.anthesisgroup.com/regulations/french-eco-score/) is linked to the *Climat et Resilience* law and Decree no.2025-957 (in effect from 1 October 2025). It uses a simplified LCA aligned with EU Product Environmental Footprint (PEF) Category Rules, consolidating 16 environmental impact categories into a single cumulative score. Products display a numeric environmental cost per 100g product. [Vaayu explains](https://www.vaayu.tech/insights/french-ecoscore-explained) it will be calculable for textile products, with third parties able to publish scores from October 2026.

**Carbon Trust Label**  
The Carbon Trust's product footprint certification (used on Quorn products) displays the absolute kg CO2e value on pack, certified by a recognised third party. More scientifically rigorous but less intuitive for consumers without context.

**Traffic Light Systems vs Absolute Numbers**

Key research finding: **Traffic light / relative labels outperform absolute numbers alone.**  
[A pre-registered experiment with 1,126 participants](https://www.sciencedirect.com/article/pii/S0950329323000071) found:
- Traffic light label (relative sustainability within category): **increased choice of low-CO2 food items** vs control
- Absolute kg CO2e label alone: **no significant effect** on choice
- Combined (traffic light + absolute): **also increased** low-CO2 choices
- Conclusion: "A label communicating the absolute carbon emissions has no effect. A traffic light label fosters the choice of low (vs high) CO2 food items."

**MGS innovation:** The Green Square unit (100g CO2e = 1 GS) is fundamentally different from both approaches. It transforms carbon into a **positive reward** rather than a warning or grade. This is a distinct and potentially more powerful mechanism — rewarding engagement rather than shaming high-carbon choices.

---

### Consumer Research on Carbon Metric Comprehension

**Awareness is low but growing:**  
[Research with energy-specialist university students](https://www.frontiersin.org/journals/climate/articles/10.3389/fclim.2025.1708974/full) found only 45.7% had heard of carbon labels. General consumer awareness is lower. This means any consumer-facing carbon unit must be immediately legible without prior knowledge.

**Key comprehension challenges:**
- Consumers lack intuitive reference points for kg CO2e values
- "3.2 kg CO2e per kg of milk" means nothing without context
- Relative comparisons (vs similar products, vs daily budget) improve understanding significantly
- Contextualisation (e.g., "equivalent to driving 12 miles") aids comprehension but adds complexity

**What works:**
1. **Simplification to a single number/grade** (Foundation Earth A+–G; Eco-Score)
2. **Comparative framing** — relative to category average or traffic-light threshold
3. **Meaningful scale anchoring** — the "1.5°C budget" framing (daily diet carbon budget of ~2–3 kg CO2e/day for a 1.5°C trajectory) provides a scientific anchor
4. **Positive reward mechanisms** — [carbon labels plus rewards significantly increase sustainable purchasing](https://www.sciencedirect.com/article/pii/S2666188825009463)
5. **Trust signals** — government-endorsed labels are more trusted than private labels, per [University of Michigan consumer research](https://sites.lsa.umich.edu/sustainablefoodsystems-new/wp-content/uploads/sites/1010/2016/05/ebedrick.pdf)

**Willingness to pay:** In a [2024 PwC survey of 20,000 consumers](https://www.strategy-business.com/article/A-better-way-to-market-sustainable-products), respondents stated willingness to pay 9.7% above average for sustainably produced goods. [NYU Stern CSB data shows sustainability-marketed products grew at 2.3× the rate of conventional items (12.3% vs 5.3% annually, 2019–2024)](https://www.strategy-business.com/article/A-better-way-to-market-sustainable-products).

---

### Making Scope 3 Meaningful at the Grocery Checkout

**The core challenge:** Scope 3 is complex, multi-layered, and largely invisible to consumers. A person buying groceries cannot intuitively connect "purchasing beef" to "Scope 3 Category 1 upstream agricultural emissions including methane from enteric fermentation and land-use change."

**The MGS approach — Green Squares as translator:**

The 100g CO2e = 1 Green Square conversion solves this by:
1. **Creating a tangible unit** — most consumers understand grams as a physical quantity
2. **Anchoring to a recognisable scale** — 100g is the weight of a standard chocolate bar; CO2e is abstracted away
3. **Making it rewarding** — GS are earned, not a penalty
4. **Enabling comparison** — consumers can see Product A earns 3 GS vs Product B earns 8 GS
5. **Scientific grounding** — 100g CO2e has precise scientific meaning (per IPCC GWP100)

**Contextualisation examples:**
- Average UK car mile = ~170g CO2e = 1.7 GS
- A cup of tea = 40g CO2e = 0.4 GS
- A beef burger serving (150g) = ~3,000g CO2e = 30 GS
- A 1.5°C-compatible daily food budget ≈ 2,000g CO2e = 20 GS/day

These anchors can be used in in-app MGS education to build consumer carbon literacy over time.

---

## Section 5: The Tier 1/Tier 2 Model — Scientific Defensibility {#section-5}

### Is a Basket-Level Average Scientifically Defensible?

**Yes — with appropriate caveats and disclosure.**

The spend-based emission factor approach is formally endorsed by the GHG Protocol as a valid (if lower-quality) method for calculating Scope 3 Category 1 emissions. [GHG Protocol Technical Guidance (Chapter 1)](https://ghgprotocol.org/sites/default/files/2022-12/Chapter1.pdf) explicitly states: "If the supplier-specific method, hybrid method, and average-data method are not feasible (e.g., due to data limitations), companies should apply the average spend-based method."

The [US EPA USEEIO model](https://www.epa.gov/land-research/us-environmentally-extended-input-output-useeio-models) and [EXIOBASE](https://exiobase.eu) are the two principal EEIO databases used globally. [Climatiq](https://www.climatiq.io/data/emission-factor/9e0ebb95-ed59-49e9-8c0a-290f0975ae77) publishes a spend-based factor for **convenience stores** of **0.186 kg CO2e/USD** (cradle-to-shelf, US 2022 data). For "all other retail," the factor is **0.231 kg CO2e/USD**.

**UK conversion for Tier 1 calibration:**

Using the Climatiq convenience store factor (0.186 kg CO2e/USD) and applying a GBP/USD conversion:
- At ~$1.27/£ (2025 average), this equates to approximately **0.24 kg CO2e/GBP**
- Or 2.4 GS per £1 spent at a convenience store

For UK grocery (standard supermarket), applying category-level EEIO adjustments based on product mix:
- A comprehensive UK grocery basket is estimated at **0.25–0.45 kg CO2e/GBP** depending on food mix (higher for meat-heavy baskets)
- A typical £100 UK weekly grocery shop → approximately **25–45 kg CO2e** → **250–450 GS** (2.5–4.5 GS/£)

**Sensitivity by product category (using EEIO + LCA blending):**

| Category | Estimated kg CO2e/£ spent | GS per £ |
|---|---|---|
| Fresh beef/lamb | 2.0–4.0 | 20–40 |
| Fresh poultry | 0.8–1.5 | 8–15 |
| Dairy (milk, cheese) | 0.5–1.2 | 5–12 |
| Fresh vegetables | 0.15–0.35 | 1.5–3.5 |
| Ambient grocery (tinned, pasta, cereals) | 0.3–0.6 | 3–6 |
| Frozen food (mixed) | 0.4–0.9 | 4–9 |
| Confectionery/snacks | 0.5–1.0 | 5–10 |
| Beverages (soft drinks, juice) | 0.2–0.5 | 2–5 |
| Non-food FMCG (cleaning, personal care) | 0.2–0.4 | 2–4 |

*Note: These are estimates derived from Poore & Nemecek ingredient emission factors, typical product composition, and UK retail pricing. They should be validated against retailer Scope 3 data for Tier 1 calibration.*

---

### How to Calibrate GS-per-£-Spent Ratios by Retailer Sector

**Recommended calibration approach:**

1. **Obtain retailer's total Scope 3 emissions** (from annual report or sustainability disclosure)
2. **Obtain total retail revenue** (from annual report)
3. **Calculate average emission intensity:** Total Scope 3 ÷ Revenue = kg CO2e/£
4. **Validate against EEIO benchmark** (Climatiq EXIOBASE or USEEIO factors)
5. **Apply sector-specific adjustments** for product mix

**UK major retailer reference data:**

| Retailer | Scope 3 (tCO2e, most recent) | Revenue (£bn) | Estimated kg CO2e/£ | GS/£ |
|---|---|---|---|---|
| M&S | ~5.2m (2023/24) | ~13.0 | ~0.40 | ~4.0 |
| Tesco | ~1.9m (S1+2+3 combined; S3 likely ~23m) | ~57.5 (UK) | ~0.40 | ~4.0 |
| Sainsbury's | ~706,115t (S1+2 only per DitchCarbon; S3 likely 20x) | ~31.0 | ~0.35 | ~3.5 |

*Note: These figures are illustrative; full Scope 3 data requires direct retailer disclosure. M&S 2023/24 Scope 3 of 5.2m tCO2e is specifically for M&S's own-brand product footprints, not total market sales.*

**Practical Tier 1 calibration for MGS:**

- **Conservative starting point:** 3 GS per £1 spent at any FMCG retailer
- **Category-adjusted:** 2 GS/£ for non-food; 3 GS/£ for ambient grocery; 5 GS/£ for fresh meat-heavy baskets
- **Aspirational (full product-mix accounting):** Use retailer-specific total Scope 3 ÷ total revenue, updated annually

**Disclosure requirement:** For Tier 1 to be scientifically defensible, MGS must clearly state:
- The GS rate is based on average emission intensity for the retailer sector
- Individual products may have higher or lower actual footprints
- Tier 2 provides product-specific data where available

---

### Should Different Product Categories Earn Different GS Rates?

**Yes — and this is the most scientifically robust approach.**

The emission intensity of different food categories varies by a factor of >100 (bananas at 0.9 kg CO2e/kg vs beef at 99 kg CO2e/kg). Applying a single GS/£ rate across all product categories introduces significant errors in both directions:
- Underestimates GS for high-carbon products (beef, lamb, dairy)
- Overestimates GS for low-carbon products (vegetables, legumes, plant-based)

**Proposed tiered category rate structure for Tier 1:**

| Tier 1 Sub-tier | Product Categories | Basis | GS per £ (approx) |
|---|---|---|---|
| T1-A (High intensity) | Beef, lamb, mutton, game | 30–50 kg CO2e/kg avg; £10–20/kg → 1.5–4 kg CO2e/£ | 15–40 |
| T1-B (Medium-high) | Pork, poultry, fish, dairy, cheese | 5–12 kg CO2e/kg avg; £8–15/kg → 0.4–1.5 kg CO2e/£ | 4–15 |
| T1-C (Medium) | Eggs, rice, processed food, frozen | 1–5 kg CO2e/kg avg; £2–8/kg → 0.3–1.5 kg CO2e/£ | 3–15 |
| T1-D (Low) | Vegetables, fruit, legumes, bread | 0.1–2 kg CO2e/kg avg; £1–4/kg → 0.1–0.5 kg CO2e/£ | 1–5 |
| T1-E (Non-food) | Household, personal care, textiles | 0.2–0.5 kg CO2e/£ (EEIO) | 2–5 |

**Practical limitation of category-differentiated Tier 1:** Requires EPOS to pass department/category codes to the GS calculation engine. Standard EPOS systems already hold this data — the integration simply requires mapping retailer category codes to MGS emission factor tiers.

**Recommendation:** Implement a 5-tier Tier 1 structure based on EPOS department codes, calibrated annually using WRAP and Defra emission factor data. This maintains simplicity for consumers (GS awarded at basket level) while significantly improving scientific accuracy vs a flat rate.

---

### Interaction Between Tier 1 and Tier 2

Where a product has Tier 2 data (brand-funded, fixed GS per product based on certified PCF):

- **Tier 2 GS should replace Tier 1 GS for that product** in the basket calculation
- This creates a commercial incentive for brands to invest in Tier 2: their product's GS rate becomes more accurate, and if the product has a lower-than-average footprint, it earns fewer GS (more authentic) or more GS (if positioned as lower-carbon)
- The consumer sees a mixed basket: some products with brand-certified GS (Tier 2), others with category-average GS (Tier 1)

This dual-tier structure mirrors the GHG Protocol's own data hierarchy: supplier-specific data (Tier 2) > average-data method (Tier 1) > spend-based method.

---

## Section 6: Key Conclusions and Recommendations {#section-6}

### Summary of Findings

| Research Area | Key Finding |
|---|---|
| Scope 3 materiality | Categories 1, 4, 9, 11, 12 cover ≥67% of food retail Scope 3; Cat 1 alone is 55–77% |
| Product-level data | ISO 14067/PAS 2050 PCFs are scientifically valid; accuracy ±20–50%; verification recommended |
| EPOS integration | GTIN/SKU already exists in all EPOS systems; PCF can be added to product master or via API |
| Consumer labels | Traffic light > absolute numbers alone for behaviour change; rewards outperform penalties |
| Basket-level intensity | ~0.25–0.45 kg CO2e/£ for UK grocery; ~2.5–4.5 GS/£ at flat rate, or 1–40 GS/£ by category |
| Scientific defensibility | Spend-based Tier 1 is GHG Protocol-endorsed; must be disclosed as "average intensity estimate" |

### Recommendations for MGS Design

1. **The Green Square (100g CO2e) unit is scientifically sound.** It maps directly to the kg CO2e metric used in all major carbon accounting standards, expressed at a scale (100g) that is intuitive and proportionate to typical product-level emissions.

2. **Tier 1 flat-rate should be replaced with a 5-category rate structure** as soon as EPOS category-code integration is available. A flat ~3 GS/£ is defensible for v1.0 but significantly underserves the scientific potential.

3. **Tier 2 PCF submissions should require ISO 14067 or PAS 2050 compliance** with third-party verification recommended (though not mandatory for entry). CarbonCloud, Mondra, Foundation Earth, and Carbon Trust are all viable PCF partners for brands.

4. **GTIN-PCF linkage is technically feasible.** The BRC Mondra Coalition model demonstrates that product-level PCF data can be systematically linked to GTINs and integrated with Oracle ERP systems. MGS should model a similar API-based or product-master injection approach.

5. **Oatly and Quorn provide proof of concept for on-pack carbon labelling.** Their data can serve as reference points for Tier 2 entry GS values before brands submit their own certified PCFs.

6. **Consumer communication should emphasise reward, relative comparison, and contextualisation** — not raw CO2e numbers. "You earned 45 Green Squares today — that's like planting a tree" is more effective than "Your basket produced 4.5 kg CO2e."

7. **Tier 1 is scientifically defensible with explicit disclosure.** The GHG Protocol endorses spend-based methods as a valid starting point. MGS must clearly communicate on its platform that Tier 1 GS rates are based on sector-average emission intensities and that Tier 2 provides greater accuracy.

8. **The most material Scope 3 insight for MGS:** Category 1 (purchased goods and services) — which is precisely what Tier 2 captures — accounts for 55–77% of total food retail Scope 3. By driving brands to certified Tier 2, MGS is not just consumer gamification — it is directly addressing the most material segment of retail's climate footprint.

---

## Sources and References

1. [GHG Protocol Corporate Value Chain (Scope 3) Standard](https://ghgprotocol.org/corporate-value-chain-scope-3-standard) — GHG Protocol, 2011
2. [Technical Guidance for Calculating Scope 3 Emissions](https://ghgprotocol.org/sites/default/files/standards/Scope3_Calculation_Guidance_0.pdf) — GHG Protocol
3. [WRAP Scope 3 Protocols for UK Food and Drink Businesses](https://www.wrap.ngo/system/files/2024-01/WRAP-Scope-3-Protocols-for-UK-Food-and-Drink-Businesses-full-draft-for-consultation-Jan-2024-v2.pdf) — WRAP, January 2024
4. [CDP Technical Note: Relevance of Scope 3 Categories by Sector](https://cdn.cdp.net/cdp-production/cms/guidance_docs/pdfs/000/003/504/original/CDP-technical-note-scope-3-relevance-by-sector.pdf) — CDP, 2022
5. [Poore & Nemecek (2018): Reducing food's environmental impacts through producers and consumers](https://www.science.org/doi/10.1126/science.aaq0216) — Science, Vol 360
6. [ISO 14067:2018 — Greenhouse gases — Carbon footprint of products](https://www.iso.org/standard/71206.html) — ISO
7. [GHG Protocol PAS 2050 Factsheet](https://ghgprotocol.org/sites/default/files/2022-12/GHG%20Protocol%20PAS%202050%20Factsheet.pdf) — GHG Protocol
8. [Guide to PAS 2050](https://www.wkcgroup.com/wp-content/uploads/2023/02/PAS-2050-Assessment-of-the-life-cycle-greenhouse-gas-emissions-of-goods-and-services.pdf) — Carbon Trust / Defra
9. [Retailers' road map to decarbonized value chains](https://www.mckinsey.com/capabilities/sustainability/our-insights/retailers-climate-road-map-charting-paths-to-decarbonized-value-chains) — McKinsey, July 2024
10. [WWF What's in Store for the Planet: UK Shopping Baskets 2022](https://www.wwf.org.uk/sites/default/files/2022-11/WWF-Whats-in-Store-for-our-Planet-the-Impact-of-UK%20Shopping-Baskets-on-Climate-and-Nature-2022-v1.pdf) — WWF-UK / Eunomia
11. [Oatly Climate Footprint Product Label](https://www.oatly.com/oatly-who/sustainability-plan/climate-footprint-product-label) — Oatly
12. [Quorn Carbon Footprint Page and Carbon Trust Report 2022](https://www.quorn.co.uk/carbon-footprint) — Quorn / Carbon Trust
13. [Foundation Earth Eco-Impact Labelling](https://www.theconsumergoodsforum.com/race-to-zero-hub-resources/foundation-earth-eco-impact-labelling/) — The Consumer Goods Forum, 2024
14. [The science behind spend-based emission factors](https://www.climatiq.io/blog/science-behind-spend-based-emission-factors) — Climatiq, December 2025
15. [Carbon footprint labels involving traffic lights foster sustainable food choices](https://www.sciencedirect.com/article/pii/S0950329323000071) — Ecological Economics, 2023
16. [M&S ESG Report 2024](https://corporate.marksandspencer.com/sites/marksandspencer/files/2024-06/ESG_Report_2024.pdf) — Marks & Spencer
17. [Mondra: The Future of Carbon Accounting in Food Retail](https://www.mondra.com/blog/carbon-is-not-just-a-number-the-future-of-carbon-accounting-software-in-food-retail) — Mondra, February 2026
18. [BRC Mondra Coalition for UK Food Retailers](https://fooddigital.com/retail/scope-3-uk-food-retailers-unite-to-tackle-ghg-emissions) — Food Digital, August 2024
19. [US EPA USEEIO Models and Supply Chain Emission Factors](https://www.epa.gov/land-research/us-environmentally-extended-input-output-useeio-models) — EPA
20. [Greenhouse Gas Reporting Conversion Factors 2025](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025) — UK Government (DESNZ), June 2025
21. [Carbon footprint data collection: challenges and solutions](https://www.carbon-direct.com/insights/carbon-footprint-data-collection-common-challenges-and-how-to-solve-them) — Carbon Direct, April 2025
22. [CarbonCloud ClimateHub: 10,000 food products](https://carboncloud.com/blog/climate-footprint-branded-food-usa/) — CarbonCloud, 2023
23. [ISO 14067: Carbon Footprinting Without the Checks](https://www.decerna.co.uk/knowledge-base/life-cycle-assessment/iso-standards/iso-14067/) — Decerna, 2025
24. [French Eco-Score Explained](https://www.vaayu.tech/insights/french-ecoscore-explained) — Vaayu, November 2025
25. [Carbon labels and rewards: driving sustainable consumer purchase behaviour](https://www.sciencedirect.com/article/pii/S2666188825009463) — ScienceDirect, 2025

---

*Research compiled March 2026 for My Green Squares (MGS). All data and references verified at time of compilation. Emission factors should be reviewed annually as Defra and WRAP update their databases.*
