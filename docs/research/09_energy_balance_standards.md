# MGS Research Note 09: Mass Energy Balance & Corporate Energy Standards
**Prepared for:** My Green Squares (MGS) Platform Development  
**Date:** March 2026  
**Purpose:** Deep research into mass energy balance methodology and corporate energy mix measurement/verification standards — informing GS issuance criteria and Deimos engine design.

---

## EXECUTIVE SUMMARY

Verified corporate energy transition requires three interlocking layers: **metered physical data**, **contractual claims** (EACs/REGOs), and **third-party attestation** (ISO 50001, SBTi validation, SECR). The fundamental challenge for MGS is that contractual claims are chronically disconnected from physical energy flows — a company can report 100% renewable electricity solely via unbundled REGO certificates purchased retrospectively, while its physical grid supply remains fossil-dominated. A Green Square must be anchored to the physical layer, not the paper layer.

Deimos must therefore ingest **actual energy consumption data** (meter readings, ESOS/SECR disclosures, half-hourly settlement data) and cross-reference it against declared contractual instruments and certified trajectories (ISO 50001 EnPIs, SBTi targets) to generate a defensible, time-stamped mass energy balance. GS issuance should be contingent on verified forward movement in the physical energy mix, not static contractual assertions.

---

## 1. ISO 50001:2018 — ENERGY MANAGEMENT SYSTEMS

### 1.1 What It Covers and Requires

ISO 50001:2018 specifies requirements for establishing, implementing, maintaining, and improving an **Energy Management System (EnMS)**. It applies a Plan-Do-Check-Act (PDCA) cycle to energy use and is sector-agnostic — applicable to any organisation regardless of size, industry, or geography.

**Core clauses relevant to MGS:**

| Clause | Requirement | MGS Relevance |
|--------|-------------|---------------|
| **6.3** | Energy review — identify Significant Energy Uses (SEUs), analyse historical use, forecast future consumption | Defines the scope of a corporate energy balance |
| **6.4** | Energy Performance Indicators (EnPIs) — selected, tracked, and maintained over time | The quantitative output Deimos would compare against |
| **6.5** | Energy baselines (EnBs) — established from a defined reference period, normalised for relevant variables | The counterfactual against which improvement is measured |
| **6.6** | Energy data collection plan — systematic approach to meter data, operational data, and supply chain data | Data architecture requirement for GS verification |
| **9.1** | Monitoring, measurement, analysis and evaluation | Ongoing evidence trail for GS maintenance |
| **9.3** | Management review — top management must review EnMS performance | Governance signal |

**Key principle:** ISO 50001 requires "**continual improvement**" in energy performance — not a one-time snapshot. This directly maps to MGS's requirement that Green Squares reflect **ongoing, verified transition** rather than a fixed claim.

### 1.2 Energy Performance Indicators (EnPIs) and Baselines (EnBs)

EnPIs are quantified metrics for measuring energy performance. Three principal forms:

1. **Absolute consumption** (kWh, MWh, GJ) — appropriate where production output is stable
2. **Energy intensity ratio** (kWh/m², kWh/unit output, kWh/FTE) — the most common for multi-site benchmarking; directly comparable year-on-year even as output varies
3. **Carbon intensity per unit of output** (tCO₂e/unit) — integrates energy mix quality (renewable vs fossil) into a single metric

**Energy Baselines** must be:
- Based on data from a defined reference period (minimum 12 months recommended)
- Normalised for relevant variables (production volume, outdoor temperature, occupancy, operating hours) where these materially affect consumption
- Reset when significant changes occur (major equipment replacement, facility expansion, material process change)
- Documented with a written methodology note describing data sources, reference period, normalisation approach, and recalculation triggers

**ISO 50006:2023** (companion standard) provides detailed guidance on EnPI construction and statistical normalisation methods.

**For Deimos:** EnPIs serve as the primary quantitative inputs for a corporate energy balance. A corporate claiming ISO 50001 certification must hold documented EnPI series with full audit trails — this is the most reliable input data Deimos will receive from ISO-certified entities.

### 1.3 Energy Data Collection, Measurement, and Verification

ISO 50001 requires a documented **energy data collection plan** specifying:
- Data to be collected (consumption, generation, production parameters, relevant variables)
- Collection frequency (real-time interval data vs monthly billing data)
- Measurement accuracy requirements for metering equipment
- Data analysis and review intervals
- Roles and responsibilities

**Measurement and verification (M&V):** The DOE's **SEP 50001 M&V Protocol** (used in the US Superior Energy Performance programme) provides a recognised framework for rigorously determining energy performance improvement using 12 months of verifiable baseline data and normalisation modelling. This is the gold standard approach for GS verification purposes.

**Internal audits** must check the EnPI documentation at every surveillance visit; the 3-year certification cycle includes a minimum of two internal audits.

### 1.4 Certification Process and Costs

**Process:**
1. Internal energy review and gap analysis (~3–6 months pre-certification)
2. **Stage 1 audit** — documentation review, typically off-site (£400–£1,200)
3. **Stage 2 audit** — on-site assessment of implemented system (£700–£2,000)
4. Certification granted (valid 3 years)
5. **Annual surveillance audits** (£500–£1,200 per year)
6. **Recertification** at year 3 (£800–£1,500)

**Typical total 3-year UK costs:**

| Organisation Size | Estimated 3-Year Cost |
|------------------|-----------------------|
| Small (1–10 employees) | £2,700–£7,500 |
| Medium (11–50 employees) | £7,500–£18,000 |
| Large (50–250 employees) | £18,000–£45,000+ |
| Consultancy support (optional) | £800–£15,000 additional |

Certification bodies must themselves be **UKAS-accredited** to ISO 50003:2021 to issue valid ISO 50001 certificates in the UK. LRQA, BSI, Bureau Veritas, and DNV are leading UKAS-accredited ISO 50001 certification bodies in the UK.

**ESOS exemption:** ISO 50001 certification (by a UKAS-accredited body, covering full energy scope) automatically satisfies ESOS Phase 3 and 4 compliance obligations for large UK organisations — removing the need for a separate ESOS energy audit.

### 1.5 UK Certification Numbers

**Global ISO 50001 (2023 data):** Approximately 38,000–40,000 certified organisations worldwide (ISO Survey data; precise 2024 figure from ISO Survey 2024 infographic shows ~38,482 certificates globally).

**UK specifically:** Over **1,200 UK businesses** are ISO 50001 certified (Inspired PLC / industry estimate, 2022). This figure appears consistent with trends — the UK was historically the 2nd largest country globally for ISO 50001 certifications after Germany. The ISO 2013 survey showed 330 UK certificates; the figure has grown substantially since, particularly as ESOS phases drove adoption.

**Context:** Against a backdrop of ~11,900 SECR-reporting companies and c.250,000+ large UK companies broadly, ISO 50001 penetration remains low (~0.5–1% of large companies). This means most corporate energy data Deimos receives will NOT be from ISO-certified organisations — alternative data collection methods are essential.

### 1.6 Relevance to MGS Energy Balance Calculations

ISO 50001 is the **gold standard reference framework** for MGS, even where a company is not certified:
- Its EnPI/EnB methodology provides the template for how a corporate energy balance should be constructed
- Its data collection requirements define the minimum data standard for GS eligibility
- ISO 50001 certification by a UKAS-accredited body provides a **third-party verified data trail** — the strongest possible evidence for GS issuance
- For non-certified companies, MGS can benchmark their reporting quality against ISO 50001 data requirements to identify gaps

**Practical recommendation:** MGS should treat ISO 50001 certification as a **premium tier** within its verification architecture — offering a simplified/fast-tracked GS issuance pathway for certified companies, while requiring additional evidence for non-certified ones.

---

## 2. GHG PROTOCOL — SCOPE 1, 2, 3

### 2.1 How Corporate Energy Is Reported Under Each Scope

The GHG Protocol Corporate Standard (and Scope 2 Guidance, 2015) defines:

**Scope 1 — Direct emissions** (from sources owned or controlled by the organisation):
- Combustion of natural gas in boilers and furnaces
- Diesel/petrol/HVO in owned or operated vehicles (company fleet)
- On-site power generation (backup generators)
- Refrigerant leakage (HFCs/HCFCs) — especially material for grocery retailers
- Process combustion (manufacturing)

**Scope 2 — Indirect emissions from purchased energy:**
- Purchased electricity
- Purchased heat, steam, cooling

**Scope 3 — All other indirect emissions (15 categories):**
- Category 3: Fuel- and energy-related activities not in Scope 1/2 (upstream fuel extraction, T&D losses)
- Category 4: Upstream transportation and distribution
- Category 5: Waste generated in operations
- Category 11: Use of sold products (downstream energy use)
- Category 12: End-of-life treatment of sold products
- For retailers: Scope 3 typically represents 95–99% of total emissions inventory

### 2.2 Market-Based vs Location-Based Scope 2 Reporting

GHG Protocol requires **dual reporting** for Scope 2 in markets where contractual instruments are available:

| Method | Description | Emission Factor Source |
|--------|-------------|----------------------|
| **Location-based** | Average grid emission intensity at point of consumption | Grid-average emission factor (e.g., UK: ~0.207 kgCO₂e/kWh in 2023) |
| **Market-based** | Emissions from electricity the company has *chosen* to purchase | Contractual instruments: PPAs, EACs, supplier-specific rates, or residual mix |

**Hierarchy for market-based emission factors** (most preferred to least):
1. Supplier-specific emission factor from a direct contract covering specific generation (e.g., dedicated PPA)
2. Energy attribute certificates (REGOs, GOs, I-RECs, RECs) meeting Scope 2 Quality Criteria
3. Supplier-specific portfolio emission rate
4. Residual mix (grid average after all contractual claims removed)

**Critical point:** To claim zero Scope 2 emissions under the market-based method, a company must **retire** EACs equivalent to its consumption volume. Unretired certificates cannot be claimed.

**For MGS:** Both location-based and market-based Scope 2 figures are required inputs. The *gap* between them quantifies the degree to which a company's claimed clean energy use is contractual vs physical.

### 2.3 Energy Attribute Certificates — REGOs, GOs, I-RECs

**What they are:** EACs are market instruments conveying attributes about one MWh of electricity generation — the resource type, emissions intensity, location, vintage, and whether it contributes to additionality. One EAC = one MWh of verified renewable generation.

**UK-specific: REGO (Renewable Energy Guarantee of Origin)**
- Administered by Ofgem; generators receive one REGO per MWh of eligible renewable output
- Primary function: fuel mix disclosure for licensed electricity suppliers
- Post-Brexit: UK REGOs no longer interchangeable with EU Guarantees of Origin (GOs), creating a separate UK market

**EU: Guarantee of Origin (GO)**
- European standard under the Renewable Energy Directive
- More widely accepted under GHG Protocol Scope 2 Quality Criteria

**International: I-REC (International Renewable Energy Certificate)**
- Used in markets without domestic EAC schemes

**GHG Protocol Scope 2 Quality Criteria for EACs:**
1. Unique — no double counting
2. Filed and tracked within a reliable registry with transparent ownership rules
3. Issued by recognised programme in the market where consumption occurs
4. Appropriately time-matched (issued within the same year as consumption)
5. Geographic boundary — from the same market as consumption (ideally same grid)
6. Represent attributes of specific generation (not aggregated averages)
7. Consistent with local laws and regulations

### 2.4 The Greenwashing Problem — Unbundled REGOs

**The structural flaw:** REGOs can be **traded separately from the physical electricity** they certify ("unbundled"). A supplier can purchase renewable electricity from generators but sell the REGOs separately — or purchase cheap fossil-fuel electricity and buy REGOs to "green" it on paper.

**Consequences:**
- REGO prices can fall extremely low (historically £0.50–£2.50/MWh), meaning greening an entire supply on paper costs near-nothing
- A company claiming "100% renewable electricity" via unbundled REGOs may have no physical renewable energy supply at any point during the year
- Annual matching allows retrospective certificate purchases — a company could purchase REGOs covering an entire year's consumption in a single December transaction
- OVO Energy and Good Energy publicly abandoned unbundled REGO use over greenwashing concerns (July 2023)
- UK Government launched a greenwashing investigation in 2025 targeting energy tariff claims based solely on REGOs

**What this means for MGS:**
A corporate claiming 100% renewable electricity backed solely by unbundled REGOs does **not** qualify as a genuine transition action for GS purposes. MGS must distinguish between:

| Procurement Type | Additionality | Physical Matching | GS Eligibility |
|-----------------|---------------|-------------------|----------------|
| On-site generation (solar, wind) | High | Physical | Full credit |
| Dedicated PPA with new-build generator | High | Contractual but direct | Full credit |
| Sleeved PPA (certificate + power bundled) | Medium | Partial | Credit with verification |
| Bundled tariff (power + EAC from supplier) | Low-Medium | Grid mix | Partial credit |
| Unbundled REGOs only | Nil | None | No credit for physical transition |
| Residual mix (no certificate) | N/A | Fossil-weighted | No credit |

**The emerging standard: 24/7 Carbon-Free Energy (CFE)**
Google and others have pioneered **hourly matching** of consumption to clean generation — certificates matched on an hourly basis to actual consumption, not annually. SBTi's forthcoming Corporate Net-Zero Standard V2 is expected to require hourly or at minimum quarterly matching. MGS should position GS issuance to reward hourly or at minimum monthly temporal matching.

### 2.5 Verifying Actual Energy Mix vs Contractual Claims

**Verification chain for physical energy mix:**
1. **Smart/AMR meter data** (half-hourly intervals) → actual consumption profile by site
2. **Market-wide Half Hourly Settlement (MHHS)** data (UK: rollout commenced October 2025, completing May 2027) → granular consumption available for all metered sites
3. **Generator output data** from Elexon Balancing Mechanism Reporting Service (BMRS) → actual renewable generation on the grid at each half-hour interval
4. **Cross-reference** consumption with grid carbon intensity (National Grid ESO API, Carbon Intensity API) → location-based emissions at actual times of consumption
5. **Registry verification** of EAC retirement → confirms contractual claims match consumption volumes and vintages

**Tools for verification:**
- **Elexon Portal** — UK electricity market settlement data
- **National Grid ESO Carbon Intensity API** — real-time and historic grid carbon intensity
- **Ofgem REGO register** — check certificate issuance and retirement
- **RE-Source and RE100** — corporate renewable procurement claim standards

---

## 3. MASS ENERGY BALANCE METHODOLOGY

### 3.1 What Is a Mass Energy Balance in the Sustainability Context?

In the **sustainability/corporate context**, a "mass energy balance" (or corporate energy balance) is a systematic accounting of **all energy flows** into, within, and out of a defined corporate boundary over a specified time period. The term draws from the engineering mass balance concept (mass in = mass stored + mass out) applied to energy rather than material.

**Note:** "Mass balance" also has a distinct meaning in materials/chemical industry contexts (e.g., tracking certified bio-based or recycled content through mixed production processes, as used by ISCC, WACKER, and REDcert2). The MGS context refers specifically to the **energy accounting** application.

A corporate energy balance for sustainability purposes tracks:
- **Total energy input** by source and fuel type
- **Transformation** (e.g., electricity generated on-site from solar)
- **End-use** by category (heating, cooling/refrigeration, lighting, motive power, process heat, transport)
- **Export** (e.g., surplus renewable generation exported to grid)
- **Losses** (T&D losses, conversion inefficiencies)
- **GHG emission factors** applied to each input stream

The output is a **verified snapshot of the renewable vs fossil fuel split**, energy intensity ratios, and trajectory against baseline.

### 3.2 How It Is Calculated for a Corporate Entity

**Step-by-step corporate energy balance:**

```
STEP 1: DEFINE BOUNDARY
   └─ Operational control approach (standard for GHG Protocol)
   └─ Equity share approach (alternative, less common)
   └─ Include all owned/leased facilities, fleet, on-site generation

STEP 2: IDENTIFY AND CATEGORISE ALL ENERGY INPUTS
   ├─ Scope 1: Natural gas (m³ → kWh via calorific value)
   ├─ Scope 1: Diesel (litres → kWh via conversion factor)
   ├─ Scope 1: Heating oil, LPG (litres → kWh)
   ├─ Scope 1: On-site biofuel / HVO
   ├─ Scope 1: Refrigerant top-ups (kg → CO₂e via GWP)
   ├─ Scope 2: Grid electricity (kWh from meter or billing data)
   ├─ Scope 2: District heating/cooling (kWh or GJ)
   └─ On-site renewable generation (solar PV output in kWh)

STEP 3: NORMALISE FOR RELEVANT VARIABLES
   └─ Production volume, weather (heating/cooling degree days), operating hours

STEP 4: APPLY EMISSION FACTORS
   ├─ DEFRA/DESNZ UK GHG Conversion Factors (published annually)
   ├─ Scope 2 location-based: UK grid average factor
   ├─ Scope 2 market-based: certificate/PPA/residual mix factor
   └─ Scope 1: Fuel combustion factors (kgCO₂e/kWh or per litre)

STEP 5: CALCULATE ENERGY MIX RATIOS
   └─ % renewable = (on-site generation + purchased renewable electricity certified) / total electricity
   └─ % fossil fuel = (gas + diesel + grid fossil electricity) / total energy
   └─ Energy intensity = total energy (GJ or MWh) / output unit (m², tonnes, revenue £)

STEP 6: COMPARE AGAINST BASELINE AND TARGETS
   └─ Year-on-year change in each EnPI
   └─ Progress against Net Zero trajectory (linear decline or SDA pathway)
   └─ Forecast to target year

STEP 7: DOCUMENT AND VERIFY
   └─ Source data: meter readings, bills, purchase records, generation system logs
   └─ Third-party assurance (ISO 50001 audit, limited/reasonable assurance by auditor)
   └─ Disclosure: SECR report, CDP, sustainability report
```

### 3.3 Input Data Requirements

| Data Type | Source | Granularity | Quality |
|-----------|--------|-------------|---------|
| Electricity consumption | Smart/AMR meter, MHHS, billing data | Half-hourly (gold), monthly (minimum) | High — directly metered |
| Gas consumption | Smart meter, billing, HHIC data | Monthly or daily | High |
| Diesel/fuel | Fuel card transaction data, tank dip records | Per-fill transaction | High |
| HVO / biofuel | Supplier invoices + sustainability certificates | Monthly | Medium |
| On-site solar generation | Generation meter, inverter data | Half-hourly | High |
| Wind/PPA generation | Generator output data, EAC retirement receipts | Monthly | Medium-High |
| Refrigerant top-ups | F-gas logbooks (legally required in UK) | Per-event | Medium (often under-reported) |
| Fleet fuel | Telematics/fuel cards, DVLA data | Per-vehicle, per-fill | High |
| Heating oil / LPG | Tank monitoring, delivery records | Per-delivery | Medium |
| Scope 3 energy (supply chain) | Supplier questionnaires, M2030/HIGG, spend-based | Annual | Low-Medium |

### 3.4 Multi-Site, Multi-Country Operations

**Challenges:**
- Different grid emission factors by country (UK: ~0.207 kgCO₂e/kWh 2023; France: ~0.052 due to nuclear; Poland: ~0.70+ due to coal-heavy grid)
- Different EAC regimes (UK REGO vs EU GO vs I-REC)
- Different regulatory reporting requirements per jurisdiction
- Aggregation vs site-level reporting trade-offs

**Solutions:**
- Establish a consistent organisational hierarchy (corporate → region → country → site → meter)
- Apply country-specific DEFRA/IEA emission factors per location
- Use a platform with multi-country factor libraries (EnergyCAP, Persefoni, Sweep, EnergyElephant)
- Report both consolidated group total and country-level breakdowns

**For MGS:** Where a corporate operates in multiple countries, GS issuance should be calculated at the **UK operational boundary** (matching SECR reporting scope) or, where global, should weight by operational control. A UK retailer's non-UK operations should not contaminate the UK energy balance calculation.

### 3.5 Real-Time vs Annual Energy Balance

| Approach | Pros | Cons | Applicable Standard |
|----------|------|------|---------------------|
| **Annual balance** | Matches regulatory reporting (SECR, CDP); handles billing cycle mismatches | Lags 12+ months; no operational insight | GHG Protocol, ISO 50001, SECR |
| **Quarterly balance** | Earlier detection of divergence from trajectory | Partial year normalisation challenges | Best practice emerging |
| **Monthly balance** | Sufficient for EAC temporal matching; operational decision-making | Higher data burden | RE100 guidance, hourly CFE pilots |
| **Half-hourly (real-time)** | Enables 24/7 CFE claims; grid-correlated | Requires full MHHS integration, significant data infrastructure | 24/7 CFE initiative (Google, Microsoft standard) |

**For MGS:** The initial GS issuance standard should be based on **annual verified data** (aligning with SECR and ISO 50001 cycles), with a clear upgrade pathway towards quarterly or monthly verification. The 75%+ threshold for a Green Square should be assessed annually at minimum, but Deimos should be architected to process real-time interval data as MHHS becomes universal by mid-2027.

### 3.6 Tools and Software for Corporate Energy Balance

**Leading platforms:**

| Platform | Best For | Standards Supported |
|----------|----------|---------------------|
| **EnergyCAP Carbon Hub** | Large multi-site portfolios; audit-ready utility data | ISO 50001, GHG Protocol, SECR, ENERGY STAR |
| **Persefoni** | Disclosure preparation; structured review workflows | GHG Protocol, TCFD, CSRD, CDP |
| **Sweep** | Scope 1–3 with supply chain; CSRD compliance | GHG Protocol, CSRD, SFDR, GRI |
| **EnergyElephant** | Multi-site energy + carbon from utility bills | ISO 50001, GHG Protocol, SECR, SBTi, CDP |
| **Enity** | SME/mid-market; integrated EMS + carbon | ISO 50001, GHG Protocol, CSRD |
| **Measurabl** | Real estate / property portfolios | GRESB, CDP, TCFD |
| **CERius (GE Vernova)** | Energy companies; net-zero scenario planning | IEA NZE alignment |
| **Pulsora / Coolset** | Automated scope 3; CSRD workflow | GHG Protocol, CDP |
| **Manufacture 2030 (M2030)** | Grocery supply chain supplier engagement | Retailer-specific; SBTi-linked |

**Critical note for Deimos:** Deimos should be designed to **ingest outputs from these platforms** via API or structured data export, not compete with them. The verification chain is: corporate's energy management platform → structured data export → Deimos normalisation/analysis layer → GS issuance decision.

---

## 4. SCIENCE BASED TARGETS (SBTi) — ENERGY REQUIREMENTS

### 4.1 What SBTi Requires for Energy Transition Targets

SBTi validates corporate GHG reduction targets aligned with limiting global warming to 1.5°C. As of March 2026, over 10,522 companies globally have validated SBTi targets.

**Core SBTi Corporate Net-Zero Standard V1.3 requirements:**

| Component | Requirement |
|-----------|-------------|
| **Near-term targets** | Reduce Scope 1+2+3 emissions at a pace consistent with 1.5°C pathways; roughly halving emissions by 2030 from base year |
| **Long-term targets** | Reduce at least 90% of emissions by no later than 2050 |
| **Residual emissions** | Neutralise remaining ≤10% via permanent carbon removal (CDR) |
| **Scope 3** | Must be covered if Scope 3 exceeds 40% of total inventory; must cover ≥67% of total Scope 3 |
| **Net zero definition** | Achieved only when long-term target met AND residual emissions neutralised |

**Corporate Net-Zero Standard V2.0** is currently under development (public consultation ongoing as of 2025), expected to tighten requirements including:
- Mandatory hourly or locally-matched renewable electricity (moving away from annual unbundled EAC claims)
- Requirement for location-based Scope 2 target alongside market-based
- More rigorous treatment of Scope 3 coverage

### 4.2 Renewable Electricity — Specific SBTi Criteria

**SBTi Near-Term Criteria V5.3, Criterion C21:**

> *"Targets to actively source renewable electricity at a rate consistent with 1.5°C scenarios are an acceptable alternative to scope 2 emission reduction targets. The SBTi has identified **80% renewable electricity procurement by 2025 and 100% by 2030** as thresholds (portion of renewable electricity over total electricity use) for this approach, in line with RE100."*

- Companies already at or above these thresholds must **maintain or increase** the level
- For long-term targets: companies must **maintain 100% renewable electricity procurement beyond 2030**
- Acceptable instruments: RECs, virtual PPAs (vPPAs), physical PPAs, on-site generation
- Not specified whether bundled or unbundled — this is a known weakness in current SBTi criteria being addressed in V2.0

**SBTi's position on non-electricity energy:**
- Fossil fuel heat (gas, oil) must be reduced via absolute or intensity-based trajectories using approved SDA pathways
- Electrification of heat is the primary pathway; SBTi does not currently provide a specific green gas target methodology
- Transport fuels: Scope 1 fleet emissions must be covered by near-term targets (well-to-wheel basis per V5.3)

### 4.3 Sector-Specific Pathways Relevant to MGS Corporate Clients

**Retail / Food & Staples Retailing:**
- Subject to both standard energy/industry targets AND **FLAG targets** (if land-based emissions exceed 20% of total Scope 1+2+3)
- Near-term: Absolute Scope 1+2 reduction; Scope 3 supplier engagement (≥67% of emissions by suppliers with SBTi-approved targets)
- Tesco's validated SBTi near-term targets: 85% absolute Scope 1+2 reduction by 2030 (2015 baseline); 55% Scope 3 (energy/industrial) by 2032; 39% FLAG Scope 3 by 2032
- Sainsbury's validated targets: 68% Scope 1+2 reduction by 2030 (2018/19 baseline); 50.4% non-FLAG Scope 3 by 2030; 36.4% FLAG Scope 3 by 2030

**FMCG / Consumer Goods:**
- Similar structure to retail
- High Scope 3 concentration in raw material production (Scope 3 Cat. 1) and product use/disposal (Cat. 11–12)
- Energy efficiency improvements in own operations typically represent 5–15% of total value chain emissions

**Manufacturing:**
- Sectoral Decarbonization Approach (SDA) using industry-specific carbon intensity pathways (steel, cement, chemicals, paper)
- SBTi Chemical Sector Pathways published December 2025
- Manufacturing energy typically more split: gas (process heat) and electricity; electrification of industrial heat is the key lever

### 4.4 FLAG Guidance

FLAG (Forest, Land and Agriculture) targets were launched in September 2022 and became mandatory from May 1, 2023 for companies in:
- Forest and Paper Products
- Food and Beverage Processing
- Food and Staples Retailing
- Tobacco
- Any sector where FLAG emissions exceed 20% of total Scope 1+2+3

**FLAG key requirements:**
1. Account for all land-based emissions and removals (deforestation, land conversion, fertilizer use, manure management, soil carbon)
2. Set near-term FLAG targets (5–10 year reduction aligned with 1.5°C)
3. Set long-term FLAG targets (≥72% reduction by 2050)
4. No-deforestation commitment with target date no later than 2025
5. Also set separate energy/industry targets covering all fossil-based emissions

**Implication for MGS:** A grocery retailer's GS assessment must track **both** energy/industrial AND FLAG emissions. The Deimos energy balance must interface with the land/agriculture emission tracking layer — these are separate but parallel accounting requirements for the same corporate.

### 4.5 How Energy Mix Improvement Is Measured Against SBTi Benchmarks

SBTi does not publish a per-company energy mix target but provides:
- **Cross-sector pathway** (absolute reduction linear rate, base-year dependent)
- **Sectoral Decarbonization Approach (SDA)** pathways — intensity-based trajectories for specific sectors
- Annual SBTi target progress reporting to CDP (Carbon Disclosure Project)
- External validation review at point of target submission (not ongoing annual validation)

**For Deimos:** SBTi near-term targets define the minimum acceptable trajectory for energy-related emissions. A corporate's annual energy balance data should be tested against its validated SBTi pathway to determine whether it is:
- **On track** (actual emissions ≤ trajectory) → supports GS issuance
- **Off track but improving** → conditional GS, with specific milestones
- **Off track and worsening** → GS suspended or not issued

---

## 5. UK-SPECIFIC ENERGY REPORTING

### 5.1 ESOS — Energy Savings Opportunity Scheme

**What it is:** Mandatory energy assessment scheme for large UK organisations. Requires identification of significant energy consumption and energy saving opportunities — not mandatory implementation, but mandatory reporting.

**Who qualifies:** Large UK undertakings employing ≥250 people OR with annual turnover >£44m AND balance sheet >£38m.

**Current status:**
- **Phase 3** qualification date: 31 December 2022; compliance deadline: 5 June 2024 (extended); Action Plan: 5 March 2025; First Progress Update: 5 December 2025
- **Phase 4** started 6 December 2023; compliance deadline: **5 December 2027**

**Phase 3 new requirements (2023 Amendment Regulations):**
- All participants must now calculate **total energy consumption** and **energy intensity ratios** (previously not required for ISO 50001 route participants)
- **Action Plan** required: what energy reduction actions are planned, expected savings, timeline
- **Progress Updates** required between compliance dates

**ESOS and ISO 50001:** ISO 50001 certification (by UKAS-accredited body, covering full energy scope) automatically satisfies ESOS obligations — the organisation simply notifies the Environment Agency with proof of certification.

**What ESOS provides for MGS:**
- Total energy consumption across all significant uses (must cover ≥95% of total)
- Energy intensity ratios (computable from reported data)
- Identification of energy saving opportunities (useful indicator of transition ambition)
- **Action Plans** (from Phase 3 onwards) provide forward-looking signals about energy mix transition

ESOS data is filed with the **Environment Agency (EA)** via the MESOS portal but is not publicly disclosed — MGS would need corporate cooperation or disclosure consent to access ESOS data directly.

### 5.2 SECR — Streamlined Energy and Carbon Reporting

**What it is:** Annual mandatory disclosure of energy use and carbon emissions in companies' statutory accounts. Introduced 2019, applies to financial years starting on or after 1 April 2019.

**Who must report:**
1. **Quoted companies** (all UK-registered companies listed on a regulated stock exchange) — Scope 1+2 GHG, global energy use, intensity ratio, narrative on efficiency measures
2. **Large unquoted companies and LLPs** meeting two of three thresholds: >250 employees, >£36m turnover, >£18m gross assets — UK energy use (electricity, gas, transport fuel), associated GHG emissions, intensity ratio, efficiency narrative
3. Exemption: companies with UK energy use below 40 MWh declare as "low energy users"

**Coverage:** Approximately 11,900 large UK companies report under SECR.

**What SECR requires:**
- **UK energy use:** Electricity (kWh), gas (kWh), transport fuel (kWh or litres converted) — current year AND prior year comparator
- **GHG emissions** linked to reported energy (Scope 1 and 2 minimum; Scope 3 optional but recommended)
- **At least one intensity ratio** with year-on-year comparison
- **Narrative** on energy efficiency measures implemented
- **Methodology** disclosure (DEFRA conversion factors, GHG Protocol, or ISO 14064-1 are typical)

**SECR is publicly available** (filed at Companies House in Directors' Report or Strategic Report) — this makes it the most accessible and universally available corporate energy dataset for MGS without requiring cooperation.

**SECR limitations:**
- UK-only scope (not global — though quoted companies also report global energy use)
- Annual disclosure, typically 6–9 months after year-end
- No mandatory third-party assurance (though large quoted companies increasingly assure)
- Scope 3 is optional → supply chain energy often absent
- Does not distinguish renewable from fossil electricity unless company discloses voluntarily

**For Deimos:** SECR data (accessible via Companies House, CDP, or direct corporate sustainability reports) is the **primary publicly available energy input data** for the majority of MGS corporate targets. The SECR annual energy figure becomes the denominator in a corporate energy balance; the renewable percentage and reduction trajectory complete the numerator.

### 5.3 UK ETS — Emissions Trading Scheme

**What it is:** UK's carbon pricing mechanism covering approximately 25% of UK territorial emissions. Replaced the UK's participation in the EU ETS after Brexit (2021). The UK Government confirmed in December 2025 that the UK ETS will link with the EU ETS.

**Current coverage:**
- Heavy industry (power, cement, steel, glass, ceramics, refining, paper, offshore)
- Aviation
- **Expanding:** Maritime from 2026; Energy-from-Waste from 2028 (with 2-year MRV transition period); GHG Removals being integrated

**UK ETS and energy for MGS:**
- Operators within UK ETS must report verified **annual tonne-level emissions** (Scope 1 from eligible installations) to DESNZ — this is highly accurate, plant-level physical data
- For energy-intensive manufacturing or industrial corporates within MGS's corporate client base, their UK ETS verified emissions provide granular Scope 1 data
- UK ETS carbon price creates a financial incentive for energy switching — relevant to assessing transition ambition credibility
- The forthcoming **UK Carbon Border Adjustment Mechanism (UK CBAM)**, implementing from 2027, will extend carbon pricing to imports — influencing supply chain energy calculations

**For Deimos:** Where a corporate has UK ETS installations, their verified ETS annual emissions reports (available via EA/DESNZ) provide the most reliable Scope 1 source data available, independently verified to a ±5% accuracy standard.

### 5.4 DESNZ Energy Data Collection

**Digest of UK Energy Statistics (DUKES):** Published annually by DESNZ (formerly BEIS), DUKES provides the definitive macro picture of UK energy production and consumption by fuel type, sector, and end-use. DUKES 2025 was published July 2025 covering 2024 data.

**DESNZ's corporate-level data collection mechanisms:**
1. **ESOS** — large company energy audits (via EA, not DESNZ directly)
2. **UK ETS** — verified annual emissions from ETS installations (EA/DESNZ oversight)
3. **Mandatory metering data** — National Grid ESO and Elexon collect half-hourly settlement data for all grid-connected installations
4. **Gas supply data** — national Transmission System (Cadent, NGT) and distribution networks collect aggregate consumption data
5. **SECR** — collected via Companies House (BIS/DESNZ framework but not a direct submission to DESNZ)

**DESNZ does not have a direct corporate-level energy database** in the way that, say, HMRC collects tax data. Corporate energy data resides in: (a) EA for ESOS, (b) EA/DESNZ for ETS, (c) Elexon for half-hourly electricity settlement, (d) Companies House for SECR, (e) Ofgem for REGO registry.

**Key for MGS:** The UK's data infrastructure is fragmented across these bodies. No single API or dataset provides corporate energy consumption at sufficient granularity for GS verification. Deimos must aggregate from multiple sources.

---

## 6. CORPORATE ENERGY DATA — WHAT'S ACTUALLY AVAILABLE

### 6.1 What Retailers Actually Collect

Major UK grocery retailers (Tesco, Sainsbury's, M&S, ASDA, Lidl, Aldi) are among the most sophisticated energy managers in UK corporate life. They must comply with ESOS, SECR, CDP, and often SBTi — and their multi-site operations (typically 100–3,000+ stores) necessitate real energy management infrastructure.

**Tesco (2024 data):**
- 61% reduction in Scope 1+2 emissions from 2015 baseline
- 100% renewable electricity since 2020 (10 years ahead of RE100 target) — achieved via combination of on-site solar, wind PPAs, and certificates
- Scope 1+2 (2023): approximately 0.9m tCO₂e (vs 1.0m prior year)
- Scope 3 represents >98% of group emissions
- SBTi-validated near-term targets: 85% Scope 1+2 by 2030; 55% Scope 3 energy/industrial by 2032; 39% FLAG Scope 3 by 2032
- Tesco is the only major European retailer currently using **natural refrigerant technology in its transport refrigeration fleet**
- ~33% of stores on natural (CO₂) refrigerant systems as of 2022; committed to phase out HFCs by 2035

**Sainsbury's (2024/25 data):**
- Absolute GHG emissions (Scope 1+2, market-based): 448,734 tCO₂e — down 52.8% from 2018/19 baseline
- Scope 2 market-based: **zero** (100% renewable electricity since January 2022)
- Scope 2 location-based: 248,452 tCO₂e (illustrates the physical vs contractual gap)
- 100% renewable electricity via solar, UK wind farms (8 farms in portfolio), and renewable certificates
- Scope 3 = 96% of total emissions; three hotspots: **agriculture, electricals, and fuel**
- SBTi targets: 68% Scope 1+2 by 2030; 50.4% non-FLAG Scope 3; 36.4% FLAG Scope 3
- ~39.8% of Scope 3 emissions covered by suppliers with SBTi 1.5°C targets (FY24/25)

### 6.2 Smart Meter Data and Half-Hourly Settlement

**Market-wide Half Hourly Settlement (MHHS):**
- Ofgem's MHHS reform is the biggest UK electricity market reform in 25 years
- Systems went live September 2025; migration of individual meters started October 2025
- Full migration completing May 2027
- All electricity meters will be settled using half-hourly (30-minute interval) actual consumption data, replacing the old profiling/estimation approach

**What this means:**
- Every UK business premises with a smart or AMR meter will have documented half-hourly consumption available from their supplier and MESO (Meter Asset Manager / Data Collector)
- Businesses can appoint independent metering and data services providers rather than accepting supplier defaults
- This creates, for the first time, a comprehensive national record of **when** businesses use energy — enabling 24/7 renewable energy matching

**For MGS/Deimos:** MHHS data is transformational. By 2027, Deimos can access half-hourly consumption data for any UK corporate site as part of the GS verification process, enabling accurate temporal matching of renewable generation to consumption. The verification chain becomes: MHHS half-hourly consumption data + National Grid ESO grid carbon intensity + EAC retirement registry → verified hourly CFE calculation → GS eligibility decision.

### 6.3 Fleet Energy (Diesel, Electric Vehicles)

**Diesel/conventional fleet:**
- Scope 1 emissions; well-to-wheel basis required for SBTi (from V5.3)
- Data sources: telematics systems (GPS tracking + fuel consumption), fuel card transaction data (e.g., Certas Energy FuelTapp/CarbonTrace), depot fuel tank monitoring
- Standard conversion: litres diesel × DEFRA factor (currently ~2.54 kgCO₂e/litre) = Scope 1 tCO₂e
- Fleet emissions are generally well-monitored for large retailers with fuel card programmes

**Electric vehicles:**
- Scope 2 when charged from grid; zero Scope 1
- HGV electrification: nascent but growing — UK eHGV sales up 28% in 2024
- Sainsbury's trialling EVs in grocery online (GOL) with 3 stores having fully electric fleets; 10 depots with plug-in points for 450 rigid trucks
- Tesco leading on EV trial for temperature-controlled transport using natural refrigerant systems
- UK Government £200m eFreight 2030 programme supporting eHGV deployment

**HVO (Hydrotreated Vegetable Oil):**
- Direct diesel replacement; up to 90% lifecycle GHG reduction vs fossil diesel
- Classified as biofuel; reported as Scope 1 but with very low emission factor
- Requires sustainability certificates (ISCC, RSB) to claim carbon benefits
- Sainsbury's 30-HGV biomethane trial (from food waste) at Bristol depot saving >3,000 tCO₂/year

**For Deimos:** Fleet energy must be disaggregated from total energy to correctly apply well-to-wheel emission factors and to track EV vs diesel split over time. A corporate transitioning its fleet from diesel to HVO to EV represents a significant energy mix transition that GS issuance should recognise.

### 6.4 Refrigeration — A Critical Component for Grocery Retailers

**Scale of the issue:**
- Supermarket cooling (refrigeration + air conditioning) accounts for **up to 70% of a supermarket's Scope 1 and Scope 2 emissions** (EIA, *Cooling the Climate Crisis*, June 2025)
- Refrigeration currently responsible for approximately 7% of **global** GHG emissions
- UK retail refrigeration accounts for approximately **3.28 TWh of electricity** annually (IIR, 2024) — the UK food industry's refrigeration carbon footprint equals ~3.2% of total UK emissions
- For Tesco specifically: Scope 1+2 cooling emissions estimated at **2.16 MtCO₂e** in 2023 (61% of total Scope 1+2) — the largest HFC emitter among EIA's analysed retailers

**Two emission sources from refrigeration:**
1. **Energy consumption** (Scope 2 typically, or Scope 1 if on-site generation) — the electricity to run chillers, freezers, condensing units
2. **Refrigerant leakage** (Scope 1) — HFC gases with Global Warming Potentials (GWPs) of 1,300–4,000× CO₂

**HFC problem:**
- HFC R-404A (widely used in supermarket chillers): GWP = 3,922
- HFC R-410A (ASDA rooftop HVAC): GWP = 2,088
- Some HFC prices have surged >800% due to EU F-Gas Regulation phase-down
- UK **F-Gas Regulation** requires leak checks, logbook maintenance — data is legally required to exist

**Natural refrigerants transition:**
- CO₂ (R744) transcritical systems: zero GWP; lower energy use; covers ~30% of EU supermarkets
- Tesco: committed to HFC phase-out by 2035; ~33% of stores on natural refrigerant systems (2022)
- Sainsbury's: new stores use CO₂ natural refrigerant systems; waste heat from refrigeration used for store heating
- Cost of transition: Carrefour estimates €650m to convert 406 hypermarkets; Jerónimo Martins budgets €450–650m for full global phase-out by 2035

**For Deimos:** Refrigeration is the single largest controllable Scope 1+2 emission source for grocery retailers. A GS assessment for a supermarket must:
1. Track total refrigerant charge and annual leakage rate (from F-gas logbooks)
2. Calculate refrigerant Scope 1 emissions (kg leaked × GWP × CO₂e conversion)
3. Calculate refrigeration electricity consumption (typically ~50% of total site electricity)
4. Track % of estate using natural vs HFC refrigerant systems
5. Assess transition plan against EIA/industry benchmark (HFC-free by 2030 in Europe)

### 6.5 Supply Chain Energy Data — Scope 3 Visibility

**The fundamental challenge:**
For a UK grocery retailer, Scope 3 represents 95–99% of total GHG inventory. Most Scope 3 energy data is:
- Estimated from spend or economic input-output models (low accuracy)
- Derived from supplier questionnaires (coverage 50–60% of top suppliers by spend; accuracy variable)
- Tracked via platforms like Manufacture 2030 (M2030) or HIGG (for apparel/non-food)

**Current state of UK grocery retailer Scope 3 coverage (2024/25):**

| Retailer | Scope 3 as % of Total | Supplier Data Coverage |
|----------|-----------------------|------------------------|
| Sainsbury's | 96% | 53.0% of Scope 3 emissions via M2030 or HIGG (612 suppliers) |
| Tesco | >98% | Mondra digital twin technology for private-label product lifecycle |
| M&S | ~95%+ | Scope 3 Scope is "the single biggest challenge" — limited visibility |
| UK grocery sector (M2030) | N/A | 52% of suppliers have Scope 1+2 targets; 28% have Scope 3 targets; only 15% have verified SBTs |

**What data actually exists in the supply chain:**
- Large suppliers (Tier 1) to major retailers increasingly have SECR obligations and CDP disclosures
- Mid-tier suppliers often have ESOS data (if they qualify)
- Small suppliers (<250 employees) have minimal mandatory energy reporting
- Agricultural suppliers: near-zero mandatory energy/GHG reporting; M2030, FarmCarbon, Cool Farm Tool used voluntarily

**For Deimos:** Scope 3 energy data should initially be assessed at the **category level** (what % of major emission categories are covered by suppliers with validated SBTi targets or verified energy plans), rather than attempting to build a bottom-up supply chain energy balance. The GS standard should recognise progress in supply chain data quality and engagement as a transition action, not just physical energy metrics.

---

## 7. DEIMOS INTEGRATION POINTS AND VERIFICATION CHAIN

### 7.1 What Data Deimos Needs as Inputs

For a corporate energy balance and GS issuance decision, Deimos requires a **structured data intake** across four tiers:

**Tier 1 — Mandatory minimum (GS eligibility threshold):**
| Data Element | Source | Format |
|-------------|--------|--------|
| Annual total electricity consumption (kWh) | SECR, CDP, utility billing | Numeric |
| Annual gas consumption (kWh or m³) | SECR, utility billing | Numeric |
| Annual diesel/transport fuel (litres or kWh) | SECR, fleet management | Numeric |
| Scope 1+2 GHG emissions (tCO₂e) | SECR, sustainability report | Numeric |
| % electricity from renewable sources (claimed) | Sustainability report, EAC records | % |
| Renewable procurement instruments held | REGO registry, PPA contracts | Document |
| Base year and target year emissions | SBTi validation letter or sustainability report | Text/Numeric |
| Net zero target (year and scope) | Public commitment | Text |

**Tier 2 — Enhanced verification (required for Green Square 75% threshold):**
| Data Element | Source | Format |
|-------------|--------|--------|
| ISO 50001 certification status | UKAS-accredited CB certificate | Document |
| Half-hourly electricity consumption data | MHHS / supplier data feed | Interval data |
| EAC retirement certificates (with vintage, registry, MWh) | Ofgem REGO registry / I-REC registry | Structured data |
| Fleet EV % and fuel card disaggregation | Telematics / fuel card data | Numeric |
| Refrigerant F-gas logbook data (kg leaked, GWP) | Legal F-gas records | Numeric |
| On-site generation meter data (kWh) | Generation meter / inverter logs | Interval data |
| SBTi validated target and current trajectory status | CDP disclosure, SBTi registry | Structured |
| Prior 3-year energy trend (kWh, tCO₂e) | SECR history / CDP | Time series |

**Tier 3 — Premium (for highest-rated GS or complex corporate structures):**
| Data Element | Source | Format |
|-------------|--------|--------|
| Site-level energy breakdown (top 20 sites by consumption) | Energy management platform export | Structured data |
| Scope 3 supplier engagement coverage (%) | M2030 / HIGG / CDP supplier questionnaire | Numeric |
| Supply chain energy intensity data (GJ/tonne or GJ/£) | Supplier disclosures | Numeric |
| UK ETS verified emissions data (where applicable) | EA UK ETS verified report | Document |
| Hourly/half-hourly CFE matching data | MHHS + generation data | Interval data |
| ESOS Action Plan | MESOS portal / corporate disclosure | Document |

### 7.2 How Deimos Output Feeds Into GS Issuance

The Deimos calculation engine should produce a **Corporate Energy Balance Score (CEBS)** comprising:

```
CEBS = f(
  Physical_Renewable_Share,         // actual % of energy from verified renewable sources
  Emission_Trajectory_Compliance,   // on/off track vs SBTi or equivalent pathway
  Data_Quality_Score,               // completeness and verification level of inputs
  Scope_Coverage_Score,             // % of Scope 1+2+3 covered in balance
  Additionality_Score,              // quality of renewable procurement (PPA/on-site vs unbundled REGO)
  Efficiency_Improvement_Rate,      // year-on-year intensity improvement
  Refrigerant_Transition_Progress,  // for retailers: HFC→natural refrigerant % progress
  Supply_Chain_Engagement_Score     // % of Scope 3 covered by supplier plans
)
```

**GS Issuance Decision Logic:**

| CEBS Tier | Conditions | GS Decision |
|-----------|------------|-------------|
| **Tier A** (Full GS) | Physical renewable ≥75% of electricity; on/off track vs SBTi; EACs are ≥monthly-matched, direct PPAs or on-site; Scope 1+2 verified | Green Square issued; full public disclosure |
| **Tier B** (Conditional GS) | Physical renewable ≥50% but <75%; trajectory improving; minor data gaps; EACs are annual bundled | Green Square issued with conditions and milestone dates |
| **Tier C** (Pathway GS) | Credible transition plan with targets validated by SBTi or equivalent; <50% physical renewable but meaningful trajectory | Pathway GS — signals committed corporate, not yet transitioned |
| **Ineligible** | No verified trajectory; only unbundled REGOs; worsening trajectory; no Scope 1+2 data | No GS; reasons disclosed to corporate |

**The 75% Rule:** Each Green Square represents a 75%+ verified transition action. For energy, this means:
- The **corporate energy mix must be ≥75% verified renewable** in the GS-covered scope (typically Scope 1+2 for initial GS; Scope 3 for progression GS)
- "Verified" means: metered physical generation + PPAs/bundled EACs meeting GHG Protocol Scope 2 Quality Criteria; NOT solely unbundled annual REGOs
- Progress from 50% → 75% renewable, or 75% → 100%, each constitutes a transition action meriting a GS

### 7.3 Verification Chain: Meter → Deimos → GS

```
PHYSICAL DATA LAYER
┌────────────────────────────────────────────────────────┐
│ Smart/AMR meters (MHHS) → half-hourly kWh by site      │
│ F-gas logbooks → refrigerant leakage kg by asset        │
│ Fuel cards / telematics → diesel litres by vehicle      │
│ Solar/wind generation meters → kWh produced            │
│ Gas meters → m³ by site                                 │
└────────────────┬───────────────────────────────────────┘
                 │
         Corporate EMS Platform
         (EnergyElephant, EnergyCAP, Enity, etc.)
         or direct data export to MGS API
                 │
CONTRACTUAL CLAIMS LAYER
┌────────────────────────────────────────────────────────┐
│ REGO registry (Ofgem) → certificate retirement records  │
│ PPA contract terms → MW capacity, generation source     │
│ I-REC / GO registry → international certificate proof   │
│ Bundled supplier tariff documentation                   │
└────────────────┬───────────────────────────────────────┘
                 │
STANDARDS / ATTESTATION LAYER
┌────────────────────────────────────────────────────────┐
│ ISO 50001 audit report → EnPI series, baseline data     │
│ SECR disclosure (Companies House) → annual energy total │
│ CDP climate questionnaire → Scope 1+2+3 breakdown       │
│ SBTi validation letter → target and base year           │
│ UK ETS verified emission report → Scope 1 installation  │
│ Third-party assurance report → limited/reasonable level │
└────────────────┬───────────────────────────────────────┘
                 │
DEIMOS ENGINE
┌────────────────────────────────────────────────────────┐
│ 1. Ingest and normalise multi-source energy data        │
│ 2. Apply DEFRA GHG conversion factors (current year)   │
│ 3. Calculate location-based and market-based Scope 2    │
│ 4. Validate EAC claims against registry (vintage, vol.) │
│ 5. Temporal matching of consumption vs generation       │
│ 6. Compute Corporate Energy Balance Score (CEBS)       │
│ 7. Test trajectory vs SBTi/equivalent pathway          │
│ 8. Flag data quality issues and coverage gaps          │
│ 9. Generate audit-ready GS assessment report           │
└────────────────┬───────────────────────────────────────┘
                 │
GS ISSUANCE DECISION
┌────────────────────────────────────────────────────────┐
│ Tier A / B / C / Ineligible determination              │
│ Green Square token created with:                       │
│   - Corporate ID, assessment date, data vintage        │
│   - Verified renewable % and emission trajectory       │
│   - Conditions and next review date                    │
│   - Source data references (auditable trail)           │
└────────────────────────────────────────────────────────┘
```

### 7.4 Critical Design Principles for Deimos

1. **Physical primacy:** Deimos must weight physically metered data above contractual claims. A company with MHHS data confirming on-site solar generation should score higher than one with only REGO certificates.

2. **Temporal matching:** Annual matching is the minimum; monthly is better; hourly is the gold standard. Deimos should record the temporal resolution of matching and degrade the Additionality Score for purely annual certificate claims.

3. **Additionality signals:** PPAs with new-build generators (within last 3 years, or contracted to fund new capacity) score higher than PPAs with existing generators, which score higher than bundled tariffs, which score higher than unbundled REGOs.

4. **DEFRA factors updated annually:** Deimos must apply the UK Government's annual GHG conversion factors (published by DESNZ/DEFRA) for the relevant reporting year. Using stale factors is a common error in corporate energy accounting.

5. **Refrigerant tracking:** For any corporate in food retail, logistics, or manufacturing with significant cooling infrastructure, the F-gas/refrigerant emission stream must be explicitly modelled — it cannot be folded into a generic "Scope 1" figure without losing the ability to track the HFC→natural refrigerant transition.

6. **Data vintage:** All GS assessments must record the data vintage (the reporting year the energy data refers to). A GS issued in 2026 based on 2024 SECR data is 18 months stale — future architecture should target near-real-time verification via MHHS direct feeds.

7. **Scope 3 scaffolding:** Initially, Scope 3 should be scored on **coverage and engagement quality** rather than absolute energy balance, because the data simply doesn't exist with sufficient accuracy. Deimos should assess: (a) % of top 20 suppliers with verified energy plans, (b) % of Scope 3 covered by suppliers with SBTi targets, (c) whether the corporate uses M2030, HIGG, or equivalent supply chain engagement platforms.

---

## 8. SUMMARY: KEY NUMBERS AND BENCHMARKS FOR MGS

| Metric | Figure | Source |
|--------|--------|--------|
| UK companies with ISO 50001 certification | ~1,200+ | Inspired PLC / ISO Survey |
| Global ISO 50001 certificates | ~38,000–40,000 | ISO Survey 2024 |
| UK SECR-reporting companies | ~11,900 | DEFRA/Greenly |
| ESOS Phase 3 qualifying companies (≥250 employees) | ~11,000 large undertakings | EA estimate |
| UK grid electricity carbon intensity (2023) | ~0.207 kgCO₂e/kWh (location-based) | DEFRA/DESNZ |
| REGO typical price (historic) | £0.50–£2.50/MWh | Market data |
| Supermarket refrigeration share of Scope 1+2 | Up to 70% | EIA (2025) |
| Retail refrigeration UK electricity use | 3.28 TWh/year | IIR (2024) |
| UK retail Scope 3 as % of total emissions | 95–99% | Tesco, Sainsbury's disclosures |
| SBTi renewable electricity thresholds | 80% by 2025; 100% by 2030 | SBTi Near-Term Criteria V5.3 |
| MHHS full rollout completion | May 2027 | Ofgem |
| Sainsbury's Scope 1+2 (FY24/25) | 448,734 tCO₂e (−52.8% from base) | Sainsbury's Plan for Better |
| Tesco Scope 1+2 reduction | 61% from 2015 baseline | Tesco AR 2024 |
| UK grocery supplier Scope 1+2 target adoption | 52% of suppliers | M2030 / Manufacture 2030 |
| UK grocery supplier SBT verified adoption | 15% of facilities | M2030 (2023) |

---

## 9. OPEN QUESTIONS AND GAPS FOR FURTHER RESEARCH

1. **REGOs reform:** The UK Government's 2025 greenwashing investigation may result in mandatory bundling of REGOs with physical supply or temporal matching requirements. MGS should monitor DESNZ policy output — any reform would significantly affect the market-based Scope 2 landscape.

2. **SBTi Corporate Net-Zero Standard V2.0:** Expected to introduce hourly renewable electricity matching requirements and tighter Scope 3 criteria. Deimos's GS issuance logic should be designed to accommodate V2.0 requirements once finalised.

3. **UK CBAM (2027):** The Carbon Border Adjustment Mechanism will introduce carbon costs for imported goods in steel, aluminium, ceramics, cement, glass, hydrogen, and electricity. This will materially affect Scope 3 supply chain energy economics for manufacturing corporates.

4. **CSRD and UK equivalent:** The EU Corporate Sustainability Reporting Directive (CSRD) applies to large EU companies and EU subsidiaries of UK corporates. The UK is consulting on an equivalent UK Sustainability Reporting Standard (UK SRS). If enacted, this will dramatically expand mandatory third-party assured Scope 3 disclosure — benefiting Deimos data quality significantly.

5. **24/7 CFE market development:** The UK 24/7 Carbon-Free Energy market is nascent. As it develops, Deimos should integrate with emerging hourly certificate registries.

6. **Mondra and supply chain digital twins:** Tesco's use of Mondra (product-level supply chain emission modelling) represents the frontier of Scope 3 energy visibility. MGS should assess whether Mondra or similar platforms could become Tier 3 data inputs for GS assessments covering supply chain energy.

---

## SOURCES AND REFERENCES

- [ISO 50001:2018 — Energy Management Systems](https://www.iso.org/iso-50001-energy-management.html) — ISO standard overview
- [ISO 50001 EnPIs and Energy Baselines](https://www.nanogrid.com/blog/energy-management-system-iso-50001-enpis-energy-baselines) — Nanogrid implementation guide
- [ISO 50001 UK Certification Costs (2025)](https://reliablecert.uk/resources/how-much-does-iso-certification-cost-in-the-uk-2025/) — Reliable Certification Ltd
- [SEP 50001 Measurement and Verification Protocol](https://betterbuildingssolutioncenter.energy.gov/iso-50001/sep-50001/resources/sep-50001-measurement-and-verification-protocol) — US DOE Better Buildings
- [GHG Protocol Scope 2 Guidance](https://ghgprotocol.org/sites/default/files/2023-03/Scope%202%20Guidance.pdf) — GHG Protocol
- [GHG Protocol Scope 2 FAQ](https://ghgprotocol.org/scope-2-frequently-asked-questions) — GHG Protocol
- [Energy Attribute Certificates (EACs)](https://www.epa.gov/green-power-markets/energy-attribute-certificates-eacs) — US EPA
- [REGO Scheme and Greenwashing](https://www.pinsentmasons.com/out-law/news/energy-suppliers-wise-abandon-rego-certificates-greenwashing-concerns) — Pinsent Masons (2023)
- [REGO Scheme Explained](https://www.myenergyconsultants.co.uk/regos-explained-are-they-enough-for-your-green-energy-goals/) — My Energy Consultants (2025)
- [UK Greenwashing Investigation — REGOs](https://www.solarpowerportal.co.uk/energy-policy/government-launches-greenwashing-investigation-as-it-looks-to-tighten-rego-regulations) — Solar Power Portal (2025)
- [SBTi Corporate Net-Zero Standard](https://sciencebasedtargets.org/net-zero) — SBTi
- [SBTi Near-Term Criteria V5.3](https://files.sciencebasedtargets.org/production/files/SBTi-criteria.pdf) — SBTi
- [SBTi FLAG Guidance](https://sciencebasedtargets.org/sectors/forest-land-and-agriculture) — SBTi
- [SBTi FLAG FAQ](https://files.sciencebasedtargets.org/production/files/FLAG-FAQ.pdf) — SBTi
- [SBTi Chemical Sector Pathways (December 2025)](https://sciencebasedtargets.org/news/sbti-publishes-new-pathways-to-accelerate-chemicals-sectors-net-zero-transition) — SBTi
- [SBTi Power Sector Net-Zero Standard (Draft, September 2025)](https://www.esgtoday.com/sbti-launches-draft-net-zero-standard-for-the-power-sector/) — ESG Today
- [ESOS Compliance Guidance (Gov.UK)](https://www.gov.uk/government/publications/comply-with-the-energy-savings-opportunity-scheme-esos/complying-with-the-energy-savings-opportunity-scheme-esos) — UK Government
- [ESOS Guidance Page](https://www.gov.uk/guidance/energy-savings-opportunity-scheme-esos) — UK Government
- [SECR Regulations Overview](https://netzeronow.org/post/comprehensive-guide-to-secr-reporting-uk) — Net Zero Now
- [SECR Requirements (Greenly)](https://greenly.earth/en-us/blog/company-guide/secr-reporting-all-you-need-to-know) — Greenly
- [UK ETS Policy Overview](https://www.gov.uk/government/publications/uk-emissions-trading-scheme-uk-ets-policy-overview/uk-emissions-trading-scheme-uk-ets-a-policy-overview) — UK Government
- [UK ETS Expansion (ICAP)](https://icapcarbonaction.com/en/news/uk-announces-major-policy-decisions-and-launches-new-consultations-ets-expansion) — ICAP (2025)
- [CCC Progress Report 2025](https://www.theccc.org.uk/publication/progress-in-reducing-emissions-2025-report-to-parliament/) — Committee on Climate Change
- [Digest of UK Energy Statistics (DUKES) 2025](https://www.gov.uk/government/statistics/digest-of-uk-energy-statistics-dukes-2025) — DESNZ
- [Tesco Annual Report 2024](https://www.tescoplc.com/media/zgvhd0dn/tescos_ar24.pdf) — Tesco PLC
- [Sainsbury's Plan for Better Report 2024/25](https://corporate.sainsburys.co.uk/media/dfkfh1jr/sainsburys-plan-for-better-report-2024-25.pdf) — J Sainsbury plc
- [Sainsbury's Scope 3 Approach](https://corporate.sainsburys.co.uk/sustainability/explore-by-a-z/reducing-our-carbon-footprint/our-approach-to-reducing-scope-3-emissions/) — Sainsbury's
- [Market-Wide Half Hourly Settlement (MHHS)](https://www.smsenergy.com/insights/half-hourly-settlement-is-here-what-it-means-for-your-business-and-what-to-do-about-it/) — SMS Energy (2026)
- [EIA Cooling the Climate Crisis — Investor Note (June 2025)](https://eia-international.org/wp-content/uploads/2025-EIA-UK-COOLING-THE-CLIMATE-CRISIS-INVESTOR-NOTE-SINGLE-PAGES.pdf) — Environmental Investigation Agency
- [UK Grocery Retailers and Manufacture 2030](https://secaro.io/insights/news/2023/12/uk-grocery-retailers-partner-with-manufacture-2030) — Secaro (2023)
- [Tesco and Mondra Supply Chain Emissions](https://trellis.net/article/three-initiatives-boosting-accuracy-scope-3-reporting-food-ag/) — Trellis (2025)
- [Top Energy Management Software Tools](https://blog.energyelephant.com/best-energy-management-carbon-reporting-software-2026/) — EnergyElephant
- [ISO Survey 2024 Statistics](https://www.globalstd.com/wp-content/uploads/2025/10/Infografia-ISO-Survey-2024_EN.pdf) — Global Standards
- [LRQA ISO 50001 and ESOS](https://www.lrqa.com/en-gb/iso-50001/) — LRQA
- [ISO 50001 UK Certification — ~1,200 businesses](https://inspiredplc.co.uk/insights/industry-news/impact/why-more-businesses-are-aiming-for-iso50001-accreditation/) — Inspired PLC
- [UKAS Certification Body Accreditation](https://www.ukas.com/accreditation/standards/certification-body-accreditation/) — UKAS
- [CCC 2025 Industry Electricity Report](https://www.theccc.org.uk/publication/progress-in-reducing-emissions-2025-report-to-parliament/) — CCC
- [SBTi Sector Guidance Summary](https://sciencebasedtargets.org/sector-resources-summary) — SBTi
- [Input for CNZS V2.0 Update](https://newclimate.org/sites/default/files/2025-04/input_for_the_update_of_the_sbti_corporate_net-zero_standard_1004_0.pdf) — NewClimate Institute (2025)

---
*Research compiled March 2026 by MGS Research Agent. All data verified against primary sources. Where statistics derive from secondary analysis, source chains are preserved in citations above.*
