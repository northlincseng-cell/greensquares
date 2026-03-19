# LCA Standards and Methodology
## Research for My Green Squares (MGS) Sustainability Platform

**Research Date:** March 2026  
**Purpose:** Deep-dive into LCA standards and methodology to inform MGS's internal LCA and mass energy balance system for product-level carbon footprinting. Outputs must be credible for CSRD assurance by Big 4 auditors, trusted by corporate clients, and aligned with GHG Protocol, SBTi, and CCP standards.

---

## Table of Contents

1. [ISO 14040:2006 and ISO 14044:2006 — The LCA Framework](#1-iso-140402006-and-iso-140442006)
2. [ISO 14067:2018 — Product Carbon Footprint](#2-iso-140672018)
3. [PAS 2050:2011 — BSI Product Carbon Footprint](#3-pas-20502011)
4. [EU Product Environmental Footprint (PEF)](#4-eu-product-environmental-footprint-pef)
5. [GHG Protocol Product Standard](#5-ghg-protocol-product-standard)
6. [Practical Requirements for MGS](#6-practical-requirements-for-mgs)
7. [Standards Hierarchy and Decision Framework for MGS](#7-standards-hierarchy-and-decision-framework)

---

## 1. ISO 14040:2006 and ISO 14044:2006

### Overview

[ISO 14040](https://www.iso.org/standard/37456.html) and [ISO 14044](https://www.iso.org/standard/38498.html) are the foundational international standards for Life Cycle Assessment. They work as a pair: ISO 14040 provides principles and framework; ISO 14044 specifies detailed requirements and guidelines. Published initially in 1997 and revised in 2006, they received Amendment 1 in 2020. The 2020 Amendment enhanced alignment with ISO 14067 (carbon footprinting) and ISO 14064 (GHG accounting), and clarified treatment of biogenic carbon, land-use change, and carbon storage.

ISO 14040 is not a certification standard — organisations cannot become "ISO 14040 certified." It is a guideline standard. All downstream product carbon footprint standards (ISO 14067, GHG Protocol Product Standard, PAS 2050, PEF) are built upon it.

### The Four Phases of LCA

The [ISO 14040/14044 framework](https://www.decerna.co.uk/knowledge-base/life-cycle-assessment/iso-standards/iso-14040-and-14044/) defines LCA through four interconnected, iterative phases:

| Phase | Core Activities | Key Outputs |
|-------|----------------|-------------|
| **1. Goal and Scope Definition** | Define purpose, intended audience, functional unit, system boundaries, data quality requirements, assumptions | Study mandate, system diagram, cut-off rules |
| **2. Life Cycle Inventory (LCI)** | Collect all input/output data: raw materials, energy, emissions to air/water/soil, waste, co-products | Quantified inventory table |
| **3. Life Cycle Impact Assessment (LCIA)** | Classify and characterise inventory data into impact categories (e.g., GWP, acidification, eutrophication) | Impact category results per functional unit |
| **4. Interpretation** | Identify significant issues, run completeness/sensitivity/consistency checks, draw conclusions | Recommendations, limitations, uncertainty statement |

The phases are **iterative** — results from Phase 3 often require revisions to the system boundary or additional data collection in Phase 2.

### The Seven Fundamental Principles

| Principle | Description |
|-----------|-------------|
| Life Cycle Perspective | Consider the entire life cycle from cradle to grave; prevent burden shifting between stages |
| Environmental Focus | Address environmental aspects and impacts; economic/social aspects are outside scope unless explicitly included |
| Relative Approach | All results relate to the functional unit |
| Iterative Approach | LCA phases interact and inform each other |
| Transparency | Document all choices, assumptions, and limitations with a clear audit trail |
| Comprehensiveness | Consider all relevant environmental issues to identify potential trade-offs |
| Priority of Scientific Approach | Base decisions on natural science; document value choices where science is inconclusive |

### Functional Unit Definition

The functional unit (FU) is the quantified performance of a product system, providing a reference to which all inputs and outputs are related. It must:

- Define precisely **what function** is being assessed and in what quantity
- Be quantifiable (e.g., "1 kg of product delivered to retail shelf" rather than "one product")
- Enable **comparability** across different products or processes serving the same function
- Be accompanied by a **reference flow** — the amount of product required to fulfil the FU

For FMCG products, typical FUs are per kg, per serving, per 100g (aligning well with MGS's "per Green Square = 100g CO2e" framework), or per unit of product at shelf. The choice must be justified in the Goal and Scope.

### System Boundary Requirements

System boundary defines where the assessment starts and stops. Key boundary types used in practice:

| Boundary Type | Scope | Typical Use |
|---------------|-------|-------------|
| **Cradle-to-grave** | Raw material extraction → end-of-life disposal | Full consumer product footprint |
| **Cradle-to-gate** | Raw material extraction → factory gate | B2B, intermediate products, partial CFP |
| **Cradle-to-shelf** | Extraction → retail shelf | Retail/FMCG standard (includes logistics, retail energy) |
| **Cradle-to-cradle** | Full cycle including recycling back into production | Circular economy products |
| **Gate-to-gate** | Manufacturing only | Process optimisation |

ISO 14044 requires **clear justification** for boundary choices. Inclusions and exclusions must be documented and justified. A common cut-off rule permits excluding processes contributing less than 1% of total environmental burden, provided at least 95% of total mass/energy flows are captured.

### Allocation Rules

Allocation is the procedure for partitioning inputs and outputs of a process between co-products. ISO 14044 defines a **hierarchy** that must be followed:

1. **Avoid allocation** — subdivide the process into sub-processes, or expand the system boundary (system expansion / substitution method) to include the function of the co-product
2. If unavoidable, **physical allocation** — allocate based on measurable physical relationships (e.g., mass, energy content, molar weight)
3. If physical relationships cannot be established, **economic allocation** — allocate based on relative economic value (revenue/market value)
4. Other relationships may be used but must be justified

The choice of allocation method can significantly affect results. ISO 14044 requires documenting and justifying the chosen approach. For food processing (e.g., a wheat mill producing flour and bran), mass allocation is common; for joint products with very different economic values (e.g., crude oil refining), economic allocation may be more appropriate.

> **MGS relevance:** For multi-output food production processes (e.g., dairy producing milk and cream), consistent application of the same allocation rule across all products is critical for comparability.

### Critical Review Requirements

[ISO 14071:2024](https://standards.iteh.ai/catalog/standards/cen/c02203d4-bf33-4108-a66b-e3cae9b7392c/en-iso-14071-2024) (updated January 2024) specifies requirements and guidance for critical review of LCA studies, supplementing ISO 14040/44.

Critical review is **mandatory** when:
- The LCA supports **comparative assertions disclosed to the public** (e.g., "Product A is lower-carbon than Product B")
- Stakeholders specifically request independent verification

Critical review types:
- **End-of-study review** — conducted after completion
- **Concurrent review** — conducted during study development (preferred for complex studies)

Review panel requirements for comparative public assertions:
- Must include at least one **independent external expert**
- For studies with significant stakeholder interest: panel must include **interested parties** (e.g., NGOs, consumers, regulators)

Reviewers check that:
- Methodology is consistent with ISO standards and scientifically valid
- Data is appropriate and reasonable relative to study goals
- Interpretations reflect identified limitations
- The study is transparent and verifiable

Output: A **Critical Review Statement** (unambiguous statement of conformity with ISO 14040/44) and a **Critical Review Report** (detailed findings).

### What Makes an LCA "ISO Compliant"?

An LCA is ISO 14040/44 compliant when it:

1. Follows all four phases with required elements documented
2. Applies the seven principles (especially transparency and life cycle perspective)
3. Defines a functional unit, system boundary, and data quality requirements
4. Applies the allocation hierarchy with justification
5. Uses scientifically valid characterisation methods for LCIA
6. Conducts completeness, sensitivity, and consistency checks
7. Undergoes critical review (mandatory for comparative public assertions)
8. Documents all assumptions, limitations, and data sources

**Important note:** ISO 14040 compliance is **self-declared** — there is no certification body or mandatory third-party verification for compliance. The critical review (when required) provides the external check.

---

## 2. ISO 14067:2018

### Overview

[ISO 14067:2018](https://www.iso.org/standard/71206.html) — *Greenhouse gases — Carbon footprint of products — Requirements and guidelines for quantification* — is the specific international standard for product carbon footprinting (PCF). It is built directly on ISO 14040 and ISO 14044, and focuses exclusively on **climate change** as the single impact category. It replaced ISO/TS 14067:2013 and is currently the most authoritative internationally recognised PCF standard. The ISO website flags it as "International Standard to be revised [90.92]" — an updated version is in development but not yet published as of March 2026.

### Key Differences from ISO 14040/44

| Aspect | ISO 14040/44 | ISO 14067 |
|--------|-------------|-----------|
| **Scope** | Multiple environmental impact categories (15+) | Climate change only (kg CO₂e) |
| **Purpose** | General LCA framework | Specific carbon footprint quantification |
| **Impact Assessment** | Must address all relevant categories (GWP, acidification, eutrophication, etc.) | Only GWP via IPCC characterisation factors |
| **Verification** | Required for comparative public assertions | Optional (mentioned as enhancing credibility) |
| **Communication** | Covered within scope | Explicitly excluded — governed by ISO 14026 |
| **Offsets** | Not addressed | Explicitly excluded from CFP calculation |
| **Biogenic carbon** | Must be addressed | Requires separate reporting of biogenic uptake and emissions |

The practical implication: an ISO 14067 PCF study is **faster and cheaper** than a full ISO 14040/44 LCA (typically £3,000–£8,000 vs. £15,000–£50,000+ for a full LCA), but only covers one impact category. For CSRD and regulatory claims, an ISO 14067 study may not be sufficient if other impact categories are material.

### Full vs. Partial Carbon Footprint

| Type | Boundary | Requirement |
|------|----------|-------------|
| **Full CFP** | Cradle-to-grave (complete life cycle) | Required for consumer-facing comparative claims |
| **Partial CFP** | Cradle-to-gate, gate-to-gate, or other defined stages | Permitted if excluded stages are clearly disclosed |

Partial CFPs are common in B2B contexts (e.g., a supplier providing cradle-to-gate data for inclusion in a customer's full CFP). For FMCG retail claims and consumer-facing labels, full (or at minimum cradle-to-shelf) CFPs are expected.

### Specific Requirements Under ISO 14067

**Functional unit and boundaries:**
- Full CFPs require life-cycle-wide boundaries
- Partial CFPs must disclose excluded stages prominently
- Boundary choice drives results enormously (e.g., for electronics, use-phase electricity can represent 80%+ of total footprint; a cradle-to-gate study would miss this entirely)

**Data quality requirements:**
- Lists: time coverage, geographical coverage, technology coverage, precision, completeness, representativeness, consistency, reproducibility
- **Does not specify minimum thresholds** for any of these dimensions — no mandated minimum % primary data
- This is a significant gap: a study using 90% industry-average database values technically complies with ISO 14067

**Biogenic carbon:**
- Must be reported **separately** from fossil GHG emissions
- Biogenic CO₂ uptake (carbon sequestered during crop growth) and biogenic CO₂ emissions (released at end-of-life) must be distinguished
- Land-use change emissions must be considered

**Allocation:**
- Follows ISO 14044 hierarchy (avoid → physical → economic)
- Must document and justify the chosen approach

**Impact assessment:**
- Uses IPCC GWP characterisation factors
- Standard does not mandate which IPCC Assessment Report or time horizon (20-year vs. 100-year GWPs)
- Best practice: use GWP100 from IPCC AR6 (2021) — this is what most current auditors expect

**Electricity treatment:**
- Permits: consumption mix (average grid), supplier-specific, or contractual instruments (REGOs/PPAs)
- The choice significantly affects results for energy-intensive products

### Reporting Requirements (Clause 7)

A CFP Study Report must include:
- Goal and scope (what was assessed, why, intended audience)
- System boundary with diagram
- Functional unit definition and justification
- Data quality assessment
- Allocation procedures with justification
- Cut-off criteria (what was excluded as negligible, and why)
- Impact assessment method (IPCC version, time horizon)
- Results with biogenic carbon reported separately
- Uncertainty analysis
- Limitations and assumptions
- Interpretation of significant issues

### Verification Requirements (Clause 8) — The Critical Gap

ISO 14067 makes **verification optional**: *"A critical review facilitates understanding and enhances the credibility of CFP; if any review shall follow ISO/TS 14071."*

In practice this means:
- No requirement for third-party verification
- No mandatory site visits
- No requirement for accredited verifiers
- No requirement for public registration
- No enforcement mechanism for comparative claims

**Contrast with EPDs (Environmental Product Declarations under ISO 14025):** EPDs require mandatory third-party verification, site visits to validate primary data, accredited verifiers, and publication in a public registry.

> **MGS implication:** For outputs intended to support CSRD assurance, MGS will need to implement voluntary third-party verification to fill this gap, since ISO 14067 alone does not guarantee the audit trail required by Big 4 assurance teams.

### What You Can and Cannot Claim

**Can claim:**
- "The carbon footprint of [product] is X kg CO₂e per kg, calculated in accordance with ISO 14067:2018"
- "The carbon footprint covers [specific life cycle stages] and excludes [stated stages]"
- Comparisons between products **only if** Annex B conditions are met (identical PCRs, equivalent FUs, boundaries, data quality, allocation, impact methods, and assumptions)

**Cannot claim:**
- Net-zero or carbon neutral on the basis of ISO 14067 alone (offsetting is explicitly excluded from calculations)
- Environmental superiority on dimensions other than climate
- Broad comparisons without meeting Annex B conditions

**Communication:**
- Communication rules (how to report on labels, in marketing) are governed by **ISO 14026** — ISO 14067 is silent on this
- Claimed conformance with ISO 14067 must be supported by a CFP study report

### Relationship to EU PEF

ISO 14067 and PEF are complementary but distinct:
- ISO 14067 covers **climate change only**; PEF covers **16 environmental impact categories**
- PEF is more prescriptive (mandated datasets, mandatory PEFCRs where available)
- PEF is more demanding on data quality (EF-compliant datasets required)
- ISO 14067 is accepted as the methodological basis for a PCF component within a PEF study
- EU Green Claims Directive (if enacted) will likely accept ISO 14067-compliant PCFs as one approved method for substantiating climate claims

---

## 3. PAS 2050:2011

### Overview and History

[PAS 2050](https://www.bsigroup.com/en-GB/standards/pas-2050/) (Publicly Available Specification 2050) was published by BSI British Standards in 2008 and revised in 2011. Co-sponsored by the Carbon Trust and DEFRA, it was the **world's first consensus-based internationally applicable standard for product carbon footprinting**. It directly influenced both ISO 14067 and the GHG Protocol Product Standard — both standards drew extensively on PAS 2050's methodology during development.

### Key Characteristics

| Feature | PAS 2050:2011 |
|---------|--------------|
| **Coverage** | GHG emissions only (same as ISO 14067) |
| **Life cycle** | Cradle-to-grave (B2C products); cradle-to-gate (B2B intermediate products) |
| **Boundary** | System boundary consistent with BSI supplementary requirements (sector-specific rules) |
| **Data requirement** | Primary data required for processes owned/controlled by organisation AND where supplier contributes >10% of total |
| **Allocation default** | Economic allocation as default (contrasting with ISO 14067's physical-first hierarchy) |
| **Capital goods** | Excluded by default (optional) — this differs from GHG Protocol which requires inclusion |
| **Land use change** | Direct LUC included; indirect LUC excluded (same as GHG Protocol) |
| **Time period** | 100-year GWP as default |

### How PAS 2050 Differs from ISO 14067

| Dimension | PAS 2050 | ISO 14067 |
|-----------|----------|-----------|
| **Prescriptiveness** | More prescriptive, less room for interpretation | More general, more methodological flexibility |
| **Allocation default** | Economic allocation preferred | Physical allocation first (ISO 14044 hierarchy) |
| **Capital goods** | Excluded by default | Included (if significant) |
| **Recording vs reporting** | Focused on internal recording; communication not required | No communication requirements (see ISO 14026) |
| **Verification** | Not required for conformance claim | Optional |
| **Sector-specific rules** | "Supplementary Requirements" (SRs) — industry-specific rules | "CFP-Product Category Rules" (CFP-PCRs) via ISO/TS 14027 |
| **Cut-off** | 95% coverage rule (at least 95% of product life cycle mass/energy must be included) | 1% insignificance threshold with justification |

The difference in allocation defaults can produce materially different results: for a dairy product, physical (mass) allocation would distribute more burden to cheese than whey; economic allocation to cheese would differ if market prices diverge significantly.

### Relationship with GHG Protocol Product Standard

The GHG Protocol Product Standard was published simultaneously in 2011 and **built directly on PAS 2050**. Key difference: the GHG Protocol adds explicit **public reporting requirements** (PAS 2050 only requires recording/documentation). The cross-pollination between the two standards during development means their methodological foundations are substantially aligned; only minor differences remain (see Section 5 for GHG Protocol details).

### Is PAS 2050 Still Relevant in 2026?

PAS 2050 retains relevance in specific contexts, but its primacy has diminished:

| Context | Assessment |
|---------|------------|
| **UK regulatory use** | No current UK regulation mandates PAS 2050 specifically |
| **Customer requirements** | Some UK supply chain procurement requirements still cite PAS 2050 — particularly in food retail |
| **International comparability** | ISO 14067 is now the preferred international standard; PAS 2050 is increasingly seen as legacy |
| **Auditor preference** | Big 4 auditors in the UK will accept either PAS 2050 or ISO 14067, but ISO 14067 is increasingly the reference |
| **Legacy programmes** | Carbon Trust certification, some UK retailer programmes still reference PAS 2050 |
| **New product footprinting** | ISO 14067 is the recommended starting point for new studies |

[SimaPro's 2025 guidance](https://simapro.com/insights/product-carbon-footprint-standards-which-standard-to-choose/) confirms: "ISO 14067 can be considered the international reference standard for conducting PCF" and is the all-rounder standard to use absent specific regulatory requirements. PAS 2050 "is widely used and is considered the first carbon footprint standard used internationally" but is now largely retained for sector-specific historical reasons.

> **MGS recommendation:** Design the MGS methodology around ISO 14067 as the primary PCF standard, noting alignment/consistency with PAS 2050 where relevant. This ensures backward compatibility with legacy programmes while meeting current international expectations.

---

## 4. EU Product Environmental Footprint (PEF)

### What PEF Is

The Product Environmental Footprint (PEF) is a methodology developed by the European Commission to standardise how companies measure and communicate the environmental performance of products. It is based on LCA (ISO 14044 methodology) but is far more prescriptive, mandating specific databases, impact categories, and data quality requirements.

PEF first introduced in 2013 (pilot phase 2012–2019), then transitional period 2019–2025. The method was **finalised and approved by the European Commission in May 2025**, with updates to the methodology planned for 2026 and a new supporting database expected 2027–2028.

### PEF vs ISO 14067: Key Differences

| Dimension | PEF | ISO 14067 |
|-----------|-----|-----------|
| **Impact categories** | 16 mandatory categories | Climate change only |
| **Prescriptiveness** | Very high — mandated EF-compliant datasets, PEFCRs, data quality scoring | Low — methodological flexibility |
| **Databases** | Must use EF-compliant datasets (Environmental Footprint database) | Any reputable background database (ecoinvent, Agribalyse, etc.) |
| **Data quality** | Quantitative Data Quality Ratio (DQR) required; EC recommends caution with DQR > 3 | Qualitative data quality assessment; no minimum thresholds |
| **Product-specific rules** | PEFCRs define mandatory rules for specific product categories | CFP-PCRs optional |
| **Comparability** | Designed for cross-product comparison within same category | Not designed for cross-study comparison without full Annex B alignment |
| **Status** | Voluntary (with regulatory potential) | Internationally recognised standard |
| **Effort** | Significantly higher (6-18 months typical) | Lower (2-6 months typical) |

### PEF's 16 Impact Categories

PEF requires assessment across all 16 Environmental Footprint (EF) impact categories:

1. Climate change (GWP) — expressed as kg CO₂e
2. Ozone depletion
3. Human toxicity (cancer)
4. Human toxicity (non-cancer)
5. Particulate matter
6. Ionising radiation
7. Photochemical ozone formation
8. Acidification
9. Eutrophication (terrestrial)
10. Eutrophication (freshwater)
11. Eutrophication (marine)
12. Ecotoxicity (freshwater)
13. Land use
14. Water use
15. Resource use (minerals and metals)
16. Resource use (fossils)

### PEF Category Rules (PEFCRs)

PEFCRs are product-specific rules that define, for a given product category:
- The mandatory functional unit
- System boundary requirements
- Data quality requirements
- Which processes must use primary vs. secondary data
- Hotspot processes requiring specific modelling
- Weighting/normalisation for aggregated scores

**PEFCRs published or approved as of March 2026:**
- Apparel and footwear: **Final PEFCR v3.1 approved May 2025** by the European Commission
- Cut flowers and potted plants: Published
- Synthetic turf: Published
- Battery electric vehicles: In development
- Food and beverage: Various PEFCRs in development (no universal FMCG PEFCR yet)

For food products without a published PEFCR, companies conducting PEF studies must follow the general PEF Guide and document their modelling choices more extensively.

### EU Green Claims Directive Status (Critical Update)

The Green Claims Directive (proposed March 2023) was designed to require companies to substantiate voluntary environmental claims using recognised methodologies, with PEF as the reference framework.

**Current status (as of March 2026):** The directive is **stalled**. The European Commission warned it might withdraw the proposal unless microenterprises (fewer than 10 employees or under €2M revenue) are excluded. [Carbonfact's January 2026 analysis](https://www.carbonfact.com/blog/policy/green-claims-directive-fashion) confirms: "As of June 2025, the implementation of the Green Claims Directive is uncertain... legislative process paused."

Key timeline:
- March 2023: Commission published draft directive
- March 2024: Formally adopted by European Parliament and Council
- 2024–2026: Transposition into national laws (implementation period)
- **Current status: Formal negotiations paused; full enforcement date indefinite**

Despite the stall, the regulatory direction of travel is clear: the EU intends to make life-cycle-based substantiation of environmental claims mandatory for consumer-facing products. PEF or equivalent methodology (ISO 14067 for climate-specific claims) will ultimately be required.

### CSRD Reference to PEF

The Corporate Sustainability Reporting Directive (CSRD) references PEF as **one option** (not the only option) for assessing environmental impacts. [UKFT's May 2025 update](https://ukft.org/pef-update-may25/) confirms: "The PEF method is also referenced in the Corporate Sustainability Reporting Directive (CSRD) as one option for assessing environmental impacts across a company's operations and supply chain."

### Implications for MGS Clients Selling to EU Retailers

| Scenario | Implication |
|----------|-------------|
| Client makes explicit environmental claims (carbon labels, "eco" claims) on EU-sold products | Green Claims Directive (when enacted) will require substantiation via PEF or equivalent; interim requirement to use ISO 14067 or other recognised standard |
| Client reports under CSRD | PEF is one acceptable methodology; ISO 14067 for climate, full PEF for multi-category |
| Client sells to EU retailer with sustainability procurement requirements | Major EU retailers (Carrefour, Lidl, Aldi, etc.) increasingly require PCF data aligned with PEF or ISO 14067 |
| Client product category has a PEFCR | Should use PEF methodology — it provides regulatory "safe harbour" for environmental claims |
| Client product category has no PEFCR | ISO 14067 (for climate) or general PEF Guide study are both acceptable |

> **MGS system design implication:** The MGS LCA engine should produce results compatible with ISO 14067 **and** structured to facilitate PEF compliance for clients requiring it. The 16 PEF impact categories can be computed using the same LCI data if EF-compliant databases are used. Designing the database layer to support EF-compliant datasets from the outset (e.g., using Ecoinvent with EF 3.1 characterisation factors) provides maximum flexibility.

---

## 5. GHG Protocol Product Standard

### Overview

The [GHG Protocol Product Life Cycle Accounting and Reporting Standard](https://ghgprotocol.org/product-standard) was published in 2011 by WRI (World Resources Institute) and WBCSD (World Business Council for Sustainable Development). It is the most widely used framework for corporate GHG accounting globally — [97% of S&P 500 companies reporting to CDP](https://www.carbon-direct.com/insights/key-updates-to-ghg-protocol-and-sbti-what-companies-need-to-know) use GHG Protocol accounting.

The Product Standard complements the corporate-level GHG Protocol Corporate Accounting Standard (Scope 1/2/3) by providing product-level accounting. It is **currently under revision** — drafts for public consultation were expected during 2025, with final standards and guidance timed for the second half of 2026.

### How It Maps onto ISO Standards

| Feature | GHG Protocol Product Standard | ISO 14040/44 | ISO 14067 |
|---------|-------------------------------|--------------|-----------|
| **Methodological basis** | Builds on ISO 14040/44 principles | Foundation standard | Builds on ISO 14040/44 |
| **Scope** | GHG emissions and removals (climate change) | Multiple environmental impacts | Climate change only |
| **Public reporting requirements** | Explicit and mandatory | Not covered | Not covered |
| **Assurance requirements** | First or third-party assurance required | Critical review for comparative assertions | Verification optional |
| **Data quality** | Five Data Quality Indicators; qualitative uncertainty statement required | Data quality documentation required | Data quality documentation required |
| **Capital goods** | **Required** to include | Not specified | Included if significant |
| **Allocation default** | Physical first; then economic | Physical first; then economic | Physical first; then economic |
| **Offsets** | Shall **not** be included in inventory results; reported separately | Not addressed | Excluded |
| **Performance tracking** | Required over time with consistent unit of analysis | Not required | Not required |

The key differentiator of the GHG Protocol Product Standard versus ISO 14067 and PAS 2050 is its **mandatory public reporting requirements** and its explicit connection to the corporate Scope 3 framework.

### The Five Calculation Approaches

The GHG Protocol distinguishes five methods for calculating Scope 3 Category 1 (Purchased Goods and Services) emissions, in descending order of data quality:

| Approach | Description | Data Quality | Best For |
|---------|-------------|-------------|---------|
| **1. Supplier-specific** | Cradle-to-gate GHG inventory from actual supplier (Product Standard-compliant) | Highest | Tier 1 strategic suppliers with LCA capability |
| **2. Hybrid** | Combines supplier-specific Scope 1+2 data with secondary data for upstream emissions | High | Suppliers able to provide Scope 1+2 but not full LCA |
| **3. Average-data (activity-based)** | Mass or volume of goods × industry-average emission factor (kg CO₂e/kg) | Medium | Where activity data available but no supplier-specific data |
| **4. Spend-based** | Economic value of goods × emission factor per unit currency (kg CO₂e/£) | Low | Last resort; poor accuracy; sensitive to price fluctuations |
| **5. Fuel/energy-based** | Energy consumption × emission factor | Medium | Fuel use specifically |

The GHG Protocol **strongly encourages** improving from spend-based toward supplier-specific over time. Under forthcoming GHG Protocol revisions (expected finalisation 2026–2027), spend-based data is expected to face stricter requirements, with mandatory disaggregation of spend-based vs. activity-based data and multi-year data quality improvement plans.

> **MGS relevance:** The MGS platform operates at the intersection of approaches 1-3. By providing product-level PCFs, MGS enables client companies to move from spend-based to supplier-specific data for Scope 3 reporting — this is a core value proposition.

### Data Quality Indicators (DQIs)

The GHG Protocol Product Standard defines five DQIs:
1. **Technological representativeness** — does the data reflect the actual technology used?
2. **Temporal representativeness** — how recent is the data?
3. **Geographical representativeness** — does the data reflect the actual geography of production?
4. **Completeness** — what fraction of relevant processes are included?
5. **Reliability** — is the data from primary measurements, literature, or estimation?

Each DQI should be assessed and documented. The qualitative uncertainty statement (required for public reporting) must acknowledge where uncertainty is highest.

### Uncertainty Requirements

Under the Product Standard:
- A **qualitative uncertainty statement** must be included in all public inventory reports
- The statement must acknowledge the most significant sources of uncertainty (data gaps, proxy data, allocation assumptions)
- Quantitative uncertainty analysis (e.g., Monte Carlo simulation) is recommended but not mandatory
- Typical product LCA uncertainty at ±15–35% at 95% confidence interval — results should never be reported with false precision (e.g., reporting 3.47 kg CO₂e when uncertainty is ±20%)

> **Best practice for MGS outputs:** Report results rounded to no more than 2 significant figures. Include a data quality tier (e.g., "Tier A: >60% primary data; Tier B: 30–60% primary; Tier C: <30% primary"). Flag uncertainty prominently.

### Reporting and Verification Requirements

Public reporting under the GHG Protocol Product Standard requires:
- Contact information and product name/description
- System boundary (cradle-to-grave or cradle-to-gate, with justification)
- Functional unit
- Inventory results (total GHG emissions and removals, by life cycle stage)
- Biogenic carbon separately
- Carbon stored in product (for intermediate products)
- Data quality statement
- Assurance statement (required; first or third-party)

**Assurance requirements:** The Product Standard requires all publicly reported inventories to be **assured by first or third party**. The assurance statement must include:
- Level of assurance achieved (limited or reasonable)
- Whether first or third party
- Summary of assurance process
- Relevant competencies of assurance providers

Under CSRD, the applicable assurance standard is **ISSA 5000** (new IAASB standard for sustainability assurance) or equivalent (ISAE 3000/3410). Big 4 auditors conducting CSRD limited assurance apply these standards and will check whether product-level PCF data feeding into corporate Scope 3 disclosures is credible and well-documented.

---

## 6. Practical Requirements for MGS

### What Data Inputs Does a Credible Product LCA Need?

A credible product LCA for a retail FMCG product requires the following data by life cycle stage:

| Life Cycle Stage | Required Data Inputs | Primary vs Secondary |
|-----------------|---------------------|---------------------|
| **Agricultural raw materials** | Crop species, origin country/region, farming system (conventional/organic), yield, fertiliser type and rate, pesticide use, irrigation, land type | Primary preferred for key hotspot ingredients (>5% of footprint); secondary (Ecoinvent, Agribalyse) acceptable for minor ingredients |
| **Animal products** | Species, production system (intensive/extensive/organic), feed composition, manure management, herd size, milk/meat yield | Primary data significantly improves accuracy; secondary for background |
| **Processing/Manufacturing** | Energy consumption (electricity and heat) by type, water consumption, processing aids, packaging materials, waste/by-product quantities | Primary data required for Tier 1 manufacturers under all major standards |
| **Packaging** | Material type, weight, recycled content, end-of-life scenario (recycling rate in destination market) | Secondary for material emission factors; primary for weights |
| **Transport (inbound)** | Distance (km), transport mode (road/rail/sea/air), load factor | Primary for significant freight; secondary emission factors acceptable |
| **Retail/Distribution** | Distance to distribution centre and retail, cold chain vs. ambient, energy use at warehouse/store | Secondary acceptable (UK/EU retail industry averages exist) |
| **Consumer use** | Preparation method, cooking time/energy, food waste rate at consumer | Secondary (WRAP food waste data, energy use surveys) acceptable |
| **End of life** | Destination of packaging (recycling, landfill, incineration, composting), food waste destination | Country-level statistics acceptable |

### Data Quality Tiers for FMCG Retail

| Tier | Description | Auditor Assessment |
|------|-------------|-------------------|
| **Gold (Tier 1)** | >60% primary data; all key hotspot processes use supplier-specific data; ISO 14067 or GHG Protocol compliant study report; third-party verified | Fully acceptable for CSRD assurance and comparative claims |
| **Silver (Tier 2)** | 30–60% primary data; key processing and packaging use primary data; agricultural inputs from verified regional databases; ISO 14067 compliant report | Acceptable for CSRD assurance with clear uncertainty disclosure; not suitable for precise comparative claims |
| **Bronze (Tier 3)** | <30% primary data; largely based on Ecoinvent/Agribalyse averages with product recipe (BOM) as primary input; process-based LCA methodology | Acceptable for hotspot identification and directional benchmarking; requires explicit uncertainty caveat; suitable as starting point for client onboarding |

The majority of existing platform LCAs (Mondra, CarbonCloud, Foundation Earth) start at Bronze/Silver tier using automated calculation from Bill of Materials, then improve toward Gold through supplier engagement.

### Minimum Viable LCA for CSRD Assurance Acceptance

Based on current Big 4 auditor practice and CSRD guidance, the minimum viable product LCA that would be accepted for CSRD limited assurance must:

**Methodological requirements:**
1. Follow a recognised standard (ISO 14067, GHG Protocol Product Standard, or PEF where PEFCR exists)
2. Define a clear, quantified functional unit
3. Document system boundary (cradle-to-gate is acceptable for Scope 3 supplier data; cradle-to-shelf/grave for consumer-facing claims)
4. Apply consistent, documented allocation rules
5. Use background emission factors from a recognised LCI database (Ecoinvent, Agribalyse, USDA, etc.) with version documentation
6. Include a data quality assessment (qualitative acceptable; quantitative preferred)
7. Produce a documented CFP study report meeting ISO 14067 Clause 7 requirements

**Data requirements:**
1. Bill of Materials (BOM) with ingredient weights — primary data from client
2. Processing energy data (kWh electricity, MJ heat per tonne product) — primary from client
3. Packaging material types and weights — primary from client
4. Transport modes and distances — primary from client for key routes
5. Background emission factors from recognised database for raw material LCI

**Governance/audit trail requirements:**
1. Methodology documented in a version-controlled method document
2. Calculation model auditable (traceable from input data to output result)
3. Assumptions and limitations explicitly documented
4. Data sources cited with version numbers and access dates
5. Results reviewed internally before use in CSRD reports

**Verification:**
- For CSRD Scope 3 inclusion: first-party verification (internal review by qualified sustainability professional) is sufficient at limited assurance stage
- For consumer-facing claims or comparative assertions: third-party verification recommended

> **Critical point:** The auditor is not typically verifying individual product LCAs in detail during CSRD limited assurance. They are verifying the **system, methodology, and governance framework**. An auditable, well-documented, methodologically sound platform — even if operating at Silver tier — will pass limited assurance if the uncertainty is disclosed. What fails audits is undocumented methodology, untraceable calculations, and unsupported comparative claims.

### How Existing Platforms Handle This

#### Mondra (UK, food retail focus)

[Mondra](https://www.mondra.com) provides AI-powered product-level carbon intelligence for food retailers and suppliers. Key methodology features:
- Co-founded the [BRC Mondra Coalition](https://brcmondracoalition.com/standards) — a sector-wide programme harmonising product footprinting for UK food industry
- LCA Methodology V7.1 (February 2025) — open standard published for peer review
- Aligns with PACT (Partnership for Carbon Transparency), SBTi FLAG reporting, and PEF Category Rules
- Integrates with existing ERP/specification data — "processes thousands of LCAs in under 4 hours"
- Cradle-to-gate (cradle to retail shelf) methodology
- Partnership with ImpactBuying (Dutch) for supply chain data
- Member of Global Sustainability Transition Alliance (GSTA) for EU harmonisation

The BRC Mondra Coalition methodology is publicly available at v7.1 and has undergone extensive consultation (including NGOs and agencies). This level of transparency — open methodology, versioned, peer-reviewed — is the gold standard for auditor acceptance.

#### CarbonCloud (Sweden, food sector)

[CarbonCloud](https://carboncloud.com/brief-methodology/) calculates climate footprints from cradle to retail shelf (excluding consumer use and disposal) for food products. Key methodology features:
- **Consistent treatment across all products** — allocation, system boundaries, and energy systems applied identically for all calculations, enabling fair cross-product comparisons
- Regional electricity data — accounts for geographical variation (e.g., Swedish grid vs. German grid)
- Combines generic secondary data (national statistics) with primary recipe/supplier data
- Results expressed per kg of product
- Focused on **comparability** — all food products calculated the same way

CarbonCloud's key insight: standard LCAs often cannot be compared because practitioners make different choices on allocation, system boundaries, and energy systems while all remaining "ISO compliant." CarbonCloud forces consistency to enable genuine comparison.

#### Foundation Earth (UK, food and drink)

[Foundation Earth](https://blonksustainability.nl/launch-of-foundation-earths-lca-methodology-for-evironmental-footprint-labelling) launched a harmonised, PEF-friendly LCA methodology for food and drink in March 2023 (developed with Blonk Sustainability and the Deutsches Institut für Lebensmitteltechnik). Key features:
- **16 PEF impact categories** — full environmental score, not just carbon
- Open-source methodology
- Designed for front-of-pack environmental scoring
- Provides guidance on primary and secondary data sources by product type
- Simplified PEF data quality assessment approach
- Enables comparison between different food chains producing the same product type
- Builds on existing PEFCRs and PEF Guidance (with own rules where PEFCRs don't exist)

Foundation Earth's approach is more ambitious than Mondra/CarbonCloud (multi-impact vs. carbon-only) but consequently more data-intensive and slower.

#### PACT Methodology v3 (Cross-industry, B2B supply chains)

The [PACT Methodology v3](https://www.carbon-transparency.org/pact-methodology) (Partnership for Carbon Transparency, WBCSD) launched April 2025 as an industry-agnostic methodology for calculating and exchanging **cradle-to-gate PCFs**. It is designed for B2B Scope 3 data exchange. Key features:
- Aligns with GHG Protocol Product Standard and ISO 14067
- Cradle-to-gate scope (designed for supplier-to-customer data exchange)
- Two reliability metrics: **Primary Data Share (PDS)** and **Data Quality Ratings (DQRs)**
- PDS must be reported with all PCFs; DQRs required by end-2027
- Technical API specification for machine-to-machine PCF data exchange
- Third-party verification required for "PACT Conformant" status

PACT is becoming the de facto B2B Scope 3 data exchange standard. If MGS clients are supplying PCF data to larger corporate customers for their Scope 3 reporting, PACT Conformant PCFs are increasingly what those customers require.

---

## 7. Standards Hierarchy and Decision Framework for MGS

### The Standards Landscape (Relationships)

```
                    ISO 14040:2006 / ISO 14044:2006
                     (LCA Principles and Framework)
                              |
              ┌───────────────┼────────────────────────┐
              │               │                        │
         ISO 14067        PAS 2050:2011           GHG Protocol
          :2018            (carbon only,         Product Standard
        (carbon           UK-origin,             (carbon only,
         only)            B2C + B2B)              public reporting)
              │               │                        │
              └───────────────┴────────────────────────┘
                              │
                    EU PEF / PEFCRs
               (16 impact categories,
              EF-compliant datasets,
              product-specific rules)
```

All product carbon footprint standards are **layered on top of ISO 14040/44**. PEF is the most prescriptive, ISO 14067 the most flexible, with PAS 2050 and GHG Protocol occupying middle ground.

### Standards Decision Matrix for MGS

| Use Case | Recommended Standard | Rationale |
|----------|---------------------|-----------|
| **Default product PCF for FMCG clients** | ISO 14067:2018 | International reference; accepted by all auditors; flexible enough for platform-scale automation |
| **UK retail supply chain (BRC members)** | BRC Mondra Coalition methodology (ISO 14067 + GHG Protocol compatible) | Industry-specific open standard; pre-accepted by UK retailers; BRC membership |
| **EU retailer clients with Green Claims obligations** | PEF (where PEFCR exists) or ISO 14067 (where no PEFCR) | PEF provides regulatory safe harbour for EU claims; required for Green Claims Directive compliance when enacted |
| **B2B supplier data exchange (Scope 3)** | PACT Methodology v3 (aligned with GHG Protocol + ISO 14067) | De facto standard for B2B PCF exchange; machine-readable; required by growing number of corporate buyers |
| **CSRD assurance (Scope 3 Category 1)** | GHG Protocol Product Standard (supplier-specific method) | Directly feeds into Scope 3 corporate reporting; accepted by Big 4 |
| **Corporate client Scope 3 reporting** | GHG Protocol Scope 3 Standard (Category 1) | Direct standard for corporate-level disclosures |

### Recommended MGS Methodology Architecture

For a system targeting CSRD assurance credibility, the following approach is recommended:

**Core calculation engine:**
- Follows ISO 14067:2018 principles
- System boundary: cradle-to-shelf (aligned with GHG Protocol supplier-specific method, cradle-to-gate for intermediate products)
- Functional unit: per kg of finished product (enabling per-100g CO2e calculation for Green Square conversion)
- Allocation: ISO 14044 hierarchy (physical first, economic second) — document clearly

**Data architecture:**
- Background LCI database: Ecoinvent (current version, EF-compliant characterisation factors) + Agribalyse for food products
- Foreground (primary) data: client BOM, processing energy, packaging weights, transport data
- Emission factors: documented and version-controlled; updated annually

**Data quality framework:**
- Adopt PACT-style PDS (Primary Data Share) metric — percentage of product footprint calculated from primary data
- Adopt tiered DQR (Data Quality Rating) per ingredient/process
- Flag Tier C (low-quality) data prominently in outputs

**Documentation and audit trail:**
- Every product LCA result should be traceable: input data → calculation model → output result
- Method document version-controlled and publicly available (following Mondra's open-methodology approach)
- Every emission factor cited with source, version, and date

**Verification pathway:**
- Level 1 (internal): Automated consistency checks (plausibility ranges by product category)
- Level 2 (platform-level): Annual third-party review of methodology and model (covers CSRD limited assurance needs)
- Level 3 (product-level): Optional third-party verification per product for consumer-facing claims or competitive comparisons

**CSRD assurance readiness checklist:**

| Requirement | MGS Design Response |
|-------------|-------------------|
| Documented methodology | Published method document (versioned, like BRC Mondra Coalition) |
| Traceable calculations | Audit trail from BOM to CO₂e output |
| Recognised standard (ISO 14067 / GHG Protocol) | ISO 14067 as primary; GHG Protocol-compatible |
| Data quality disclosure | PDS metric + DQR per product |
| Uncertainty acknowledgement | ±% range reported; tier flagged |
| Assurance statement | Platform-level methodology review by qualified third party |

### Key Standards Timeline to Watch

| Year | Event | MGS Impact |
|------|-------|-----------|
| **2025** | PEF Guide finalised (May); PEFCR v3.1 for Apparel/Footwear approved | Reference for multi-category LCA clients |
| **2026** | GHG Protocol corporate/product standard revisions expected (final H2 2026) | May require changes to Scope 3 calculation methods; monitor for mandatory primary data requirements |
| **2026** | CSRD Wave 2 (large companies 1000+ employees) first report (FY2025) | Major MGS client segment enters compliance; CSRD-ready PCF data critical |
| **2026–2027** | EU Green Claims Directive (if enacted) enforcement begins | EU retailer clients require substantiated environmental claims |
| **2027** | PACT DQR requirements become mandatory | B2B PCF exchanges must include full data quality ratings |
| **2027–2028** | EF database v4.0 expected (3,200 datasets) | Background database upgrade for PEF-compliant studies |
| **2028** | SBTi CNZS v2.0 in effect | Product-level decarbonisation targets tighten; MGS PCF data feeds SBTi validation |

---

## Appendix: Glossary of Key Terms

| Term | Definition |
|------|-----------|
| **CFP** | Carbon Footprint of a Product — sum of GHG emissions and removals over a product's life cycle, expressed in kg CO₂e |
| **Cradle-to-gate** | System boundary from raw material extraction to factory gate |
| **Cradle-to-grave** | System boundary covering entire product life cycle including end-of-life |
| **DQR** | Data Quality Rating — quantitative score for data quality indicators |
| **EF-compliant** | Datasets or studies using EU Environmental Footprint characterisation factors and databases |
| **Functional unit** | Quantified performance of a product system, providing reference for all inventory data |
| **GWP** | Global Warming Potential — measure of how much heat a greenhouse gas traps relative to CO₂ over a specified time horizon (usually 100 years) |
| **LCI** | Life Cycle Inventory — the compiled data of all inputs (energy, materials) and outputs (emissions, waste) across the product life cycle |
| **LCIA** | Life Cycle Impact Assessment — the phase that translates LCI data into impact categories |
| **PACT** | Partnership for Carbon Transparency (WBCSD) — methodology and technical network for B2B PCF data exchange |
| **PDS** | Primary Data Share — percentage of product footprint calculated from primary (supplier-specific) activity data |
| **PEF** | Product Environmental Footprint — EU standardised multi-criteria LCA methodology |
| **PEFCR** | Product Environmental Footprint Category Rules — product-specific mandatory rules within the PEF framework |
| **PCF** | Product Carbon Footprint — synonymous with CFP |
| **PCR** | Product Category Rules — rules for a specific product category that ensure consistency in EPD or CFP calculations |
| **Partial CFP** | CFP covering only specified stages of the product life cycle (e.g., cradle-to-gate only) |
| **System expansion** | Allocation avoidance method that expands system boundary to include functions of co-products |

---

*Research compiled March 2026. Sources include ISO standards documentation, BSI PAS 2050 guidance, European Commission PEF technical guidance, GHG Protocol documentation, BRC Mondra Coalition published methodology, Foundation Earth methodology (via Blonk Sustainability), CarbonCloud methodology, PACT Methodology v3, and current academic and industry literature on LCA standards practice.*
