# CO2e Normalisation Methods for My Green Squares (MGS)
## Research Report: Converting Diverse Sustainability Actions into 100g CO2e Units

**Prepared:** March 2026  
**Purpose:** Establish scientifically defensible emission factors and normalisation methodologies to underpin the Green Square (GS) as a universal micro-unit of sustainability, where 1 GS = 100g CO2e.

---

## Executive Summary

The Green Square concept — 1 GS = 100g CO2e — is achievable and scientifically defensible across all five target action categories, provided each conversion is grounded in recognised emission factor databases and methodology frameworks. This report sets out the specific emission factors, calculation approaches, and scientific basis for:

1. **Fossil-to-renewable energy transitions** — well-established, with excellent data quality
2. **Manufacturing process changes** — LCA-based, good data availability via ecoinvent/DEFRA
3. **Consumer purchasing behaviour** — viable with appropriate scope boundaries
4. **GHG Protocol Scope 3 categories** — all 15 categories convertible; data quality varies
5. **Land use / forestry / rewilding** — the MGS 1 kg CO2e/m² claim is scientifically defensible as an annual sequestration rate, but requires careful framing

The fundamental formula for all conversions is:

> **GS Awarded = CO2e Reduction (grams) ÷ 100**

---

## 1. Standard Databases and Methodologies

### 1.1 DEFRA/BEIS UK Greenhouse Gas Conversion Factors (2025)

Published annually by the UK Department for Energy Security and Net Zero, these are the gold standard for UK-based carbon accounting. The 2025 edition (using 2023 data) is the most current.

**Source:** [GOV.UK GHG Conversion Factors 2025](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025)

Key characteristics:
- Updated annually; 2025 edition uses 2023 GHGI/DUKES underlying data
- GWP values: CH4 = 28, N2O = 265 (AR5/UNFCCC-consistent)
- Covers electricity, fuels, transport, refrigerants, waste, water
- Includes Well-To-Tank (WTT) upstream emissions as separate factors
- Structured around Scope 1 (direct), Scope 2 (energy indirect), and Scope 3 (value chain)

### 1.2 US EPA Emission Factors Hub (2024/2025)

Equivalent US reference for organisational GHG reporting.

**Source:** [EPA GHG Emission Factors Hub](https://www.epa.gov/climateleadership/ghg-emission-factors-hub)

Key characteristics:
- Draws on EPA GHGRP, eGRID, and the US GHG Emissions Inventory
- Uses AR5 GWP values (CH4 = 28, N2O = 265)
- Key addition in 2025: grid gross loss percentages by eGRID subregion
- US average grid electricity: ~0.373 kgCO2e/kWh (823 lb CO2/MWh converted)

### 1.3 GHG Protocol Corporate Standard and Scope 3 Standard

The internationally accepted methodological framework.

**Sources:**
- [GHG Protocol Corporate Standard](https://ghgprotocol.org/corporate-value-chain-scope-3-standard)
- [Scope 3 Calculation Guidance](https://ghgprotocol.org/scope-3-calculation-guidance-2)

Five calculation methods supported:
1. **Supplier-specific** — highest accuracy; requires primary data from value chain partners
2. **Hybrid** — combines supplier-specific with secondary data for gaps (recommended best practice)
3. **Average-data (activity-based)** — uses physical quantities × average emission factors (kg CO2e/kg, per kWh, etc.)
4. **Spend-based** — uses economic value × industry average emission factors (kg CO2e/$)
5. **Fuel-based** — fuel type and quantity × combustion emission factors

For the MGS platform, the **average-data / activity-based** method is most suitable for creating pre-defined conversion rates per action type.

### 1.4 ecoinvent Database

The world's leading lifecycle assessment (LCA) database, used extensively in product carbon footprinting.

**Source:** [ecoinvent Database](https://ecoinvent.org/database/)

Key characteristics:
- Contains >26,000 datasets covering materials, energy, transport, waste, agriculture
- Version 3.9+ integrates IPCC 2021 characterisation factors
- Provides cradle-to-gate emission factors for raw materials and manufactured products
- Commonly referenced for manufacturing and material switching calculations
- Paid access required for full database; many secondary sources publish derived values

### 1.5 IPCC AR6 Lifecycle Emission Factors (2022)

**Source:** [IPCC AR6 WG3 Chapter 6](https://www.ipcc.ch/report/ar6/wg3/chapter/chapter-6/)

Harmonised median lifecycle emission factors from hundreds of peer-reviewed studies:

| Technology | Median (gCO2e/kWh) | Typical Range |
|---|---|---|
| Coal | 820 | 740–910 |
| Natural Gas (CCGT) | 490 | 410–650 |
| Oil/Gas peakers | 650 | — |
| Solar PV (utility) | 41 | 20–55 |
| Wind (onshore) | 11 | 7–15 |
| Wind (offshore) | 12 | 8–35 |
| Nuclear | 12 | 5–25 |
| Hydropower | 24 | 4–300+ |

### 1.6 ISO Standards for Carbon Accounting

| Standard | Scope | Relevance to MGS |
|---|---|---|
| **ISO 14064-1:2018** | Organisational GHG inventories (Scope 1, 2, 3) | Framework for overall platform carbon accounting |
| **ISO 14064-2:2019** | GHG reduction projects | Basis for verifying individual reduction actions |
| **ISO 14064-3:2019** | Verification and validation | Third-party assurance of GS claims |
| **ISO 14067:2018** | Product Carbon Footprint (PCF) | Basis for product-level GS assignments |
| **ISO 14040/44:2006** | Life Cycle Assessment (LCA) | Underpins manufacturing and material switches |

ISO 14067 is the standard most directly relevant to product-level CO2e assignment, as it mandates LCA-based calculation of carbon footprint per functional unit — directly enabling "1 unit of product X = Y Green Squares."

---

## 2. Fossil-to-Renewable Energy Transition

### 2.1 Core Emission Factors

The marginal emission reduction from switching from a fossil fuel to a renewable energy source is the difference between their lifecycle emission factors.

#### UK Grid Electricity (DEFRA 2025)
**Source:** [DEFRA 2025 GHG Methodology Paper](https://assets.publishing.service.gov.uk/media/6846b0870392ed9b784c0187/2025-GHG-CF-methodology-paper.pdf)

| Metric | Value |
|---|---|
| UK grid electricity (direct, 2023 data) | **0.209 kgCO2e/kWh** |
| UK grid electricity (incl. imports) | **0.196 kgCO2e/kWh** |
| T&D losses (Scope 3 upstream) | 0.020 kgCO2e/kWh |
| UK grid (15% lower than 2024 — decarbonisation trend) | Decreasing annually |

#### Fossil Fuel Combustion (DEFRA 2025)

| Fuel | kgCO2e/kWh (NCV) | kgCO2e/litre | Notes |
|---|---|---|---|
| Coal | ~0.34 | — | Combustion only |
| Natural Gas | ~0.20 | — | Combustion only |
| Diesel | ~0.27 | **2.65–2.68** | Combustion only |
| Petrol | ~0.25 | **2.22–2.39** | Combustion only |

*WTT (well-to-tank upstream) adds ~15–25% on top of direct combustion factors.*

#### US Equivalents (EPA 2024)

| Fuel | CO2 per unit |
|---|---|
| Motor Gasoline | 8.78 kgCO2/gallon |
| Diesel No. 2 | 10.21 kgCO2/gallon |
| US Grid Average | ~0.373 kgCO2e/kWh |

#### IPCC AR6 Lifecycle Factors (Global)

| Source | gCO2e/kWh | kgCO2e/kWh |
|---|---|---|
| Coal | **820–980** | 0.82–0.98 |
| Natural Gas | **450–500** | 0.45–0.50 |
| Solar PV (rooftop) | **40–50** | 0.04–0.05 |
| Wind (onshore) | **10–40** (median 11) | 0.011 |
| Nuclear | **5–20** (median 12) | 0.012 |
| Hydropower | **4–300+** (median 24) | 0.024 |

Sources: [EcoFlow lifecycle comparison](https://www.ecoflow.com/ca/blog/power-generation-emissions-by-source); [COWI comparison](https://www.cowi.com/news-and-press/news/2023/comparing-co2-emissions-from-different-energy-sources/)

### 2.2 Green Square Conversion: Energy Switching

**Formula:**  
`CO2e Saved (g) = kWh consumed × (EF_fossil − EF_renewable) × 1000`  
`Green Squares = CO2e Saved (g) ÷ 100`

#### Example Calculations

**Switching 1 kWh from UK grid to solar PV:**
- Grid: 0.209 kgCO2e/kWh
- Solar lifecycle: 0.045 kgCO2e/kWh
- Saving = 0.164 kgCO2e = 164g CO2e = **1.64 Green Squares per kWh**

**Switching 1 kWh from coal to wind:**
- Coal: 0.90 kgCO2e/kWh (lifecycle average)
- Wind: 0.011 kgCO2e/kWh (lifecycle)
- Saving = 0.889 kgCO2e = 889g CO2e = **8.89 Green Squares per kWh**

**Switching home heating from gas boiler to heat pump (UK):**
- Gas boiler: ~0.20 kgCO2e/kWh (gas combustion)
- Heat pump (on UK grid): 0.209/3.5 COP ≈ 0.060 kgCO2e/kWh heat delivered
- Saving ≈ 0.14 kgCO2e/kWh heat = **1.4 Green Squares per kWh heat**

**Installing 1 kW of rooftop solar in UK (annual basis):**
- Average UK solar yield: ~900 kWh/kW/year
- Annual saving: 900 × 0.164 = 148 kgCO2e/year = **1,476 Green Squares per kW per year**

### 2.3 Methodology Notes

- **Displacement vs. lifecycle:** MGS should decide whether to use combustion-only factors (simpler, higher reduction value) or full lifecycle factors (more rigorous, somewhat smaller delta). **Recommendation: Use lifecycle factors** for renewables to be conservative and defensible.
- **Grid decarbonisation:** UK grid emission factor is falling ~5–10% per year. MGS should use the DEFRA annual update and note the vintage in its methodology.
- **Additionality:** For renewable installations, DEFRA factors represent marginal avoided emissions from grid displacement, which is the appropriate baseline.

---

## 3. Manufacturing Process Changes

### 3.1 Packaging Material Switching

Lifecycle emission factors for packaging materials (cradle-to-gate, per kg of material):

| Material | kgCO2e/kg (virgin) | kgCO2e/kg (recycled) | Source |
|---|---|---|---|
| Virgin plastics (PET) | 2.5–3.0 | 0.23 (recycled) | EPA WARM, ecoinvent |
| Virgin plastics (HDPE) | 1.8–2.5 | 0.21 (recycled) | EPA WARM |
| Virgin plastics (PS) | 3.5 | — | EPA WARM |
| Cardboard / corrugated | 0.8–1.2 | 0.4–0.7 | FEFCO, ecoinvent |
| Corrugated board (2022 industry avg) | **0.491 (per kg)** | — | [FEFCO/CCB 2022](https://www.procarton.com/wp-content/uploads/2023/03/The-Carbon-Footprint-of-Carton-Packaging-2023_FINAL.pdf) |
| Glass (virgin) | 0.33 | 0.28 (-15% recycled) | Industry LCA |
| Aluminium (virgin) | 8–16 | 0.5 (recycled scrap) | International Aluminium |
| Steel (virgin) | 1.8–2.5 | 0.32 (recycled) | ecoinvent |

**Key insight from PlasticsEurope:** Replacing plastic packaging with alternatives (glass, metal, paper) increases total lifecycle GHG by a factor of ~2.7 on average, primarily because plastic packaging achieves the same functional unit with much less material mass. The relevant CO2e calculation must use a **functional unit** (e.g., "protect 1 litre of liquid") not raw kg-for-kg comparison.

Sources: [EcoHedge plastics factors](https://ecohedge.com/data/factors/plastics); [EcoHedge paper factors](https://ecohedge.com/data/factors/paper)

### 3.2 Supply Chain Logistics (Transport Mode Switching)

Emission factors by freight mode (kgCO2e per tonne-km):

| Mode | kgCO2e/tonne-km | gCO2e/tonne-km | Source |
|---|---|---|---|
| **Air freight** | 0.49–2.52 | 490–2,520 | DEFRA 2025 |
| **Air freight** (industry) | 1.054 | 1,054 | [Climate Action Accelerator](https://climateactionaccelerator.org/solutions/sea_freight/) |
| **Road (HGV, avg)** | 0.19 | 190 | DEFRA 2025 |
| **Road (LGV diesel)** | 0.64 | 640 | DEFRA 2025 |
| **Rail** | 0.016 | 16 | Industry average |
| **Sea (container)** | 0.003–0.019 | 3–19 | [Climatiq](https://www.climatiq.io/blog/accuracy-freight-emissions-calculations) |
| **Barge** | ~0.030 | 30 | Industry |

**Switching examples (per 1 tonne moved 1,000 km):**

| Switch | CO2e Saving | Green Squares |
|---|---|---|
| Air → Sea (1,000 km) | ~1,035 kgCO2e | 10,350 GS |
| Air → Road (1,000 km) | ~865 kgCO2e | 8,650 GS |
| Road → Rail (1,000 km) | ~174 kgCO2e | 1,740 GS |
| Road → Sea (1,000 km) | ~171–187 kgCO2e | 1,710–1,870 GS |

### 3.3 Manufacturing Process Improvements

Calculating CO2e from process changes follows ISO 14067 / GHG Protocol Product Standard:

**Steps:**
1. Define functional unit (e.g., "produce 1 kg of product X")
2. Calculate baseline cradle-to-gate emissions using ecoinvent or DEFRA/EPA factors
3. Calculate improved-process emissions using same system boundary
4. CO2e saving = baseline − improved = Green Squares ÷ 100

**Representative emission factors for common industrial processes:**

| Process / Material | CO2e | Unit | Source |
|---|---|---|---|
| Steel production (virgin) | 1.8–2.5 | kgCO2e/kg | ecoinvent |
| Aluminium (primary, global avg) | 8–16 | kgCO2e/kg | IEA/ecoinvent |
| Cement production | 0.6–0.9 | kgCO2e/kg | ecoinvent |
| Cotton textile (global avg) | 3–5 | kgCO2e/kg | ecoinvent |
| Electricity (UK 2023) | 0.209 | kgCO2e/kWh | DEFRA 2025 |
| Natural gas heating | 0.20 | kgCO2e/kWh | DEFRA 2025 |

**Waste reduction:**

| Waste material | Landfill EF | Recycling EF | Saving | Source |
|---|---|---|---|---|
| Food waste | 0.68 | (composting 0.11) | 0.57 tCO2e/tonne | EPA WARM |
| Mixed MSW | 0.58 | varies | varies | EPA WARM |
| PET plastic | 0.02 | 0.23 (saves vs production) | — | EPA WARM |

### 3.4 Product Carbon Footprint Methodology

For product-level GS assignment, **ISO 14067:2018** is the applicable standard. The GHG Protocol Product Life Cycle Standard provides equivalent guidance.

**Recommended workflow for MGS:**
1. Require manufacturers to provide ISO 14067-compliant PCF (cradle-to-grave or cradle-to-gate)
2. Accept ecoinvent-derived secondary factors as fallback for products without primary LCA data
3. Express GS as: `GS = PCF_baseline (gCO2e) − PCF_improved (gCO2e) ÷ 100` per functional unit

---

## 4. Consumer Purchasing Behaviour

### 4.1 Food Choices

Food product carbon footprints vary enormously. Data from Poore & Nemecek (2018) — the largest food LCA meta-analysis (38,700 farms, 119 countries) — provides the most comprehensive baseline.

| Food Product | kgCO2e/kg (global avg) | Green Squares per 100g |
|---|---|---|
| Beef (beef herd) | 60–100 | 60–100 |
| Lamb & mutton | ~24 | 24 |
| Prawns (farmed) | ~12 | 12 |
| Beef (dairy herd) | ~33 | 33 |
| Cheese | ~11 | 11 |
| Pork | ~7 | 7 |
| Poultry | ~6 | 6 |
| Eggs | ~5 | 5 |
| Rice | ~2.7 | 2.7 |
| Tofu | ~2.0 | 2 |
| Milk | ~1.6 | 1.6 |
| Tomatoes | ~0.7–2.1 | 0.7–2.1 |
| Vegetables (typical) | ~0.5–1.5 | 0.5–1.5 |
| Peas / legumes | ~1.0 | 1 |
| Nuts | ~1.4 | 1.4 |
| Avocados | ~2.5 | 2.5 |

Sources: [Our World in Data food emissions](https://ourworldindata.org/food-choice-vs-eating-local); [Statista food GHG emissions](https://www.statista.com/statistics/1201677/greenhouse-gas-emissions-of-major-food-products/)

**GS applications:**
- Switching from 200g beef to 200g chicken (one meal): saves ~(200×60/1000 − 200×6/1000) = ~10.8 kgCO2e = **108 Green Squares per meal**
- Switching from dairy milk to oat milk (200ml, ~0.2kg): saves ~(0.2×1.6 − 0.2×0.9) = ~0.14 kgCO2e = **1.4 Green Squares per glass**

### 4.2 Local vs. Imported Food

**Critical finding:** Transport typically accounts for only 6–10% of food's total lifecycle emissions. [Our World in Data analysis](https://ourworldindata.org/food-choice-vs-eating-local) shows that **what you eat matters far more than where it comes from** for most foods.

| Scenario | Transport EF | Share of total footprint |
|---|---|---|
| Beef shipped 9,000 km by sea | 0.21 kgCO2e/kg (0.35% of 60 kgCO2e/kg total) | ~0.35% |
| Avocados shipped 9,000 km | 0.21 kgCO2e/kg (8% of 2.5 kgCO2e/kg total) | ~8% |
| Air-freighted fresh produce | 1.054 kgCO2e/tonne-km | Up to 50% of total footprint |

**However:** A 2022 Nature Food study found food-miles emissions are 3.5–7.5x higher than previously thought for fruits and vegetables (which often require refrigerated transport). This makes local sourcing of fresh produce more significant than older estimates suggested. Source: [LettUs Grow summary](https://www.lettusgrow.com/blog/summary-nature-study-food-miles)

**MGS Recommendation:** For food purchasing actions, use product-level LCA data rather than transport-only factors. Assign GS to switching between product categories (e.g., meat to plant-based), not simply local vs. imported claims.

### 4.3 Electric vs. Fossil Fuel Delivery

| Vehicle Type | Emission Factor | Source |
|---|---|---|
| Diesel van (avg) | 255.8 gCO2e/vkm | DEFRA 2025 |
| Diesel van (Ford Transit) | 469 gCO2e/km (lifecycle) | Peer-reviewed LCA |
| Electric van (Ford E-Transit) | 363 gCO2e/km (lifecycle) | Same study |
| BEV delivery (UK grid charged) | ~80–120 gCO2e/km operational | Estimated |

**GS for switching delivery from diesel van to EV:**
- Per 100km delivery route: diesel saves ~(255.8 − ~100) × 100 = ~15,580g CO2e = **155.8 Green Squares per 100km route** (operational only)

**Note:** Lifecycle manufacturing emissions for EVs are ~10–14 tCO2e vs 6–9 tCO2e for ICE vehicles. EV emissions 'break even' after 30,000–50,000 km (UK grid), then provide ongoing savings.

### 4.4 Spend-Based Consumer Carbon

For broad consumer spending categories where product-level data is unavailable, EEIO (Environmentally-Extended Input-Output) spend-based factors can be used. These provide kg CO2e per $ (or £) of spend by sector:

| Sector (EEIO typical) | kgCO2e/$ spend |
|---|---|
| Food and beverage | ~0.25–0.45 |
| Clothing | ~0.25–0.35 |
| Electronics | ~0.10–0.25 |
| Services (professional) | ~0.05–0.15 |

These are coarse and carry ±30–50% uncertainty but are acceptable for initial screening and MGS consumer-facing products where precise LCA data is unavailable.

---

## 5. GHG Protocol Scope 3 — All 15 Categories

The Scope 3 Standard defines 15 categories. Each can be normalised to Green Squares using the same formula. Below is a summary of applicable methodologies and representative emission factors.

**Source:** [GHG Protocol Corporate Value Chain Standard (2011)](https://ghgprotocol.org/corporate-value-chain-scope-3-standard); [Technical Guidance for Calculating Scope 3 Emissions](https://ghgprotocol.org/scope-3-calculation-guidance-2)

### 5.1 Upstream Categories (1–8)

| Cat. | Name | Primary Methodology | Key Emission Factor Reference | GS Conversion Basis |
|---|---|---|---|---|
| **1** | Purchased Goods & Services | Average-data (kg × kgCO2e/kg) or Spend-based ($ × kgCO2e/$) | ecoinvent; EEIO databases (EPA, Exiobase) | Per kg of material switched; per $ shifted to lower-carbon supplier |
| **2** | Capital Goods | Average-data or Spend-based | EEIO; ecoinvent | Per unit of equipment procured (LCA-based) |
| **3** | Fuel & Energy Related Activities | Activity-based using WTT factors | DEFRA WTT factors; EPA upstream factors | Per kWh or litre; WTT addition ~15–25% |
| **4** | Upstream Transport & Distribution | Distance × weight × mode EF | DEFRA 2025 (kg CO2e/tkm); GLEC framework | Per tonne-km; mode-switching savings |
| **5** | Waste Generated in Operations | Waste type × disposal method EF | DEFRA waste factors; EPA WARM | Per kg diverted from landfill to recycling |
| **6** | Business Travel | Distance × mode EF; hotel nights | DEFRA 2025 transport factors | Per km flown/driven; per hotel night |
| **7** | Employee Commuting | Distance × mode EF | DEFRA 2025 transport factors | Per commuter km; mode switching |
| **8** | Upstream Leased Assets | Energy use × grid EF | DEFRA 2025 electricity factor | Per kWh consumed in leased space |

**Specific values for key categories:**

**Category 4 — Transport/Distribution (DEFRA 2025):**

| Mode | kgCO2e/tkm |
|---|---|
| HGV (all, 50% load) | 0.19 |
| LGV diesel | 0.64 |
| Air (long-haul) | 0.49 |
| Sea freight | 0.003–0.019 |

**Category 6 — Business Travel (DEFRA 2025):**

| Mode | gCO2e/pkm |
|---|---|
| Domestic flight | 124 |
| Short-haul flight | 69 |
| Long-haul flight | 83 (×1.7 RF multiplier for radiative forcing) |
| Average car (petrol) | 144 |
| Average car (diesel) | 165 |
| National Rail | ~35–41 |
| Local bus | 104 |

*GS example: One return London–Edinburgh flight (2 × 534 km) = ~2 × 534 × 0.069 kgCO2e/km × 1.7 RF = ~125 kgCO2e = **1,250 Green Squares per flight avoided***

**Category 5 — Waste (EPA WARM):**

| Material | Landfill (tCO2e/tonne) | Recycling (saving vs production) |
|---|---|---|
| Food waste | 0.68 | Composting: 0.11 |
| Mixed MSW | 0.58 | — |
| HDPE plastic | 0.02 (landfill) | 0.21 (recycled saves vs virgin) |
| Newspaper/paper | 0.39 | ~0.02 |

*GS: Diverting 1 tonne of food waste from landfill to composting saves ~0.57 tCO2e = 5,700 Green Squares. Per kg food waste composted: 0.57 kgCO2e = **5.7 Green Squares per kg***

### 5.2 Downstream Categories (9–15)

| Cat. | Name | Primary Methodology | Key Emission Factor Reference | GS Conversion Basis |
|---|---|---|---|---|
| **9** | Downstream Transport | Distance × weight × mode EF | DEFRA 2025; GLEC | Per tkm; same as Cat. 4 |
| **10** | Processing of Sold Products | LCA of downstream processing | ecoinvent | Per kg processed |
| **11** | Use of Sold Products | Units sold × lifetime energy use × grid EF | DEFRA/EPA grid factors | Per kWh saved over lifetime; per product efficiency improvement |
| **12** | End-of-Life Treatment | Waste material × disposal EF | DEFRA waste factors; EPA WARM | Per kg diverted from landfill |
| **13** | Downstream Leased Assets | Energy use × grid EF | DEFRA electricity factor | Per kWh |
| **14** | Franchises | Franchisee Scope 1+2 emissions | Franchisee GHG inventory | Per franchisee action |
| **15** | Investments | Investee Scope 1+2 emissions | EEIO; investee disclosures | Per investment decision |

**Category 11 — Use of Sold Products:**

This is typically the largest Scope 3 category for manufacturers of energy-consuming products (appliances, electronics, vehicles).

*Formula:*
```
Cat. 11 emissions = Σ (units sold × average lifetime uses × energy per use × grid EF)
```

*GS example: An A+++ washing machine vs. A-rated:*
- A-rated: 0.85 kWh/cycle
- A+++: 0.50 kWh/cycle
- Lifetime (500 cycles): saving = 500 × (0.85−0.50) × 0.209 kgCO2e = 36.6 kgCO2e
- **366 Green Squares per machine sold** (over its lifetime)

### 5.3 Data Quality Hierarchy for Scope 3

Per GHG Protocol guidance (and echoed in [Terrascope's methodology guide](https://www.terrascope.com/reports-guides/methods-of-calculating-scope-3-emissions)):

1. **Tier 1 (Best):** Primary data from suppliers/value chain partners (supplier-specific method)
2. **Tier 2:** Industry-specific LCA data from ecoinvent or published PCFs
3. **Tier 3:** Spend-based EEIO factors (lowest precision; use only as a last resort)

**Recommendation for MGS:** Clearly communicate uncertainty tiers to users. Label GS earned from Tier 1 data as "verified" and Tier 3 as "estimated."

---

## 6. Land Use, Forestry, and Nature-Based Solutions

### 6.1 Tropical Rainforest Carbon Storage

Understanding the distinction between **carbon stock** (stored) and **annual sequestration** (flow) is essential for defensible claims.

#### Carbon Stocks in Tropical Forests (Stored Carbon)

| Source | Carbon Stock | CO2e equivalent |
|---|---|---|
| IPCC AR4 Chapter 9 | 350–900 tCO2e/ha (forest stocks) | **3.5–9 kgCO2e/m²** |
| MIT Climate Portal (tropical moist) | 163.8 tC/ha (above + below ground) = **601 tCO2e/ha** | **60 kgCO2e/m²** |
| UNFCCC Tier 1 (tropical equatorial) | 250 tC/ha biomass = **917 tCO2e/ha** | **92 kgCO2e/m²** |
| Cool Earth | ≥200 tC/ha = **733 tCO2e/ha** | **73 kgCO2e/m²** |
| Rainforest Rescue | 120–400 tC/ha = **440–1,467 tCO2e/ha** | **44–147 kgCO2e/m²** |

Sources: [MIT Climate Portal forest carbon](https://climate.mit.edu/posts/supply-curve-forest-based-co2-removal); [Cool Earth carbon potential](https://www.coolearth.org/why-we-exist/why-rainforest/carbon-potential-of-rainforest/); [Rainforest Rescue carbon data](https://www.rainforest-rescue.org/topics/climate-and-the-rainforest/forests-and-soils)

#### Annual Sequestration Rate (Active Carbon Uptake)

| Source | Sequestration Rate | CO2e/m²/year |
|---|---|---|
| MIT Climate Portal (tropical moist) | 11 tCO2e/ha/year (3 tC/ha/year × 3.67) | **1.1 kgCO2e/m²/year** |
| IPCC AR4 (afforestation range) | 1–35 tCO2e/ha/year globally | 0.1–3.5 kgCO2e/m²/year |
| WRI Global Forest Watch | Net 7.6 GtCO2e/year from ~4 billion ha | ~1.9 kgCO2e/m²/year average |
| US EPA (US average forest) | 0.67 tC/ha/year = **2.46 tCO2e/ha/year** | 0.25 kgCO2e/m²/year |

Sources: [MIT climate portal supply curve](https://climate.mit.edu/posts/supply-curve-forest-based-co2-removal); [WRI forests carbon sink](https://www.wri.org/insights/forests-absorb-twice-much-carbon-they-emit-each-year); [EPA forest equivalencies](https://www.epa.gov/energy/greenhouse-gas-equivalencies-calculator-calculations-and-references)

### 6.2 Scientific Assessment of the MGS Claim: 1 kg CO2e per m²

**MGS current claim:** 10 GS = 1 m² of rainforest → 10 × 100g = **1,000g = 1 kg CO2e per m²**

This implies 10 tCO2e per hectare.

#### Assessment

| Interpretation | Scientific Basis | Verdict |
|---|---|---|
| **As annual sequestration** (1 kg CO2e/m²/year) | MIT tropical moist forest: 1.1 kgCO2e/m²/year | ✅ **Scientifically sound and conservative** |
| **As stored carbon stock** (one-time protection value) | Actual stored: 35–147 kgCO2e/m² | ⚠️ **Significantly undervalues forest by 35–147×** |
| **As REDD+ avoided emissions** (project-based) | Varies by project; typically 3–10 tCO2e/ha/year avoided | ✅ **In range; conservative** |

**Conclusion:** If the 1 kg CO2e/m² claim is presented as representing **annual carbon sequestration** or **annual avoided emission value** from protecting the forest from deforestation, it is scientifically defensible and conservative. However, it **should not be presented as the total stored carbon value** of that m² of forest, which is 35–150× larger.

#### Recommended Framing

> "Each square metre of protected tropical rainforest sequesters approximately 1 kg CO2e per year — equivalent to 10 Green Squares. This is based on MIT Climate Portal research showing tropical moist forests sequester ~11 tCO2e per hectare annually. Protecting 1 m² of rainforest from deforestation represents an ongoing annual carbon benefit, as the 200–917 tCO2e of carbon stored per hectare in that forest would otherwise be released if deforested."

### 6.3 Tree Planting

| Metric | Value | Source |
|---|---|---|
| CO2 sequestered per tree per year (global average) | **10–40 kgCO2/year** (median ~25 kg) | [EcoTree analysis](https://ecotree.green/en/how-much-co2-does-a-tree-absorb) |
| Tropical forest: CO2 per tree per year | ~18.3 kgCO2/tree/year | [MIT Climate Portal](https://climate.mit.edu/posts/supply-curve-forest-based-co2-removal) |
| CO2 stored in mature tropical tree (270 kgC/tree) | ~990 kgCO2 | MIT Climate Portal |

**GS from tree planting:**
- Planting 1 tree in tropical forest: ~18 kgCO2/year = **180 Green Squares per year**
- Over 30-year lifetime: ~540 kgCO2 = **5,400 lifetime Green Squares per tree**

### 6.4 Rewilding and Habitat Restoration

Carbon sequestration rates for different habitat types (tCO2e/ha/year):

| Habitat Type | Sequestration Rate | Notes | Source |
|---|---|---|---|
| Tropical forest (active growth) | 1–35 tCO2e/ha/year | Range; varies by age, species | IPCC AR4 |
| UK woodland (passive rewilding) | **7.3–12.6 tCO2e/ha/year** | Rothamsted 118yr data (2.0–3.44 tC/ha/yr × 3.67) | [LSE Grantham Institute](https://www.lse.ac.uk/granthaminstitute/wp-content/uploads/2023/11/Exploring-the-carbon-sequestration-potential-of-rewilding-in-the-UK.pdf) |
| Peatland restoration (boreal/temperate) | 0.5–3.4 tCO2e/ha/year (CO2 net sink) | After 5–20 year establishment | [PMC peatland restoration](https://pmc.ncbi.nlm.nih.gov/articles/PMC11068583/) |
| Degraded UK peatland (drained) | Emits 17.3 Mt CO2e/year from ~10% of UK land | Source; restoration abates emissions | LSE Grantham |
| Seagrass / blue carbon | 0.4–3.8 tCO2e/ha/year | High uncertainty | Literature |
| Grassland rewilding | 0.5–2.0 tCO2e/ha/year | Highly variable | Literature |

**GS from peatland restoration (UK):**
- Restoring 1 hectare of degraded peatland: ~1–5 tCO2e/year saved = **10,000–50,000 Green Squares per hectare per year**
- Per square metre: **1–5 Green Squares per m² per year** (this is higher than the tropical forest claim!)

### 6.5 Avoided Deforestation (REDD+)

The Verified Carbon Standard (Verra VCS) is the dominant framework for REDD+ carbon credits.

**Source:** [Verra VCS Program](https://verra.org/programs/verified-carbon-standard/)

- Each Verified Carbon Unit (VCU) = 1 tonne CO2e avoided or removed
- Projects must demonstrate additionality, permanence, and independent verification
- VM0048 (new 2023 REDD methodology) uses jurisdiction-level deforestation baselines

**Typical avoided deforestation values:**
- High-risk tropical forest: 5–20 tCO2e/ha/year of avoided emissions
- Average REDD+ projects: ~3–8 tCO2e/ha/year

*At 10 tCO2e/ha/year avoided:*  
`1 m² = 10,000 gCO2e/year = 100 Green Squares per m² per year`

This suggests the MGS claim of 10 GS per m² per year may actually be **significantly conservative** for high-risk avoided deforestation scenarios (where 100 GS/m²/year would be justified).

---

## 7. Synthesis: Building the 100g CO2e Universal Unit

### 7.1 The Core Normalisation Framework

Any sustainability action can be expressed as Green Squares using this general framework:

```
Step 1: Identify the activity and its measurable unit
         (e.g., kWh of energy, km of transport, kg of material, m² of land)

Step 2: Identify the baseline emission factor (EF_baseline)
         using DEFRA 2025 / EPA 2024 / ecoinvent / IPCC AR6

Step 3: Identify the improved scenario emission factor (EF_improved)
         using the same database and system boundaries

Step 4: CO2e saving = activity × (EF_baseline − EF_improved)
         expressed in grams of CO2e

Step 5: Green Squares = CO2e saving ÷ 100

Step 6: Apply a confidence/accuracy tier label
         (Tier 1 = verified; Tier 2 = industry average; Tier 3 = estimate)
```

### 7.2 Reference Table: Green Squares per Common Action

| Action | Unit | CO2e Saving | Green Squares |
|---|---|---|---|
| Switch 1 kWh: UK grid → solar PV | per kWh | 164g | **1.64 GS** |
| Switch 1 kWh: coal → wind (lifecycle) | per kWh | 889g | **8.89 GS** |
| Avoid 1 short-haul return flight (UK–Spain) | per trip | ~130–200 kgCO2e | **1,300–2,000 GS** |
| Avoid 1 domestic flight (Lon–Edinburgh) | per trip | ~62 kgCO2e | **620 GS** |
| Drive EV instead of petrol car (UK grid) | per 100km | ~14 kgCO2e | **140 GS** |
| Reduce 1 beef meal (200g) → chicken | per meal | ~10.8 kgCO2e | **108 GS** |
| Reduce 1 beef meal (200g) → lentils | per meal | ~11.7 kgCO2e | **117 GS** |
| Divert 1 kg food waste from landfill | per kg | ~570g | **5.7 GS** |
| Protect 1 m² tropical rainforest | per m²/year | ~1,000g (annual) | **10 GS/year** |
| Plant 1 tree (tropical, annual) | per tree/year | ~18,000g | **180 GS/year** |
| Switch packaging: 1 kg virgin plastic → recycled | per kg | ~2,000–3,000g | **20–30 GS/kg** |
| Ship 1 tonne 1,000km: air → sea | per consignment | ~1,035 kgCO2e | **10,350 GS** |
| Restore 1 m² UK peatland | per m²/year | ~100–500g | **1–5 GS/year** |
| Replace 1 diesel van delivery with EV (100km) | per delivery | ~15,580g | **155.8 GS** |
| Install 1 kW rooftop solar (UK, annual) | per year | 148 kgCO2e | **1,480 GS/year** |

### 7.3 Data Quality and Uncertainty

| Tier | Method | Uncertainty | Recommended Label |
|---|---|---|---|
| 1 | Primary data / supplier PCF / metered | ±5–15% | "Verified" |
| 2 | Industry LCA / ecoinvent / DEFRA defaults | ±15–30% | "Estimated (high confidence)" |
| 3 | EEIO spend-based / generic proxies | ±30–50% | "Estimated (indicative)" |

### 7.4 Boundary Consistency Rules for MGS

To prevent double-counting and ensure like-for-like comparisons, MGS should define consistent boundaries:

1. **System boundary:** Prefer lifecycle/well-to-grave for material and energy claims; at minimum, ensure upstream (WTT/cradle-to-gate) emissions are included — not just combustion-point factors.
2. **Baseline:** Always compare against a clearly defined counterfactual (e.g., "UK grid electricity in [year]" or "average UK diet").
3. **Additionality:** An action should only earn GS if it represents a genuine reduction *above* business-as-usual. Installing rooftop solar in 2026 earns GS against the current grid mix.
4. **GWP standard:** Use AR5 100-year GWPs (CH4=28, N2O=265) for consistency with DEFRA/EPA — do not mix AR4 and AR5 values.
5. **Temporal consistency:** Land-based sequestration claims (trees, forests) should specify the time period (annual rate vs. lifetime) to avoid over-claiming.

---

## 8. Key Sources and Databases

| Source | URL | Best Used For |
|---|---|---|
| DEFRA 2025 GHG Conversion Factors | https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025 | UK electricity, fuels, transport, waste |
| DEFRA 2025 Methodology Paper | https://assets.publishing.service.gov.uk/media/6846b0870392ed9b784c0187/2025-GHG-CF-methodology-paper.pdf | Technical basis for UK factors |
| EPA GHG Emission Factors Hub 2024 | https://www.epa.gov/climateleadership/ghg-emission-factors-hub | US fuels, electricity, waste |
| GHG Protocol Scope 3 Standard | https://ghgprotocol.org/corporate-value-chain-scope-3-standard | Framework for all 15 Scope 3 categories |
| GHG Protocol Scope 3 Calc. Guidance | https://ghgprotocol.org/scope-3-calculation-guidance-2 | Calculation methods by category |
| ecoinvent Database | https://ecoinvent.org/database/ | Manufacturing, materials, LCA |
| IPCC AR6 WG3 Chapter 6 | https://www.ipcc.ch/report/ar6/wg3/chapter/chapter-6/ | Global lifecycle electricity EFs |
| IPCC AR4 Forestry Chapter | https://www.ipcc.ch/site/assets/uploads/2018/02/ar4-wg3-chapter9-1.pdf | Forest carbon stocks and sequestration |
| ISO 14067:2018 | https://www.iso.org/obp/ui/en/ | Product Carbon Footprint standard |
| Verra VCS Program | https://verra.org/programs/verified-carbon-standard/ | REDD+ and nature-based carbon credits |
| Our World in Data — Food | https://ourworldindata.org/food-choice-vs-eating-local | Food product CO2e benchmarks |
| MIT Climate Portal — Forests | https://climate.mit.edu/posts/supply-curve-forest-based-co2-removal | Tropical forest carbon sequestration |
| WRI Global Forest Watch | https://www.wri.org/insights/forests-absorb-twice-much-carbon-they-emit-each-year | Forest carbon flux data |
| LSE Grantham Rewilding Report | https://www.lse.ac.uk/granthaminstitute/wp-content/uploads/2023/11/Exploring-the-carbon-sequestration-potential-of-rewilding-in-the-UK.pdf | UK rewilding carbon values |
| FEFCO Carton CO2 2023 | https://www.procarton.com/wp-content/uploads/2023/03/The-Carbon-Footprint-of-Carton-Packaging-2023_FINAL.pdf | Cardboard packaging CO2 |
| EcoHedge Materials Factors | https://ecohedge.com/data/factors/plastics | Plastic, paper emission factors |

---

## 9. Recommendations for MGS Platform

### 9.1 Immediate Actions

1. **Anchor the platform to DEFRA 2025 conversion factors** (updated annually) for all UK-based energy and transport calculations. Commit to annual updates.

2. **Register the forest claim correctly:** Present 10 GS = 1 m²/year as *annual carbon sequestration value*, not a one-time stock credit. Consider amending to 10 GS/m²/year with a clear note that the total forest carbon stock is worth many thousands of GS per m² — but is reported annually for consistency.

3. **Create a tiered emission factor library** built on DEFRA (UK), EPA (US), and ecoinvent — with clear tier labels (verified vs. estimated).

4. **For product-level GS** (manufactured goods), require or facilitate ISO 14067-compliant PCFs from brand partners. Use ecoinvent secondary data as fallback.

5. **Adopt the GHG Protocol Scope 3 framework** as the structural backbone for categorising partner actions — this ensures regulatory alignment as CSRD, SEC climate disclosures, and similar mandates expand.

### 9.2 Scientific Defensibility

The 100g CO2e unit is well-calibrated for consumer-scale actions:
- **Too small for single decisions:** One dietary switch per day generates ~5–100+ GS; one flight represents 600–2,000 GS — these ranges create meaningful engagement.
- **Appropriate for energy:** Switching to solar generates ~1.64 GS/kWh — a household using 3,000 kWh/year from solar earns ~4,920 GS annually, which is tangible and motivating.
- **Right scale for land:** At 10 GS/m²/year for tropical rainforest, protecting 1 hectare = 100,000 GS/year. This is a large but communicable number for corporate sponsors.

### 9.3 Key Risks to Flag

| Risk | Mitigation |
|---|---|
| Forest claim misunderstood as "total value" of m² | Always express as annual rate; provide clear explainer |
| Grid decarbonisation erodes energy GS values over time | Annual DEFRA factor updates are essential |
| Scope 3 data quality varies widely | Implement tier labelling; audit supplier claims |
| Food carbon claims contentious (methane GWP debates) | Use AR5 100yr GWP; cite Poore & Nemecek (2018) |
| Local vs. imported framing misleads on food | Emphasise product-type switching over provenance |
| Additionality challenges for common actions | Define BAU baseline explicitly in methodology documentation |

---

*End of research document. All emission factors sourced from publicly available, peer-reviewed, or government-published databases as cited throughout. Recommend peer review of this summary by a qualified carbon accountant prior to publication of MGS methodology.*
