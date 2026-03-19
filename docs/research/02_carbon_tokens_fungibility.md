# Carbon Tokens & Fungibility: Deep Research for My Green Squares (MGS)
*Research completed: March 2026*

---

## Executive Summary

Carbon credit markets have spent three decades wrestling with the same problem MGS faces: how do you make units from radically different activities — planting trees in Uganda, installing solar panels in Bangladesh, or replacing cookstoves in Cambodia — interchangeable and consistently valued? The answer every major system converges on is **abstraction through standardisation**: strip the unit back to a single common denominator (1 tonne CO₂e), enforce rigorous methodology to ensure that denominator means the same thing regardless of source, and let independent verification create trust in the abstraction.

MGS's proposed unit (1 Green Square = 100g CO₂e = £0.003) is a natural micro-denomination of this model. At £30/tonne CO₂e equivalent, it sits near the premium end of today's voluntary carbon market, and above average spot prices — positioning it as a high-integrity product. This report documents how every major existing system approaches fungibility, what has failed, and what design lessons apply directly to MGS.

---

## Part 1: Existing Carbon Unit Systems

### 1.1 Verra VCS (Verified Carbon Standard)

**Scale:** The world's most widely used voluntary carbon crediting programme — over 2,579 registered projects in 132+ countries, with more than 1.3 billion tonnes of GHG reduced or removed. ([Verra](https://verra.org/programs/verified-carbon-standard/))

**The Fungibility Mechanism:**

Verra achieves fungibility through a single, abstracted unit: the **Verified Carbon Unit (VCU)**, where one VCU = one metric tonne of CO₂ equivalent reduced or removed. ([Verra](https://verra.org/programs/verified-carbon-standard/)) Regardless of whether the project is a wind farm in India, a forest-protection scheme in Brazil, or an agricultural soil carbon project in Kenya, all VCUs are nominally interchangeable on the open market.

The standardisation is achieved through:

1. **Common Accounting Methodology Layer**: Each project type must use a Verra-approved methodology that specifies how to calculate the baseline scenario (what would have happened without the project), quantify the additionality (emissions reduced beyond business as usual), account for leakage (emissions displaced elsewhere), and handle permanence risk (what happens if the carbon store is reversed). The methodologies are project-type specific but all output the same unit: tonnes CO₂e. ([Verra VCS Methodologies](https://verra.org/program-methodology/vcs-program-standard/overview/))

2. **Seven Quality Assurance Principles**: All VCUs must be real, measurable, additional, permanent, independently verified, uniquely numbered, and conservatively estimated. These are the "rules of the common currency."

3. **Independent Third-Party Verification**: A Validation and Verification Body (VVB) — an accredited auditor — must validate the project design and verify actual results before any VCU can be issued. This decouples trust from the project developer and anchors it in the methodology and the auditor.

4. **Registry with Unique IDs**: Every VCU carries a unique serial number in the Verra Registry, is publicly visible, and can only be retired (used) once. This prevents double-counting.

5. **Labels and Tags**: VCUs can carry additional quality tags (e.g., Climate, Community & Biodiversity Standards — CCB) that signal co-benefits, without changing the core fungibility of the tonne unit.

**The Fungibility Paradox**: Despite the common unit, VCUs are not truly fungible in practice. A forestry VCU and a renewable energy VCU technically both = 1 tonne, but they trade at very different prices because buyers value project type, co-benefits, vintage year, and geography. The registry creates nominal fungibility; the market creates de facto differentiation.

**Relevance to MGS**: MGS can borrow Verra's core architecture — a common abstracted unit, per-activity methodologies that all reduce to the same unit, and independent verification. The key difference is that MGS operates at the consumer/product level (100g increments) rather than project/tonne level.

---

### 1.2 Gold Standard

**Founded:** 2003 by WWF and other NGOs specifically to address the weak integrity of early CDM credits. ([SustainCERT](https://www.sustain-cert.com/news/carbon-credits-101-what-is-the-gold-standard))

**Approach to Fungibility:**

Gold Standard issues **GSVERs (Gold Standard Verified Emission Reductions)** — the same 1 tonne CO₂e unit, but with stricter co-benefit requirements: every project must contribute to at least two UN Sustainable Development Goals in addition to the core carbon reduction. ([Gold Standard](https://www.goldstandard.org/publications/paris-agreement-alignment-information))

Gold Standard's fungibility approach adds a second dimension: **multi-SDG standardisation**. It doesn't just standardise the carbon unit — it standardises the social and environmental impact assessment, making it possible to compare a clean cookstove project in Kenya with a small-scale solar project in India on both carbon and development grounds.

**2026 Paris Alignment Transition**: Gold Standard has set 1 January 2026 as the transition point for Paris-aligned methodologies. All 2026+ vintage credits must use Paris Agreement-aligned methodologies, phasing out legacy CDM-era approaches. ([Gold Standard Paris Alignment](https://www.goldstandard.org/publications/paris-agreement-alignment-information)) This means the fungibility layer is being re-anchored to NDC targets and regulatory surplus requirements — credits must represent reductions *above and beyond* what national law already mandates.

**Pricing Signal**: Gold Standard credits typically command a premium over Verra VCS due to the additional co-benefit requirements. Energy efficiency credits: ~€8.20/tCO₂e + Fairtrade premium; forest management: ~€13/tCO₂e. ([Gold Standard](https://www.goldstandard.org/news/what-is-a-carbon-credit-worth))

**Relevance to MGS**: Gold Standard's multi-SDG framework is highly relevant. If a Green Square from coffee carries the same carbon claim as one from solar panels, MGS could add a parallel dimension — SDG tagging — that differentiates types within the common unit without breaking fungibility.

---

### 1.3 Plan Vivo

**Founded:** 1994 — the oldest voluntary carbon standard, responsible for **the world's first voluntary carbon market credits** (Scolel'te project in Mexico). ([Plan Vivo](https://www.planvivo.org/projects))

**Key Differentiators:**

- Focused exclusively on **small-scale, community-led, nature-based projects** (agroforestry, reforestation, sustainable land use).
- Projects are designed by and for local communities — the "plan vivo" (living plan) is a community-authored land management document.
- Issues **Plan Vivo Certificates** rather than VCUs — the unit is the same (1 tonne CO₂e) but the certification process emphasises community ownership and long-term relationships over corporate transactions. ([Plan Vivo Certify](https://www.planvivo.org/projects/certify-a-project))
- Includes a **buffer pool** mechanism for serialised credits to address reversal risk (e.g., a forest fire removing previously certified carbon). ([Regreener Plan Vivo Guide](https://www.regreener.earth/blog/the-5-best-plan-vivo-carbon-credit-projects-of-2026))

**Comparison with Other Standards:**

| Dimension | Plan Vivo | Gold Standard | Verra VCS |
|---|---|---|---|
| Project scale | Small/community | Small–large | Any scale |
| Project focus | Nature-based only | All types | All types |
| Co-benefits | Required (community) | Required (2+ SDGs) | Optional (labels) |
| Credit unit | 1 tonne CO₂e | 1 tonne CO₂e | 1 tonne CO₂e |
| Registry | Public, serialised | Public | Public, serialised |
| Market position | Niche, premium | Premium | Mass market |

**Relevance to MGS**: Plan Vivo's community-led model is the closest analogue to the MGS concept of embedding carbon accounting in everyday consumer transactions. The challenge — which Plan Vivo faces too — is that the verification process is expensive relative to the scale of individual activities.

---

### 1.4 Article 6 of the Paris Agreement — ITMOs

**What it is**: Article 6 of the Paris Agreement establishes frameworks for international cooperation on carbon markets. It has three sub-mechanisms: ([UNFCCC Article 6](https://unfccc.int/process-and-meetings/the-paris-agreement/article6))

- **Article 6.2**: Decentralised bilateral trading of **Internationally Transferred Mitigation Outcomes (ITMOs)** between countries. Any unit of mitigation can be an ITMO as long as corresponding adjustments are made to both parties' national emissions inventories.
- **Article 6.4**: A new UN-supervised centralised crediting mechanism (successor to the CDM) — the "Paris Agreement Crediting Mechanism" — with stricter additionality and baseline standards. ([Columbia SIPA CGEP](https://www.energypolicy.columbia.edu/publications/how-to-fully-operationalize-article-6-of-the-paris-agreement/))
- **Article 6.8**: Non-market approaches to international cooperation.

**The Fungibility Problem Article 6 Solves:**

The critical innovation is the **Corresponding Adjustment (CA)**: when a mitigation outcome is transferred from one country to another, the seller adds the tonnes back to its own emissions inventory and the buyer subtracts them. This prevents the same tonne being counted twice — once toward the host country's NDC and once toward the buyer's offsetting claim. ([Sylvera Article 6 FAQ](https://www.sylvera.com/blog/article-6-authorizations-corresponding-adjustments-faq))

Without CAs, there is no true fungibility across international boundaries because the same unit could serve multiple masters. Article 6 essentially creates a "single ownership" rule at the sovereign level.

**Current Status (post-COP29)**: COP29 (Baku, 2024) reached agreement on Article 6.2 rules, including an UNFCCC secretariat automated consistency check. However, avoidance credits under Article 6 remain contentious and the issue has been deferred to 2028. Removal credits have new approved methodologies, but disagreements persist over their fungibility with avoidance credits. ([Columbia SIPA CGEP](https://www.energypolicy.columbia.edu/publications/how-to-fully-operationalize-article-6-of-the-paris-agreement/))

**ITMO Characteristics**: ITMOs are defined in any unit (not necessarily tonnes CO₂e) and cover any sector. This flexibility is both a strength (any mitigation outcome can be traded) and a weakness (different units undermine fungibility). In practice, most ITMOs are denominated in tCO₂e.

**Relevance to MGS**: Article 6's corresponding adjustment principle is directly relevant to MGS's fungibility challenge. MGS must ensure that a Green Square earned from buying coffee (which may have reduced embedded supply chain emissions) and one from installing solar panels cannot be "double claimed" — i.e., the underlying emissions reduction cannot also be claimed by the product manufacturer in their Scope 3 reporting. This is the micro-scale version of the sovereign double-counting problem.

---

### 1.5 CORSIA (Carbon Offsetting and Reduction Scheme for International Aviation)

**What it is**: The UN's ICAO-managed carbon offsetting scheme for international aviation. Airlines must offset their emissions growth above a 2019 baseline by purchasing **CORSIA Eligible Emissions Units (EEUs)**. ([ICAO CORSIA](https://www.icao.int/CORSIA/corsia-eligible-emissions-units))

**Phase Status**: CORSIA's First Phase (2024–2026) is now active. From 2027, all international flights will be subject to offsetting requirements. Demand for CORSIA-eligible credits is projected at 1.5 billion tonnes through 2035. ([ACR CORSIA Approval](https://acrcarbon.org/news/acr-approved-by-icao-for-2027-2029-corsia-compliance-period/))

**How Airlines Achieve Fungibility:**

CORSIA's approach is a **whitelist model**: ICAO's Technical Advisory Body (TAB) assesses carbon programmes against the CORSIA Emissions Unit Eligibility Criteria, which include:

- Robust quantification and verification
- No double counting
- Additionality
- Permanence (or buffer pools for nature-based)
- No net harm to SDGs
- Host country authorisation (corresponding adjustment from 2021 vintages onward)

Only credits from approved programmes — currently including Verra VCS, Gold Standard, ACR, and Isometric — may be used. ([GreenAir News](https://www.greenairnews.com/?p=8325)) Each EEU still = 1 tonne CO₂e, so the common unit persists. CORSIA doesn't make different project types equally valuable in the market — it simply sets a minimum quality floor above which all EEUs are nominally interchangeable for compliance purposes.

**Relevance to MGS**: CORSIA is a perfect model for the "whitelist + common unit" approach. MGS could operate similarly: define a set of approved activity types that meet a quality threshold, and then allow all approved activities to generate Green Squares at the same nominal rate. Buyers (consumers) accept them as interchangeable because the underlying quality bar is consistent.

---

## Part 2: Blockchain Carbon Tokens

### 2.1 Toucan Protocol and the Base Carbon Tonne (BCT)

**Mechanism**: Toucan built the infrastructure to bring voluntary carbon credits onto blockchain. The process has three tiers: ([Toucan Protocol FAQs](https://blog.toucan.earth/toucan-9-faqs/))

1. **Bridge**: Carbon credits (initially Verra VCS) are "bridged" onto chain via the Toucan Carbon Bridge. The original registry credit is retired (immobilised), and a unique **TCO2 token** is minted on-chain. Each TCO2 is an NFT — non-fungible — because it retains all metadata from the original credit: project type, vintage year, methodology, country.

2. **Pooling**: To create fungibility, TCO2 tokens are deposited into **Carbon Pools** with defined eligibility criteria. The Base Carbon Tonne (BCT) pool accepts any TCO2 from any methodology, issued from 2008 onwards, provided less than 10 years have passed since verification. The Nature Carbon Tonne (NCT) pool is more selective, accepting only nature-based methodology credits from 2012 onwards.

3. **Reference Token**: On depositing a TCO2 into a pool, the depositor receives one fungible **BCT or NCT token** in return. BCT/NCT tokens are ERC-20 tokens — fully fungible, tradeable on DEXs, usable in DeFi. They can be redeemed for a TCO2 (the actual credit) at any time; only TCO2s can be retired.

**How Fungibility is Created**: The pool acts as a liquidity aggregator. Individual credits differ by project and vintage; the pool strips those attributes and outputs an undifferentiated unit. This is conceptually identical to how a money market fund strips individual bond characteristics to output a single unit value — at the cost of losing specific project attribution.

**Launched**: October 2021. Within six months, over 20 million tonnes had been bridged — demonstrating rapid market adoption. ([Osler](https://www.osler.com/en/insights/updates/tokenized-carbon-credits-blockchain-revolutionizing-markets/))

**Critical Problem**: Because BCT accepted any Verra credit from 2008 onwards, it became a magnet for the cheapest, lowest-quality legacy credits — so-called "junk carbon." The pool's gating criteria were insufficiently discriminating. In May 2022, Verra banned tokenisation via retirement, halting Toucan's bridge operations. This highlighted a fundamental tension: fungibility (accepting everything) and quality (only accepting the best) are in direct conflict.

**Resolution and Current State**: Toucan subsequently shifted to a custodial bridge model (credits are held rather than retired at origin, enabling two-way bridging). It now requires higher-quality, more recent credits. The experience taught that **quality gating at pool entry** is critical to maintaining fungibility's credibility.

**Key Technical Insight for MGS**: The NFT → ERC-20 pool architecture is the most elegant existing solution to the "specific → fungible" problem. MGS could adapt it: each verified sustainability activity mints a unique token (with full provenance metadata), and a pool with defined quality criteria converts it into a fungible Green Square token. The pool rules define fungibility.

---

### 2.2 KlimaDAO

**Model**: KlimaDAO is a DeFi protocol built on top of Toucan's BCT. It forked the Olympus DAO model: every KLIMA token is backed 1:1 by BCT in the KlimaDAO treasury. ([CoinGecko](https://www.coingecko.com/research/publications/what-is-klima-dao-and-how-does-it-work))

**Carbon Strategy**: KlimaDAO's stated goal was to drive up carbon prices by buying and locking BCTs in its treasury — a "carbon black hole" that removes credits from the market. By creating artificial scarcity, it aimed to raise the cost of offsetting for polluters.

**What Went Wrong**: KlimaDAO launched in October 2021 and KLIMA token prices spiked dramatically, then collapsed. The incentive structure attracted speculative capital rather than genuine climate investors. The BCT pool it was built on was already drawing in low-quality legacy credits (see above). The protocol achieved large TVL briefly but has since shrunk significantly. It remains operational but is a cautionary tale about applying DeFi tokenomics to environmental assets.

**Lessons for MGS**:
- Token-based mechanisms that create speculation divorced from underlying climate value tend to collapse when the speculative premium deflates.
- A Green Square that becomes a speculative asset rather than a utility token risks the same fate.
- KlimaDAO's treasury model (backing tokens with real carbon assets) is sound in principle; the failure was in the quality of the backing assets and the speculative framing.

---

### 2.3 Flowcarbon

**Model**: Flowcarbon (founded 2022, backed by a16z) vertically integrates across the voluntary carbon market and tokenises high-quality credits. Rather than accepting all credits like BCT, Flowcarbon creates themed bundles — e.g., **GNT (Goddess Nature Token)** bundles nature-based credits from Gold Standard and Verra into a curated basket. ([Reddit/RegenerativeFinance](https://www.reddit.com/r/RegenerativeFinance/comments/y0cksd/how_does_flowcarbon_tokenize_their_credits/))

**Gold Standard Partnership**: Flowcarbon was selected by Gold Standard for the readiness phase of their official tokenisation programme — working to finalise guidelines for tokenising Gold Standard credits with registry integration. ([Flowcarbon/Gold Standard](https://www.flowcarbon.com/knowcarbon/flowcarbon-selected-by-gold-standard)) This is the first instance of a major registry formally partnering with a blockchain platform.

**Key Approach Differences vs Toucan**:
- **Custodial rather than retirement-based bridge** — credits remain on the original registry until token retirement
- **Quality-curated bundles** — GNT is not "any nature credit"; it's a curated selection meeting Flowcarbon's quality criteria
- **Registry collaboration** — working within the existing registry system rather than around it

**Relevance to MGS**: Flowcarbon's curated-bundle approach — creating a single token from a quality-filtered basket of diverse project types — is directly applicable. MGS could create a Green Square backed by a curated basket of verified sustainability activities, where the basket rules ensure quality without requiring consumers to understand each underlying project.

---

### 2.4 Carbonplace

**What it is**: Described as the "SWIFT of carbon markets," Carbonplace is a bank-backed carbon credit settlement and portfolio management infrastructure. Founded by a consortium of nine major global banks including BBVA, BNP Paribas, NatWest, Standard Chartered, UBS, and others. Raised USD 45 million in September 2023. ([Markets Media](https://www.marketsmedia.com/bank-consortium-invests-45m-in-carbonplace/))

**How It Works**: Carbonplace does not create fungibility at the credit level — each credit retains its attributes from its originating registry (Verra, Gold Standard, Puro, ACR, etc.). Instead, it creates **settlement infrastructure fungibility**: a single account provides access to all 12+ registries. It standardises the *transaction process*, not the underlying asset, enabling delivery-versus-payment settlement (simultaneous credit transfer and payment, eliminating counterparty risk). ([Carbonplace](https://carbonplace.com/how-it-works))

**Significance for Market Integrity**: Carbonplace is the TradFi response to the blockchain carbon token movement. Banks are building the "pipes" for carbon credit trading within regulated financial infrastructure, with KYC/AML compliance, audit-ready records, and bank-grade security. As of 2025, it provides access to 12 registries in a single interface.

**Key Differentiator from Blockchain Approaches**: Carbonplace doesn't tokenise anything. Credits remain in traditional registries. It standardises access, not the credits themselves. This is the "boring but robust" institutional-grade approach vs the "exciting but fragile" DeFi approach.

**Relevance to MGS**: Carbonplace's model matters for MGS's banking relationships and potential institutional-grade settlement infrastructure. When MGS scales to institutional buyers or corporate offsetting partners, Carbonplace-style infrastructure is the operational model.

---

### 2.5 How Blockchain Achieves Fungibility On-Chain: Summary Architecture

```
UNIQUE CREDIT (registry)
       ↓
  [Bridge Layer]
  Verify & lock/retire original credit
  Mint unique NFT/token (TCO2 in Toucan model)
  — carries all metadata: project, vintage, methodology
       ↓
  [Pool / Bundle Layer]
  Apply quality gating criteria
  Pool similar credits together
  Mint fungible ERC-20 reference token (BCT, NCT, GNT)
  — strips metadata, creates interchangeable unit
       ↓
  [Utility Layer]
  Fungible token used in DeFi, traded on DEX
  Can be redeemed for underlying NFT
  NFT retired to claim offset
```

The critical insight: **fungibility is created at the pool layer by aggregation and quality gating, not at the individual credit level.** The market price of the pool token reflects the weighted average quality of its constituents.

---

## Part 3: Micro-Credit Approaches and Fractionalisation

### 3.1 Has Anyone Tried Micro-Denominations?

The carbon market's minimum unit of 1 tonne CO₂e has always been a barrier to consumer and micro-business participation. Several approaches have addressed this:

**Stripe Climate**: Stripe routes a small percentage of transaction revenue (as low as 1%) to a portfolio of high-quality carbon removal projects. This effectively creates micro-purchasing — a $0.50 transaction might result in $0.005 going to carbon removal, a fraction of a gram. Stripe aggregates these micro-contributions to purchase full credits at scale, then retires them. ([Stripe Climate](https://stripe.com/climate)) This is the "aggregator" model: individuals don't own micro-credits, Stripe handles the aggregation and retirement.

**Doconomy DO Black Card**: Launched in 2019 (discontinued 2022), the world's first credit card with a carbon spending limit. Used the Åland Index to calculate per-transaction CO₂ emissions in grams, allowed users to set carbon caps on their spending, and offered offsetting via UN-certified projects. ([Mastercard/Doconomy](https://www.mastercard.com/news/europe/sv-se/nyhetsrum/pressmeddelanden/sv-se/2019/april/do-black-the-world-s-first-credit-card-with-a-carbon-limit/)) Doconomy now provides the underlying carbon footprint calculation engine to financial institutions rather than direct-to-consumer cards.

**Yayzy (London fintech)**: Analyses bank transaction data to calculate the carbon footprint of each purchase in grams CO₂e, offering micro-offsetting per transaction via verified projects integrated with banking platforms.

**Blockchain Fractionalisation**: Multiple blockchain platforms (Toucan, and more recently purpose-built platforms) support fractional carbon credit ownership down to 0.001 tCO₂e (1 kg CO₂e). One platform documented enabling purchases down to 0.37 tonne increments for a small café. ([Techaroha](https://techaroha.com/fractional-carbon-credit-tokenization-guide/)) Smart contracts can theoretically support arbitrary precision — theoretically down to gram-level (0.000001 tCO₂e), though practical minimum transaction economics set a floor.

**Academic/Blockchain Research**: A 2025 paper proposed blockchain-based carbon trading where "any value, no matter how small, can be traded" — noting that a farmer who has grown only 10 trees (far less than the ~45 needed for 1 tonne) could receive fractional compensation for their contribution. ([Taylor & Francis](https://www.tandfonline.com/doi/full/10.1080/19498241.2025.2611313))

### 3.2 Challenges of Fractionalisation

**1. Verification Cost vs Unit Value**

The core economic challenge: third-party verification of a carbon project costs thousands to tens of thousands of dollars regardless of the number of credits produced. Fractionalising a tonne into 10,000 units (of 100g each) does not reduce verification costs — it just spreads them across more units. At the micro-unit level, verification cost per unit can exceed unit value.

*For MGS*: At £0.003 per Green Square, a 100-tonne project generates £300 in Green Square revenue. Verification costs for a 100-tonne project might be £5,000–£30,000. This only works if:
- MGS operates as an aggregator (buying bulk credits and retailing micro-units), not as a project-level verifier
- Verification costs are borne at the tonne level, not the gram level
- Consumer trust is in MGS as an aggregator, not in per-unit verification

**2. Registry Minimum Thresholds**

Most registries (Verra, Gold Standard) have minimum project sizes and minimum verification intervals. A single cup of certified sustainable coffee does not generate its own carbon credit — the upstream supply chain credit is generated by the supplier's project (e.g., a Gold Standard-certified cooperative), not the individual purchase. MGS must either partner with certified suppliers or operate as a claims-layer above certified projects.

**3. Double-Counting Risk at Consumer Level**

If a coffee company earns Verra credits for its sustainable farming practices, and then MGS also awards Green Squares to consumers for buying that coffee, the same emission reduction has been counted twice — once for the company's Scope 1/2 claims, and once for the consumer's Green Square. This is the consumer-level version of the double-claiming problem that Article 6 addresses at sovereign level.

*For MGS*: Careful partner selection and contractual arrangements must ensure that activities generating Green Squares are either:
- Not already claimed by the supplier in their own Scope 1/2/3 reporting, or
- Explicitly transferred to MGS/consumer on purchase (analogous to a corresponding adjustment)

**4. Permanence at Micro-Scale**

A 100g CO₂e reduction from buying solar panels is genuinely permanent (the energy has been generated). A 100g CO₂e credit from a forestry project is less permanent — if the tree burns 5 years later, the carbon is re-released. At the micro-unit level, tracking permanence risk and maintaining buffer pools becomes administratively complex. Mainstream approach is to aggregate into a central buffer pool at the tonne level, not the gram level.

**5. Price Floor Economics**

With a credit priced at £0.003, the unit economics must be extremely lean. Transaction fees, blockchain gas fees, verification costs, and intermediary margins all eat into this floor. Most consumer micro-carbon platforms (Doconomy, Stripe Climate) avoid this by using micro-contributions to fund bulk credit purchases, rather than creating a new micro-denomination instrument per se.

### 3.3 Maintaining Verification Integrity at Micro Level

The most robust approaches in practice:

| Approach | How It Works | Integrity Mechanism |
|---|---|---|
| **Aggregator model** | Platform buys full (tonne-level) certified credits; retails micro-units | Integrity at tonne level; micro-units are accounting constructs |
| **Fractional blockchain token** | Full credit minted as token; smart contracts fractionalise | Registry lock ensures 1-to-1 backing; fractions provably sum to whole |
| **Activity-based estimation** | Emission factor databases used to estimate per-activity reductions | Integrity from estimation accuracy; periodic calibration required |
| **Supplier certification** | Only certified partners (e.g., Gold Standard certified farms) can generate units | Third-party project-level certification; consumer inherits it |

MGS likely needs a hybrid: **activity-based estimation** (for consumer-facing attributions like "buying this coffee = X Green Squares") backed by **aggregator-level certified credit retirement** (MGS periodically retires a tonne-level credit matching the total Green Squares issued in a period). This is how Stripe Climate operates.

---

## Part 4: Pricing Mechanisms

### 4.1 Current Voluntary Carbon Market Prices per Tonne (2025–2026)

The voluntary carbon market has no single price — it is hundreds of micro-markets by project type, methodology, vintage, geography, and quality. ([Sylvera](https://www.sylvera.com/blog/carbon-market-trends))

**Headline Numbers (2025/early 2026):**

| Market Segment | Price Range ($/tCO₂e) | Notes |
|---|---|---|
| VCM average spot (2024 data) | $4–$6 | Based on 45 project listings, avg asking price; offers from $0.25 to $27 |
| High-quality ARR (Dec 2025) | $26 avg spot | Up from $14 at start of 2025 |
| BBB+ rated ARR projects | >$35 median | Sylvera ratings framework |
| Lower-rated ARR | <$20 | Growing supply glut |
| Nature-based credits (EU, 2026) | €7–€24 | Premium projects up to €60 |
| Technology-based removals | €100–€500+ | Direct Air Capture, BECCS |
| Durable CDR offtakes | $180 avg | 30x spot market average |
| EU ETS compliance permits (Dec 2025) | €82.85/tonne | Up 21.52% year-on-year |
| Global compliance average | ~€16/tonne | Covers ~28% of global emissions |

Sources: [CarbonCredits.com Live Prices](https://carboncredits.com/carbon-prices-today/), [Sylvera 2026 Trends](https://www.sylvera.com/blog/carbon-market-trends), [Regreener 2026 Forecast](https://www.regreener.earth/blog/carbon-credit-prices-today-trends-and-forecasts-for-2026)

**Total Market Size**: ~$1 billion in actual retirements in 2025 (up 6% from $954 million in 2024). Voluntary carbon market projected to reach €3 billion in 2026 and €15 billion by 2035 (CAGR ~20.6%). ([Regreener](https://www.regreener.earth/blog/carbon-credit-prices-today-trends-and-forecasts-for-2026))

### 4.2 How £0.003 per 100g CO₂e (= £30/tonne) Compares

Converting MGS's proposed pricing to standard market terms:

**1 Green Square = 100g CO₂e = £0.003**
**1 tonne CO₂e = 10,000 Green Squares = £30.00**

**Market Comparison (converting to USD at ~1.27 USD/GBP):**
- MGS implied price: **~$38/tonne CO₂e**
- VCM average spot (2024): **$4–$6/tonne** → MGS is 6–9× the market average
- High-quality ARR (Dec 2025): **$26/tonne** → MGS is ~45% above this premium tier
- EU ETS compliance: **€82.85 (~$89/tonne)** → MGS is below compliance market pricing
- CDR offtakes: **$180/tonne** → MGS is well below cutting-edge removal prices

**Assessment**:

£30/tonne positions MGS firmly in the **premium voluntary market tier** — above average spot prices but below EU compliance levels and CDR technology prices. This is achievable and credible for high-quality activities. Key considerations:

1. **Implicit premium justification**: At £30/tonne, consumers are paying well above the commodity market for offset credits. The premium must be justified by co-benefits, convenience, brand trust, and the social proof of the Green Square mechanism — not purely carbon economics.

2. **Price stability challenge**: Voluntary carbon prices have been extremely volatile (market shrank by >two-thirds 2021–2024 per Bloomberg). At £0.003 per Green Square, MGS is fixing its consumer price while underlying carbon costs fluctuate. This requires either a hedging strategy or acceptance of margin volatility.

3. **Upside scenario**: EY forecasts voluntary carbon prices of $75–$125/tonne by 2035, driven by stricter standards. At those prices, MGS's £30/tonne would be below market rate — meaning the Green Square could actually become underpriced and highly competitive, or provide room for MGS to raise the Green Square price.

4. **Consumer reference point**: Most consumers have no idea what a tonne of CO₂e costs. £0.003 is psychologically a rounding error. The power of the Green Square is not the price — it's the visibility of the unit. Doconomy found the same: consumers respond to carbon footprint numbers, not carbon prices.

### 4.3 Price Discovery and Stability Mechanisms

Existing markets use several mechanisms to manage price discovery and stability:

**Buffer Pools (Insurance Mechanism)**: Nature-based projects contribute 10–25% of generated credits to a central buffer pool managed by the registry. If a project fails (e.g., deforestation, fire), credits from the buffer are cancelled to compensate, maintaining the integrity of already-sold credits. ([Sylvera Buffer Pools](https://www.sylvera.com/blog/carbon-credit-buffer-pools)) This is the market's primary permanence risk mechanism.

**Futures and Derivatives**: The CFTC approved voluntary carbon credit derivative contracts in September 2024, providing a mechanism for price discovery and hedging. Xpansiv's CBL exchange is the world's largest carbon credit and renewable energy certificate cash marketplace. ([Xpansiv](https://xpansiv.com))

**Quality Ratings**: Third-party ratings agencies (Sylvera, BeZero Carbon, MSCI) provide standardised quality ratings (analogous to bond ratings) that enable price differentiation based on quality, creating a yield curve across project types.

**Minimum Prices**: Gold Standard's Fairtrade minimum pricing model sets floor prices for specific project types to protect project developers in low-liquidity markets. ([Gold Standard](https://www.goldstandard.org/news/what-is-a-carbon-credit-worth))

**For MGS Price Stability**: The fixed £0.003 price is a deliberate design choice — predictability over market efficiency. This requires MGS to:
- Purchase underlying credits at below-market rates (possible if buying in bulk, in advance/forward contracts)
- Maintain a reserve fund to absorb carbon price increases
- Periodically review and adjust the Green Square price (with sufficient notice to avoid trust erosion)

---

## Part 5: Lessons from Failures

### 5.1 Carbon Market Failures 2010–2020: Systemic Issues

The Clean Development Mechanism (CDM) under the Kyoto Protocol was the first large-scale international carbon market and its failure defined the problems every subsequent system has tried to address:

**Industrial Gas Projects (HFC-23, N₂O)**: Manufacturers of refrigerant gases found they could earn enormous CDM credits by destroying HFC-23 (a potent greenhouse gas) as a byproduct — so much so that it became financially rational to *produce more refrigerant* in order to *earn more credits* for destroying the byproduct. This is a textbook case of perverse incentives destroying additionality.

**Over-Issued Renewable Energy Credits**: Renewable energy projects that were already commercially viable (and would have been built without carbon finance) were awarded CDM credits. The additionality test failed because methodologies used conservative rather than realistic baseline assumptions. Billions of tonnes of credits with no real emissions benefit.

**Inflated Baselines in REDD+ (Deforestation)**: Forest protection projects (REDD+) calculated credits based on how much deforestation *would have happened* without the project. Many projects systematically overestimated the threat to their forests, generating inflated credit volumes. Academic studies found the threat to forests overestimated by ~400% on average for Verra projects. ([Morfo/Guardian Analysis](https://www.morfo.rest/article/verra-vs-guardian-carbon-offsets))

**Chinese Rice Cultivation Projects**: Dozens of Chinese agricultural projects on Verra's registry were found to contain accounting loopholes and questionable integrity claims. Shell had purchased hundreds of thousands of credits from these projects. Verra eventually cancelled the projects but had no mechanism to compel replacement credits. ([Climate Home News](https://www.climatechangenews.com/2023/05/23/verra-boss-steps-down-after-criticism-of-its-carbon-credits/))

### 5.2 The 2023 Greenwashing Scandals

**The Guardian Investigation (January 18, 2023)**: A landmark investigation published jointly by The Guardian, SourceMaterial.org, and Die Zeit claimed that over 90% of Verra's rainforest REDD+ credits were "phantom credits" — not representing real emissions reductions. Analysis drawn from a 2022 Cambridge University study found that the threat to forests had been overestimated by ~400%, meaning most "saved" trees were never at risk. ([OUP Academic/ROF Study](https://academic.oup.com/rof/article/30/1/321/8362620))

The article triggered a market-wide shock: stock prices of companies that had retired non-CCB-labelled credits fell significantly in the days following publication. Verra's CEO David Antonioli announced his departure in May 2023.

**South Pole / Kariba (Zimbabwe) Scandal**: The Kariba REDD+ project — at one point the third most widely used carbon project globally, with ~22 million credits purchased by Volkswagen, Gucci, Nestlé, McKinsey & Co. — became the subject of a Verra investigation. After a two-year probe, Verra concluded that ~two-thirds of Kariba's stated climate benefits were fictitious, with approximately 15 million excess credits issued. ([Bloomberg](https://www.bloomberg.com/news/articles/2025-10-17/majority-of-carbon-credits-from-tarnished-project-deemed-bogus), [LA Times](https://www.latimes.com/business/story/2025-10-17/majority-of-carbon-credits-from-tarnished-project-deemed-bogus))

The fallout revealed a **structural flaw**: Verra can cancel credits and request replacement, but it cannot compel project developers to provide compensation. As of 2025, Verra had requested Carbon Green Investments (the project owner) to cancel ~12.5 million credits, but CGI had not responded. CarbonPlan researchers described this as "a deep structural flaw in the largest registry of the global carbon market."

**Chinese Forestry Projects (2025)**: Verra rejected four forestry projects in Guizhou, China, due to "serious allegations regarding the authenticity of government approval documents," affecting credits purchased by Apple, Shell, and others. ([Trellis](https://trellis.net/article/apple-shell-china-forest-project-verra-investigation/)) Under Verra rules, the developer must purchase and retire 4.4 million replacement credits, but Verra's ability to compel this remains unclear.

**Market Contraction**: The voluntary carbon market shrank by more than two-thirds between 2021 and 2024, driven by credibility concerns and corporate pullback from carbon neutrality claims. ([Bloomberg](https://www.bloomberg.com/news/articles/2025-10-17/majority-of-carbon-credits-from-tarnished-project-deemed-bogus))

### 5.3 Market Reforms Since 2023

**ICVCM and the Core Carbon Principles (CCPs)**: The Integrity Council for the Voluntary Carbon Market (ICVCM) launched its 10 Core Carbon Principles in 2023 — a global quality benchmark covering governance, emissions impact, and sustainable development. ([ICVCM](https://icvcm.org/core-carbon-principles/)) As of November 2025:
- 7 crediting programmes approved as CCP-Eligible
- 36 methodologies approved as CCP-Approved
- ~51 million unretired CCP-labelled credits available (roughly 4% of 2024 issuances)
- CCP-labelled credits command up to 25% price premium

The CCP system is creating a quality tier that enables genuine market differentiation — effectively a credit rating agency for carbon.

**VCMI Claims Code**: The Voluntary Carbon Markets Integrity Initiative (VCMI) launched guidance on legitimate corporate claims for carbon credit use, attempting to end the "carbon neutral" claim free-for-all.

**Verra REDD+ Methodology Overhaul**: Following the Guardian article, Verra committed to retire and replace its entire REDD+ methodology set by mid-2025, adopting new calibrated approaches to baseline assessment that reduce the scope for overestimation.

**Market "Financialisation"**: The market has adopted a "trust but verify" approach — buyers now expect data-driven due diligence (third-party ratings, registry verification, project-level assessments) rather than relying on certification alone. This mirrors the evolution of bond markets from relying on issuer disclosure to requiring independent credit ratings.

**Paris Alignment**: Gold Standard's 2026 Paris alignment transition, CORSIA's phase expansion, and the growth of Article 6 authorisations are all pulling voluntary and compliance markets closer together — raising the floor for credit quality.

**Summary of Key Reforms:**

| Reform | Organisation | Status (2026) |
|---|---|---|
| Core Carbon Principles | ICVCM | Active; 36 approved methodologies |
| REDD+ methodology overhaul | Verra | Completed mid-2025 |
| Paris alignment for all 2026+ credits | Gold Standard | Effective Jan 2026 |
| CORSIA Phase 1 (mandatory offsetting) | ICAO | Active 2024–2026 |
| CFTC voluntary carbon derivatives guidance | CFTC | Approved Sep 2024 |
| COP29 Article 6.2 rules | UNFCCC | Agreed Nov 2024; implementation ongoing |

---

## Part 6: Synthesis for My Green Squares (MGS)

### 6.1 The Core Fungibility Problem and Solution

Every system reviewed above converges on the same architecture:

**Step 1: Abstract to a common unit.** All activity types — regardless of mechanism — reduce to a single common denominator (tonne CO₂e). MGS's Green Square (100g CO₂e) is the equivalent micro-unit.

**Step 2: Enforce quality through methodology.** Each activity type needs an approved calculation methodology — a defensible, conservative way to calculate how many units are earned. Verra has 150+ approved methodologies for different sectors. MGS needs simplified versions for each product/service category it serves.

**Step 3: Verify independently.** Third-party verification decouples trust from the platform. At micro-scale, this requires either project-level verification (expensive per unit) or an activity-database/emission-factor approach backed by periodic audit.

**Step 4: Prevent double-counting.** The most critical integrity requirement. Each unit must have a unique ID, be issued only once, and be retired (used) only once. The Verra registry model (unique serial number + public retirement record) is the standard approach.

**Step 5: Create fungibility through pooling or abstraction.** Green Squares from solar panels and from coffee are interchangeable if (a) they pass through the same quality-gating methodology, and (b) the underlying activity types are comparable in quality and durability. The pool architecture (project-specific unit → quality-gated pool → fungible token) is the on-chain approach. MGS's off-chain equivalent is: verified activity → quality check → Green Square issuance.

### 6.2 Specific Design Recommendations from Market Evidence

**1. Adopt the "Aggregator + Emission Factor" Model (Not the "Per-Activity Credit" Model)**

At £0.003/unit, issuing a formal carbon credit for each Green Square is economically unviable — verification costs would exceed unit values. The practical model is:

- Use approved emission factor databases (DEFRA, GHG Protocol, Ecoinvent) to calculate the CO₂e content of each product/service category
- Issue Green Squares based on these estimates — transparent, auditable, and defensible
- Periodically (e.g., quarterly), MGS retires certified voluntary carbon credits (Verra/Gold Standard) matching the total Green Squares issued — providing a tonne-level backstop
- This is exactly how Stripe Climate operates and why it maintains credibility despite the micro-transaction model

**2. Build a Quality Whitelist (CORSIA Model)**

Define a set of approved activity categories, each with:
- An approved emission factor/methodology
- A minimum quality threshold for the product/service
- A corresponding adjustment mechanism (to prevent double-counting with supplier claims)

Don't try to accept all activities — curate the whitelist and expand it over time. Verra started with a handful of project types and now has 150+.

**3. Solve Double-Counting Before You Scale**

The biggest integrity risk for MGS is double-counting:
- If a coffee brand already claims "carbon neutral" using Verra credits for their supply chain, and MGS also issues Green Squares to the consumer for buying that coffee, the same tonne has been claimed twice
- Solution: require contractual confirmation from supply chain partners that specific emission reductions have not been, and will not be, claimed in the partner's own GHG inventory
- This is analogous to Gold Standard's "Regulatory Surplus" requirement (credits must exceed what's already mandated/claimed)

**4. Create a Buffer Pool / Insurance Reserve**

Nature-based activities have reversal risk (a forest planted today may burn, a rewilded meadow may be ploughed). At the £0.003 price point, an insurance reserve of even 10–15% of Green Squares issued would create a meaningful buffer.

**5. Price Positioning at £30/tonne is Defensible but Requires Premium Narrative**

At 6–9× the commodity spot market, £0.003/Green Square needs to be justified by:
- Convenience and accessibility (frictionless micro-unit vs complex tonne-level purchasing)
- Quality premium (high-integrity activities only, backed by certified credits)
- Co-benefits (SDGs, community impact, consumer engagement)
- Brand trust (MGS as the certifying body)

This is exactly what Gold Standard does vs. raw commodity offsets. The premium is real and sustainable if the quality is real.

**6. Learn from the Specific Failure Modes**

| Failure Mode | Example | MGS Mitigation |
|---|---|---|
| Inflated baselines | REDD+ projects overstating forest threat | Conservative emission factor selection; independent methodology review |
| Perverse incentives | HFC-23 manufacturing for credits | Only allow reductions in activities customers would undertake anyway; no gaming incentives |
| Registry enforcement gaps | Kariba shortfall unresolved | Retire certified credits quarterly; maintain clear public retirement records |
| Speculative token dynamics | KlimaDAO collapse | Design Green Squares as utility tokens, not investment tokens; avoid speculative framing |
| Low-quality aggregation | BCT's "junk carbon" problem | Quality whitelist; regular methodology review; remove activities that fail audit |
| Greenwashing via offsets | Companies buying cheap credits for "carbon neutral" claims | Ensure Green Squares represent genuine activity-embedded reductions, not just offset purchases |

### 6.3 Competitive Positioning

MGS's model — micro-denomination, activity-embedded, consumer-facing — has no direct comparator in the current market. The closest analogues:

| Comparator | Similarity | Key Difference |
|---|---|---|
| Stripe Climate | Micro-contribution aggregation | B2B, not consumer-facing; doesn't create a tradeable unit |
| Doconomy | Consumer-facing carbon footprint tracking | Discontinued; tracking only, not credit issuance |
| Toucan BCT | Fungibility architecture | Institutional/crypto audience; tonne-level minimum |
| Gold Standard | Quality premium positioning | Tonne-level; no consumer interface |

**The opportunity**: No one has successfully created a high-integrity, consumer-facing micro-unit that is both accessible (tiny price point, frictionless earning) and credible (independently backed, no double-counting). The market architecture exists to do it. The main barriers are:
1. Solving double-counting at the consumer/product level
2. Making verification cost-efficient at scale
3. Maintaining price stability vs underlying carbon market volatility

---

## Appendix: Key Sources

| Topic | Source | URL |
|---|---|---|
| Verra VCS Programme | Verra | https://verra.org/programs/verified-carbon-standard/ |
| VCS Methodologies | Verra | https://verra.org/program-methodology/vcs-program-standard/overview/ |
| Gold Standard Paris Alignment 2026 | Gold Standard | https://www.goldstandard.org/publications/paris-agreement-alignment-information |
| Gold Standard Credit Valuation | Gold Standard | https://www.goldstandard.org/news/what-is-a-carbon-credit-worth |
| Plan Vivo Standard | Plan Vivo | https://www.planvivo.org |
| Article 6 Mechanisms | UNFCCC | https://unfccc.int/process-and-meetings/the-paris-agreement/article6 |
| Article 6 Operationalisation | Columbia SIPA CGEP | https://www.energypolicy.columbia.edu/publications/how-to-fully-operationalize-article-6-of-the-paris-agreement/ |
| Article 6 CAs/LoAs FAQ | Sylvera | https://www.sylvera.com/blog/article-6-authorizations-corresponding-adjustments-faq |
| CORSIA Eligible Units | ICAO | https://www.icao.int/CORSIA/corsia-eligible-emissions-units |
| CORSIA Airlines Guidance | IATA | https://www.iata.org/en/programs/sustainability/corsia/ |
| CORSIA ACR Phase 2 Approval | ACR | https://acrcarbon.org/news/acr-approved-by-icao-for-2027-2029-corsia-compliance-period/ |
| CORSIA GreenAir News (Verra/GS Phase 2) | GreenAir | https://www.greenairnews.com/?p=8325 |
| Toucan Protocol FAQs (BCT/NCT) | Toucan | https://blog.toucan.earth/toucan-9-faqs/ |
| Toucan History | Toucan | https://blog.toucan.earth/toucan-history/ |
| Tokenised Carbon Credits Overview | Osler | https://www.osler.com/en/insights/updates/tokenized-carbon-credits-blockchain-revolutionizing-markets/ |
| KlimaDAO Explained | CoinGecko | https://www.coingecko.com/research/publications/what-is-klima-dao-and-how-does-it-work |
| Flowcarbon/Gold Standard Partnership | Flowcarbon | https://www.flowcarbon.com/knowcarbon/flowcarbon-selected-by-gold-standard |
| Carbonplace Platform | Carbonplace | https://carbonplace.com/how-it-works |
| Carbonplace $45m Raise | Markets Media | https://www.marketsmedia.com/bank-consortium-invests-45m-in-carbonplace/ |
| Fractional Carbon Tokenisation | Techaroha | https://techaroha.com/fractional-carbon-credit-tokenization-guide/ |
| Blockchain Carbon Market Architecture | Taylor & Francis | https://www.tandfonline.com/doi/full/10.1080/19498241.2025.2611313 |
| VCM Prices 2025/2026 | Sylvera | https://www.sylvera.com/blog/carbon-market-trends |
| Live Carbon Prices | CarbonCredits.com | https://carboncredits.com/carbon-prices-today/ |
| 2026 Price Forecast | Regreener | https://www.regreener.earth/blog/carbon-credit-prices-today-trends-and-forecasts-for-2026 |
| Credit Pricing Analysis | Carbonmark | https://www.carbonmark.com/post/understanding-carbon-credit-pricing |
| Carbon Credit Comparison 2025 | ClimateSeed | https://climateseed.com/blog/comparison-of-carbon-credits-in-2025 |
| Carbon Market 2026 Guide | Regreener | https://www.regreener.earth/carbon-credits-guide |
| ICVCM Core Carbon Principles | ICVCM | https://icvcm.org/core-carbon-principles/ |
| ICVCM CCP Impact Report 2025 | ICVCM | https://icvcm.org/engagement-impact/ccp-impact-report-2025/ |
| Guardian Investigation Impact (academic) | OUP/ROF | https://academic.oup.com/rof/article/30/1/321/8362620 |
| Guardian vs Verra | Morfo | https://www.morfo.rest/article/verra-vs-guardian-carbon-offsets |
| Verra CEO Departure | Climate Home News | https://www.climatechangenews.com/2023/05/23/verra-boss-steps-down-after-criticism-of-its-carbon-credits/ |
| Kariba Scandal (LA Times) | LA Times | https://www.latimes.com/business/story/2025-10-17/majority-of-carbon-credits-from-tarnished-project-deemed-bogus |
| Kariba Scandal (Bloomberg) | Bloomberg | https://www.bloomberg.com/news/articles/2025-10-17/majority-of-carbon-credits-from-tarnished-project-deemed-bogus |
| Apple/Shell China Projects | Trellis | https://trellis.net/article/apple-shell-china-forest-project-verra-investigation/ |
| Buffer Pools Explainer | Sylvera | https://www.sylvera.com/blog/carbon-credit-buffer-pools |
| VCM Double Counting | ACS Publications | https://pubs.acs.org/doi/10.1021/acs.est.4c03792 |
| Double Counting Tech Solutions | Carbonmark | https://www.carbonmark.com/post/how-technologies-solve-double-counting-problems-in-carbon-markets-key-takeaways-from-cop29-azerbaij |
| Stripe Climate | Stripe | https://stripe.com/climate |
| Doconomy DO Black Card | Mastercard | https://www.mastercard.com/news/europe/sv-se/nyhetsrum/pressmeddelanden/sv-se/2019/april/do-black-the-world-s-first-credit-card-with-a-carbon-limit/ |
| Doconomy discontinued | USA Today | https://www.usatoday.com/story/news/factcheck/2024/05/23/carbon-limit-credit-card-un-fact-check/73816150007/ |
| VCM scandals framework | ScienceDirect | https://www.sciencedirect.com/science/article/pii/S258979182500026X |
| Carbon market quality pricing | Lockton | https://global.lockton.com/news-insights/beyond-price-rethinking-carbon-credit-value-in-the-voluntary-market |

---

*Research compiled for My Green Squares (MGS). All prices and market data as of March 2026. Prices are approximate and subject to significant market volatility.*
