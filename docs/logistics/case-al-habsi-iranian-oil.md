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

<svg viewBox="0 0 720 660" width="100%" role="img" aria-label="Corporate graph of the Al Habsi network" style="max-width:720px">
  <g font-family="JetBrains Mono, monospace" text-anchor="middle">
    <rect x="200" y="12" width="320" height="82" rx="18" fill="rgba(255,255,255,0.06)" stroke="rgba(255,255,255,0.3)"/>
    <text x="360" y="34" fill="rgba(230,233,238,0.45)" font-size="11.5">PERSON</text>
    <text x="360" y="56" fill="#e6e9ee" font-size="17">AL HABSI</text>
    <text x="360" y="78" fill="rgba(230,233,238,0.55)" font-size="12.5">oil trader · Oman</text>
    <line x1="360" y1="94" x2="123" y2="138" stroke="rgba(255,255,255,0.25)"/>
    <line x1="360" y1="94" x2="360" y2="138" stroke="rgba(255,255,255,0.25)"/>
    <line x1="360" y1="94" x2="597" y2="138" stroke="rgba(255,255,255,0.25)"/>
    <rect x="10" y="138" width="226" height="88" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="123" y="158" fill="rgba(230,233,238,0.45)" font-size="11.5">COMPANY</text>
    <text x="123" y="180" fill="#e6e9ee" font-size="14.5">Nimr International LLC</text>
    <text x="123" y="202" fill="rgba(230,233,238,0.55)" font-size="12.5">Oman · Iraq · UAE</text>
    <rect x="247" y="138" width="226" height="88" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="360" y="158" fill="rgba(230,233,238,0.45)" font-size="11.5">COMPANY</text>
    <text x="360" y="180" fill="#e6e9ee" font-size="14.5">Nimr International SRL</text>
    <text x="360" y="202" fill="rgba(230,233,238,0.55)" font-size="12.5">Romania</text>
    <rect x="484" y="138" width="226" height="88" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="597" y="158" fill="rgba(230,233,238,0.45)" font-size="11.5">COMPANY</text>
    <text x="597" y="180" fill="#e6e9ee" font-size="14.5">Bravery Maritime Corp</text>
    <text x="597" y="202" fill="rgba(230,233,238,0.55)" font-size="12.5">Liberia · Dubai</text>
    <line x1="123" y1="226" x2="123" y2="282" stroke="rgba(255,255,255,0.25)"/>
    <line x1="597" y1="226" x2="597" y2="282" stroke="rgba(255,255,255,0.25)"/>
    <rect x="10" y="282" width="226" height="88" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="123" y="302" fill="rgba(230,233,238,0.45)" font-size="11.5">COMPANY</text>
    <text x="123" y="324" fill="#e6e9ee" font-size="14.5">Orbit Petrochemicals</text>
    <text x="123" y="346" fill="rgba(230,233,238,0.55)" font-size="12.5">Oman · trading arm</text>
    <rect x="484" y="282" width="226" height="88" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="597" y="302" fill="rgba(230,233,238,0.45)" font-size="11.5">TANKER</text>
    <text x="597" y="324" fill="#e6e9ee" font-size="14.5">M/T Oman Pride</text>
    <text x="597" y="346" fill="rgba(230,233,238,0.55)" font-size="12.5">IMO 9153525 · VLCC</text>
    <rect x="10" y="418" width="320" height="82" rx="18" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
    <text x="170" y="440" fill="rgba(230,233,238,0.45)" font-size="11.5">PERSON</text>
    <text x="170" y="462" fill="#e6e9ee" font-size="15">WANG SHAOYUN</text>
    <text x="170" y="484" fill="rgba(230,233,238,0.55)" font-size="12.5">front companies · Las Vegas · HK</text>
    <rect x="390" y="418" width="320" height="82" rx="6" fill="none" stroke="#ff6e40" stroke-dasharray="5 3"/>
    <text x="550" y="440" fill="rgba(255,110,64,0.65)" font-size="11.5">ORGANIZATION</text>
    <text x="550" y="462" fill="#ff6e40" font-size="15">IRGC-QODS FORCE · Ghasemi</text>
    <text x="550" y="484" fill="rgba(255,110,64,0.75)" font-size="12.5">the client · 70% split</text>
    <line x1="330" y1="459" x2="390" y2="459" stroke="#ff6e40" stroke-dasharray="5 3" opacity="0.5"/>
    <text x="360" y="555" fill="rgba(230,233,238,0.4)" font-size="12">rounded = person · square = company · dashed orange = sanctioned client</text>
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

<svg viewBox="0 0 720 515" width="100%" role="img" aria-label="Route map of the scheme, real coastlines from Natural Earth" style="max-width:720px">
  <defs><clipPath id="casemap-frame"><rect x="0" y="0" width="720" height="378"/></clipPath></defs>
  <g font-family="JetBrains Mono, monospace">
    <rect x="0" y="0" width="720" height="378" fill="rgba(255,255,255,0.015)" stroke="rgba(255,255,255,0.12)"/>
    <g clip-path="url(#casemap-frame)" fill="rgba(255,255,255,0.06)" stroke="rgba(255,255,255,0.35)" stroke-width="1"><path d="M747,18 L745,19 L743,20 L743,23 L742,25 L744,26 L746,27 L747,63 L744,64 L744,66 L743,64 L742,67 L740,67 L738,68 L735,68 L733,67 L734,65 L732,63 L732,61 L733,58 L735,56 L736,54 L734,53 L734,50 L733,48 L731,48 L732,45 L734,46 L737,47 L737,44 L735,43 L734,40 L735,38 L733,37 L730,38 L728,37 L726,36 L724,38 L722,37 L720,37 L722,36 L719,35 L719,32 L721,30 L724,30 L721,29 L722,27 L724,24 L724,22 L721,22 L719,21 L717,22 L715,20 L712,19 L710,20 L707,20 L705,20 L702,21 L700,22 L698,23 L695,24 L694,26 L691,27 L689,28 L686,29 L688,27 L690,26 L691,24 L688,24 L686,22 L688,21 L690,19 L692,18 L694,16 L695,14 L694,12 L692,10 L689,10 L687,10 L684,11 L682,12 L680,14 L679,16 L677,17 L674,18 L672,19 L670,20 L668,23 L667,25 L664,26 L662,26 L659,26 L657,25 L654,26 L653,29 L654,32 L656,34 L659,35 L661,35 L664,35 L666,36 L668,39 L666,40 L666,42 L669,44 L671,44 L674,43 L677,40 L678,39 L681,38 L684,38 L686,40 L688,40 L692,41 L695,41 L697,41 L698,44 L697,46 L694,45 L691,46 L689,47 L685,48 L683,48 L681,50 L681,53 L678,54 L676,52 L678,54 L675,55 L674,58 L671,59 L670,61 L668,62 L668,65 L670,66 L672,67 L675,68 L677,69 L678,72 L679,74 L680,76 L681,78 L682,81 L683,83 L685,85 L687,86 L688,89 L690,90 L692,92 L690,92 L687,91 L684,92 L682,90 L680,89 L677,90 L675,90 L674,88 L672,87 L673,89 L675,90 L678,90 L681,90 L682,92 L685,93 L687,95 L690,96 L692,98 L691,100 L688,101 L686,102 L684,103 L681,104 L678,105 L681,106 L684,106 L686,105 L689,106 L690,108 L692,109 L691,111 L689,112 L691,113 L693,115 L690,115 L688,116 L690,117 L690,119 L687,120 L689,121 L688,123 L685,123 L684,126 L681,126 L682,128 L681,131 L680,133 L677,132 L677,135 L676,137 L674,139 L676,137 L673,138 L673,140 L672,142 L670,144 L668,143 L670,144 L672,144 L671,146 L672,149 L669,148 L667,149 L669,151 L667,152 L665,154 L663,154 L663,157 L661,156 L658,156 L656,158 L658,159 L656,161 L654,163 L652,164 L650,165 L647,165 L646,168 L644,169 L644,172 L641,171 L639,173 L636,172 L634,172 L635,174 L633,173 L630,174 L628,175 L626,176 L623,175 L624,177 L621,177 L620,175 L618,173 L617,170 L620,170 L617,170 L615,172 L617,174 L617,177 L614,177 L614,179 L612,181 L609,181 L607,181 L604,182 L602,183 L599,184 L597,185 L594,184 L592,185 L589,187 L587,189 L589,191 L590,193 L588,195 L586,196 L584,194 L583,191 L582,189 L583,186 L582,184 L580,185 L577,185 L575,183 L573,182 L571,180 L572,183 L569,184 L567,185 L564,185 L562,186 L561,188 L559,189 L556,190 L555,192 L554,194 L552,196 L551,198 L548,199 L547,202 L547,204 L546,206 L547,209 L548,211 L550,213 L552,215 L553,217 L554,220 L556,222 L558,224 L560,226 L562,227 L564,229 L566,231 L568,232 L570,234 L571,236 L573,238 L575,240 L575,242 L576,245 L577,248 L578,250 L578,253 L578,255 L578,258 L579,260 L579,263 L578,265 L578,267 L578,270 L578,273 L576,274 L574,276 L572,277 L570,279 L568,280 L565,282 L563,283 L561,284 L558,284 L556,282 L554,284 L556,286 L554,288 L552,286 L553,288 L550,286 L552,288 L554,290 L553,292 L550,290 L548,288 L550,290 L551,293 L548,295 L545,296 L543,298 L541,300 L539,301 L538,298 L538,296 L538,292 L539,290 L541,288 L539,287 L536,286 L535,284 L532,283 L530,282 L528,284 L528,281 L528,278 L526,280 L523,280 L523,278 L523,275 L522,273 L520,271 L519,269 L516,268 L515,266 L513,265 L510,264 L508,264 L505,264 L503,262 L503,259 L504,257 L501,256 L498,257 L496,257 L496,260 L495,262 L495,265 L495,268 L494,270 L492,274 L491,276 L490,279 L489,282 L488,284 L488,286 L488,289 L488,292 L488,294 L491,295 L493,294 L494,297 L495,300 L496,302 L498,305 L498,308 L499,311 L500,313 L499,311 L498,308 L497,310 L498,312 L502,315 L504,316 L507,316 L510,318 L512,320 L514,322 L518,325 L521,328 L523,330 L524,332 L526,334 L526,337 L526,340 L526,342 L526,345 L526,349 L526,351 L528,354 L530,356 L531,358 L532,360 L533,362 L534,365 L531,364 L529,365 L527,367 L525,364 L522,363 L520,361 L518,360 L515,358 L513,356 L511,355 L508,354 L507,351 L507,349 L505,347 L503,345 L501,343 L501,341 L500,338 L500,336 L499,334 L499,331 L498,328 L498,326 L498,323 L496,321 L495,319 L493,317 L492,314 L491,312 L489,311 L488,309 L486,307 L484,306 L483,303 L481,305 L479,302 L479,300 L480,297 L480,295 L481,292 L482,290 L483,287 L484,285 L482,288 L482,285 L481,282 L483,280 L483,278 L483,275 L484,273 L482,271 L483,269 L482,266 L483,264 L482,261 L482,258 L480,256 L479,254 L478,256 L478,254 L478,251 L477,249 L476,246 L475,244 L475,241 L475,239 L474,236 L473,234 L474,231 L475,229 L472,229 L470,227 L470,225 L469,223 L466,221 L467,224 L466,227 L465,229 L463,230 L461,228 L462,230 L459,230 L457,232 L456,234 L454,236 L453,234 L452,236 L451,233 L450,236 L449,233 L447,235 L448,233 L446,235 L447,232 L447,230 L446,232 L444,234 L443,231 L444,228 L444,226 L445,224 L446,221 L446,218 L445,216 L444,214 L443,211 L442,209 L442,206 L442,204 L441,206 L438,207 L436,204 L439,205 L441,203 L439,201 L438,199 L436,198 L434,197 L432,195 L431,197 L430,194 L429,192 L430,194 L428,192 L426,190 L424,188 L423,185 L423,183 L422,180 L421,178 L420,175 L418,173 L416,174 L414,175 L412,173 L411,170 L410,168 L408,167 L410,168 L409,171 L409,173 L409,176 L410,178 L408,180 L407,182 L406,179 L404,178 L405,176 L404,178 L404,180 L402,182 L401,180 L402,177 L401,180 L400,177 L400,180 L400,182 L398,182 L396,179 L396,182 L394,183 L394,180 L392,183 L392,180 L391,183 L389,183 L388,180 L388,178 L387,180 L386,182 L382,184 L380,184 L377,186 L378,190 L376,193 L375,196 L373,198 L370,197 L372,198 L370,199 L367,200 L365,201 L362,200 L361,202 L363,201 L361,204 L358,206 L356,209 L354,211 L352,213 L349,215 L347,216 L345,218 L343,220 L340,222 L337,223 L336,225 L336,228 L334,230 L331,231 L328,231 L326,232 L325,234 L323,236 L320,235 L318,237 L317,239 L316,242 L316,245 L317,248 L315,250 L317,253 L318,256 L318,259 L317,261 L317,264 L316,266 L314,269 L313,271 L313,274 L312,276 L314,279 L314,283 L314,285 L311,285 L309,286 L308,288 L306,290 L305,293 L308,294 L306,294 L303,295 L301,296 L299,298 L298,301 L297,303 L295,304 L292,305 L289,304 L287,301 L285,299 L284,297 L283,295 L282,291 L281,288 L282,291 L282,288 L281,286 L280,283 L278,281 L278,278 L277,276 L275,273 L273,271 L271,268 L270,266 L269,264 L268,260 L267,258 L267,255 L266,253 L265,250 L264,248 L263,246 L261,244 L260,240 L259,238 L257,235 L256,233 L255,230 L255,228 L255,225 L254,223 L253,220 L253,218 L252,215 L251,213 L251,210 L251,208 L250,205 L250,203 L250,200 L249,197 L250,195 L251,192 L251,190 L250,188 L248,186 L250,184 L253,182 L250,183 L248,181 L248,179 L250,178 L248,178 L245,177 L246,180 L244,182 L246,183 L244,186 L243,188 L240,189 L238,190 L235,191 L233,192 L230,191 L228,189 L226,188 L224,186 L222,184 L220,182 L217,180 L216,178 L218,176 L220,177 L223,176 L225,175 L227,174 L229,171 L226,171 L224,172 L221,173 L218,172 L215,171 L213,169 L211,167 L212,165 L214,163 L212,164 L210,166 L209,164 L206,163 L204,163 L202,161 L201,159 L200,156 L198,155 L195,154 L195,152 L194,150 L192,148 L190,148 L192,148 L190,149 L187,150 L184,150 L182,150 L179,150 L177,151 L174,151 L172,150 L169,150 L167,150 L164,151 L160,151 L157,151 L155,151 L152,152 L150,151 L148,152 L144,151 L142,151 L139,149 L137,150 L134,150 L132,150 L128,149 L126,149 L124,148 L121,148 L118,148 L116,147 L113,146 L111,146 L110,144 L109,141 L109,138 L108,136 L106,134 L104,134 L101,133 L99,134 L96,135 L94,137 L92,137 L89,139 L87,140 L84,139 L82,138 L79,138 L76,136 L73,134 L70,132 L68,130 L65,129 L63,128 L60,128 L58,126 L56,125 L55,121 L54,119 L53,116 L51,115 L51,113 L49,111 L47,109 L46,107 L41,108 L39,106 L37,106 L35,108 L33,108 L30,108 L27,108 L28,110 L26,112 L28,114 L28,117 L30,119 L31,121 L33,124 L34,126 L34,128 L36,130 L39,130 L39,133 L41,134 L44,136 L46,137 L46,140 L47,142 L45,144 L46,146 L48,149 L50,151 L51,153 L52,155 L52,153 L52,150 L52,148 L54,145 L55,143 L58,144 L59,146 L58,148 L59,150 L59,153 L58,156 L57,158 L59,160 L61,161 L64,162 L66,162 L68,160 L71,161 L73,161 L76,161 L78,161 L81,161 L84,160 L86,158 L87,156 L89,154 L91,152 L93,150 L95,148 L97,147 L99,145 L100,142 L102,140 L102,143 L102,146 L102,148 L102,151 L103,154 L104,158 L106,160 L108,162 L111,163 L114,164 L117,164 L120,165 L122,165 L124,167 L126,169 L128,171 L129,173 L131,175 L133,175 L133,178 L132,180 L130,182 L129,185 L126,186 L125,188 L123,190 L122,193 L120,195 L119,193 L117,194 L116,197 L115,199 L114,202 L115,204 L116,207 L112,207 L110,208 L107,209 L105,211 L104,213 L103,216 L100,216 L96,217 L94,218 L92,220 L92,223 L91,225 L88,225 L86,225 L82,225 L80,226 L78,227 L75,227 L73,228 L70,229 L67,231 L65,233 L65,235 L63,238 L61,239 L59,240 L55,242 L51,242 L48,244 L46,245 L43,245 L40,246 L38,247 L36,249 L34,251 L31,252 L29,252 L26,252 L23,254 L20,256 L16,257 L14,257 L11,257 L8,257 L6,258 L4,260 L1,261 L-1,263 L-3,263 L-5,264 L-8,264 L-10,264 L-13,263 L-14,261 L-16,259 L-16,256 L-16,253 L-17,251 L-18,248 L-18,246 L-19,243 L-21,241 L-20,239 L-20,236 L-19,234 L-20,231 L-20,228 L-22,226 L-23,224 L-24,221 L-26,219 L-27,254 L-25,256 L-24,258 L-21,260 L-20,262 L-18,262 L-16,265 L-14,268 L-15,270 L-17,272 L-20,272 L-22,274 L-19,274 L-17,274 L-15,275 L-13,277 L-11,280 L-9,282 L-6,284 L-4,284 L-1,284 L1,283 L4,282 L6,281 L9,281 L11,281 L14,281 L16,280 L19,279 L21,277 L24,278 L28,278 L30,276 L33,276 L35,277 L38,276 L41,276 L43,275 L46,274 L48,273 L50,271 L53,270 L55,271 L56,274 L55,276 L55,279 L55,282 L54,284 L57,284 L54,285 L53,287 L53,290 L52,293 L51,295 L50,297 L48,300 L47,302 L46,304 L44,306 L43,309 L42,311 L39,315 L38,318 L37,320 L35,326 L33,328 L31,331 L29,334 L28,336 L26,339 L23,342 L21,344 L18,347 L16,349 L15,351 L13,352 L10,355 L7,357 L2,360 L0,361 L-3,363 L-6,366 L-8,367 L-11,370 L-14,372 L-16,375 L-19,378 L-21,380 L-23,382 L-25,384 L-26,386"/><path d="M88,9 L85,6 L82,5 L81,3 L80,0 L78,-1 L75,-1 L73,-1 L70,2 L70,5 L71,8 L70,6 L68,3 L67,1 L67,-2 L68,-4 L69,-6 L66,-8 L64,-8 L61,-9 L59,-11 L56,-10 L57,-13 L55,-15 L54,-17 L53,-19 L48,-21 L47,-23 L50,-24 L52,-24 L54,-23 L57,-23 L55,-25 L20,-27 L18,-25 L16,-24 L17,-22 L19,-20 L21,-18 L22,-16 L21,-14 L23,-16 L23,-14 L23,-11 L23,-9 L24,-7 L26,-4 L29,-2 L30,1 L33,2 L35,4 L37,6 L38,8 L40,10 L41,12 L44,13 L46,13 L48,16 L46,15 L43,16 L40,16 L40,19 L39,21 L40,24 L38,26 L35,26 L34,28 L35,32 L35,35 L36,38 L38,40 L43,41 L46,41 L48,44 L51,45 L54,47 L57,48 L61,48 L64,49 L67,48 L70,47 L73,47 L76,46 L80,46 L78,46 L80,47 L81,44 L80,42 L79,38 L79,36 L80,33 L80,30 L81,28 L79,26 L77,24 L75,24 L74,21 L76,23 L76,20 L74,18 L71,18 L72,20 L70,18 L69,16 L70,13 L71,10 L74,11 L76,11 L78,12 L81,12 L85,12 L87,10"/><path d="M584,448 L580,448 L578,447 L575,447 L573,447 L570,448 L567,448 L564,447 L562,446 L559,445 L557,445 L554,445 L553,442 L551,441 L549,439 L546,440 L544,440 L546,438 L547,436 L548,433 L550,431 L552,432 L555,432 L558,433 L560,432 L563,434 L565,434 L568,435 L570,434 L572,436 L572,439 L575,439 L577,440 L580,440 L582,440 L586,440 L589,441 L591,438 L592,436 L594,436 L597,438 L600,438 L602,439 L604,440 L607,440 L609,442 L610,444 L611,446 L613,447 L616,448 L618,447 L621,447 L624,448 L585,449"/><path d="M674,386 L673,383 L673,380 L672,378 L673,376 L674,374 L676,371 L677,369 L679,371 L681,369 L682,367 L685,366 L688,366 L690,368 L692,368 L695,369 L697,369 L700,370 L703,370 L705,370 L708,370 L710,370 L712,369 L714,368 L716,365 L718,364 L721,363 L721,366 L720,368 L718,370 L716,372 L715,374 L712,374 L709,375 L706,375 L704,374 L700,374 L696,374 L693,374 L691,374 L688,374 L686,374 L683,374 L680,373 L677,375 L676,378 L675,381 L676,384 L677,386 L680,387 L681,390 L683,391 L686,390 L687,388 L689,386 L691,386 L694,386 L697,385 L699,385 L702,383 L704,383 L706,385 L705,387 L703,386 L700,386 L699,388 L697,390 L695,392 L693,393 L691,395 L688,395 L689,397 L691,399 L693,401 L694,403 L696,405 L696,408 L695,411 L697,412 L699,414 L701,416 L700,418 L697,418 L695,418 L694,421 L691,421 L688,420 L689,418 L690,415 L687,414 L685,412 L683,410 L684,407 L685,405 L684,402 L682,402 L678,404 L678,407 L679,409 L679,412 L678,415 L678,418 L679,420 L678,423 L678,425 L679,428 L676,428 L674,429 L671,429 L669,427 L670,424 L671,422 L671,419 L672,417 L672,414 L670,412 L670,409 L668,409 L665,410 L664,407 L665,405 L664,402 L666,401 L667,398 L668,396 L669,393 L669,391 L670,388 L671,386 L672,384"/><path d="M504,362 L502,359 L504,357 L507,360 L508,362 L510,363 L513,365 L515,367 L516,370 L518,371 L521,372 L523,373 L521,375 L518,376 L521,376 L523,374 L526,373 L528,375 L529,378 L527,379 L525,380 L527,382 L525,384 L527,386 L529,388 L532,387 L535,388 L535,392 L536,394 L537,396 L538,399 L537,401 L538,399 L541,399 L543,399 L546,401 L547,404 L549,405 L549,408 L547,411 L548,414 L547,416 L548,419 L548,421 L548,424 L548,427 L547,430 L545,429 L543,427 L542,429 L539,429 L537,428 L537,430 L534,429 L533,427 L531,426 L529,423 L527,422 L525,421 L522,419 L519,416 L516,414 L515,412 L514,410 L510,407 L508,404 L506,402 L504,400 L503,398 L503,395 L501,393 L500,390 L498,388 L498,386 L496,384 L494,382 L493,380 L492,377 L489,376 L487,375 L487,372 L486,370 L485,366 L484,364 L482,361 L480,360 L478,358 L475,358 L474,355 L474,352 L471,351 L470,349 L468,346 L466,344 L464,344 L462,342 L459,340 L457,338 L456,336 L454,334 L453,332 L452,330 L454,327 L457,328 L460,330 L462,331 L465,331 L468,330 L470,332 L472,331 L476,334 L477,336 L479,338 L479,340 L482,342 L483,344 L486,345 L488,347 L490,348 L493,349 L495,351 L495,354 L497,354 L498,357 L501,359 L503,360"/><path d="M668,330 L666,333 L663,334 L661,333 L658,334 L660,336 L662,337 L660,339 L657,340 L655,339 L653,341 L654,343 L653,345 L650,345 L652,347 L652,350 L654,351 L655,354 L657,356 L657,358 L656,361 L658,363 L660,364 L662,366 L664,368 L666,370 L663,370 L660,371 L658,370 L656,368 L657,370 L655,371 L654,374 L653,376 L653,379 L652,381 L653,384 L652,386 L650,387 L648,389 L646,388 L644,391 L643,393 L643,396 L644,398 L644,401 L642,403 L640,404 L641,407 L639,409 L637,411 L633,413 L630,414 L627,416 L626,413 L626,410 L624,409 L622,407 L620,409 L618,408 L615,407 L613,406 L609,408 L606,408 L603,410 L601,407 L601,404 L598,404 L594,406 L592,405 L590,404 L588,405 L587,402 L586,400 L586,397 L585,395 L585,392 L585,390 L583,387 L581,386 L578,386 L580,384 L577,383 L577,380 L577,378 L576,375 L575,373 L575,371 L575,368 L578,366 L578,363 L579,361 L582,359 L583,362 L585,363 L588,362 L590,364 L593,364 L595,365 L598,366 L595,365 L595,362 L596,360 L596,357 L598,357 L598,354 L600,352 L603,352 L606,351 L608,351 L612,350 L614,348 L615,346 L619,342 L620,340 L621,337 L623,337 L626,336 L628,334 L630,332 L633,334 L635,332 L634,330 L635,328 L638,328 L639,326 L640,323 L642,321 L644,319 L645,317 L646,315 L646,318 L648,316 L651,318 L653,319 L655,321 L654,324 L656,324 L657,327 L659,326 L662,326 L664,328 L666,330 L668,329"/><path d="M734,312 L733,315 L732,317 L731,320 L730,318 L729,315 L728,313 L725,314 L724,317 L725,319 L726,321 L726,324 L724,326 L722,326 L722,324 L720,325 L718,325 L715,323 L713,322 L711,319 L711,317 L711,314 L713,312 L712,310 L709,309 L707,308 L706,310 L703,310 L700,311 L700,308 L698,309 L696,311 L695,314 L694,316 L692,314 L693,311 L694,309 L695,306 L698,305 L701,305 L702,302 L704,301 L706,300 L708,300 L710,303 L709,306 L711,304 L714,303 L715,300 L717,302 L718,300 L718,297 L720,298 L723,297 L725,295 L724,293 L724,290 L726,292 L728,293 L730,295 L731,297 L732,299 L733,302 L732,304 L733,307 L734,309 L734,311"/><path d="M696,212 L695,215 L694,218 L695,220 L696,222 L698,224 L697,227 L696,229 L695,232 L693,234 L690,234 L690,236 L688,239 L688,241 L689,244 L690,246 L690,249 L692,251 L694,253 L695,250 L697,249 L700,249 L702,251 L703,253 L705,251 L708,253 L710,254 L707,254 L708,257 L709,260 L711,260 L712,263 L712,265 L710,264 L711,262 L709,262 L706,261 L705,259 L704,257 L701,256 L699,254 L697,252 L698,255 L699,257 L697,256 L694,255 L692,253 L690,253 L688,255 L685,255 L683,255 L682,253 L680,250 L682,249 L684,246 L681,245 L680,248 L678,246 L676,245 L675,241 L674,239 L674,236 L673,234 L673,231 L675,232 L678,234 L678,230 L678,227 L679,225 L679,222 L678,219 L679,216 L680,214 L680,212 L682,210 L685,210 L687,211 L690,213 L692,214 L694,211"/><path d="M412,176 L412,178 L411,176 L410,174 L412,176"/><path d="M722,285 L720,285 L720,287 L718,286 L718,284 L718,281 L716,279 L715,276 L717,276 L719,275 L720,278 L720,280 L722,282 L722,285"/><path d="M726,278 L724,278 L722,277 L720,275 L720,272 L718,271 L716,270 L714,266 L716,265 L719,265 L721,265 L723,267 L725,268 L724,271 L724,273 L726,276"/><path d="M583,388 L580,390 L580,387 L583,387"/><path d="M488,393 L486,394 L483,390 L483,387 L485,386 L486,389 L488,391"/><path d="M537,368 L536,370 L534,369 L536,367"/><path d="M517,367 L517,369 L515,368 L515,365 L517,367"/><path d="M463,356 L460,355 L457,354 L457,352 L459,353 L461,355 L463,356"/><path d="M571,343 L569,345 L567,343 L568,340 L570,342"/><path d="M432,258 L431,261 L432,263 L432,266 L431,268 L430,271 L430,274 L428,272 L429,269 L430,265 L430,262 L430,260 L431,257"/><path d="M692,94 L689,94 L687,93 L689,93"/><path d="M738,77 L736,78 L733,79 L730,79 L732,77 L735,76 L737,77"/><path d="M736,448 L734,448 L732,449 L729,449 L731,447 L734,446 L736,448"/><path d="M621,440 L620,442 L617,442 L614,443 L610,442 L611,440 L614,440 L618,440 L621,440"/><path d="M570,404 L569,406 L566,406 L564,407 L563,405 L564,402 L566,401 L568,402"/><path d="M732,394 L730,395 L726,395 L723,395 L726,394 L728,394 L732,394"/><path d="M723,394 L720,395 L717,396 L715,396 L714,393 L717,393 L720,393 L722,394"/><path d="M556,401 L554,404 L552,404 L549,404 L548,401 L547,398 L545,397 L543,397 L543,394 L544,392 L546,394 L548,392 L550,393 L550,396 L551,399 L554,401"/><path d="M746,393 L744,394 L741,393 L744,390 L746,391"/><path d="M706,389 L705,392 L704,390 L701,392 L700,390 L703,388 L704,391 L706,389"/><path d="M746,385 L744,385 L742,383 L741,381 L744,382 L744,384"/><path d="M476,369 L476,372 L474,371 L472,369 L470,367 L471,364 L473,366 L475,368"/><path d="M696,318 L694,320 L692,319 L694,317"/><path d="M716,289 L714,291 L712,292 L709,290 L711,288 L713,287 L715,287"/><path d="M726,289 L725,287 L725,285 L726,287"/><path d="M678,270 L675,270 L674,268 L676,269"/><path d="M712,272 L709,271 L707,269 L704,270 L704,267 L704,265 L706,266 L709,268 L711,270"/><path d="M694,264 L694,266 L693,269 L692,267 L694,264"/><path d="M715,253 L714,256 L711,256 L712,253 L715,253"/><path d="M85,265 L83,266 L80,267 L78,267 L75,265 L77,264 L80,265 L82,264 L85,265"/><path d="M101,135 L99,137 L97,138 L94,139 L96,137 L99,135"/><path d="M332,314 L332,317 L330,320 L327,322 L324,323 L322,324 L319,324 L317,324 L315,322 L314,319 L314,316 L313,313 L313,310 L313,307 L312,305 L314,302 L315,299 L315,297 L316,294 L316,292 L318,293 L320,293 L318,292 L315,291 L318,291 L322,294 L323,296 L324,298 L326,300 L328,302 L328,305 L329,307 L331,309 L332,312"/><path d="M594,201 L592,202 L591,205 L590,207 L589,210 L586,211 L584,212 L582,214 L579,213 L576,213 L574,212 L573,209 L572,206 L573,204 L576,203 L578,201 L580,199 L582,198 L584,198 L587,198 L590,198 L592,198 L594,200"/><path d="M692,153 L691,156 L691,158 L690,161 L689,164 L688,167 L688,170 L686,172 L684,174 L683,177 L683,180 L681,177 L679,176 L677,173 L676,171 L676,168 L676,166 L677,163 L679,161 L680,159 L681,157 L683,155 L684,152 L687,152 L689,150 L692,152"/><path d="M744,380 L744,377 L744,375 L743,372 L743,370 L742,368 L743,365 L743,363 L745,360 L746,358 L746,361 L747,363 L747,366 L745,368 L745,371 L747,368 L747,374 L746,377 L747,380 L747,383 L745,381"/><path d="M707,280 L706,283 L705,286 L704,288 L704,291 L704,293 L704,296 L702,296 L701,294 L698,293 L697,291 L697,288 L700,288 L701,285 L701,282 L702,280 L705,279"/><path d="M711,280 L711,284 L710,286 L708,288 L707,291 L705,293 L705,290 L706,287 L707,285 L709,283 L710,280 L711,277 L712,279"/><path d="M672,283 L670,285 L668,286 L666,288 L664,289 L663,292 L662,294 L660,295 L658,297 L656,299 L653,300 L651,302 L651,299 L654,297 L656,295 L658,294 L660,292 L662,290 L664,288 L666,286 L667,284 L669,282 L669,279 L670,276 L671,278 L671,281"/><path d="M704,275 L703,277 L701,279 L700,281 L697,282 L695,283 L692,284 L693,282 L693,279 L693,276 L694,273 L692,272 L695,272 L697,273 L700,274 L702,275"/><path d="M740,409 L738,411 L736,413 L733,412 L731,410 L729,408 L731,406 L736,406 L738,406 L740,408"/><path d="M689,264 L688,266 L686,268 L684,266 L683,264 L682,262 L680,259 L679,257 L681,257 L684,256 L687,258 L689,260 L688,262"/><path d="M642,412 L641,414 L639,412 L640,409 L642,410"/><path d="M522,371 L520,371 L517,371 L517,368 L520,369 L522,370"/><path d="M510,360 L510,362 L508,361 L510,359"/><path d="M700,422 L698,424 L698,427 L696,426 L696,424 L696,421 L698,420 L700,422"/><path d="M703,425 L701,427 L699,429 L699,426 L700,424 L700,422 L701,419 L703,418 L704,420 L702,422 L702,425"/></g>
    <text x="72.0" y="139.5" fill="rgba(230,233,238,0.35)" font-size="11" text-anchor="middle">PERSIAN</text>
    <text x="76.5" y="145.8" fill="rgba(230,233,238,0.35)" font-size="11" text-anchor="middle">GULF</text>
    <text x="131.4" y="153.9" fill="rgba(230,233,238,0.35)" font-size="9.5" text-anchor="middle">HORMUZ</text>
    <text x="166.5" y="247.5" fill="rgba(230,233,238,0.3)" font-size="11" text-anchor="middle">ARABIAN SEA</text>
    <text x="391.5" y="270.0" fill="rgba(230,233,238,0.3)" font-size="11" text-anchor="middle">BAY OF BENGAL</text>
    <text x="630.0" y="264.6" fill="rgba(230,233,238,0.3)" font-size="11" text-anchor="middle">SOUTH CHINA SEA</text>
    <circle cx="47.9" cy="114.8" r="5" fill="rgba(255,255,255,0.6)"/>
    <circle cx="84.9" cy="145.2" r="5" fill="rgba(255,255,255,0.6)"/>
    <line x1="65.7" y1="138.2" x2="47.9" y2="114.8" stroke="rgba(230,233,238,0.35)" stroke-width="1"/><text x="65.7" y="139.5" fill="#e6e9ee" font-size="13" text-anchor="middle">Kharg</text>
    <line x1="85.5" y1="139.0" x2="84.9" y2="145.2" stroke="rgba(230,233,238,0.35)" stroke-width="1"/><text x="85.5" y="140.4" fill="#e6e9ee" font-size="13" text-anchor="middle">Sirri</text>
    <circle cx="139.5" cy="166.5" r="18" fill="none" stroke="#ff6e40" stroke-dasharray="6 4" stroke-width="2"/>
    <text x="137.7" y="173.7" fill="#ff6e40" font-size="14" text-anchor="start">STS AT SEA</text>
    <text x="137.7" y="180.9" fill="rgba(255,110,64,0.8)" font-size="12" text-anchor="start">AIS dark</text>
    <path d="M47.9,114.8 L53.1,124.2 L61.2,132.3 L75.6,140.4 L91.8,143.1 L104.4,139.0 L113.2,152.4 L126.0,162.0 L162.0,216.0 L207.0,288.0 L265.5,322.2 L319.5,337.5 L369.0,328.5 L436.5,328.5 L450.0,328.5 L464.2,322.0 L479.2,326.2 L508.5,355.5 L515.2,360.0 L522.0,364.5 L526.5,366.8 L533.2,366.8 L535.5,364.5 L535.5,337.5 L551.2,321.8 L585.0,306.0 L612.0,261.0 L657.0,198.0 L679.5,144.0 L691.2,126.0 L694.8,119.6 L693.0,112.5 L703.7,109.9 L697.5,100.8 L698.4,90.0 L697.5,72.0 L698.4,54.0 L699.3,42.3 L698.4,33.3 L687.5,40.1" fill="none" stroke="rgba(255,255,255,0.5)" stroke-width="2" stroke-dasharray="7 5"/>
    <polygon points="694,30 689,39 699,39" fill="rgba(255,255,255,0.6)"/>
    <text x="238.5" y="316.8" fill="rgba(230,233,238,0.45)" font-size="11.5" text-anchor="middle">Oman Pride → Niovi</text>
    <circle cx="687.5" cy="40.1" r="5" fill="rgba(255,255,255,0.6)"/><text x="676.8" y="32.4" fill="#e6e9ee" font-size="12" text-anchor="middle">Yantai</text>
    <circle cx="670.8" cy="59.6" r="5" fill="rgba(255,255,255,0.6)"/><text x="674.1" y="62.1" fill="#e6e9ee" font-size="12" text-anchor="start">Lanshan</text>
    <circle cx="678.4" cy="53.4" r="5" fill="rgba(255,255,255,0.6)"/><text x="682.2" y="54.9" fill="#e6e9ee" font-size="12" text-anchor="start">Qingdao</text>
    <text x="360.0" y="370.8" fill="rgba(230,233,238,0.35)" font-size="10.5" text-anchor="end">coastlines: Natural Earth · route schematic</text>
    <g font-family="JetBrains Mono, monospace" text-anchor="middle">
      <rect x="557" y="402" width="165" height="72" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
      <text x="639" y="428" fill="#e6e9ee" font-size="14.5">CHINESE BUYERS</text>
      <text x="639" y="450" fill="rgba(230,233,238,0.55)" font-size="12">state-owned refineries</text>
      <line x1="555" y1="438" x2="541" y2="438" stroke="rgba(255,255,255,0.4)"/><polygon points="541,433 531,438 541,443" fill="rgba(255,255,255,0.4)"/>
      <rect x="374" y="402" width="165" height="72" rx="6" fill="rgba(255,255,255,0.04)" stroke="#ff6e40"/>
      <text x="456" y="428" fill="#e6e9ee" font-size="14.5">US BANKS</text>
      <text x="456" y="448" fill="#ff6e40" font-size="11.5">$8.5M BLOCKED</text>
      <text x="456" y="464" fill="#ff6e40" font-size="11.5">Jul 1 2021</text>
      <line x1="372" y1="438" x2="358" y2="438" stroke="rgba(255,255,255,0.4)"/><polygon points="358,433 348,438 358,443" fill="rgba(255,255,255,0.4)"/>
      <rect x="191" y="402" width="165" height="72" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
      <text x="273" y="428" fill="#e6e9ee" font-size="14.5">SHELLS</text>
      <text x="273" y="450" fill="rgba(230,233,238,0.55)" font-size="12">Marshall Is · UK · HK</text>
      <line x1="189" y1="438" x2="175" y2="438" stroke="rgba(255,255,255,0.4)"/><polygon points="175,433 165,438 175,443" fill="rgba(255,255,255,0.4)"/>
      <rect x="8" y="402" width="165" height="72" rx="6" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.25)"/>
      <text x="90" y="428" fill="#e6e9ee" font-size="14.5">SPLIT 70 / 30</text>
      <text x="90" y="450" fill="rgba(230,233,238,0.55)" font-size="12">IRGC-QF / Wang</text>
      <text x="360" y="498" fill="rgba(230,233,238,0.45)" font-size="12">money flows west — and the dollar node is where it died</text>
    </g>
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
