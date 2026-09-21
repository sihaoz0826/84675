# Technology Map — slide and speaking guide

**Course:** 84-375 / 84-675 Geopolitics of Innovation (Canfil)  
**Team:** Steve Zhou, Tiger Li, Gloria Miao  
**When:** Monday, September 28, 2026, 2:00–3:20pm, WEH 4708  
**Length:** 20:00 of content, then 5–10 minutes Q&A (Q&A is *not* in the 20)  
**NSTC area:** Positioning, Navigation, and Timing — **PNT** (government shorthand for “where you are, how you get there, and what time it is”)  
**Product:** **Iridium STL** (Satellite Time and Location) — sold by Iridium Communications Inc. after it bought Satelles, Inc. on 2 April 2024

This file is the notes to build slides from. Sparse slides; timed speech lives here. **11 spoken slides** (7 required + 4 extras). Bibliography is **appendix slides after** the spoken deck — not used to pad the 20 except a ~15 second “sources in the appendix” closer. Architecture is **content on the product slide**, not a separate diagram slide.

**GenAI:** this guide is research for humans to cite. Do not paste ChatGPT onto slides. If anyone uses GenAI later on slides or notes, the syllabus requires a citation of how it was used plus the prompt (verbatim output = quotation marks **and** italics).

**Canvas:** slides + notes due 24 hours before the talk → treat **Sunday, 27 September 2026 ~2:00pm** as the conservative target; check the Canvas clock.

---

## What this is, in one page

Read this before any slide. If you can explain this page out loud, you can explain the product.

### What GPS does

**GPS** is the U.S. Global Positioning System. Satellites high in the sky broadcast a free signal. Your phone, a bank’s computers, a power-grid sensor, and a fighter jet all use that signal to answer two questions: **where am I?** and **what time is it, exactly?**

The family name for all such systems is **GNSS** (Global Navigation Satellite System). GPS is the American one. Europe has Galileo. China has BeiDou. Russia has GLONASS. When we say “GPS” in this talk, we usually mean the U.S. system people actually depend on. When we say GNSS, we mean the whole family.

The “T” in PNT — **timing** — is the quiet superpower. Cell networks, stock trades, and electric-grid sensors need a shared, precise clock. GPS became that clock because it was accurate and free.

### Why GPS can fail

GPS satellites are very far away (about 20,000 km). By the time the signal reaches Earth, it is **weak** — like a whisper. Two attacks matter for this class:

- **Jamming:** blasting radio noise so receivers cannot hear the whisper. Like someone shouting over a conversation.
- **Spoofing:** broadcasting a *fake* GPS signal so the receiver believes a lie — the wrong time, or the wrong place. Like a fake radio station pretending to be NPR.

Ukraine (2022–) made this political, not theoretical. Armies already knew GPS could be jammed. Now governments also worry that **civilian** clocks — 5G, aviation comms, finance — sit on the same fragile signal.

### What Iridium is

**Iridium** is a U.S. company with **66 satellites already in orbit**. They fly in **LEO** — Low Earth Orbit — about 780 km up. That is much closer than GPS (roughly 25 times closer).

Iridium was not built as a GPS rival. Motorola designed it in 1987 as a **satellite phone network**: a cell-tower grid in space so a handset could work over an ocean. The phone business almost died. The Pentagon helped keep the network alive. The satellites are still up, still talking.

Think of Iridium as a fleet of radio towers that happens to fly.

### What STL is

**STL** means **Satellite Time and Location**. It is a **timing and coarse-location signal that rides on those existing Iridium satellites** as a **backup to GPS**.

Nobody launched a new GPS. Engineers reused leftover radio capacity on satellites that were already flying — like putting a trusted clock message onto a phone network’s unused billboard space. A special receiver on the ground reads that message, checks that it is real (not a spoof), and outputs a pulse that means “this is the time.”

**What it is good at:** a trusted clock, including **indoors**, when GPS is jammed, spoofed, or just too weak.  
**What it is not:** a better Google Maps. It does **not** replace GPS for driving or tractor-precision farming.

**One-sentence version for the room:** *GPS is the city’s power grid. Iridium STL is a backup generator that was installed by rewiring a phone company’s existing towers — you did not build a new power plant.*

### Acronyms we will actually say (expand the first time)

| Short | Full name | Plain meaning |
|---|---|---|
| **PNT** | Positioning, Navigation, and Timing | where / how you go / what time it is |
| **GPS** | Global Positioning System | the U.S. space clock-and-map |
| **GNSS** | Global Navigation Satellite System | GPS + Galileo + BeiDou + the rest |
| **LEO** | Low Earth Orbit | nearby space (~780 km for Iridium) |
| **STL** | Satellite Time and Location | Iridium’s GPS-backup time (and rough place) signal |
| **CI** | Critical infrastructure | 5G, power, finance, aviation — the stuff a country cannot afford to lose |
| **ITAR** | International Traffic in Arms Regulations | U.S. munitions export rules (State Department) |
| **EAR** | Export Administration Regulations | U.S. commercial dual-use export rules (Commerce) |
| **CSAC** | Chip-Scale Atomic Clock | a tiny hardware clock (a *different* product; backup topic only) |
| **UTC** | Coordinated Universal Time | the world’s official time; “NIST time” / “Naval Observatory time” are U.S. versions of it |
| **FAA** | Federal Aviation Administration | U.S. civil aviation regulator — a named STL customer via L3Harris |

---

## 0. Why we picked this product (read this second)

**Use Iridium STL.** The syllabus wants **one named product**, not “PNT” and not “GPS as a whole.”

We picked it because a geopolitics class can actually *argue* about it:

- It is **real and on today**, not a slideware constellation.
- It has a **life story** (idea → service in 2016 → Iridium buys the company in 2024).
- It has **politics**: GPS over-dependence, Ukraine jamming, U.S. backup-PNT policy.
- It has **countries in the supply chain** (U.S. operator, Franco-Italian satellite builder, SpaceX launch; older satellites even rode Russian and Chinese rockets).
- It has an **export-control puzzle** (rules written for GPS-like satellites vs a commercial phone network carrying a PNT signal).
- We can show **evidence** of civilian and government use, not just a brochure.

Manufacturer: **Iridium Communications Inc.**, McLean, VA. The service was invented and sold by **Satelles, Inc.** (Reston/Herndon, VA; older name iKare Corp.), then absorbed as **Iridium STL / Iridium PNT**.

It also quietly covers all three NSTC (Feb 2024) PNT subfields without extra slides: a non-GPS source of PNT; spoofing resistance (the signal is authenticated); and it is harder to drown out than GPS because the satellites are closer and shout louder.

### Other products we looked at (and why they lose)

| Candidate | Why it looked tempting | Why it is a worse talk for *this* class |
|---|---|---|
| **Iridium STL** (chosen) | Named system; space + ground + user story; 2016→2024 lifecycle; dual-use + GPS politics; export-control story; NIST / CISA / FAA evidence | — |
| **Microchip SA.45s CSAC** (tiny atomic clock chip) | Beautiful hardware; DARPA/NIST science → 2011 commercial product | Mostly a U.S. lab-to-factory story. Weak *international* sourcing drama. Less GPS geopolitics. |
| **Xona Pulsar** (a new LEO GPS-like startup) | Also a named LEO PNT system | Constellation is not scaled. Hard to answer “did it create markets or displace firms?” without speculating. |
| **Collins MAPS Gen II** (Army GPS-backup box) | Named military product | Basically **military-only**. Dual-use evidence is thin. Public export details are thin. |
| **GPS III (Lockheed)** | Named satellite | Too close to talking about GPS itself. It is a block upgrade of a government utility, not a distinct product story. |

**If the instructor says “STL is a service, not a product”:** the syllabus allows “an actual or conceptual design.” STL is a named, patented design: constellation + receivers. Hardware you can point at: Satelles/Iridium evaluation kits and partner timing boxes (Adtran Oscilloquartz, VIAVI, Safran). **Only switch to the SA.45s CSAC chip if forced.**

---

## 1. Fit-check: the seven syllabus questions in plain English

The assignment is not dumbed down. These are still the seven required answers. The right-hand column is how a non-engineer should *think* about each one.

| # | Syllabus question | How STL answers it (say this, not the spec sheet) |
|---|---|---|
| 1 | What is it / how it works / functions, components, architecture | A GPS-backup **clock** (and a rough “where”) broadcast from Iridium’s 66 existing satellites. Three layers: **space** (the satellites), **ground** (Virginia control, tied to official U.S. time), **user** (a box that checks the signal is real and ticks once a second). |
| 2 | Lifecycle diagram: idea → prototype → scaling → dominant design/platform | Small firm (Satelles) reuses leftover Iridium radio space → 2016 commercial service → partners sell boxes → **2024: Iridium buys Satelles** and STL becomes a platform product. GPS is still the world’s main PNT design; STL is becoming the main *commercial GPS-backup* offering that is actually on. |
| 3 | Inspiration: sci-fi, military, market, both, other | **Both military and market**, not sci-fi. Markets needed indoor/trusted time. Militaries needed GPS that cannot be easily jammed or faked. Bonus origin: leftover capacity on a satphone network looking for a job. The host satellites themselves started as a 1987 Motorola phone idea, later rescued by the Pentagon. |
| 4 | Recombinant or radical + family tree | **Recombinant** (Arthur): new combination of old pieces — existing satellites + leftover messages + cryptography + clock math. Not a new law of physics. Family tree = GPS (space as a clock) + Iridium (loud nearby satellites), not a new kind of orbit. |
| 5 | Sourcing, countries, export controls / standards | U.S. company runs it; France/Italy designed the new satellites; Arizona assembled them; SpaceX launched them. Older Iridium sats also flew on Russian and Chinese rockets. Export rules: **ITAR** (munitions) vs **EAR** (commercial). Washington wrote a munitions clause for “spacecraft that provide PNT signals,” which may be too blunt for a commercial phone network doing backup timing. **We do not have Iridium’s license file — say that.** |
| 6 | Spin-on / spin-off / dual-use / single-use / GPT + evidence | **Dual-use** (civilians *and* governments). Trajectory is **spin-on**: civilian phone network → PNT sold to civilian critical infrastructure *and* to government. Evidence: CISA 2020; NIST tests; L3Harris/FAA 2024 contract; 2016 “buy this off the shelf, Pentagon” pitch. **Not** a general-purpose technology (GPT). |
| 7 | Incremental or disruptive; new markets; displacement | **Disruptive as a GPS-backup clock** (new market: indoor, authenticated, GPS-independent time). **Not** a GPS killer for navigation. Did **not** knock out Lockheed or Qualcomm. Iridium *absorbed* Satelles. |

---

## 2. Timing table (adds to 20:00)

Each person talks **continuously**. No slide-to-slide speaker hopping.

The old 10-slide script was **thin** (~1,965 words ≈ 13–15 minutes at 130–150 words/min). Speak tracks below are ~**2,760 words**. At a normal student pace with pointing at the lifecycle diagram (~130–140 words/min) that is **~19:30–21:00**. Slightly rich on purpose. If you run long, cut spoken extras first; do not skip a required question and do not read the appendix.

| Block | Speaker | Clock | Slides | Minutes |
|---|---|---|---|---|
| 1 | **Steve Zhou** | 0:00–6:40 | 0 Title · 1 Problem (extra) · 2 Product · 3 Lifecycle | **6:40** |
| 2 | **Tiger Li** | 6:40–13:20 | 4 Inspiration · 5 Design · 6 Cooperation | **6:40** |
| 3 | **Gloria Miao** | 13:20–20:00 | 7 Applications · 8 Case (extra) · 9 Implications · 10 Close | **6:40** |
| — | (all, after 20:00) | 20:00+ | Appendix bibliography (not spoken) · Q&A | 5–10 extra |

**Spoken extras (not replacements for the seven):** 0 title/hook · 1 jamming/spoofing problem · 8 named FAA case · 10 course takeaway. There is **no** extra architecture-diagram slide — architecture is a few plain bullets on the product slide. No dedicated handoff *slide* — the handoff is a spoken sentence at the end of Steve’s block and the start of Tiger’s.

**Speaker order:** Steve → Tiger → Gloria. Steve emailed the professor and should open; Gloria closes so the classification and market-claims land last (that is what discussants will attack).

**Handoffs (practice these sentences):**

- Steve → Tiger, end of lifecycle slide: “Tiger will pick up with where the idea came from, why this is recombinant rather than radical, and who actually builds and controls it.”
- Tiger → Gloria, end of cooperation slide: “Gloria will classify the applications — dual-use, not a general-purpose technology — then a named customer, and whether this is incremental or disruptive.”

If a slide runs long, cut the *spoken* extras first (Motorola host lore, partner brand names, 2030 revenue forecast, data-center aside on the case slide). Do not skip a required question.

---

## 3. Stances to hold (do not waffle)

Say these in course language. Each has one everyday comparison.

- **Q4 Design: recombinant, not radical.**  
  **Recombinant** = a new recipe from ingredients already in the kitchen. **Radical** = inventing a new ingredient. STL did not discover a new physics of space. It combined GPS-style “space is a clock,” Iridium’s existing satellites, leftover radio messages, and a password so you can tell a real signal from a fake.

- **Q6 Applications: dual-use, with a spin-on trajectory.** Not spin-off, not single-use, not a GPT.  
  **Dual-use** = the same product has civilian *and* military/government customers — like a pickup truck that farmers and armies both buy.  
  **Spin-on** = civilian tech that security users later pick up (the reverse of GPS: military clock → your phone). Iridium began as Motorola’s satellite-phone bet. STL now times FAA comms.  
  **Spin-off** would be DARPA invents it, Walmart uses it later. That is the tiny atomic-clock chip’s story, not this one.  
  **GPT / general-purpose** would mean it becomes an economy-wide engine, like electricity or GPS itself. STL is a specialized backup.

- **Q7 Implications: disruptive for complementary / GPS-backup *timing*. Incremental as a navigation technique.**  
  **Disruptive** (Christensen) does *not* mean “destroyed GPS.” It means you entered where the incumbent is **weak**. Netflix did not open better video stores; it went after people who hated driving to Blockbuster. STL does not beat GPS at outdoor maps. It goes after indoor clocks and fake-GPS problems. Say that tension out loud. CISA’s own table shows STL failing fine positioning.

Course hooks (Weeks 1–5) — *one spoken line each, not a reading report*:

- **Arthur:** recombinant / combinatory / recursive — existing pieces, nested inside an older network (`Definitions.pdf`).
- **Clark & Henderson:** architectural innovation — same Iridium satellites, new job for the leftover message channel.
- **Cronin (W2):** commercial/open innovation as strategic surprise — the Pentagon can *buy* a GPS backup instead of launching one.
- **Kania / Zegart (W1):** GPS as a securitized, over-relied-upon U.S. foundation; Ukraine jamming as the demand shock.
- **Godin (W4):** **not** the linear model (lab science → product). Unused radio space + market/military demand.
- **Kline & Pinch (W4):** users (data centers, 5G, FAA) pulled STL toward *timing*, not precision farming.
- Lecture typology: this is a **system** sitting on a **platform**; dual-use; not GPT.

---

## 4. Slide-by-slide guide

Required slides keep the **syllabus prompt** as the spine. Short title + prompt on the slide. Extras have no syllabus prompt.

---

### Slide 0 — Title / hook (extra) · Steve · 1:00

**On the slide**

- **Iridium STL:** a backup clock that rides on a satellite-phone network
- One line: **GPS is a whisper. We needed a clock that still ticks when that whisper is jammed or faked.**
- 84-375 / 84-675 · Technology Map · 28 Sep 2026
- Steve Zhou · Tiger Li · Gloria Miao
- Area: **Positioning, Navigation, and Timing (PNT)**
- Product: Iridium Satellite Time and Location (STL)  
  Iridium Communications Inc. (bought Satelles, 2024)
- Tiny footer: “20 minutes · sources in appendix”

**Speak (1:00)**

- We are presenting a backup for the part of GPS nobody notices until it fails: the clock.
- Your phone, a cell tower, and a power-grid sensor all take free time from satellites about 20,000 kilometers up. That signal is a whisper. It can be jammed. It can be faked. When the whisper fails, it is not just maps that break. Clocks do — the shared second that 5G, banks, and grid sensors run on.
- Our product is **Iridium STL** — Satellite Time and Location. A backup clock, already on, hitchhiking on 66 satellites built as phones in space. Nobody launched a new GPS.
- Three speakers, no hopping. I cover what it is and how it grew. Tiger covers origin, design, and who builds it. Gloria covers dual-use evidence and whether it is disruptive.

---

### Slide 1 — Problem (extra) · Steve · 1:35

**On the slide** (one picture, four labels)

- GPS satellites ~20,000 km → **a whisper** at a phone in your pocket
- **Jamming:** shout over the whisper → receiver hears nothing
- **Spoofing:** a fake radio station → receiver believes a lie (wrong time, or wrong place)
- Ukraine 2022–: armies already knew; now **civilian clocks** are the worry (5G, grid sensors, aviation comms)
- 2020 policy line: **stop using only one clock**
- Not on the slide: we are not saying GPS is dying

**Speak (1:35)**

- Here is the problem in one picture. GPS is a public utility that was never designed to be a public utility. The satellites are far away. By the time the signal reaches a phone in your pocket, it is weak — like someone whispering across a football field.
- Two attacks matter for this class. **Jamming** is shouting over the whisper so the receiver hears nothing. **Spoofing** is a fake radio station: the receiver still hears a voice, but the voice is lying about the time or the place.
- Armies have jammed GPS for years. Ukraine from 2022 on made the civilian version political. Cell networks, aviation radios, and grid sensors sit on the same fragile clock. If that clock jumps, 5G can glitch, a trading timestamp can be wrong, and a grid sensor can look healthy when it is not. A geopolitics class cares because this is a country discovering that its civilian clocks sit on a military-grade vulnerability.
- We are not saying GPS is dying. We are saying the United States built a civilization on a free, unauthenticated whisper. The policy response after 2020 was: stop using only one clock. Civilian infrastructure still mostly uses that one clock. That is the hole a backup product can walk into. Next: what the product actually is.

---

### Slide 2 — (1) Product · Steve · 2:20  
**Title:** What is the product, and how does it work?  
**Prompt (smaller):** Discuss core system functions, critical components/subsystems, and architecture in which the components are embedded.

**On the slide** (sparse — human labels, not a spec sheet). Architecture is **plain bullets on this slide**. Do **not** draw a custom phone-vs-box / two-skies diagram.

- **Product:** Iridium STL — a GPS *backup*, not a GPS replacement
- **What it does:** trusted **time** (the main job) + a rough **“where”**
- **GPS far vs Iridium near:** GPS ~20,000 km (a whisper at a phone). Iridium ~780 km (loud bursts, including **indoors**)
- **Architecture — three layers:**
  1. **Space:** 66 low-orbit satellites already used for satellite phones
  2. **Ground:** a control center in Virginia, tied to official U.S. time
  3. **User:** an indoor **box**, not a phone — checks “is this real?” and ticks **once a second**
- Independent test (NIST, not the brochure): good enough for telecom clocks; **not** survey-grade maps
- Optional visual: two photos or two icons (phone vs indoor box). Skip if you don’t want to make it.

**Speak (2:20)**

- STL is a clock message riding on a phone network in space. Analogy: GPS is the city’s power grid. STL is a backup generator installed by rewiring towers that were already there. You did not build a new power plant.
- Iridium’s satellites were already talking to phones. They had leftover radio time — unused billboard space. A company called Satelles put a coded time stamp into that leftover space. The satellite thinks it is sending a short message. The receiver on the ground treats that message as a clock it can trust.
- Three jobs. One: recover official time. Two: get a rough location from when the signal arrives and how the satellite is moving. Three: **authenticate** — prove the burst came from a real satellite beam, not a basement spoofer.
- You do not need four GPS-like satellites in view. A couple of Iridium satellites plus a local clock is the usual mode. Fast low-orbit motion actually helps.
- Architecture in three layers — say them; you do not need a custom picture. **Space:** 66 satellites, about 780 kilometers up, not 20,000. GPS is a continuous weak whisper at a phone in your pocket. STL is short loud bursts at an indoor box. Same job — what time is it — different radio. The satellites also talk to each other, so Iridium can keep constellation time even when many birds are out of sight of U.S. ground stations. GPS depends more on uploading from the ground.
- **Ground:** official U.S. time goes into control in Leesburg, Virginia. That is the studio. The transmitters are the satellites. Each one paints Earth with many narrow spotlights. Each beam has a password that changes about every second. That is the anti-spoof story. A jammer in another country cannot easily replay the right beam’s password.
- **User:** not a phone in a pocket. A small module plus a “pepper shaker” indoor antenna, dropped into an ordinary-looking timing box that ticks once a second into 5G, a data center, or FAA gear.
- How good is the clock? Cite **NIST**, not marketing. Their tests put typical receivers well under a millionth of a second of official U.S. time — telecom-grandmaster territory. That is “keep 5G honest.” It is not “park a tractor on a centimeter.”
- Flag: “a thousand times stronger” is the vendor line that NIST and SpaceNews repeat. Indoor is real. Metal roofs and underground still lose. We are not selling magic.
- Course word: this is a **system** — constellation, ground, receivers — sitting on a **platform**, the Iridium phone network. Next is how that platform got captured.

**If someone asks in Q&A** (do not put this on the slide or in the main speak)

- Orbit: ~780 km LEO; ~25× closer than GPS; vendor/NIST line is ~1,000× / ~30 dB stronger at L-band.
- 6 orbital planes × 11 satellites; ~100-minute period; 86.4° inclination.
- Radio: L-band 1616–1626.5 MHz; ~90 ms bursts on the old paging channel.
- 48 spot beams per satellite; 48 × 66 ≈ 3,168 beams; keys ~1 second (company technical decks).
- Ka-band crosslinks between satellites; user link is L-band ~1620 MHz.
- User chain: antenna → amplifier → radio chip → processor → crypto check → local oscillator → 1 pulse-per-second / 10 MHz output.
- Partner boxes: Oscilloquartz, VIAVI, Safran.
- NIST 2023: typical oven-controlled crystal kit, max offset **<200 ns** vs UTC(NIST); rubidium **<75–80 ns** peak. Later work: some setups meet ITU-T G.8272 PRTC-A (100 ns), i.e. a 5G “grandmaster” clock.

---

### Slide 3 — (2) Lifecycle · Steve · 1:45  
**Title:** Lifecycle  
**Prompt:** Draw a flow diagram of the development and diffusion lifecycle. Key milestones: conceptualization → prototype → scaling → dominant design/platform.

**On the slide** — horizontal flow (this *is* the required diagram):

```
Idea                         Prototype              Scaling                    Platform
Satelles / iKare             Trials                 Commercial service         Iridium buys Satelles
~2008–2015                   before May 2016        23 May 2016 →              2 Apr 2024
“We can put a clock          military / academic    New Iridium satellites     STL becomes Iridium’s
on leftover phone            / commercial demos     finished 2019              own PNT product
radio time”                  (they borrowed a       partners sell the boxes    ~$115M for the rest of
                             network already        “thousands of users”       the company*
                             in orbit)              (O’Connor 2024)
```

Footnote on slide: \*Iridium number; 2030 revenue target is a **forecast**, not a fact.  
Tiny second row: **The phone network underneath:** Motorola 1987 → service 1998 → bankruptcy 1999 → Pentagon rescue 2000 → new satellites 2017–19.

**Speak (1:45)**

- **Idea.** Gregory Gutt and Michael O’Connor — GPS people, not sci-fi writers — realized Iridium’s leftover high-power message channel could carry a clock **without building new satellites**. That is recombinant from day one: reuse, do not reinvent.
- **Prototype.** Before 2016 they ran trials with military, academic, and commercial users. This was not a garage satellite. They were borrowing a multi-billion-dollar network already in orbit.
- **Scaling.** Official service: **23 May 2016**. Iridium then replaced the old satellites, 2017 to 2019. That upgrade did not reinvent STL. It kept the broadcast alive on new buses. Diffusion is through **partners** who put STL into timing boxes. Iridium is not selling you a handset. O’Connor in 2024 said thousands of users. 2023 Satelles revenue was “low tens of millions” — real, not huge.
- Look at the thin rail under the boxes. Satelles never owned the sky. Motorola’s satellite phone, 1987; service 1998; bankruptcy 1999; Pentagon rescue 2000; new satellites 2017 to 2019. STL rented leftover radio time on that history. The 2024 buy is the landlord buying the tenant.
- **Platform.** GPS is still the world’s dominant PNT design. Be honest. STL is becoming the dominant **commercial GPS-backup** offering because it is the one that is **global and on today**. The 2024 buy is the platform move: Iridium’s first-ever company acquisition. Startups like Xona are still scaling. We are not claiming we replaced GPS.
- Handoff: “Tiger will pick up with where the idea came from, why this is recombinant rather than radical, and who actually builds and controls it.”

---

### Slide 4 — (3) Inspiration · Tiger · 2:05  
**Title:** Inspiration  
**Prompt:** How did the idea originate? Sci-fi, military or market demand, both, or something else?

**On the slide**

- **Answer: both military and market** — not science fiction
- **Market:** GPS became an invisible utility for 5G, finance, data centers, power. Indoor GPS is expensive (you still need a roof antenna)
- **Military / state:** GPS jamming and spoofing (older wars; Ukraine 2022 as a later shock); 2020 executive order telling the U.S. to stop relying on one clock
- **Something else:** **stranded capacity** — leftover radio time on a satphone network looking for a job
- **Not:** a 1960s sci-fi prophecy. STL is a 2010s reuse
- One line on the host: Motorola, 1987, global satellite phone — later the **Pentagon as backup customer**

**Speak (2:05)**

- Steve just showed you a clock hitchhiking on a phone network. I will take origin, then why this is recombinant rather than radical, then who builds it and who can export it.
- Take the inspiration menu literally. **Both** military and market. Plus leftover infrastructure. Not science fiction. There is no 1960s novel that predicted a paging channel used as a clock.
- Market pull: critical infrastructure drifted onto GPS because it was free and precise. Then indoor 5G and data centers hit a boring tax — you still needed a rooftop GPS antenna. Banks need the same official time so trades settle on one clock. That is demand for a **trusted second**, not for a new map app.
- Military pull: GPS jamming is an old battlefield problem. In 2016 Satelles already said the Pentagon could buy this **off the shelf**. Ukraine from 2022 did not invent STL — the service already existed — but it **repriced** GPS backups for governments. The 2020 executive order telling the United States to stop relying on one clock is the policy version of that same fear.
- Something else, and this is the clever origin: **stranded capacity**. Motorola designed Iridium in 1987 as a global satellite phone. The phone business almost died. The Pentagon kept the network alive. Years later the leftover high-power message channel was still looking for a job. Godin’s linear model does not apply. Nobody needed a new physics breakthrough in a lab first.
- One honest limit: we do **not** have a public lab notebook that says “the Pentagon asked us in year X.” We infer inspiration from the founders’ GPS-vulnerability briefing in 2016 plus later policy. Do not invent a classified origin story.

---

### Slide 5 — (4) Design · Tiger · 2:15  
**Title:** Design — recombinant, not radical  
**Prompt:** Is the product recombinant or radical? Why? Basic genealogy if preceded by an analogous technology; key differences in hardware and use-cases.

**On the slide**

- **Stance: recombinant** — new recipe, old ingredients (Arthur)
- Also **architectural** (Clark & Henderson): same satellites, new job for leftover messages
- **Family tree (left → right):**
  - GPS: space signals as a public clock
  - Iridium: loud, nearby satellite phones
  - Cryptography: prove the beam is real
  - → **STL**
- **Vs GPS, in human terms:** closer and louder; short bursts, not a continuous whisper; passwords on each spotlight; works indoors; **fine time, coarse place**
- **Use-case shift:** “is this cell tower still on real time if GPS is lying?” — not “where is the tractor?”
- **Not radical:** no new orbit physics; the user is not getting a new kind of atomic clock from the satellite

**Speak (2:15)**

- Arthur’s test, in one comparison. **Recombinant** is making a playlist from songs you already own. **Radical** is inventing a new instrument. STL did not discover a new physics of space. It programs phenomena we already understood — delay, Doppler, radio — by reassembling practices we already had: satellite-phone messages, time-of-arrival, a filter that smooths a local clock, and a password so you can tell a real beam from a fake.
- Recursive, in Arthur’s sense: the constellation was already a nested technology. STL turns it into a component inside a timing rack. Clark and Henderson would call that **architectural innovation**: same Iridium satellites, new job for the leftover message channel. The pieces on the truck did not change. The recipe did.
- Radical would mean a new principle. Pulsar navigation using star clocks. Or a chip-scale atomic clock that *replaces* satellites altogether. That last one is CSAC’s story — Chip-Scale Atomic Clock — a different product we looked at and rejected for this talk.
- Genealogy, left to right on the slide. GPS taught the world to treat space as a public clock. Iridium taught the world a loud low-orbit radio. Cryptography added proof this spotlight is real. Satelles welded those three. That is the family tree. Not a new kind of orbit.
- Differences that matter for politics, not for radio class. Civil GPS is weak, open, and always on — easy to spoof. STL is strong, bursty, and keyed. Use-case shift: from “where is the tractor?” to “is this 5G clock still on real time if GPS is lying?”
- Evidence we are not claiming a GPS killer: CISA’s 2020 table. STL **meets** only the coarsest position bins — think “which harbor,” not “which furrow.” It fails the fine agriculture and construction bins. Recombinant complement. Say that out loud so a discussant cannot pin us as overclaiming.

**If someone asks in Q&A**

- Hardware contrast: LEO vs GPS’s medium Earth orbit; burst TDMA vs continuous GNSS; ~30 dB; spot-beam keys; indoor antenna.
- CISA 2020 Table 5: STL in the **>20 m** position class, **not** <10 cm–10 m.
- Patents: PNT signal validation (e.g. U.S. Patent 11,445,373); TESLA-like hash chains in the technical literature — say “changing beam passwords,” not “TESLA,” unless asked.

---

### Slide 6 — (5) Cooperation · Tiger · 2:20  
**Title:** Cooperation — who builds it, which countries, who can export it  
**Prompt:** How are development and parts sourced? Which countries at which points? Applicable export control regimes or standards?

**On the slide** (three columns — names, not clause numbers)

**Who builds what**

- **United States:** Iridium (runs it, McLean); Satelles (the signal, now bought); Arizona assembly; SpaceX launch; NIST (tests the clocks)
- **France / Italy:** Thales Alenia Space designed and built the new satellites
- **Partners:** Swiss/U.S. and French timing-box firms; UK antennas
- **1990s launches (historical):** U.S., **Russian**, and **Chinese** rockets — not how the new satellites flew

**The export-control punchline**

- **ITAR** = munitions list (State). Includes spacecraft that “provide PNT signals.”
- **EAR** = commercial dual-use list (Commerce). That is where ordinary comms satellites live after reform.
- Washington wrote the munitions clause for **GPS-like** satellites. STL rides a **phone** network. The Office of Space Commerce has said the clause may **over-control** commercial low-orbit PNT.
- We **do not** have Iridium’s license file.

**Speak (2:20)**

- Point at the three columns. The signal — the clock idea — is American intellectual property, written in Virginia, run by Iridium in McLean. The *host satellites* are a Franco-Italian design from Thales Alenia Space, assembled in Arizona, launched by SpaceX from California. That is alliance production, not “America alone.” Swiss and French firms make the timing boxes. A UK firm makes some of the antennas.
- Do not hide the 1990s. The original mesh STL conceptually rides was put up with **U.S., Russian, and Chinese** rockets. The replacement satellites, 2017 to 2019, are **SpaceX-only**. Trajectory: less launch dependence on Russia and China. Not zero foreign content. A geopolitics class should say both sentences.
- Export-control punchline. **ITAR** is the munitions rulebook at the State Department. **EAR** is the commercial dual-use rulebook at Commerce. Washington wrote a munitions line for spacecraft that provide PNT signals — they were thinking GPS-like birds. STL rides a commercial phone network. The Office of Space Commerce has told the PNT Advisory Board that clause may over-control commercial low-orbit PNT. We do not have Iridium’s license file. Say that. Do not guess.
- Why it matters: if you treat a backup clock on a phone network as a munition, you can export-control your own GPS insurance just as Europe and China field Galileo and BeiDou. User boxes: a receive-only indoor timing box with no military GPS mode is almost certainly **EAR, not ITAR**. If someone militarizes it, it can jump. Dual-use is a *legal fork*, not just a slogan.
- Standards are cooperation too. You cannot sell into 5G without the telecom timing language. You cannot radiate without spectrum permission. Iridium’s 1990s spectrum fight is why it *has* a global shout.
- Handoff: “Gloria will classify the applications — dual-use, not a general-purpose technology — then a named customer, and whether this is incremental or disruptive.”

**If someone asks in Q&A** (clause numbers live here)

- ITAR **USML XV(a)(9):** spacecraft that provide PNT signals (OSC 2022: may over-control commercial LEO PNT).
- EAR **9A515:** commercial comms spacecraft after export-control reform.
- Military GNSS / anti-jam antennas: EAR 7A005 / 7A105 / USML XII — **not** a typical STL indoor timing box.
- Civil GNSS-class receivers: often **7A994 or EAR99**. **STL receiver ECCN is not published.**
- FCC / ITU: Iridium exclusive L-band ~1618.7–1626.5 MHz.
- ITU-T **G.8272:** the telecom “primary clock” spec.
- SPD-7: export of U.S. PNT capabilities still licensed case by case.
- NEXT prime = Thales Alenia Space (Thales 67% / Leonardo 33%); AIT = Orbital ATK / Northrop Grumman, Gilbert, AZ.

---

### Slide 7 — (6) Applications · Gloria · 1:50  
**Title:** Applications — dual-use (spin-on), not a general-purpose technology  
**Prompt:** Spin-on / spin-off / dual-use / single-use / general purpose? Show evidence for the classification and any trajectory shifts.

**On the slide**

- **Label: DUAL-USE** — civilians *and* governments buy the same idea  
  *(pickup truck: farm and army)*
- **Trajectory: SPIN-ON** — civilian phone network → clock used by civilian infrastructure **and** governments  
  *(the reverse of GPS: military clock → your phone)*
- **Not** single-use (not Army-only)  
- **Not** general-purpose (that is GPS / electricity; STL is a specialized backup)  
- **Not** classic Pentagon spin-off (that is the tiny atomic-clock chip)

**Evidence (the slide’s job)**

1. **Named civilian contract:** L3Harris + **FAA**, April 2024 — unpack on the next slide
2. **Critical infrastructure list:** CISA/DHS 2020 — STL as a nationwide timing option (then still vendor-reported)
3. **Independent test:** NIST vs official U.S. time — GPS-independent
4. **Government path:** 2016 pitch as off-the-shelf for DoD; after Ukraine, Pentagon interest in GPS independence
5. **Honesty:** CISA table — **not** a precision-nav backup

**Speak (1:50)** — prosecutor, not brochure.

- We pick **one** label: **dual-use**. Dual-use means civilian and military or government customers for the same product. Think of a pickup truck that farmers and armies both buy. The syllabus asks for evidence and a trajectory, not a vocabulary dump.
- **Spin-on**, everyday comparison: Zoom started as office meetings; governments then used commercial video because it already existed. Reverse of spin-off. GPS is the spin-off story — military clock, later your phone. STL is the other way. Motorola’s civilian satphone bet is now a PNT input to FAA communications and, potentially, GPS-denied military ops.
- Evidence one, the best contract, I will open on the next slide with a named customer. Here, three other pieces. **CISA** in 2020, required by Congress, listed STL among nationwide commercial timing options — with a footnote that government had not yet validated vendor numbers. Then NIST *did* validate. Trajectory: claim, then independent measurement, then procurement.
- The 2016 launch quotes already market STL to **military and government as commercial off-the-shelf**. Dual-use is in the original pitch, not a later pivot.
- **Trajectory shift.** Iridium the phone system went commercial, near-death, Pentagon anchor tenant in Hawaii, then re-commercialized. STL rides that dual-use host and itself goes **infrastructure-first, government-interested.** Ukraine is an accelerant, not the birth.
- **Why not general-purpose.** GPS itself is the general-purpose PNT technology. STL is a **specialized complement**. If we call everything GPT, the word dies. NYSE use is a company claim, not audited. “Thousands of users” is company speech.

---

### Slide 8 — Case (extra) · Gloria · 1:40

**On the slide**

- **Named buyer:** L3Harris + **FAA**, five years, April 2024 (same month Iridium closed the Satelles buy)
- Public line: timing that **“removes GPS as the primary clock”**
- What it actually times: **civil aviation communications on the ground** — not a fighter jet, not the airplane’s own GPS
- Scale we can say: more than 36 L3Harris nodes + a similar number of FAA facilities; partner timing boxes
- **Same box, other rooms:** data center (no rooftop GPS antenna); 5G grandmaster clock; CISA’s critical-infrastructure timing family (power, finance, comms)
- Honesty: **no named electric-utility contract** in public sources we found — do not invent one

**Speak (1:40)**

- Abstract dual-use is easy to nod at. Here is a named buyer.
- In April 2024, the same month Iridium closed the Satelles purchase, Iridium signed a five-year contract with L3Harris for the **Federal Aviation Administration**. The public line is a timing architecture that **“removes dependencies on GPS as a primary timing source.”** More than 36 L3Harris nodes, plus a similar number of FAA facilities, using partner timing boxes.
- That is not a fighter jet. That is civil aviation communications — the kind of critical infrastructure this class means when it says the state cannot afford to lose the clock. The box does not fly the airplane. It keeps the ground network on a trusted second if GPS is jammed or spoofed.
- Same box, other buyers. A data center that does not want a rooftop GPS antenna. A 5G operator that needs a grandmaster clock NIST says is in range. CISA listed STL as a nationwide timing option for that whole family — power, finance, communications — not as a precision-nav backup. We do not have a named electric utility contract in public sources. Do not invent one. The FAA deal is the one we can point at.
- Course hook: **Cronin**. The Pentagon and the FAA can *buy* a GPS backup instead of launching GPS-backup satellites. Commercial open innovation as a state move, not a lab surprise.

---

### Slide 9 — (7) Implications · Gloria · 2:15  
**Title:** Implications — disruptive as a GPS-backup clock, not a GPS killer  
**Prompt:** Incremental or disruptive innovation? New markets? Displace dominant companies? Other effects?

**On the slide**

- **Stance: disruptive in the backup-timing market**  
  *(Netflix vs Blockbuster: enter where the incumbent is weak)*
- **Not** disruptive of GPS navigation. As a ranging method, it is **incremental**
- **New market:** commercial “time without GPS” after the 2020 executive order
- **Who got displaced?**
  - **Not** Lockheed (GPS satellites), Qualcomm (phone GPS chips), Galileo/BeiDou
  - **Yes:** Satelles got folded into Iridium
  - Competes with other backups (eLoran, NextNav, etc.) — Washington refused to pick one national winner
- **Other effects:** allied infrastructure resilience; export rules written for a different satellite era
- Iridium forecast (label as forecast): STL **>$100M** a year by **2030**

**Speak (2:15)**

- Incremental versus disruptive is a **market** question here. Arthur’s recombinant question is already answered.
- Christensen in one comparison. Netflix did not beat Blockbuster by opening better stores. It entered where Blockbuster was worst — home, no late fees. STL did not attack GPS where GPS is strongest, which is clear-sky navigation. It entered where GPS is **worst**: indoors, spoofable civil signals, rooftop-antenna cost. That is disruption of the *timing-backup* niche. As a ranging method, it is incremental. It is not creative destruction of GPS.
- New market: “responsible use of PNT” after Executive Order 13905 — layered sources, not one sky clock. CISA’s policy line is **technology-neutral resilience**. That *creates* a market for STL rather than crowning a U.S. ground-based eLoran system as the national backup. Iridium’s own forecast is more than 100 million dollars a year by 2030. Label that as a **forecast**, not a fact.
- Displacement: be disciplined. Qualcomm still ships GPS chips. Lockheed still builds GPS III. Galileo and BeiDou are untouched. What changed is **Iridium’s identity** — first acquisition, PNT as a line of business — and the **backup-PNT vendor field**. eLoran is still not operational in the United States. STL’s advantage is **it is on**.
- Geopolitical effect: a U.S. commercial low-orbit mesh becomes part of **FAA and potentially allied** timing. Cronin: the state piggybacks a private constellation instead of launching “GPS backup satellites.” Other effect: if the munitions clause for PNT spacecraft is applied bluntly, the United States could **export-control its own commercial GPS backup** just as China and Europe field BeiDou and Galileo. Policy lag is the implication.
- Do **not** claim STL has replaced GPS in war. Public evidence is critical-infrastructure timing plus interest — not a fielded Army program of record. That Army box is MAPS, a product we rejected.

---

### Slide 10 — Close (extra) · Gloria · 0:55

**On the slide**

- **Product:** Iridium STL — recombinant GPS-backup clock on a phone network; dual-use; disruptive *as a complement*
- Three takeaways for this course:
  1. **Recombinant, not radical** — leftover satphone messages + nearby loud satellites + beam passwords
  2. **Dual-use, spin-on** — civilian phone network now timing the FAA
  3. **Disruptive as a backup clock, not a GPS killer** — complement, don’t conquer
- Tiny speaker recap: Steve (what / lifecycle) · Tiger (origin / design / controls) · Gloria (use / case / effects)
- **Sources: appendix (next slides)**
- **Questions**

**Speak (0:55)**

- Thirty seconds for the course, then we stop. Iridium STL is **recombinant, not radical**: a new recipe from an old kitchen. It is **dual-use with a spin-on trajectory**: a civilian phone network now timing the FAA. It is **disruptive as a GPS-backup clock**, and it is **not a GPS killer**. Complement, do not conquer. That is the Technology Map in three labels.
- If a discussant asks recombinant versus radical, that was the design slide. Dual-use evidence was applications plus the FAA case. Disruptive versus incremental was implications.
- Our sources — NIST, CISA, Iridium, and the Office of Space Commerce on export controls — are in the appendix. We are not reading a bibliography. Questions.

---

## 5. Appendix slides (not in the 20:00)

Build 2–3 appendix slides. Do not speak them unless asked in Q&A.

### Appendix A — Sources (primary)

1. NSTC, *Critical and Emerging Technologies List Update* (Feb 2024), PNT subfields.
2. Iridium, “Completes Satelles Acquisition; Introduces Iridium STL” (2 Apr 2024).
3. Iridium, “Signs Five-Year Contract with L3Harris to Protect FAA Critical Infrastructure” (9 Apr 2024).
4. SpaceNews, Jason Rainbow, “Iridium to take over GPS backup provider for $115 million” (4 Mar 2024).
5. Iridium, STL commercial launch release (23 May 2016); SatNews / SpaceNews contemporaneous coverage.
6. NIST: Johnson et al., “Measuring the Timing Accuracy of STL Receivers” (ITSF / NIST 2023); follow-on UTC(NIST) papers (100-day MTIE; ionospheric corrections).
7. NIST Technical Note 2189, *Dependencies of Critical Infrastructure Timing Systems on GPS* (STL as GPS-independent public-access time).
8. DHS/CISA (with DOT), *PNT Backup and Complementary Capabilities to GPS* (2020; NDAA FY2017 §1618).
9. Executive Order 13905, “Strengthening National Resilience Through Responsible Use of PNT Services” (12 Feb 2020).
10. Office of Space Commerce / Jason Y. Kim, “U.S. Export Controls on GPS/GNSS Equipment,” PNT Advisory Board (18 Mar 2022) — USML XV(a)(9), 7A005, 7A105, 7A994, 9A515.
11. Thales Alenia Space, Iridium NEXT production (prime; Orbital ATK/NG Gilbert AIT; SpaceX launch).
12. FCC, Big LEO L-band sharing order, Iridium exclusive ~1618.725–1626.5 MHz (2007).
13. Gregory Gutt & Michael O’Connor, “Trusted Time and Location, Everywhere,” GPS.gov PNT Advisory Board (May 2016).
14. Satelles/Iridium technical: RNTF / ATIS WSTS decks on bursts, spot beams, Kalman; U.S. Patent 11,445,373 (PNT signal validation).
15. Inside GNSS, “Iridium STL: Protecting PNT as Part of a Layered Approach”; “LEO PNT Performance Report: STL.”
16. Smithsonian / histories of Iridium bankruptcy and DoD rescue (e.g. Smithsonian *Air & Space*; DISA EMSS contract Dec 2000).

### Appendix B — Uncertainties (put 4 bullets on a slide; say only if asked)

- **STL user-equipment export classification** is not in a public Iridium datasheet we found. Speak analogously (commercial vs munitions forks), not as a classification opinion.
- Whether broadcasting STL makes the new Iridium satellites **munitions-list PNT spacecraft**: **unresolved in public sources**; the Office of Space Commerce flagged the over-control risk.
- **NYSE** and exact user counts: company statements, not independently audited.
- CISA 2020 timing table = **submitter-reported**; NIST later measured — always pair them.
- 2030 **$100M** = Iridium forward-looking statement.
- Direct-to-phone timing = roadmap, not a current mass product.

### Appendix C — Likely discussant questions (Weeks 1–5)

Prepare 20-second answers, in the same plain language as the talk:

1. **Arthur recombinant vs radical?** STL recombines. A wholly radical PNT would look like a new physical channel — pulsars, neutrinos — or a clock chip that replaces satellites.
2. **Clark & Henderson?** Architectural innovation: leftover message channel gets a new job; satellites and radios stay the same kind of thing.
3. **Cronin / open innovation?** Complementary PNT arriving from a listed commercial satellite company, not a classified lab — surprise for states that assumed GPS was the only clock.
4. **Kania / securitization?** Civil GPS and commercial STL still sit inside national-security policy (the 2020 executive order; munitions rules).
5. **Godin linear model?** Unused capacity plus demand. NIST *validated* after the market existed; it did not *invent* STL.
6. **Users as agents (Kline & Pinch)?** Infrastructure timing users pulled the dominant use-case away from “GPS alternative navigation.”
7. **GPT?** GPS maybe. STL no.
8. **Why not CSAC (the tiny atomic clock)?** Different product: a hardware clock vs a satellite service. We needed international sourcing and GPS geopolitics.

---

## 6. Suggested lifecycle diagram (for slide 3 art)

Draw left-to-right chevrons, four boxes, one thin “host constellation” rail underneath:

```
           IDEA                         PROTOTYPE                  SCALING                     PLATFORM
   ┌────────────────────┐      ┌─────────────────┐     ┌─────────────────────┐     ┌──────────────────────┐
   │ Satelles: put a    │ ──▶  │ Trials on a     │ ──▶ │ 23 May 2016 service │ ──▶ │ 2 Apr 2024 Iridium   │
   │ clock on leftover  │      │ network already │     │ partners sell boxes │     │ buys Satelles;       │
   │ satphone radio     │      │ in orbit        │     │ new sats 2017–19    │     │ GPS-backup as a      │
   │ ~2008–2015         │      │                 │     │                     │     │ company product      │
   └────────────────────┘      └─────────────────┘     └─────────────────────┘     └──────────────────────┘
   ════════════════════════════════ HOST RAIL: Motorola satphone 1987 → 1998 service → 1999 bankruptcy
                                    → 2000 Pentagon rescue → new satellites (France/Italy + U.S. launch) 2017–19 ═
```

Visual rules: four equally wide boxes; dates inside; host rail in a different color; a small “GPS remains the world’s main PNT design” callout on the last box so we don’t overclaim.

---

## 7. Facts for Q&A (memorize; do not dump on slides)

| Fact | Source | Caution |
|---|---|---|
| 66 active LEO satellites, ~780 km, 6 planes × 11 | NIST STL papers | Standard Iridium figures |
| L-band ~1616–1626.5 MHz; Iridium exclusive ~1618.7–1626.5 | NIST TN 2189; FCC 2007 | Don’t quote extra digits |
| ~25× closer; ~1,000× / 30 dB stronger | NIST, Iridium, SpaceNews | Vendor-originated, widely repeated |
| 48 spot beams/sat; keys ~1 s | ATIS/Satelles decks | Company technical, consistent |
| ~90 ms bursts on leftover paging radio | RNT Foundation Satelles paper | Explain as “short coded messages,” not “TDMA,” unless asked |
| Service launch 23 May 2016 | Iridium PR | Satelles then a division of iKare |
| iKare former name; Gutt + O’Connor | SEC Form D | Formation ~2008 |
| Iridium owned ~20%; paid ~$115M for ~80%; closed 2 Apr 2024 | Iridium / SpaceNews | First acquisition in company history |
| 2030 >$100M service revenue target | Iridium PR | Forecast |
| 2023 Satelles revenue “low tens of millions” | Desch / SpaceNews | Company |
| NIST: typical crystal kit <200 ns max; rubidium <75 ns (2023) | NIST | Later papers even tighter |
| CISA: STL meets CI *timing*; fails fine *position* | CISA 2020 Tables 2 and 5 | Footnote: then unvalidated |
| L3Harris + FAA 5-year STL, Apr 2024 | Iridium PR; Via Satellite | Oscilloquartz devices in the stack |
| EO 13905, 12 Feb 2020 | Federal Register | “Responsible use of PNT” |
| USML XV(a)(9) PNT-signal spacecraft | OSC 2022 briefing | May over-control commercial LEO PNT |
| New sats: Thales Alenia Space; Arizona assembly; SpaceX Vandenberg | TAS / Iridium PRs | TAS = Thales 67% / Leonardo 33% |
| Original Iridium: Motorola 1987; service 1998; bankruptcy 13 Aug 1999; DISA rescue ~$72M Dec 2000 | Smithsonian; Spaceflight Now; FCW | DoD Hawaii gateway figures vary |
| Helix Geospace UK STL antennas | Vendor | Secondary |

---

## 8. How to turn this into slides (logistics)

- **11 spoken slides** (0–10) + **2–3 appendix**. Do not balloon past this. Required seven are slides **2, 3, 4, 5, 6, 7, 9** in this numbering (syllabus questions 1–7). Extras: 0 title/hook, 1 problem, 8 FAA case, 10 close. Do not merge or drop any of the seven. Do **not** add an architecture-diagram slide — architecture is plain bullets on slide 2.
- Dark, readable, ~6 bullets max. Human labels. Required diagram: the lifecycle flow on slide 3. Optional: a problem picture on slide 1; two photos or two icons on the product slide. Skip those if you do not want to make them.
- Footer on every content slide: short title + “Zhou / Li / Miao · 28 Sep 2026”.
- Print **this file** as speaker notes (device-free class; presenter laptop is the assignment exception — confirm with Canfil how the deck is displayed).
- Rehearse with a phone timer in three 6:40 blocks. If Steve overruns the problem extra or the product slide, Tiger still starts at 6:40.

**Do not:** call the product “GPS”; claim centimeter nav; claim a munitions classification of STL receivers as fact; read the appendix; interleave speakers; put Hertz, decibels, or “PRN / TDMA / burst structure” on a slide without a one-clause why-it-matters gloss.
