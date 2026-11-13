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

<svg viewBox="0 0 720 620" width="100%" role="img" aria-label="Corporate graph of the Al Habsi network" style="max-width:720px">
  <g font-family="JetBrains Mono, monospace" text-anchor="middle">
    <rect x="210" y="15" width="300" height="66" rx="6" fill="rgba(255,255,255,0.06)" stroke="rgba(255,255,255,0.3)"/>
    <text x="360" y="44" fill="#e6e9ee" font-size="18">AL HABSI</text>
    <text x="360" y="66" fill="rgba(230,233,238,0.55)" font-size="13">oil trader · Oman</text>
    <line x1="360" y1="81" x2="123" y2="125" stroke="rgba(255,255,255,0.25)"/>
    <line x1="360" y1="81" x2="360" y2="125" stroke="rgba(255,255,255,0.25)"/>
    <line x1="360" y1="81" x2="597" y2="125" stroke="rgba(255,255,255,0.25)"/>
    <rect x="10" y="125" width="226" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="123" y="154" fill="#e6e9ee" font-size="14.5">Nimr International LLC</text>
    <text x="123" y="177" fill="rgba(230,233,238,0.55)" font-size="12.5">Oman · Iraq · UAE</text>
    <rect x="247" y="125" width="226" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="154" fill="#e6e9ee" font-size="14.5">Nimr International SRL</text>
    <text x="360" y="177" fill="rgba(230,233,238,0.55)" font-size="12.5">Romania</text>
    <rect x="484" y="125" width="226" height="74" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="597" y="154" fill="#e6e9ee" font-size="14.5">Bravery Maritime Corp</text>
    <text x="597" y="177" fill="rgba(230,233,238,0.55)" font-size="12.5">Liberia · Dubai</text>
    <line x1="123" y1="199" x2="123" y2="255" stroke="rgba(255,255,255,0.25)"/>
    <line x1="597" y1="199" x2="597" y2="255" stroke="rgba(255,255,255,0.25)"/>
    <rect x="10" y="255" width="226" height="66" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="123" y="282" fill="#e6e9ee" font-size="14.5">Orbit Petrochemicals</text>
    <text x="123" y="304" fill="rgba(230,233,238,0.55)" font-size="12.5">Oman · trading arm</text>
    <rect x="484" y="255" width="226" height="66" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="597" y="282" fill="#e6e9ee" font-size="14.5">M/T Oman Pride</text>
    <text x="597" y="304" fill="rgba(230,233,238,0.55)" font-size="12.5">IMO 9153525</text>
    <rect x="10" y="380" width="320" height="60" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="170" y="405" fill="#e6e9ee" font-size="15">WANG SHAOYUN</text>
    <text x="170" y="426" fill="rgba(230,233,238,0.55)" font-size="12.5">front companies · Las Vegas · HK</text>
    <rect x="390" y="380" width="320" height="60" rx="6" fill="none" stroke="#ff6e40" stroke-dasharray="5 3"/>
    <text x="550" y="405" fill="#ff6e40" font-size="15">IRGC-QODS FORCE · Ghasemi</text>
    <text x="550" y="426" fill="rgba(255,110,64,0.75)" font-size="12.5">the client · 70% split</text>
    <line x1="330" y1="410" x2="390" y2="410" stroke="#ff6e40" stroke-dasharray="5 3" opacity="0.5"/>
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

<svg viewBox="0 0 720 880" width="100%" role="img" aria-label="Cargo flow and money flow of the scheme" style="max-width:720px">
  <g font-family="JetBrains Mono, monospace" text-anchor="middle">
    <rect x="140" y="10" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="38" fill="#e6e9ee" font-size="17">IRANIAN TERMINALS</text>
    <text x="360" y="60" fill="rgba(230,233,238,0.55)" font-size="14">Kharg · Sirri</text>
    <line x1="360" y1="74" x2="360" y2="90" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="354,90 360,102 366,90" fill="rgba(255,255,255,0.4)"/>
    <rect x="140" y="104" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="132" fill="#e6e9ee" font-size="17">NITC TANKERS</text>
    <text x="360" y="154" fill="rgba(230,233,238,0.55)" font-size="14">Dino I · Dune</text>
    <line x1="360" y1="168" x2="360" y2="184" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="354,184 360,196 366,184" fill="rgba(255,255,255,0.4)"/>
    <rect x="140" y="198" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="#ff6e40" stroke-dasharray="5 3"/>
    <text x="360" y="226" fill="#ff6e40" font-size="17">STS AT SEA</text>
    <text x="360" y="248" fill="rgba(255,110,64,0.8)" font-size="14">AIS dark</text>
    <line x1="360" y1="262" x2="360" y2="278" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="354,278 360,290 366,278" fill="rgba(255,255,255,0.4)"/>
    <rect x="140" y="292" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="320" fill="#e6e9ee" font-size="17">COMMERCIAL TANKERS</text>
    <text x="360" y="342" fill="rgba(230,233,238,0.55)" font-size="14">Oman Pride · Niovi · Carmen</text>
    <line x1="360" y1="356" x2="360" y2="372" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="354,372 360,384 366,372" fill="rgba(255,255,255,0.4)"/>
    <rect x="140" y="386" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="414" fill="#e6e9ee" font-size="17">CHINESE PORTS</text>
    <text x="360" y="436" fill="rgba(230,233,238,0.55)" font-size="14">Yantai · Lanshan · Qingdao</text>
    <text x="360" y="474" fill="rgba(230,233,238,0.45)" font-size="13">cargo flows east · paper says "Oman"</text>
    <line x1="360" y1="486" x2="360" y2="502" stroke="rgba(255,255,255,0.3)" stroke-dasharray="4 3"/>
    <polygon points="354,502 360,514 366,502" fill="rgba(255,255,255,0.3)"/>
    <rect x="140" y="518" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="546" fill="#e6e9ee" font-size="17">CHINESE BUYERS</text>
    <text x="360" y="568" fill="rgba(230,233,238,0.55)" font-size="14">state-owned refineries</text>
    <line x1="360" y1="582" x2="360" y2="598" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="354,598 360,610 366,598" fill="rgba(255,255,255,0.4)"/>
    <rect x="140" y="614" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="#ff6e40"/>
    <text x="360" y="642" fill="#e6e9ee" font-size="17">US BANKS</text>
    <text x="360" y="664" fill="#ff6e40" font-size="14">$8.5M BLOCKED · Jul 1 2021</text>
    <line x1="360" y1="678" x2="360" y2="694" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="354,694 360,706 366,694" fill="rgba(255,255,255,0.4)"/>
    <rect x="140" y="710" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="738" fill="#e6e9ee" font-size="17">SHELLS</text>
    <text x="360" y="760" fill="rgba(230,233,238,0.55)" font-size="14">Marshall Is · UK · HK</text>
    <line x1="360" y1="774" x2="360" y2="790" stroke="rgba(255,255,255,0.4)"/>
    <polygon points="354,790 360,802 366,790" fill="rgba(255,255,255,0.4)"/>
    <rect x="140" y="806" width="440" height="64" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="834" fill="#e6e9ee" font-size="17">SPLIT 70 / 30</text>
    <text x="360" y="856" fill="rgba(230,233,238,0.55)" font-size="14">IRGC-QF / Wang</text>
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

<svg viewBox="0 0 720 760" width="100%" role="img" aria-label="Rename timeline of IMO 9153525" style="max-width:720px">
  <g font-family="JetBrains Mono, monospace">
    <line x1="60" y1="20" x2="60" y2="660" stroke="rgba(255,255,255,0.3)"/>
    <circle cx="60" cy="50" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="85" y="46" fill="#e6e9ee" font-size="16">FRONT VISTA</text>
    <text x="85" y="66" fill="rgba(230,233,238,0.5)" font-size="13">2004 · Marshall Is</text>
    <circle cx="60" cy="122" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="85" y="118" fill="#e6e9ee" font-size="16">DEWI MAESWARA</text>
    <text x="85" y="138" fill="rgba(230,233,238,0.5)" font-size="13">2010 · Indonesia</text>
    <circle cx="60" cy="194" r="7" fill="#ff6e40"/>
    <text x="85" y="190" fill="#ff6e40" font-size="16">OMAN PRIDE</text>
    <text x="85" y="210" fill="rgba(255,110,64,0.8)" font-size="13">2020 · Liberia · OFAC designates 2021</text>
    <circle cx="60" cy="266" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="85" y="262" fill="#e6e9ee" font-size="16">PRIDE</text>
    <text x="85" y="282" fill="rgba(230,233,238,0.5)" font-size="13">2022 · St Kitts</text>
    <circle cx="60" cy="338" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="85" y="334" fill="#e6e9ee" font-size="16">RIDER 1</text>
    <text x="85" y="354" fill="rgba(230,233,238,0.5)" font-size="13">2022 · Palau</text>
    <circle cx="60" cy="410" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="85" y="406" fill="#e6e9ee" font-size="16">LEMUR</text>
    <text x="85" y="426" fill="rgba(230,233,238,0.5)" font-size="13">2023 · Cameroon</text>
    <circle cx="60" cy="482" r="7" fill="#ff6e40"/>
    <text x="85" y="478" fill="#ff6e40" font-size="16">LYDYA N</text>
    <text x="85" y="498" fill="rgba(255,110,64,0.8)" font-size="13">2023 · Palau · OFAC designates again 2025</text>
    <circle cx="60" cy="554" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="85" y="550" fill="#e6e9ee" font-size="16">LILLIAN</text>
    <text x="85" y="570" fill="rgba(230,233,238,0.5)" font-size="13">2025</text>
    <circle cx="60" cy="626" r="5" fill="rgba(255,255,255,0.4)"/>
    <text x="85" y="622" fill="#e6e9ee" font-size="16">SOKOLO</text>
    <text x="85" y="642" fill="rgba(230,233,238,0.5)" font-size="13">2026</text>
    <text x="60" y="720" fill="rgba(230,233,238,0.5)" font-size="14" text-anchor="middle">IMO 9153525</text>
    <text x="60" y="742" fill="rgba(230,233,238,0.5)" font-size="14" text-anchor="middle">one hull · one number · nine names</text>
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
