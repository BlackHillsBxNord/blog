---
tags:
  - logistics
  - sanctions-evasion
  - osint
---

# Logistics 101: The Field That Runs the World

Every field of security research eventually bends toward the same question: *how does the thing actually get from A to B?* Malware analysts trace supply chains of software. Intelligence analysts trace supply chains of weapons and oil. Sanctions enforcers trace supply chains of money — which is just cargo that moves faster.

Logistics is the discipline that answers that question. This post is a field guide: what logistics actually is, its major branches, and — because this is a security blog — how each branch gets inspected, gamed, and attacked. Think of it as recon on an entire industry.

## What logistics actually is

The classical definition is the **seven Rs**: getting the *right product*, in the *right quantity*, in the *right condition*, to the *right place*, at the *right time*, to the *right customer*, at the *right cost*. Miss any one of the seven and the operation failed, even if the cargo arrived.

Every logistics system, from Amazon to a sanctions-evasion network, decomposes into three primitives:

- **Nodes** — fixed points where cargo rests or changes hands: ports, warehouses, airports, factories, transshipment hubs.
- **Links** — the routes between them: sea lanes, air corridors, rail lines, roads, pipelines.
- **Modes** — how cargo physically moves: container ship, bulk carrier, air freight, truck, rail, mule, dhow.

That's it. Everything else — customs brokers, bills of lading, freight forwarders, letters of credit, AIS transponders — is *coordination overhead* layered on top of nodes, links, and modes to make the seven Rs verifiable between parties who don't trust each other.

That last sentence is the whole reason this field matters to security people. **Logistics is trust made mechanical.** And anywhere trust is mechanical, it can be spoofed, forged, or bought.

## The cast — and how each one gets gamed

### Commercial / supply chain logistics

The big one: more than 80% of world trade by volume moves by sea. Container shipping, bulk commodities, tankers, air cargo, and the warehouse-and-truck "last mile" that puts it in your hands.

Commercial logistics runs on documents as much as ships. The *bill of lading* (B/L) is the key one: it's simultaneously a cargo receipt, a contract of carriage, and proof of ownership. Present the original B/L at destination, collect the goods. Banks finance shipments against these papers through letters of credit. In a very real sense, world trade is a document-processing system with ships attached.

??? quote "How it gets gamed: the gray fleet playbook"
    The techniques below are all documented in US Treasury/OFAC designations, DOJ indictments, and UN Panel of Experts reporting. The anatomy of an evasion scheme:

    - **Go dark.** Ships carry an AIS transponder that broadcasts identity and GPS-derived position. The UN Panel of Experts on North Korea documented vessels switching AIS off before illicit ship-to-ship (STS) transfers of coal and fuel — the "dark period" is itself a detection signal.
    - **Spoof the position.** AIS is unauthenticated and trivially forged. Analysts (notably C4ADS in its work on North Korea's fleet) have caught vessels broadcasting *fake* AIS positions — appearing to sit in one port while physically transferring cargo elsewhere. Maritime-intelligence firms (e.g. Windward's published analyses) describe a commercial market in AIS manipulation — spoofing as a service.
    - **Scrub the identity.** "Flag-hopping" — repeatedly re-registering the ship under new flag states — plus layered shell ownership and repeated renames make beneficial ownership a maze. This is the modern "gray fleet": aging tankers with opaque owners, first observed at scale moving sanctioned Russian and Iranian crude.
    - **Forge the paper.** Falsified or forged bills of lading misdeclare origin ("this isn't Iranian crude, it's Omani blend"), enabling the cargo to enter legitimate finance. The DOJ's case against Omani broker Mahmood Al Habsi and Chinese national Wang Shaoyun alleges exactly this: Iranian oil relabeled and sold into the legal market, payments laundered through US banks.
    - **Blend it.** Mixing sanctioned cargo with clean product at a compliant port makes the tainted fraction statistically deniable — documented in Reuters reporting on Iranian crude blended in Malaysian waters before delivery to China, and in UN Panel of Experts reporting on blended petroleum exports.

    The inspection side — how analysts catch this — is beautiful OSINT: AIS gap analysis, satellite imagery of STS transfers at known anchorage hotspots, hull-number mismatch (transponder says one ship, imagery shows another), and corporate-registry pivoting on shell owners. U.S. government sources on the Al Habsi case: [FBI wanted page](https://www.fbi.gov/wanted/counterintelligence/mahmood-rashid-amur-al-habsi), [DOJ press release](https://www.justice.gov/usao-dc/pr/two-individuals-charged-trafficking-illicit-iranian-oil-using-us-financial-system-fund), [Rewards for Justice](https://rewardsforjustice.net/rewards/wang-shaoyun-mahmood-rashid-amur-al-habsi-and-associated-individuals-and-companies).

### Military logistics

The branch with the oldest pedigree — the word itself comes from war. Amateurs talk tactics; professionals talk logistics, because an army that can't be fed, fueled, and resupplied stops being an army. Military logistics is the same nodes/links/modes triad under an adversary trying to destroy your links.

??? quote "How it gets gamed: proxy resupply"
    States under sanctions don't move cargo with flagged military transports — they outsource to deniable civilian logistics. UN Panel of Experts reporting on Iran has documented small arms and components moving to proxy forces via unremarkable civilian dhows and trucks across the Gulf and land corridors: no flags, no manifests, mixed in with legitimate fishing and trade traffic. The evasion principle is *camouflage by context* — make your link indistinguishable from the environment's normal traffic. It's the physical version of hiding a C2 channel in ordinary HTTPS.

### Humanitarian logistics

Moving food, medicine, and shelter into crisis zones — often the hardest logistics on Earth: destroyed infrastructure, no functioning customs authority, and armed actors at every node. Organizations like the WFP's logistics arm run entire shipping lines and airlifts.

??? quote "How it gets gamed: aid diversion"
    The UN's own reporting (including UN Panel of Experts findings on Somalia and the WFP's 2019 partial suspension of food aid distributions in Yemen over diversion) documents aid diverted by armed groups and coordinated networks: siphoning from convoys, falsifying beneficiary lists, and taxing access to routes. The security lesson: in any low-trust environment, the *distribution layer* is the softest target — the last mile is where verification is weakest and local power structures interpose themselves.

### Event & reverse logistics

Two smaller but instructive branches. **Event logistics** moves enormous volumes on brutal one-shot deadlines (think Olympics or a military deployment). **Reverse logistics** is everything flowing *backwards*: returns, repairs, recycling, end-of-life.

??? quote "How it gets gamed: returns fraud"
    Reverse flows are fraud magnets because legitimate reverse traffic is anomalous by nature — irregular, poorly documented, priced by disposal logic rather than market logic. Documented patterns include returns of stolen goods for cash, counterfeit-for-genuine swaps (buy real, return fake), and brute-force refund fraud — tracked annually in the NRF's National Retail Security Survey and prosecuted in organized retail-crime cases. It's the same principle as cargo blending: a channel with intentionally noisy baselines is where anomalies hide best.

## The referees: sanctions & export controls

Every red team needs a blue team. In logistics, that's the sanctions and export-control apparatus: OFAC in the US Treasury (which maintains the SDN list and designates evasion networks), the UN Security Council and its Panels of Experts (which investigate and publish), national customs authorities, and an ecosystem of open-source investigators — journalists, NGOs like C4ADS, and hobbyist vessel trackers — who do for shipping what bug bounty hunters do for software.

Their detection toolbox, from the public case literature:

- **AIS gap analysis** — where did the transponder go quiet, and does the gap overlap a known STS hotspot?
- **Identity forensics** — hull number, paint, and superstructure matching against the claimed identity (vessels get "plastic surgery" too).
- **Corporate graph traversal** — shell-company chains across registries until a beneficial owner falls out.
- **Financial forensics** — payment flows through correspondent banks that reveal the forged-paper trail.
- **Satellite tasking** — revisit a suspicious anchorage and photograph the transfer.

It's a cat-and-mouse with real stakes: the mouse gets indicted, the cat gets a $15 million reward program.

## Where this is going

Everything above — dark AIS, STS transfers, forged bills of lading, shell ownership — isn't hypothetical. It's the alleged operating model of a real, indicted network.

In the next post I'll take apart the case of **Mahmood Rashid Amur Al Habsi**, the Omani oil broker on the FBI's wanted list: how a few hundred million dollars of Iranian crude allegedly moved from sanctioned wells to willing buyers, which of the tricks from this post the network used at each stage, and how investigators unpicked it. Logistics 101, graded on a real exam.

*Tags: [logistics](../tags.md#tag:logistics) · [sanctions-evasion](../tags.md#tag:sanctions-evasion) · [osint](../tags.md#tag:osint)*
