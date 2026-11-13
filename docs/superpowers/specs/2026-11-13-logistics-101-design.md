# Design: Logistics 101 — first post (+ Al Habsi case follow-up)

**Size:** small change (content + one new section).

## Intent & why

First real content on the blog. The author's new interest is logistics, viewed through a
security/intelligence lens: supply chains as things to inspect, evade, or attack
(sanctions evasion, smuggling, gray fleets). The post should teach the field honestly
but with the evasion thread woven throughout, written as concretely as a red team
technique writeup — mechanics, not vibes.

## Goals

- A *Logistics 101* post a newcomer can learn the field from: what logistics is, why it
  matters, its major types.
- Every concept paired with its abuse/inspection counterpart, explained practically
  (how the trick actually works: AIS spoofing mechanics, STS transfers, bill of lading
  fraud, shell-company routing) — sourced from public cases (DOJ, OFAC, UN reports).
- Ends by teeing up post 2, the Al Habsi case analysis.

## Non-goals

- Not an operational how-to for evading sanctions: analysis of publicly documented
  schemes, at the level of indictments and Treasury/UN reporting.
- Post 2 (case analysis of Mahmood Rashid Amur Al Habsi) is designed here but written
  only after post 1 is approved.

## Approach chosen (B — field through the evasion lens)

Alternatives considered: A) neutral primer + security outro (two posts feel disjoint);
C) case-first narrative (buried 101). B keeps one continuous thread and sets the blog's
tone.

## What gets built

- `docs/logistics/index.md` — section index, one-line description, matches existing stubs.
- `docs/logistics/logistics-101.md` — the post (~1,200–1,800 words):
  1. What logistics actually is (the 7 Rs; nodes/links/modes; why it's the world's
     real operating system)
  2. The cast: commercial/supply chain, military, humanitarian, event, reverse —
     each with its "and here's how it gets abused / inspected" sidebar
     (admonition blocks), e.g. commercial → gray fleets, AIS spoofing, STS transfers;
     documentation → B/L fraud; military → proxy resupply; humanitarian → aid diversion
  3. The referee problem: sanctions & export controls as the "blue team" of logistics
     (OFAC, UN PoE, vessel tracking)
  4. Teaser for the Al Habsi case
- `mkdocs.yml` — add `Logistics: logistics/index.md` to nav (between Research and Tags).
- Tags on the post: `logistics`, `sanctions-evasion`, `osint`.
- Uses existing theme features: admonitions, collapsible details for sidebars.

## Left to the builder

- Final wording, section order tweaks, specific examples per type.
- Post 2 outline (not written yet): `case-al-habsi-iranian-oil.md` — network, scheme
  mechanics, how investigators unpicked it, logistics concepts it demonstrates.
