---
tags:
  - logistics
  - sanctions-evasion
  - osint
  - case-study
---

# Case Study: The Al Habsi Network — Iranian Oil, Chinese Buyers, American Banks

In [Logistics 101](logistics-101.md) I sketched the anatomy of a sanctions-evasion scheme in the abstract: dark AIS, ship-to-ship transfers, forged bills of lading, shell ownership. This post takes apart a real, indicted network that allegedly ran that entire playbook end to end — the case of **Mahmood Rashid Amur Al Habsi**, the Omani oil trader on the FBI's wanted list, and his partner **Wang Shaoyun**, wanted on the same warrant.

This is a deep dive built on primary sources: the [12-count federal indictment](https://www.justice.gov/usao-dc/media/1337016/dl) (*United States v. Shaoyun Wang and Mahmood Rashid Amur Al Habsi*, 1:24-cr-00049, D.D.C.), the [DOJ press release](https://www.justice.gov/usao-dc/pr/two-individuals-charged-trafficking-illicit-iranian-oil-using-us-financial-system-fund), [OFAC's 2021 designation](https://home.treasury.gov/news/press-releases/jy0320) of the network, the [FBI wanted pages](https://www.fbi.gov/wanted/counterintelligence/mahmood-rashid-amur-al-habsi), and the [Rewards for Justice](https://rewardsforjustice.net/rewards/wang-shaoyun-mahmood-rashid-amur-al-habsi-and-associated-individuals-and-companies) listing offering up to $15 million. An indictment is an allegation — both defendants are fugitives, presumed innocent until proven guilty.

*One note before the mechanics: every record in this case describes private individuals using private companies. Nothing in the public record implicates the state of Oman or its government in this scheme — the companies were simply registered there, the way shells are registered in Liberia, Gibraltar, and the Marshall Islands throughout this story.*

## The principals

| Role | Who |
|---|---|
| Supply side | **Mahmood Rashid Amur Al Habsi**, Omani, b. 1984 — oil trader; ran acquisition, shipping, and document fraud through his own companies |
| Demand side | **Wang Shaoyun**, Chinese, b. 1969 — director of a Shandong refinery, chair of a Las Vegas company, general manager of its Hong Kong parent; negotiated with buyers and, allegedly, senior IRGC officials |
| The client | **Rostam Ghasemi** (a.k.a. Qasemi) — senior IRGC-Qods Force figure, previously Iran's oil minister, US-designated since 2019; per the indictment, the network operated for his benefit, on a 70/30 revenue split |

The window ran December 2019 to July 2021. The scale the indictment pleads: an allocation letter authorizing up to **10 million barrels per month for five years**.

## The corporate scaffolding

Before a single barrel moved, the network built its ownership maze — the "scrub the identity" layer from the 101 post, precisely mapped by OFAC's designation:

<svg viewBox="0 0 920 410" width="100%" role="img" aria-label="Corporate graph of the Al Habsi network" style="max-width:920px">
  <g font-family="JetBrains Mono, monospace" text-anchor="middle">
    <rect x="340" y="18" width="240" height="62" rx="6" fill="rgba(255,255,255,0.06)" stroke="rgba(255,255,255,0.3)"/>
    <text x="460" y="45" fill="#e6e9ee" font-size="17">AL HABSI</text>
    <text x="460" y="66" fill="rgba(230,233,238,0.55)" font-size="12.5">oil trader · Oman</text>
    <line x1="460" y1="80" x2="135" y2="124" stroke="rgba(255,255,255,0.25)"/>
    <line x1="460" y1="80" x2="460" y2="124" stroke="rgba(255,255,255,0.25)"/>
    <line x1="460" y1="80" x2="785" y2="124" stroke="rgba(255,255,255,0.25)"/>
    <rect x="15" y="124" width="240" height="70" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="135" y="152" fill="#e6e9ee" font-size="14.5">Nimr International LLC</text>
    <text x="135" y="173" fill="rgba(230,233,238,0.55)" font-size="12">Oman · Iraq · UAE</text>
    <rect x="340" y="124" width="240" height="70" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="460" y="152" fill="#e6e9ee" font-size="14.5">Nimr International SRL</text>
    <text x="460" y="173" fill="rgba(230,233,238,0.55)" font-size="12">Romania</text>
    <rect x="665" y="124" width="240" height="70" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="785" y="152" fill="#e6e9ee" font-size="14.5">Bravery Maritime Corp</text>
    <text x="785" y="173" fill="rgba(230,233,238,0.55)" font-size="12">Liberia · Dubai</text>
    <line x1="135" y1="194" x2="135" y2="250" stroke="rgba(255,255,255,0.25)"/>
    <line x1="785" y1="194" x2="785" y2="250" stroke="rgba(255,255,255,0.25)"/>
    <rect x="15" y="250" width="240" height="62" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="135" y="276" fill="#e6e9ee" font-size="14.5">Orbit Petrochemicals</text>
    <text x="135" y="296" fill="rgba(230,233,238,0.55)" font-size="12">Oman · trading arm</text>
    <rect x="665" y="250" width="240" height="62" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="785" y="276" fill="#e6e9ee" font-size="14.5">M/T Oman Pride</text>
    <text x="785" y="296" fill="rgba(230,233,238,0.55)" font-size="12">IMO 9153525</text>
    <rect x="15" y="344" width="300" height="56" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="165" y="367" fill="#e6e9ee" font-size="14.5">WANG SHAOYUN</text>
    <text x="165" y="387" fill="rgba(230,233,238,0.55)" font-size="12">front companies · Las Vegas · HK</text>
    <rect x="605" y="344" width="300" height="56" rx="6" fill="none" stroke="#ff6e40" stroke-dasharray="5 3"/>
    <text x="755" y="367" fill="#ff6e40" font-size="14.5">IRGC-QODS FORCE · Ghasemi</text>
    <text x="755" y="387" fill="rgba(255,110,64,0.7)" font-size="12">the client · 70% split</text>
    <line x1="315" y1="372" x2="605" y2="372" stroke="#ff6e40" stroke-dasharray="5 3" opacity="0.5"/>
  </g>
</svg>

The graph, as the indictment and OFAC tell it:

- **Al Habsi** → **Nimr International L.L.C.** (Muscat; active branches in Iraq and the UAE) → **Orbit Petrochemicals Trading LLC** (Oman) — the trading stack
- **Al Habsi** → **Bravery Maritime Corporation** (Liberia, addressed in Dubai) — the shipping vehicle, registered owner of the tanker
- **Al Habsi** → **Nimr International S.R.L.** (Romania) — a European arm
- Wang's side: a **US company in Las Vegas**, its **Hong Kong parent**, and affiliates across China, Oman, and Turkey

Four jurisdictions to incorporate in, none of them the one where the cargo was born or sold.

## The fleet

Rewards for Justice names eight vessels. The indictment shows how they were actually used — and the split is the interesting part:

| Side | Vessels | Job |
|---|---|---|
| Iranian-flagged (NITC-operated) | *Dino I*, *Dune* | Lift the crude from Iranian terminals |
| Foreign-flagged commercial | *Oman Pride*, *Niovi*, *Carmen*, *Athina II*, *Escapade* | Receive it at sea, carry it to China |

The Iranian ships never approach the buyer. The foreign ships never (on paper) touch Iran. The only place the two sides meet is mid-ocean, engine to engine:

<svg viewBox="0 0 960 330" width="100%" role="img" aria-label="Cargo flow and money flow of the scheme" style="max-width:960px">
  <g font-family="JetBrains Mono, monospace" text-anchor="middle">
    <rect x="10" y="20" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="95" y="49" fill="#e6e9ee" font-size="13.5">IRANIAN TERMINALS</text>
    <text x="95" y="70" fill="rgba(230,233,238,0.55)" font-size="11.5">Kharg · Sirri</text>
    <line x1="182" y1="57" x2="196" y2="57" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="196,52 206,57 196,62" fill="rgba(255,255,255,0.4)"/>
    <rect x="200" y="20" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="285" y="49" fill="#e6e9ee" font-size="13.5">NITC TANKERS</text>
    <text x="285" y="70" fill="rgba(230,233,238,0.55)" font-size="11.5">Dino I · Dune</text>
    <line x1="372" y1="57" x2="386" y2="57" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="386,52 396,57 386,62" fill="rgba(255,255,255,0.4)"/>
    <rect x="390" y="20" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="#ff6e40" stroke-dasharray="5 3"/>
    <text x="475" y="49" fill="#ff6e40" font-size="13.5">STS AT SEA</text>
    <text x="475" y="70" fill="rgba(255,110,64,0.75)" font-size="11.5">AIS dark</text>
    <line x1="562" y1="57" x2="576" y2="57" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="576,52 586,57 576,62" fill="rgba(255,255,255,0.4)"/>
    <rect x="580" y="20" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="665" y="49" fill="#e6e9ee" font-size="13.5">COMMERCIAL TANKERS</text>
    <text x="665" y="70" fill="rgba(230,233,238,0.55)" font-size="11.5">Oman Pride · Niovi · Carmen</text>
    <line x1="752" y1="57" x2="766" y2="57" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="766,52 776,57 766,62" fill="rgba(255,255,255,0.4)"/>
    <rect x="770" y="20" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="855" y="49" fill="#e6e9ee" font-size="13.5">CHINESE PORTS</text>
    <text x="855" y="70" fill="rgba(230,233,238,0.55)" font-size="11.5">Yantai · Lanshan</text>
    <line x1="855" y1="94" x2="855" y2="160" stroke="rgba(255,255,255,0.3)" stroke-dasharray="4 3"/>
    <polygon points="850,160 855,170 860,160" fill="rgba(255,255,255,0.3)"/>
    <text x="480" y="135" fill="rgba(230,233,238,0.45)" font-size="12">cargo flows east · paper says "Oman"</text>
    <rect x="770" y="176" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="855" y="205" fill="#e6e9ee" font-size="13.5">CHINESE BUYERS</text>
    <text x="855" y="226" fill="rgba(230,233,238,0.55)" font-size="11.5">state-owned refineries</text>
    <line x1="768" y1="213" x2="754" y2="213" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="754,208 744,213 754,218" fill="rgba(255,255,255,0.4)"/>
    <rect x="580" y="176" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="#ff6e40"/>
    <text x="665" y="205" fill="#e6e9ee" font-size="13.5">US BANKS</text>
    <text x="665" y="226" fill="#ff6e40" font-size="11.5">$8.5M BLOCKED · Jul 1 2021</text>
    <line x1="578" y1="213" x2="564" y2="213" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="564,208 554,213 564,218" fill="rgba(255,255,255,0.4)"/>
    <rect x="390" y="176" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="475" y="205" fill="#e6e9ee" font-size="13.5">SHELLS</text>
    <text x="475" y="226" fill="rgba(230,233,238,0.55)" font-size="11.5">Marshall Is · UK · HK</text>
    <line x1="388" y1="213" x2="374" y2="213" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="374,208 364,213 374,218" fill="rgba(255,255,255,0.4)"/>
    <rect x="200" y="176" width="170" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="285" y="205" fill="#e6e9ee" font-size="13.5">SPLIT 70 / 30</text>
    <text x="285" y="226" fill="rgba(230,233,238,0.55)" font-size="11.5">IRGC-QF / Wang</text>
    <text x="480" y="300" fill="rgba(230,233,238,0.45)" font-size="12">money flows west — and the dollar node is where it died</text>
  </g>
</svg>

## The operations, voyage by voyage

The indictment pleads specific cargoes. Read as a logistics log:

| Date | Event |
|---|---|
| Feb 7–12, 2020 | *Escapade* loads ~733,616 barrels near **Kharg Island** (~$37M), bound for Qingdao |
| Feb 6, 2020 — the day before | An Al Habsi company emails the *Escapade*'s captain "important instructions": **switch off AIS and LRIT after exiting the Strait of Hormuz, for the entire voyage** |
| Jun 16, 2020 | Al Habsi's Liberian company takes a **$16.5M loan from US financial companies** to buy a tanker — the future *Oman Pride* |
| Jul 18–19, 2020 | *Oman Pride* loads Iranian oil at **Sirri Island** |
| Jul 23–24, 2020 | **STS**: *Oman Pride* transfers ~1.8M barrels (~$73M) to the *Niovi* |
| Aug 18–20, 2020 | *Oman Pride* loads at Kharg; **STS** with NITC's *Dune* |
| Sep 8–11, 2020 | **STS**: ~1.8M barrels (~$66M) to the *Carmen* |
| Oct 20, 2020 | **STS** with NITC's *Dino I*; cargoes comingled with same-day Kharg oil |
| Nov 8–29, 2020 | *Athina II* transfers; **backload to *Oman Pride*** of 190,000 tons of "crude blend" — demanded directly by Ghasemi |
| Nov 7, 2020 – Jan 2021 | Deliveries: *Niovi* discharges at **Yantai**; *Carmen* at **Lanshan** — both Chinese ports |

The concealment stack, exactly as the 101 post ordered it: **AIS dark** (the captain's orders in writing), **STS laundering** (breaking the port-to-port chain), **comingling** (deniable fractions), **bribes** (per Treasury's designation).

## The paper

The forgery layer is where the case gets almost funny. To sell Iranian Light as Omani crude:

- Bills of lading for the *Carmen* and *Niovi* **falsely stated Oman as origin**, with Al Habsi's company as shipper.
- The product was marketed as **"Oman Crude Blend."**
- Buyers received spec sheets for **"Omani Light Crude Oil" that were, in the indictment's words, "identical in all respects" to a 2017 NIOC spec sheet for Iranian Light** — the forgery was a copy-paste of the real document.
- A Certificate of Quality came from **Geochem Middle East**, a legitimate inspection firm — the network simply inserted itself as the client, laundering credibility along with cargo.

And the client relationship was barely hidden. In November 2020, per the indictment, **Ghasemi emailed Al Habsi's company identifying himself as "IRGC Qods Force Deputy," called the *Oman Pride* cargo "our cargo," and demanded a backload.** The beneficiaries were directing operations by email.

## The money

Dollars, through American banks — the stage that killed everything:

- Laundering counts span wires of **$2.2M, $1.0M, $1.8M, $3.3M** (2020) and **$7.4M, $6.7M, $14.0M, $2.2M, $4.6M, $8.5M** (2021), routed through shell companies in the Marshall Islands, the UK, and elsewhere, with US banks misled about the source.
- Revenue split: **70% to the Iranian side, 30% to Wang's company.**
- **July 1, 2021: a US bank blocked the refinery's $8,512,218.90 wire** under E.O. 13224. Within weeks, by Treasury's account, the *Oman Pride* sat idle at anchorage. The scheme was over.

## How it unraveled

??? quote "The referee playbook, executed"
    - **Corporate graph traversal** (Aug 13, 2021): OFAC designated Al Habsi and all four companies in one action — Nimr, Orbit, Bravery Maritime, Nimr SRL — plus the *Oman Pride* itself, under E.O. 13224.
    - **Financial forensics**: the US-bank paper trail, including the $16.5M tanker loan, gave HSI Washington and FBI Minneapolis documents, witnesses, and jurisdiction.
    - **The indictment** (Jan 25, 2024; unsealed Feb 2): 12 counts — IEEPA and sanctions violations, money-laundering conspiracy — and a seizure warrant for ~$8.5M.
    - **The manhunt** (Jun 12, 2025): FBI wanted pages for both; State Department RFJ offer up to **$15 million**. Both remain fugitives.

## The afterlife of a sanctions vessel

Here is the part that makes the case a classic. The star tanker — IMO **9153525** — did not die with the scheme. Public vessel databases (VesselFinder, UANI's tracker, OFAC's own records) let you watch its identity cycle:

**Oman Pride** (2020, Liberia) → *Pride* (2022, St Kitts) → *Rider 1* (2022, Palau) → *Lemur* (2023, Cameroon) → *Lydya N* (2023, Palau) → *Lillian* (2025) → *Sokolo* (2026)

Nine names, six flags, one IMO number — which never changes, and which is how anyone paying attention keeps finding it:

<svg viewBox="0 0 960 300" width="100%" role="img" aria-label="Rename timeline of IMO 9153525" style="max-width:960px">
  <g font-family="JetBrains Mono, monospace" text-anchor="middle">
    <line x1="30" y1="150" x2="930" y2="150" stroke="rgba(255,255,255,0.3)"/>
    <circle cx="60" cy="150" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="60" y="112" fill="#e6e9ee" font-size="13">FRONT VISTA</text>
    <text x="60" y="93" fill="rgba(230,233,238,0.5)" font-size="11">2004 · Marshall Is</text>
    <circle cx="165" cy="150" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="165" y="192" fill="#e6e9ee" font-size="13">DEWI MAESWARA</text>
    <text x="165" y="211" fill="rgba(230,233,238,0.5)" font-size="11">2010 · Indonesia</text>
    <circle cx="270" cy="150" r="6" fill="#ff6e40"/>
    <text x="270" y="112" fill="#ff6e40" font-size="13">OMAN PRIDE</text>
    <text x="270" y="93" fill="rgba(255,110,64,0.75)" font-size="11">2020 · Liberia · OFAC 2021</text>
    <circle cx="375" cy="150" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="375" y="192" fill="#e6e9ee" font-size="13">PRIDE</text>
    <text x="375" y="211" fill="rgba(230,233,238,0.5)" font-size="11">2022 · St Kitts</text>
    <circle cx="480" cy="150" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="480" y="112" fill="#e6e9ee" font-size="13">RIDER 1</text>
    <text x="480" y="93" fill="rgba(230,233,238,0.5)" font-size="11">2022 · Palau</text>
    <circle cx="585" cy="150" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="585" y="192" fill="#e6e9ee" font-size="13">LEMUR</text>
    <text x="585" y="211" fill="rgba(230,233,238,0.5)" font-size="11">2023 · Cameroon</text>
    <circle cx="690" cy="150" r="6" fill="#ff6e40"/>
    <text x="690" y="112" fill="#ff6e40" font-size="13">LYDYA N</text>
    <text x="690" y="93" fill="rgba(255,110,64,0.75)" font-size="11">2023 · Palau · OFAC 2025</text>
    <circle cx="795" cy="150" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="795" y="192" fill="#e6e9ee" font-size="13">LILLIAN</text>
    <text x="795" y="211" fill="rgba(230,233,238,0.5)" font-size="11">2025</text>
    <circle cx="900" cy="150" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="900" y="112" fill="#e6e9ee" font-size="13">SOKOLO</text>
    <text x="900" y="93" fill="rgba(230,233,238,0.5)" font-size="11">2026</text>
    <text x="480" y="268" fill="rgba(230,233,238,0.5)" font-size="12">IMO 9153525 — one hull, one number, nine names</text>
  </g>
</svg>

In March 2025, OFAC **designated the same hull again** — now called *Lydya N*, now property of a Seychelles shell, in the same action that hit Iran's oil minister and the Russia-linked shadow fleet. Per Ukraine's sanctions registry, it was later sold to a Crimea-linked owner. A tanker built for one evasion economy graduated into another. One hull, two wars.

The other vessels scattered similarly: NITC's *Dino I* and *Dune* were separately designated (2024, 2025) for Iran-related transfers; the *Carmen* sails today under yet another name; the *Niovi* — Greek-owned, Panama-flagged — was **seized by Iran's own IRGC Navy in the Strait of Hormuz in May 2023**, while reportedly entangled in a legal dispute with Al Habsi's Nimr International over a suspect cargo. In this world, even the subcontractors get hijacked.

## The logistics read

1. **The scheme was logistics-complete.** Owned tonnage, a two-tier fleet, a four-jurisdiction corporate stack, document fraud, and payment routing — every layer from the 101 post, purpose-built. This is what "heavy logistics skills" means in practice: not genius, but competent systems engineering pointed at an illegal supply chain.
2. **The IMO number is the tell.** Names, flags, owners, and registries all rotate — the immutable identifier is the one the network can't change. Every serious investigator pivots on it; so does every serious registry-hopper failure.
3. **The weak link was money, not ships.** AIS tampering and STS worked as designed. The dollar clearing system was the node the network couldn't route around — and the $8.5M blocked wire is where the story ends.
4. **Sanctions evasion is a renewable industry.** The same hull served Iran's evasion economy and then Russia's. The skills, the shells, and even the steel are transferable — which is why vessel-tracking OSINT tracks hulls, not headlines.

*Tags: [logistics](../tags.md#tag:logistics) · [sanctions-evasion](../tags.md#tag:sanctions-evasion) · [osint](../tags.md#tag:osint) · [case-study](../tags.md#tag:case-study)*
