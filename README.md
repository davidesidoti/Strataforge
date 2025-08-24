# Strataforge — 1-page GDD & Milestones

Tagline: Dig the past. Build your legacy.

## High concept

First-person, chill-realism paleontology sim with drop-in/out co-op (2–4). Players excavate fossils at real-inspired dig sites, transport finds to a field lab, prepare and assemble specimens, then choose to sell or curate them to fund a fully customizable museum. It uniquely blends careful, hours-long digs, joint discovery unlocks, and deep museum building—filling a gap left by adjacent titles like Dinosaur Fossil Hunter (first-person excavation + museum), Fossil Hunters (casual co-op puzzle-digging), and My Museum: Treasure Hunter (expeditions + restoration).

## Target & platforms

PC first (mouse/keyboard + controller), Steam Early Access. Relaxed, systems-minded players who enjoy methodical loops (PowerWash, House Flipper vibe) and co-op builders.

## Design pillars

• Respect the craft: slow, careful, consequential digs (risk of damage; better tools reduce risk).
• Ownership & curation: your museum, your layout, your story.
• Shared discovery: co-op actions grant joint unlocks; everyone feels progress.

## Core loop (field → lab → museum)

Survey & grid → expose matrix with proper tools (brush, dental pick, air scribe) → stabilize & jacket → crate & haul to trailer/lab → prep & assembly minigames (clean, label, mount) → appraise → sell vs display → reinvest in gear, staff, and museum upgrades → unlock larger/rarer sites.

• Field accuracy touchstones you’ll model: plaster/burlap jacketing for transport; careful prep with air scribes and picks in the lab.

## Progression & pacing

• Sites: starter quarry → desert badlands → rainforest exposures → permafrost.
• Fossil scale: 10–20 min small finds → 60–120 min major skeletons (multi-session beats, auto-save at clear sub-tasks).
• Tools/logistics: hand tools → air scribe, consolidants, hoists/winches, GPR, generators; trailers → trucks → containers.
• Museum meta: rooms/wings, dioramas, signage, lighting, audio guides; staff efficiencies; special exhibitions.

## Multiplayer

• Drop-in/out 2–4; soft roles (mapper, dig lead, hauler, prep tech).
• Joint progression: if a fossil is uncovered together, all participants unlock the codex entry/replica rights.
• Personal museums: each player’s museum is separate; friends can visit, rate exhibits, and leave guestbook notes.

## Economy

Ticket sales scale with authenticity, completeness, and exhibit design; donations spike for special shows; selling funds growth but costs prestige—meaningful trade-offs create distinct playstyles (collector vs trader).

## Systems snapshot

• Digging: voxel/volume chunks with hardness & fragility; damage model (micro-chips reduce value).
• Prep: minigames keyed to real techniques (air-scribe control, consolidant cure time, micro-pinning).
• Museum: grid-free placement with snap tools; visitor AI preferences; satisfaction drives revenue multipliers.
• Research/Codex: provenance, locality, era; bonuses for complete skeletons; replicas for trade/exchange.

## Tech plan (Unity 6)

• Engine: Unity 6 LTS (current 6.x line) for stability/perf.
• Multiplayer: Netcode for GameObjects (first-party high-level SDK) + Unity Transport; relay/lobbies optional later.
• Streaming/content: Addressables for remote specimen bundles and museum props.
• Visuals: HDRP for museum/interiors; scalable settings for field sites.
• Scale/perf: where needed, DOTS/Entities for dig-volume updates and visitor crowds.

## Scope for Vertical Slice (playable 15–30 min)

• One small badlands site (2 micro-finds + 1 medium).
• Field tools: brush, pick, air scribe; basic jacketing & crating.
• Trailer-lab: single prep bench + simple assembly.
• Museum: one hall (10×20 m), 8 display props, lighting, signage, ticket counter, simple visitor loop.
• Co-op: 2 players, joint unlock, museum visiting.

## Key risks & mitigations

• Network sync of deformable digs → authoritative server on dig-volume ops; throttle with command buffers; deterministic tool passes.
• Pacing feels grindy → clear sub-goals, visible progress, mid-dig “jacket & lift” beats.
• Griefing (breaking bones) → opt-in damage, role locks in public lobbies, server settings.
• Content appetite (lots of fossils) → procedural variants + replicas; incremental specimen packs via Addressables. 

---

# Milestone plan (prototype → vertical slice)

All durations are dev-weeks; assume 3–5 person team.

**M0 — Setup & Research (1w)**
Project/CI; coding standards; small reference matrix of real techniques (jackets, prep).

**M1 — Graybox Prototype (4w)**
• Dig tile testbed (single trench), brush/pick interactions, primitive damage.
• Netcode POC: 2 clients, host migration not required.
• Crate/haul loop to a graybox trailer; one museum room with block-out exhibits.
Exit: find → extract → place in display within 10–15 min.

**M2 — Field to Lab Loop (5w)**
• Air-scribe minigame; consolidant/jacketing pass with timers.
• Basic vehicle haul; inventory & labeling; valuation.
• Addressables pipeline for fossil parts.
Exit: single medium fossil playable end-to-end; two-player joint unlock recorded.

**M3 — Museum Core (4w)**
• Placement tools (snap/grid-free), lighting presets, signage; visitor AI stub.
• Ticket revenue & donations; exhibit ratings affecting turnout.

**M4 — Visual & Audio Pass (3w)**
• HDRP setup for museum; field lighting/weather baseline; SFX for tools.

**M5 — Co-op & Save (3w)**
• Joint progression save; friend museum visiting; minimal anti-grief options.

**Vertical Slice (polish 2w)**
• One small site + one medium specimen; 2-player playtest; performance profiling; bug triage.

**Post-VS backlog (EA prep)**
• Second biome; staff systems; more tools (winch/hoist, GPR); visitor behaviors; Steam demo.
