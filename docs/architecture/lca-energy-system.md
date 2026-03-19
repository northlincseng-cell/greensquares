# MGS LCA & Mass Energy Balance Architecture Specification

**Version:** 1.0  
**Date:** March 2026  
**Classification:** Internal Architecture Document  
**Platform:** My Green Squares (MGS) — C#/.NET  

---

## 1. Executive Summary

### The Problem

My Green Squares requires an internal Life Cycle Assessment (LCA) and mass energy balance system because the platform cannot function without independent carbon quantification capability. Each Green Square represents 100g CO2e, priced at £0.003 to retailers, and requires 75%+ verified transition action — not offsets. The platform must produce auditable, standards-compliant product carbon footprints and corporate energy balance scores without depending on incumbent sustainability consultants who serve the same retailers MGS targets.

The structural challenge is threefold. First, MGS cannot force retailers or their suppliers to abandon existing consultant relationships mid-contract — [Anthesis has been embedded in Tesco since 2014](https://www.anthesisgroup.com/case-studies/supporting-tesco-to-develop-uk-retails-first-sustainability-linked-supply-chain-finance-product/), and [Mondra now covers 85%+ of UK grocery](https://www.mondra.com) for product-level carbon footprinting. Second, the outputs must be credible enough for Big 4 CSRD/ISSB assurance — [ISSA 5000 takes effect in December 2026](https://www.iaasb.org/focus-areas/understanding-international-standard-sustainability-assurance-5000) with more than double the requirements of ISAE 3000. Third, Green Squares demand physical verification of energy transition, not paper-based contractual claims — a company claiming 100% renewable electricity via unbundled REGOs at [£0.50–£2.50/MWh](https://www.pinsentmasons.com/out-law/news/energy-suppliers-wise-abandon-rego-certificates-greenwashing-concerns) does not constitute genuine transition.

### Strategic Context: Coexist Then Replace

The incumbent ecosystem is fragmented across three layers: consultancies (Anthesis, Carbon Trust, Ricardo), verification bodies (ERM CVS, Deloitte, PwC), and platforms (Mondra, Manufacture 2030, EcoVadis). No single incumbent provides both product-level LCA and corporate energy balance verification anchored to physical data. MGS enters alongside these players by providing the primary process data that consultants currently extract manually from suppliers, then progressively absorbs the calculation and verification functions as data quality and platform credibility grow.

### The Recommendation

A layered API integration strategy with progressive build-out across two distinct but interconnected calculation engines:

- **Engine 1 — Product LCA Engine:** API-first integration with CarbonCloud (food PCFs), Cool Farm Tool (agriculture), and Agribalyse/DEFRA (free background data), with openLCA IPC for novel products
- **Engine 2 — Corporate Energy Balance Engine (Deimos):** Proprietary build ingesting SECR data, MHHS half-hourly consumption, ISO 50001 EnPIs, EAC retirement records, and fleet/refrigerant data to produce a Corporate Energy Balance Score (CEBS) driving GS issuance

Total MVP cost: £50K–120K build + £12K–60K/year API costs, versus £200K–400K over three years for a full in-house LCA team with commercial software.

---

## 2. Standards Architecture

### Primary Standard: ISO 14067:2018

[ISO 14067:2018](https://www.iso.org/standard/71206.html) is the primary standard for MGS product carbon footprinting. It builds on [ISO 14040](https://www.iso.org/standard/37456.html) and [ISO 14044](https://www.iso.org/standard/38498.html) but focuses exclusively on climate change as the single impact category, producing results in kg CO2e per functional unit. An ISO 14067 PCF study is faster and cheaper than a full multi-impact LCA — typically £3,000–£8,000 versus £15,000–£50,000+ for a full ISO 14040/44 study — while remaining the [internationally recognised reference standard for product carbon footprinting](https://simapro.com/insights/product-carbon-footprint-standards-which-standard-to-choose/).

ISO 14067 makes verification optional, which is a known gap. For CSRD assurance purposes, MGS fills this gap through a three-level verification architecture (detailed in Section 6).

### Corporate Energy Framework: ISO 50001

[ISO 50001:2018](https://www.iso.org/iso-50001-energy-management.html) provides the template for corporate energy balance construction within Deimos, even for companies not ISO 50001 certified. Its Energy Performance Indicators (EnPIs) — absolute consumption, energy intensity ratios, and carbon intensity per unit of output — form the quantitative backbone of the Corporate Energy Balance Score. Approximately [1,200 UK businesses hold ISO 50001 certification](https://inspiredplc.co.uk/insights/industry-news/impact/why-more-businesses-are-aiming-for-iso50001-accreditation/) against a backdrop of ~11,900 SECR-reporting companies, meaning the majority of data Deimos processes will come from non-certified organisations using ISO 50001's methodology as a reference framework.

### GHG Protocol Alignment

The system aligns with three GHG Protocol instruments:

| GHG Protocol Standard | Application in MGS | Key Requirement |
|---|---|---|
| [Product Life Cycle Standard](https://ghgprotocol.org/product-standard) | Product-level PCF methodology; Scope 3 Category 1 | Mandatory public reporting; first or third-party assurance; five Data Quality Indicators |
| [Scope 2 Guidance (2015)](https://ghgprotocol.org/sites/default/files/2023-03/Scope%202%20Guidance.pdf) | Dual location/market-based Scope 2 reporting; EAC Quality Criteria | Both methods required; hierarchy for market-based EFs; no double counting |
| Scope 3 Standard (Cat. 1–15) | Corporate energy balance context; supplier data hierarchy | Five calculation approaches from supplier-specific (highest) to spend-based (lowest) |

The GHG Protocol Product Standard is [currently under revision](https://www.carbon-direct.com/insights/key-updates-to-ghg-protocol-and-sbti-what-companies-need-to-know), with final standards expected H2 2026. The MGS methodology layer is designed to be modular so calculation rules can be updated without rebuilding the data architecture.

### PEF Readiness

The [EU Product Environmental Footprint (PEF)](https://ukft.org/pef-update-may25/) covers 16 impact categories versus ISO 14067's single climate category. PEF readiness matters for EU retailer clients (Carrefour, Lidl, Aldi). The MGS database layer supports EF-compliant characterisation factors from the outset, enabling multi-impact assessment when PEFCRs are available. The Green Claims Directive remains [stalled as of March 2026](https://www.carbonfact.com/blog/policy/green-claims-directive-fashion), but the regulatory direction of travel is clear.

### PACT Methodology v3

The [PACT Methodology v3](https://www.carbon-transparency.org/pact-methodology) (WBCSD, April 2025) is becoming the de facto B2B Scope 3 data exchange standard. It requires two reliability metrics — Primary Data Share (PDS) and Data Quality Ratings (DQRs, mandatory by end-2027) — and provides a technical API specification for machine-to-machine PCF exchange. MGS product PCF outputs must be PACT-conformant to serve suppliers reporting to corporates like [Unilever, which uses PACT methodology for its 300-supplier programme](https://www.unilever.com/suppliers/supplier-climate-programme/).

### Standards Hierarchy

```
                         ISO 14040:2006 / ISO 14044:2006
                          (LCA Principles & Framework)
                                     |
                 ┌───────────────────┼───────────────────────┐
                 │                   │                       │
            ISO 14067           PAS 2050:2011          GHG Protocol
             :2018              (UK-origin,          Product Standard
           (carbon              legacy)              (public reporting
            only)                                     mandatory)
                 │                   │                       │
                 └───────────────────┴───────────────────────┘
                                     │
                        ┌────────────┴────────────┐
                        │                         │
                   EU PEF / PEFCRs          PACT v3 (WBCSD)
                 (16 impact categories,    (B2B PCF exchange,
                  EF-compliant datasets)    machine-readable API)
                                     │
                                     │
                            ┌────────┴────────┐
                            │                 │
                     ISO 50001:2018    GHG Protocol
                    (Corporate Energy   Scope 2/3 Guidance
                     Management)       (Corporate Energy)
                            │                 │
                            └────────┬────────┘
                                     │
                              DEIMOS ENGINE
                         (Mass Energy Balance
                          & GS Issuance Logic)
```

### Standards Decision Matrix

| Use Case | Standard | Rationale |
|---|---|---|
| Default FMCG product PCF | ISO 14067:2018 | International reference; accepted by all auditors; flexible for platform-scale automation |
| UK retail supply chain | BRC Mondra Coalition v7.1 (ISO 14067-compatible) | Industry-specific open standard; pre-accepted by UK retailers |
| EU retailer clients | PEF (where PEFCR exists) or ISO 14067 (where no PEFCR) | Regulatory safe harbour for EU environmental claims |
| B2B supplier data exchange | PACT Methodology v3 | De facto standard for machine-to-machine PCF exchange |
| CSRD Scope 3 reporting | GHG Protocol Product Standard | Directly feeds corporate Scope 3 Category 1 disclosures |
| Corporate energy balance | ISO 50001 + GHG Protocol Scope 2 Guidance | Gold standard for EnPI construction and dual Scope 2 reporting |

---

## 3. System Architecture — Two Engines

The MGS calculation system comprises two distinct engines serving different purposes but sharing data infrastructure, emission factor management, and audit trail systems.

### Engine 1: Product LCA Engine (Product Carbon Footprints)

**Purpose:** Calculate per-kg product carbon footprints for FMCG products, then convert to Green Square units (1 GS = 100g CO2e).

**Functional unit:** Per kg of finished product at retail shelf, enabling direct per-100g CO2e conversion for GS pricing.

**System boundary:** Cradle-to-shelf (raw material extraction through retail distribution), consistent with [CarbonCloud's methodology](https://carboncloud.com/brief-methodology/) and the [GHG Protocol supplier-specific method](https://ghgprotocol.org/product-standard). Consumer use and end-of-life are excluded from the default boundary but can be included for full cradle-to-grave assessments when required.

**Data flow:**

```
CLIENT INPUT                    MGS PROCESSING                    OUTPUT
┌──────────────┐    ┌──────────────────────────────────┐    ┌──────────────┐
│ Bill of       │    │ 1. Ingredient Matching           │    │ PCF per kg   │
│ Materials     │───→│    (BOM → database ingredient IDs)│───→│ (kg CO2e/kg) │
│ (BOM)         │    │ 2. Background DB Lookup          │    │              │
│               │    │    (Agribalyse, ecoinvent, DEFRA) │    │ GS conversion│
│ Processing    │    │ 3. Foreground Data Integration   │    │ (PCF ÷ 0.1)  │
│ energy data   │───→│    (kWh, MJ, transport km)       │    │              │
│               │    │ 4. LCIA Calculation              │    │ Data quality │
│ Packaging     │    │    (GWP100, IPCC AR6 factors)    │    │ tier (Au/Ag/ │
│ spec          │───→│ 5. Allocation Applied            │    │ Br)          │
│               │    │    (ISO 14044 hierarchy)          │    │              │
│ Transport     │    │ 6. Quality Scoring               │    │ Uncertainty  │
│ data          │───→│    (DQ1-DQ5 per input)           │    │ range (±%)   │
└──────────────┘    └──────────────────────────────────┘    └──────────────┘
```

**API integration layer:** Engine 1 routes calculations to the most appropriate external API based on product type:

| Product Type | API / Data Source | Coverage | Integration Method |
|---|---|---|---|
| Standard food products | [CarbonCloud API](https://carboncloud.com/api/) | Thousands of pre-calculated food PCFs, farm-to-shelf | REST API, per-product lookup |
| Agricultural crop/dairy | [Cool Farm Tool API](https://coolfarm.org/wp-content/uploads/2025/06/Cool-Farm_Annual-Report-2024_FINAL.pdf) | Farm-gate GHG for crops and dairy | REST API, farm-level assessment |
| UK energy/fuel factors | [DEFRA flat file](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025) | UK Scope 1/2 energy, transport, refrigerants | Self-hosted CSV, annual update |
| Food ingredient backgrounds | [Agribalyse v3.2](https://doc.agribalyse.fr/documentation-en/) | 2,500+ food products with full LCA profiles | Self-hosted, loaded into openLCA |
| Scope 3 spend-based | [Climatiq Enterprise API](https://www.climatiq.io/pricing) | DEFRA + EXIOBASE + EPA aggregated | REST API, per-calculation |
| Novel/custom products | [openLCA IPC](https://www.openlca.org/features/) + ecoinvent Developer | Full process-based LCA with 25,000+ datasets | gRPC from C#, self-hosted server |

**For novel or custom products:** The openLCA IPC server runs headless as a calculation server, exposing gRPC endpoints [with explicit C# support](https://github.com/GreenDelta/openLCA-ApiDoc). MGS calls the openLCA server from C# using generated gRPC stubs, passing product system definitions and receiving LCIA results. This requires an [ecoinvent Developer licence](https://ecoinvent.org/licenses/developer/) for embedded use — pricing is negotiated separately but permits sub-licensing of LCIA scores (not raw LCI data) to end users.

### Engine 2: Corporate Energy Balance Engine (Deimos)

**Purpose:** Verify corporate energy transition status for GS 75%+ threshold determination and produce a Corporate Energy Balance Score (CEBS) driving GS issuance decisions.

**Core principle:** Physical primacy. A Green Square must be anchored to the physical energy layer, not the paper layer. A company reporting 100% renewable electricity solely via unbundled REGOs does not qualify as genuine transition action. Deimos distinguishes between physically metered renewable generation, contractual PPA claims, bundled tariff certificates, and unbundled paper instruments.

**Data inputs across three verification layers:**

```
PHYSICAL DATA LAYER
┌─────────────────────────────────────────────────────────┐
│ Smart/AMR meters (MHHS) ──→ half-hourly kWh by site    │
│ F-gas logbooks ──→ refrigerant leakage kg by asset      │
│ Fuel cards / telematics ──→ diesel litres by vehicle    │
│ Solar/wind generation meters ──→ kWh produced           │
│ Gas meters ──→ m³ by site                               │
└────────────────┬────────────────────────────────────────┘
                 │
CONTRACTUAL CLAIMS LAYER
┌─────────────────────────────────────────────────────────┐
│ REGO registry (Ofgem) ──→ certificate retirement records│
│ PPA contract terms ──→ MW capacity, generation source   │
│ Bundled supplier tariff documentation                   │
└────────────────┬────────────────────────────────────────┘
                 │
STANDARDS / ATTESTATION LAYER
┌─────────────────────────────────────────────────────────┐
│ ISO 50001 audit report ──→ EnPI series, baseline data   │
│ SECR disclosure (Companies House) ──→ annual energy     │
│ CDP climate questionnaire ──→ Scope 1+2+3 breakdown     │
│ SBTi validation letter ──→ target and base year         │
│ UK ETS verified emission report ──→ Scope 1 installation│
└────────────────┬────────────────────────────────────────┘
                 │
              DEIMOS
```

**Corporate Energy Balance Score (CEBS) calculation:**

The CEBS is a composite score derived from seven weighted components:

| Component | Weight | Measurement |
|---|---|---|
| Physical Renewable Share | 30% | Actual % of energy from verified renewable sources (metered) |
| Emission Trajectory Compliance | 20% | On/off track vs SBTi or equivalent 1.5°C pathway |
| Data Quality Score | 10% | Completeness and verification level of inputs (DQ1–DQ5 weighted average) |
| Additionality Score | 15% | Quality of renewable procurement: on-site > PPA > bundled > unbundled |
| Efficiency Improvement Rate | 10% | Year-on-year energy intensity improvement (kWh/unit output) |
| Refrigerant Transition Progress | 10% | For retailers: HFC→natural refrigerant estate conversion % |
| Supply Chain Engagement Score | 5% | % of Scope 3 covered by suppliers with validated targets |

**REGO unbundling detection:** Only three procurement types receive full physical transition credit:

| Procurement Type | Additionality | Physical Matching | GS Credit |
|---|---|---|---|
| On-site generation (solar, wind) | High | Physical | Full |
| Dedicated PPA with new-build generator | High | Contractual but direct | Full |
| Sleeved PPA (certificate + power bundled) | Medium | Partial | Partial with verification |
| Bundled tariff (power + EAC from supplier) | Low-Medium | Grid mix | Partial |
| Unbundled REGOs only | Nil | None | No credit |
| Residual mix (no certificate) | N/A | Fossil-weighted | No credit |

**Tiered GS issuance decision:**

| CEBS Tier | Conditions | GS Decision |
|---|---|---|
| **Tier A (Full GS)** | Physical renewable ≥75% of electricity; on-track vs SBTi; EACs monthly-matched via direct PPAs or on-site; Scope 1+2 verified | Green Square issued; full public disclosure |
| **Tier B (Conditional GS)** | Physical renewable ≥50% but <75%; trajectory improving; minor data gaps; annual bundled EACs | GS issued with conditions and milestone dates |
| **Tier C (Pathway GS)** | Credible transition plan with SBTi-validated targets; <50% physical renewable but meaningful trajectory | Pathway GS — signals committed corporate, not yet transitioned |
| **Ineligible** | No verified trajectory; only unbundled REGOs; worsening trajectory; no Scope 1+2 data | No GS; reasons disclosed to corporate |

The 75% threshold is the initial floor, with staged progression to 80% → 85% → 90% as the platform matures and MHHS data enables granular temporal matching.

**MHHS integration roadmap:** [Market-wide Half Hourly Settlement](https://www.smsenergy.com/insights/half-hourly-settlement-is-here-what-it-means-for-your-business-and-what-to-do-about-it/) went live September 2025, with full meter migration completing May 2027. By mid-2027, Deimos can access half-hourly consumption data for any UK corporate site, enabling the verification chain: MHHS consumption + [National Grid ESO Carbon Intensity API](https://carbonintensity.org.uk/) + EAC retirement registry → verified hourly carbon-free energy calculation → GS eligibility decision.

---

## 4. Data Architecture

### Background Databases

| Database | Coverage | Cost | Format | MGS Use |
|---|---|---|---|---|
| [Agribalyse v3.2](https://nexus.openlca.org/database/Agribalyse) | 2,500+ food products, 200 agricultural raw materials (French context) | Free (ETALAB licence) | EcoSpold2/ILCD/JSON-LD | Primary free food ingredient background; loaded into openLCA |
| [ecoinvent v3.11](https://ecoinvent.org/licenses/) | 25,000+ datasets; manufacturing, agriculture, energy, transport — global | ~CHF 1,650/yr single-user; Developer licence required for embedding | EcoSpold2/JSON-LD | Gold standard background; [REST API in closed beta](https://docs.api.ecoinvent.org) |
| [DEFRA/DESNZ UK GHG Factors](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025) | UK energy, transport, refrigerants, waste, materials — Scope 1/2/3 | Free (OGL v3) | Excel/CSV flat file | Essential for Deimos corporate energy; self-hosted, annual update |
| [EXIOBASE3](https://doi.org/10.5281/zenodo.3583070) | 163 industries × 200 products, global; monetary-based MRIO | Free (CC BY-SA 4.0) | CSV/HDF5 matrices | Scope 3 spend-based fallback; via Climatiq API |

Agribalyse combined with DEFRA energy factors covers a large proportion of common FMCG food products without requiring ecoinvent. The French production context of Agribalyse limits direct UK applicability for transport assumptions and energy mix, but provides excellent proxy data for common food categories. Over time, MGS builds a proprietary UK food emission factor database layered over these free sources.

### Foreground Data

Client-supplied foreground data constitutes the primary data layer:

| Data Type | Source | Priority |
|---|---|---|
| Bill of Materials (BOM) | Client recipe/specification system | Essential — determines ingredient allocation |
| Processing energy | Client utility data (kWh electricity, MJ heat per tonne) | Essential — drives manufacturing footprint |
| Packaging materials | Client packaging specification (material type, weight, recycled content) | Essential — significant for consumer goods |
| Transport modes and distances | Client logistics data (km, mode, load factor) | Important — primary for key routes; secondary acceptable for minor |
| Refrigerant data | F-gas logbooks (legally required) | Essential for grocery retail corporates |
| Fleet fuel data | Fuel card transactions, telematics | Essential for Scope 1 fleet emissions |

### Emission Factor Management

Emission factors are version-controlled, annually updated, and source-tagged. Each factor record includes:

- Factor value and unit (e.g., 0.207 kgCO2e/kWh)
- Source database, version number, and publication date
- Geographic scope (UK, EU, global)
- Temporal validity period (e.g., DEFRA 2025: valid for reporting years starting April 2025)
- Supersession chain (which prior factor this replaces)
- Access URL for auditability

Using stale emission factors is one of the most [common audit findings identified by KPMG](https://kpmg.com/ee/en/insights/2026/01/Greenhouse-gas-accounting-in-2025-and-beyond--assurance-is-here,-standards-are-converging,-and-Scope-3-remains-the-stress-point.html). Deimos enforces current-year factor application and flags calculations using expired factors.

### Data Quality Framework

The system implements a 5-tier data quality scoring framework aligned with [ISAE 3410](https://ciferi.com/blog/isae-3410-greenhouse-gas-statements-guide) and ISO 14044:

| Level | Definition | Typical Sources | Auditor Treatment |
|---|---|---|---|
| **DQ1** — Primary measured | Direct metering, direct measurement | Own meters, fuel records, generation logs | Highest confidence; verify against source documents |
| **DQ2** — Primary calculated | Calculated from verified primary inputs | Mass balance from verified production data | High confidence; verify calculation logic |
| **DQ3** — Supplier-reported | Data reported by supplier, unverified | Supplier carbon footprint data | Moderate confidence; evaluate supplier's own controls |
| **DQ4** — Industry average | Published database average | ecoinvent, Agribalyse, DEFRA generic EFs | Acceptable for Scope 3; evaluate representativeness |
| **DQ5** — Spend-based proxy | Economic input-output model | EXIOBASE spend data × sector EF | Lowest quality; flagged in assurance reports |

Every data input is tagged with its DQ level. The platform calculates a weighted average DQ score for each product footprint and surfaces the percentage covered by DQ1–DQ2 (primary) versus DQ3–DQ5 (estimated).

**PACT Primary Data Share (PDS):** The [PACT Methodology v3](https://www.carbon-transparency.org/pact-methodology) requires reporting a PDS metric — the percentage of a product's footprint calculated from primary data. DQRs become mandatory by end-2027. The MGS DQ framework maps directly to PACT PDS, enabling conformant B2B data exchange.

**Data quality tiers for FMCG products:**

| Tier | Description | Auditor Assessment |
|---|---|---|
| **Gold** (>60% primary data) | All key hotspot processes use supplier-specific data; ISO 14067 or GHG Protocol compliant study report; third-party verified | Fully acceptable for CSRD assurance and comparative claims |
| **Silver** (30–60% primary) | Key processing and packaging use primary data; agricultural inputs from verified regional databases | Acceptable for CSRD assurance with clear uncertainty disclosure |
| **Bronze** (<30% primary) | Largely based on database averages with product BOM as primary input | Acceptable for hotspot identification; requires explicit uncertainty caveat |

The majority of existing platform LCAs ([Mondra](https://www.mondra.com), [CarbonCloud](https://carboncloud.com/brief-methodology/), Foundation Earth) start at Bronze/Silver using automated BOM calculation, then improve toward Gold through supplier engagement. MGS follows the same trajectory.

---

## 5. API Integration Architecture

### System Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                     MGS PLATFORM (C#/.NET)                          │
│                                                                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────────┐  │
│  │ Engine 1:    │  │ Engine 2:    │  │ Shared Services:         │  │
│  │ Product LCA  │  │ Deimos       │  │ - EF Version Control     │  │
│  │ Engine       │  │ (Corporate   │  │ - Audit Trail Logger     │  │
│  │              │  │  Energy)     │  │ - DQ Scoring Engine      │  │
│  └──────┬───────┘  └──────┬───────┘  │ - GS Issuance Logic     │  │
│         │                 │          │ - PACT Export Module     │  │
│         │                 │          └──────────────────────────┘  │
└─────────┼─────────────────┼───────────────────────────────────────┘
          │                 │
    ┌─────┴─────────────────┴─────────────────────────────────────┐
    │                    EXTERNAL APIs & DATA                      │
    │                                                              │
    │  Product PCFs ────────→ CarbonCloud API (food, REST)        │
    │  Agriculture ─────────→ Cool Farm Tool API (crop/dairy)     │
    │  Scope 1/2/3 ─────────→ Climatiq Enterprise API             │
    │                          (DEFRA + EXIOBASE + EPA)           │
    │  UK Statutory ─────────→ DEFRA flat file (self-hosted, free)│
    │  Advanced LCA ─────────→ openLCA IPC (gRPC, self-hosted)   │
    │                          + ecoinvent Developer licence       │
    │  Grid carbon ──────────→ National Grid ESO Carbon Intensity │
    │                          API (free, real-time)              │
    │  EAC verification ─────→ Ofgem REGO Registry               │
    │  MHHS data ────────────→ Elexon / supplier data feeds      │
    │  Free food background ─→ Agribalyse v3.2 (self-hosted)     │
    └─────────────────────────────────────────────────────────────┘
```

### API Cost Estimates at Startup Scale

| API / Data Source | Estimated Monthly Cost | Billing Model | Notes |
|---|---|---|---|
| [Climatiq Enterprise](https://www.climatiq.io/pricing) | £500–2,000 | Custom enterprise; volume-based | Aggregates DEFRA, EXIOBASE, EPA; ISO 27001, SOC 2 |
| [CarbonCloud API](https://carboncloud.com/api/) | £500–3,000 | Per-product or flat SaaS | Contact for pricing; biophysical model, academic quality |
| [Cool Farm Tool](https://coolfarm.org/) | £40–170 (annual membership) | Alliance membership model | Non-profit; Crop and Dairy APIs for embedding |
| [DEFRA flat file](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025) | Free | Open Government Licence | Annual download; CSV for automation |
| [Agribalyse v3.2](https://doc.agribalyse.fr/documentation-en/) | Free | ETALAB open licence | Self-hosted in openLCA; 2,500+ food products |
| [EXIOBASE3](https://doi.org/10.5281/zenodo.3583070) | Free | CC BY-SA 4.0 | Self-hosted; Scope 3 spend-based fallback |
| [National Grid ESO Carbon Intensity](https://carbonintensity.org.uk/) | Free | Public API | Real-time and historic grid carbon data |
| openLCA IPC server | Free (tool) | MPL 2.0 open source | Requires ecoinvent Developer licence for gold-standard data |
| ecoinvent Developer licence | £5K–15K/year (estimated) | Annual negotiated | Permits sub-licensing LCIA scores to end users |
| **Total estimated** | **£1,000–5,000/month** | | At startup scale (50–500 product calculations/month) |

This compares to £5,000–15,000/month equivalent for an in-house LCA team with full commercial software licences ([SimaPro Expert at €6,100/year](https://simapro.com/plans/) or [GaBi at ~$15,000–$17,000/year](https://www.vendr.com/marketplace/sphera)).

### C#/.NET Integration Patterns

No purpose-built C#/.NET LCA library exists in open source. The integration paths are:

| Approach | Complexity | Recommendation |
|---|---|---|
| External REST APIs (CarbonCloud, Climatiq, Cool Farm) | Low — standard HttpClient | Primary integration method |
| [openLCA gRPC via C# generated stubs](https://github.com/GreenDelta/openLCA-ApiDoc) | Medium — requires running openLCA server process | For advanced/novel LCA calculations |
| DEFRA flat file ingestion | Low — CSV parsing | Self-hosted, version-controlled factor store |
| Native C# calculation engine | High — matrix algebra with MathNet Numerics (MIT) | For Deimos CEBS calculation (proprietary) |

The core LCA matrix calculation is straightforward numerical computing — `s = h × (I - A)⁻¹ × f` — solvable in C# with [MathNet Numerics](https://numerics.mathdotnet.com/). The maths is not the hard part. The hard parts are [building the background database, handling multi-functionality allocation, and maintaining data currency](https://www.openlca.org/features/).

---

## 6. Auditability Architecture

### What Big 4 Auditors Need

The [Deloitte 2024 CEO survey](https://dart.deloitte.com/USDART/home/publications/deloitte/sustainability-spotlight/2025/sustainability-related-reporting-requirements-and-standards) found 57% of executives cite data quality as the top ESG challenge, and 81% report documentation and sign-off as a top challenge. The [KPMG 2026 GHG accounting outlook](https://kpmg.com/ee/en/insights/2026/01/Greenhouse-gas-accounting-in-2025-and-beyond--assurance-is-here,-standards-are-converging,-and-Scope-3-remains-the-stress-point.html) confirms: "Scope 3 disclosures carry more inherent limitations than Scopes 1–2" and auditors are "keeping probing Scope 3 estimates in the next filing cycle."

Auditors require five things from a carbon calculation system:

1. **Immutable calculation log** — every calculation timestamped and preserved
2. **Version-controlled methodology** — documented, consistently applied, aligned with recognised standards
3. **Traceable data lineage** — any reported figure traceable back to raw activity data
4. **Emission factor provenance** — which version of which database was used for every factor
5. **Reproducible calculations** — auditor can recalculate: Activity data × EF × GWP = emissions

### ISAE 3410 → ISSA 5000 Transition

[ISAE 3410](https://ciferi.com/blog/isae-3410-greenhouse-gas-statements-guide) (approved March 2012) remains in force until [ISSA 5000](https://www.iaasb.org/focus-areas/understanding-international-standard-sustainability-assurance-5000) takes effect on 15 December 2026. ISSA 5000 more than doubles the requirements of ISAE 3000 and introduces:

| New in ISSA 5000 | Implication for MGS |
|---|---|
| Double materiality assessment | Financial materiality AND impact materiality required |
| Enhanced value chain guidance | Scope 3 and product LCA explicitly addressed |
| Qualitative disclosure coverage | Narrative sustainability disclosures must be assurable |
| Broader scope (all sustainability, not just GHG) | Platform must accommodate non-climate metrics over time |
| Standalone standard | No parallel ISAE 3000 compliance needed |

Building the audit trail from day one is not optional — ISSA 5000 takes effect eight months from now.

### Calculation Metadata Record Structure

Every calculation output from MGS includes:

```
CALCULATION METADATA RECORD
──────────────────────────────────────────────────────

Product/Process ID:   [unique identifier]
Reporting period:     [start date] — [end date]
Standard applied:     [ISO 14067 | GHG Protocol Scope 3 Cat 1 | PACT v3]
Functional unit:      [e.g., 1 kg of product at retail shelf]
System boundary:      [cradle-to-gate | cradle-to-shelf | cradle-to-grave]
Allocation method:    [mass | economic | system expansion | none]

INPUTS:
  Activity data:
    - Item: [e.g., wheat flour]
    - Value: 0.45 kg
    - Source type: PRIMARY (BOM) | SECONDARY (database) | ESTIMATED
    - Source reference: [client specification ID / database + version]
    - DQ Level: [DQ1 | DQ2 | DQ3 | DQ4 | DQ5]
    - Period: [date range]

  Emission factors applied:
    - EF: 0.62 kgCO2e/kg wheat flour
    - Source: Agribalyse v3.2, process ID [xxx]
    - Geographic scope: France (proxy for UK)
    - Temporal validity: 2023–2025
    - Characterisation: GWP100, IPCC AR6

OUTPUTS:
  GHG result: 2.34 kgCO2e/kg product
  Green Squares: 23.4 GS per kg
  Scope boundary: Scope 3 Category 1 (purchased goods)
  Data quality score: 3.2 / 5.0 (Silver tier: 42% primary data)
  Primary Data Share (PDS): 42%
  Uncertainty range: ±18%

AUDIT FIELDS:
  Calculated by:        [user ID]
  Calculated on:        [ISO 8601 datetime]
  Approved by:          [user ID]
  Approved on:          [ISO 8601 datetime]
  Methodology version:  MGS-PCF-v1.3
  Previous period:      2.51 kgCO2e/kg (FY2024)
  Change explanation:   Supplier provided primary energy data (DQ4→DQ2);
                        updated DEFRA electricity EF (2024→2025)
```

### Three-Level Verification Architecture

| Level | Scope | Frequency | Purpose |
|---|---|---|---|
| **L1: Automated consistency** | Every calculation | Real-time | Plausibility checks against category benchmarks; flag outliers (e.g., chicken breast at 50 kgCO2e/kg is implausible); unit conversion validation; completeness checks |
| **L2: Annual methodology review** | Platform-wide | Annual | Third-party review of methodology and calculation model by qualified sustainability professional; covers CSRD limited assurance requirements; published methodology document (version-controlled, following [BRC Mondra Coalition's open-methodology approach](https://brcmondracoalition.com/standards)) |
| **L3: Product-level third-party** | Per-product (optional) | On demand | Independent third-party verification for consumer-facing claims or competitive comparisons; meets ISO 14067 Clause 8 voluntary verification provisions; required for comparative public assertions under ISO 14040 |

### The Key Insight

Auditors verify the **system and methodology**, not individual product LCAs. The [analysis of 1,100 CSRD reports](https://trellis.net/article/lessons-1100-csrd-reports/) confirms that Big 4 firms are checking whether the reporting entity has a documented, consistently applied methodology aligned with recognised standards — not recalculating every product's carbon footprint. An auditable, well-documented, methodologically sound platform operating at Silver tier passes limited assurance if uncertainty is disclosed. What fails audits is undocumented methodology, untraceable calculations, and unsupported comparative claims.

---

## 7. Incumbent Coexistence Strategy

### Retailer-Incumbent Map

| Retailer | Supply Chain Consultant | Product LCA Platform | Scope 3 Data Collection | GHG Verification | Financial Auditor |
|---|---|---|---|---|---|
| **Tesco** | [Anthesis](https://www.anthesisgroup.com/case-studies/supporting-tesco-to-develop-uk-retails-first-sustainability-linked-supply-chain-finance-product/) (since 2014) | [Mondra](https://trellis.net/article/three-initiatives-boosting-accuracy-scope-3-reporting-food-ag/) | [Manufacture 2030](https://secaro.io/insights/news/2023/12/uk-grocery-retailers-partner-with-manufacture-2030) | [ERM CVS](https://corporate.sainsburys.co.uk/media/yqzduxhw/p4b-independent-limited-assurance-report.pdf) | — |
| **Sainsbury's** | — | [Mondra](https://www.mondra.com/partners) | Manufacture 2030 | [ERM CVS](https://corporate.sainsburys.co.uk/media/yqzduxhw/p4b-independent-limited-assurance-report.pdf) (ISAE 3000) | — |
| **M&S** | — | [Mondra](https://corporate.marksandspencer.com/sites/marksandspencer/files/2025-05/Marks-and-Spencer-Group-plc-ESG-Report-2025.pdf) (~6,000 products) + [South Pole](https://corporate.marksandspencer.com/sites/marksandspencer/files/2025-05/Marks-and-Spencer-Group-plc-ESG-Report-2025.pdf) (Clothing & Home) | Manufacture 2030 + [Higg Index](https://corporate.marksandspencer.com/sites/marksandspencer/files/2025-05/Marks-and-Spencer-Group-plc-ESG-Report-2025.pdf) (Fashion) | [Deloitte](https://corporate.marksandspencer.com/sites/marksandspencer/files/2025-05/Marks-and-Spencer-Group-plc-ESG-Report-2025.pdf) (ISAE 3000/3410) | Deloitte |
| **Morrisons** | Internal | — | [Manufacture 2030](https://www.morrisons-corporate.com/globalassets/corporatesite/sustainability/morrisons-sustainability-report-fy23-24.pdf) | — | — |
| **ASDA** | Not identified | — | [EcoVadis](https://corporate.asda.com/esg-homepage) | — | — |

Key observations: Manufacture 2030 is embedded in four of the five major retailers for supply chain data collection but does not produce product-level LCA. Mondra dominates product carbon footprinting at Tesco, Sainsbury's, M&S, and Waitrose. No incumbent provides both product LCA and physical energy balance verification in a single platform.

### The "Alongside Then Replace" Model

MGS enters the ecosystem through the structural gap between data collection (M2030) and product footprinting (Mondra). The model operates in three phases:

**Phase 1 — Data provider:** MGS provides primary process data (energy, production volumes, waste) from suppliers that consultants like Anthesis currently extract through annual questionnaire cycles. M&S explicitly states its plan to improve Mondra accuracy by ["plugging in actual emissions data from M&S Food suppliers"](https://corporate.marksandspencer.com/sites/marksandspencer/files/2025-05/Marks-and-Spencer-Group-plc-ESG-Report-2025.pdf) via M2030 — those suppliers need to produce that data, and MGS enables them to do so.

**Phase 2 — Calculation layer:** As supplier data flows through MGS, the platform begins producing its own PCFs that can be cross-referenced against Mondra/CarbonCloud outputs. Higher primary data coverage inherently produces more accurate results, shifting the value proposition from "data collection tool" to "primary calculation engine."

**Phase 3 — Verification authority:** With sufficient data coverage and methodology credibility (L2 annual review, PACT conformance), MGS becomes the preferred calculation source. Consultants retain strategy and interpretation roles, but the calculation infrastructure runs on MGS.

### FMCG Brand Entry Points

| Brand | Current Stack | MGS Opportunity |
|---|---|---|
| [Unilever](https://www.unilever.com/suppliers/supplier-climate-programme/) | PACT programme; Ecochain + Nexio Projects for supplier PCFs; M2030 | Target the 300+ suppliers who need to produce PCF data for Unilever but lack internal capability |
| [Nestlé UK](https://www.nestle.com/sites/default/files/2025-02/non-financial-statement-2024.pdf) | Quantis (now acquired); internal Data Quality Management Team (2024) | Mid-maturity on systematic PCF; preparing for assurance-grade reporting |
| [PepsiCo UK](https://www.pepsico.com/newsroom/press-releases/2025/pepsico-reports-2024-progress-against-pepsico-positive-pep-sustainability-and-nutrition-goals) | Yara/CropTrak for precision agriculture | Farm-level data-driven approach aligns with Deimos energy balance |
| [Diageo](https://www.diageo.com/~/media/Files/D/Diageo-V2/Diageo-Corp/esg/esg-governance-and-reporting-centre/esg-reporting-index-gri-sasb-index-2024.pdf) | PwC assurance; ad hoc product LCA (Everpour keg study) | Systematic product-level carbon tracking across portfolio |

### The South Pole Opening

[South Pole's credibility collapse](https://www.reuters.com/sustainability/boards-policy-regulation/ceo-daniel-klier-leaves-role-south-pole-carbon-consultancy-2025-10-16/) following the Kariba REDD+ scandal (15 million excess credits confirmed by Verra review; CEO departed October 2025) creates a specific opening. South Pole assisted M&S with Clothing & Home product LCA and provided offset advisory across multiple corporates. Clients using South Pole for carbon neutrality claims face reputational scrutiny. MGS's explicit exclusion of offsets from GS calculation (aligned with ISO 14067, which explicitly excludes offsets) positions it as a credible alternative focused on actual transition rather than certificate-based claims.

---

## 8. Build vs Buy Recommendations

### Decision Matrix

| Component | Recommendation | Rationale | Estimated Cost |
|---|---|---|---|
| **Product food PCFs** | Buy ([CarbonCloud API](https://carboncloud.com/api/)) | Thousands of pre-calculated food footprints; biophysical model; scientific quality; fastest time to market | £500–3,000/month |
| **Agricultural ingredients** | Buy ([Cool Farm Tool API](https://coolfarm.org/)) | Best-in-class farm-gate calculation; non-profit API; Crop and Dairy coverage | £500–2,000/year membership |
| **Corporate Scope 1/2** | Build (DEFRA self-hosted) | [Free, UK-official](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2025); simple energy + fuel factors; CSV flat file; no dependency | Free (development time only) |
| **Corporate Scope 3** | Buy ([Climatiq Enterprise](https://www.climatiq.io/pricing)) | Aggregates DEFRA, EXIOBASE, EPA behind single REST API; ISO 27001/SOC 2 | £500–2,000/month |
| **Novel product LCA** | Hybrid ([openLCA IPC](https://www.openlca.org/features/) + ecoinvent) | Free calculation engine; ecoinvent Developer licence for gold-standard background data; C# gRPC integration | £5K–15K/year ecoinvent |
| **Deimos energy engine** | Build (core IP, proprietary) | Unique value proposition; physical-primacy verification logic; CEBS calculation; GS issuance rules | £30K–60K development |
| **Audit trail/governance** | Build (core platform feature) | Differentiating capability; immutable log, version control, metadata records; ISSA 5000 compliance | £15K–30K development |
| **UK food EF database** | Build long-term | Curate from [Agribalyse](https://doc.agribalyse.fr/documentation-en/) (free) + DEFRA + primary data from supplier network; becomes proprietary moat | £20K–50K curation over 12 months |
| **Free food background** | Self-host ([Agribalyse v3.2](https://nexus.openlca.org/database/Agribalyse)) | 2,500+ food products; free ETALAB licence; loaded into openLCA for calculation | Free |
| **Scope 3 IO fallback** | Self-host ([EXIOBASE3](https://doi.org/10.5281/zenodo.3583070)) | Free CC BY-SA; macro supply chain coverage; spend-based Scope 3 when activity data unavailable | Free |

### Cost Summary

| Cost Category | Year 1 | Year 2 | Year 3 | 3-Year Total |
|---|---|---|---|---|
| Platform build (Deimos + audit trail + integration) | £50K–120K | £20K–40K (maintenance) | £20K–40K | £90K–200K |
| API subscriptions (CarbonCloud, Climatiq, Cool Farm) | £12K–60K | £12K–60K | £12K–60K | £36K–180K |
| ecoinvent Developer licence | £5K–15K | £5K–15K | £5K–15K | £15K–45K |
| UK food EF database curation | £20K–50K | £10K–20K | £10K–20K | £40K–90K |
| **Total MGS approach** | **£87K–245K** | **£47K–135K** | **£47K–135K** | **£181K–515K** |
| **vs. Full in-house LCA team** | £150K–200K | £150K–200K | £150K–200K | **£450K–600K** |

The in-house alternative requires 2–3 FTE LCA specialists (£50K–80K salary each), SimaPro or GaBi licences (£6K–17K/year), and ecoinvent access — totalling significantly more with lower platform scalability. The API-first approach defers specialist hiring until product-market fit is confirmed.

---

## 9. Phased Implementation Roadmap

### Phase 1: Foundation (Months 1–3) — Deimos MVP + Corporate Energy

**Deliverables:**
- DEFRA flat file self-hosted factor store with version control and automated annual ingestion
- Climatiq Enterprise API integration for corporate Scope 1/2/3 calculation
- Deimos MVP: SECR data ingestion → DEFRA factor application → location/market-based Scope 2 dual reporting → basic CEBS output
- Audit trail system: immutable calculation log, metadata records, DQ tagging
- GS issuance rules engine (Tier A/B/C/Ineligible determination)

**Cost:** £20K–40K development + £6K–24K API subscriptions  
**Dependencies:** Climatiq Enterprise agreement; DEFRA 2025 factors published

### Phase 2: Product PCFs (Months 3–6) — Food Carbon Footprinting

**Deliverables:**
- CarbonCloud API integration for standard food product PCFs
- BOM ingestion pipeline (client specification data → ingredient matching → CarbonCloud lookup)
- PCF-to-GS conversion logic (per-kg CO2e ÷ 0.1 = Green Squares per kg)
- Silver-tier data quality framework with PDS tracking
- Agribalyse v3.2 self-hosted as free background layer for products not in CarbonCloud

**Cost:** £15K–30K development + £6K–36K API subscriptions  
**Dependencies:** CarbonCloud commercial agreement; first client BOM data

### Phase 3: Agriculture + Advanced LCA (Months 6–12) — Full Product Coverage

**Deliverables:**
- Cool Farm Tool API integration for agricultural ingredient footprinting (crop and dairy)
- openLCA IPC server deployment with ecoinvent Developer licence for novel/custom products
- Full cradle-to-shelf system boundary including transport and packaging modules
- L2 annual methodology review (first third-party methodology audit)
- Audit trail export capability for Big 4 auditor access

**Cost:** £20K–40K development + ecoinvent licence (£5K–15K)  
**Dependencies:** Cool Farm Alliance membership; ecoinvent Developer licence negotiation; openLCA gRPC server deployment

### Phase 4: MHHS + Proprietary Data (Months 12–18) — Physical Verification

**Deliverables:**
- MHHS half-hourly consumption data integration (Elexon/supplier feeds)
- National Grid ESO Carbon Intensity API integration for temporal carbon matching
- Hourly/half-hourly CFE verification capability
- Proprietary UK food emission factor database (curated from Agribalyse + DEFRA + primary supplier data)
- REGO registry integration for automated EAC verification
- Refrigerant transition tracking module (F-gas logbook data → HFC/natural split analysis)

**Cost:** £25K–50K development + £20K–50K database curation  
**Dependencies:** MHHS migration completion (May 2027); Elexon data feed agreements; sufficient supplier data volume

### Phase 5: PACT + PEF (Months 18–24) — Market Expansion

**Deliverables:**
- PACT Conformant PCF exchange capability (machine-to-machine API for B2B Scope 3 data)
- PEF readiness for EU retailer clients (multi-impact assessment using EF-compliant characterisation factors)
- DQR reporting (mandatory under PACT from end-2027)
- SBTi FLAG integration for food/agriculture emission tracking alongside energy balance
- Platform-level L2 review refresh with ISSA 5000 alignment

**Cost:** £15K–30K development  
**Dependencies:** PACT technical specification stability; PEFCR availability for relevant food categories

### Implementation Timeline Summary

```
2026                                          2027
Q2      Q3      Q4      Q1      Q2      Q3      Q4
│       │       │       │       │       │       │
├──Phase 1──┤   │       │       │       │       │
│  DEFRA +  │   │       │       │       │       │
│  Climatiq │   │       │       │       │       │
│  Deimos   │   │       │       │       │       │
│  MVP      │   │       │       │       │       │
│           ├──Phase 2──┤       │       │       │
│           │ CarbonCloud│      │       │       │
│           │ Product PCFs      │       │       │
│           │ Agribalyse│       │       │       │
│           │           ├──Phase 3──────┤       │
│           │           │ Cool Farm     │       │
│           │           │ openLCA/ecoinv│       │
│           │           │ L2 Audit      │       │
│           │           │               ├──Phase 4──────┤
│           │           │               │ MHHS (May '27)│
│           │           │               │ UK food EF DB │
│           │           │               │ REGO integrat.│
│           │           │               │       ├─Phase 5─
│           │           │               │       │ PACT
│           │           │               │       │ PEF
──────────────────────────────────────────────────────────
Key dates:     │ISSA 5000│    │MHHS     │GHG Protocol│
               │Dec 2026 │    │May 2027 │revision    │
```

---

## 10. Key Risks and Mitigations

### Technical Risks

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| **ecoinvent API still in [closed beta](https://docs.api.ecoinvent.org)** | High | Medium — delays direct API integration | Use Agribalyse (free, 2,500 food products) + DEFRA as initial background layer; openLCA IPC with downloaded ecoinvent database as interim |
| **CarbonCloud API pricing prohibitive** | Medium | High — blocks primary food PCF capability | Fall back to Agribalyse + openLCA self-hosted calculation; higher development cost but no API dependency |
| **openLCA gRPC stability** | Medium | Medium — affects novel product calculations | Run openLCA server in Docker container with health monitoring; Brightway2 Python microservice as alternative backend |
| **MHHS data access complexity** | Medium | Medium — delays temporal energy verification | Accept annual SECR data as interim; MHHS is mandatory for suppliers by May 2027, reducing access friction |

### Market Risks

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| **Mondra dominance in UK food retail** | High | High — 85%+ of UK grocery uses Mondra | Target suppliers, not retailers directly; provide primary process data that Mondra needs; position as data feeder, not competitor |
| **GHG Protocol revision (H2 2026)** | High | Medium — may change Scope 3 methodology | Modular methodology layer; calculation rules separated from data architecture; can be updated without platform rebuild |
| **REGO reform uncertainty** | Medium | Medium — changes market-based Scope 2 landscape | Deimos already designed to distinguish physical vs contractual; any reform toward bundling/temporal matching strengthens MGS position |
| **South Pole reputational contagion** | Low | Low — indirect exposure through M&S relationship | MGS explicitly excludes offsets from GS calculation; aligns with ISO 14067's explicit offset exclusion |

### Regulatory Risks

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| **[ISSA 5000 effective Dec 2026](https://www.iaasb.org/focus-areas/understanding-international-standard-sustainability-assurance-5000)** | Certain | High — doubled assurance requirements | Build audit trail from day one; calculation metadata records designed for ISSA 5000 from Phase 1 |
| **CSRD Omnibus simplification** | Likely | Medium — may reduce Wave 2/3 scope | Core demand for audit-grade data persists regardless; UK SRS S2 filling regulatory gap for UK-listed companies |
| **UK CBAM (2027)** | Likely | Medium — affects Scope 3 supply chain economics | Deimos energy balance already tracks upstream energy mix; CBAM creates additional demand for MGS data |
| **Green Claims Directive (EU) enforcement timing** | Uncertain | Medium — affects PEF urgency | Phase 5 PEF readiness positioned as contingent build; ISO 14067 sufficient for current EU claims |

### Data Risks

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| **Supplier data quality insufficient** | High | Medium — Bronze-tier outputs limit credibility | Explicit DQ scoring and uncertainty disclosure; start at Bronze, improve to Silver/Gold through engagement; auditors accept disclosed uncertainty |
| **Emission factor inconsistency across databases** | Medium | Medium — different databases produce different results | Document all factor choices; version-control; use consistent methodology within product categories; flag where different sources produce materially different results |
| **SECR data staleness (6–9 months lag)** | High | Low | SECR is baseline; MHHS data provides near-real-time overlay; data vintage recorded on every GS assessment |

---

## 11. Regulatory Timeline

| Date | Event | MGS Impact |
|---|---|---|
| **2025 (already effective)** | [CSRD Wave 1](https://www.geofluxus.com/blog/csrd-timeline-eu-delays) — large public-interest entities >500 employees report FY2024 | Wave 1 companies already reporting; establishes assurance demand baseline |
| **H2 2026** | [GHG Protocol corporate/product standard revisions](https://www.carbon-direct.com/insights/key-updates-to-ghg-protocol-and-sbti-what-companies-need-to-know) (drafts for consultation) | Monitor for mandatory primary data requirements; MGS methodology layer designed for modular update |
| **15 December 2026** | [ISSA 5000 effective](https://www.iaasb.org/focus-areas/understanding-international-standard-sustainability-assurance-5000); ISAE 3410 withdrawn | Doubled assurance requirements; MGS audit trail must be production-ready |
| **January 2027** | [UK SRS S2 (climate) mandatory for listed companies](https://www.gov.uk/guidance/uk-sustainability-reporting-standards) under FCA CP26/5 (proposed) | UK-listed retailers (Tesco, Sainsbury's, M&S) require climate disclosure; Deimos data feeds reporting |
| **2027** | [UK CBAM implementation](https://icapcarbonaction.com/en/news/uk-announces-major-policy-decisions-and-launches-new-consultations-ets-expansion) — carbon border adjustment for steel, aluminium, cement, ceramics, glass, hydrogen | Affects Scope 3 supply chain energy economics; creates demand for upstream energy balance data |
| **May 2027** | [MHHS full rollout completion](https://www.smsenergy.com/insights/half-hourly-settlement-is-here-what-it-means-for-your-business-and-what-to-do-about-it/) | All UK electricity meters settled half-hourly; enables Deimos 24/7 CFE verification |
| **End 2027** | [PACT DQR requirements become mandatory](https://www.carbon-transparency.org/pact-methodology) | B2B PCF exchanges must include full data quality ratings; MGS Phase 5 deliverable |
| **2028** | [CSRD Wave 2](https://www.geofluxus.com/blog/csrd-timeline-eu-delays) — large EU companies >1,000 employees report FY2027 (delayed by Stop-the-Clock) | Major expansion of CSRD reporting population; significant new client demand |
| **2028** | [SBTi Corporate Net-Zero Standard V2.0](https://sciencebasedtargets.org/net-zero) expected in effect | Mandatory hourly or locally-matched renewable electricity; Deimos temporal matching capability critical |
| **2027–2028** | [EF database v4.0](https://ukft.org/pef-update-may25/) expected (3,200 datasets) | Background database upgrade for PEF-compliant studies; MGS Agribalyse layer supplemented |
| **2028** | [UK ETS expansion](https://icapcarbonaction.com/en/news/uk-announces-major-policy-decisions-and-launches-new-consultations-ets-expansion) — Maritime (2026), Energy-from-Waste (2028) | Broader UK ETS coverage provides more verified Scope 1 data to Deimos |
| **2026–2028** | [EU Green Claims Directive](https://www.carbonfact.com/blog/policy/green-claims-directive-fashion) (if enacted) enforcement | PEF or equivalent required for consumer environmental claims; drives Phase 5 PEF readiness |

---

## Appendix A: Glossary

| Term | Definition |
|---|---|
| **CEBS** | Corporate Energy Balance Score — Deimos composite output driving GS issuance |
| **CFP / PCF** | Carbon Footprint of a Product / Product Carbon Footprint — sum of GHG emissions over a product's life cycle, in kg CO2e |
| **DQ1–DQ5** | Data Quality levels from primary measured (DQ1) to spend-based proxy (DQ5) |
| **EAC** | Energy Attribute Certificate — market instrument conveying attributes about 1 MWh of electricity generation (REGO, GO, I-REC) |
| **EnPI / EnB** | Energy Performance Indicator / Energy Baseline — ISO 50001 quantitative metrics for energy performance |
| **GS** | Green Square — MGS unit representing 100g CO2e of verified transition action |
| **MHHS** | Market-wide Half Hourly Settlement — Ofgem reform for granular electricity consumption data |
| **PDS** | Primary Data Share — PACT metric for % of footprint from primary data |
| **REGO** | Renewable Energy Guarantee of Origin — UK certificate for 1 MWh of renewable generation, administered by Ofgem |
| **SECR** | Streamlined Energy and Carbon Reporting — UK annual mandatory energy/carbon disclosure in statutory accounts |

---

*Architecture specification compiled March 2026 from research notes 08–11. All factual claims cite primary sources via inline links. This document is version-controlled; future updates will track GHG Protocol revision outcomes, ISSA 5000 implementation guidance, and MHHS rollout progress.*
