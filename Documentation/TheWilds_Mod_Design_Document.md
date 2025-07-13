
# The Wilds: Satisfactory - Mod Design Document

## Overview

**Mod Name:** The Wilds: Satisfactory  
**Game:** Satisfactory (UE 5.3.x+)  
**Mod Type:** Difficulty Enhancement / Creature AI / Combat / Base Defense  
**Author(s):** EvilGenius  
**Version:** 0.1 (Design Draft)

### Summary

The Wilds: Satisfactory introduces heightened survival mechanics into the game by significantly increasing the threat from native wildlife. It adds nest-based monster spawns, structure damage, attack waves synchronized with the day-night cycle, and defense systems the player can build to protect infrastructure.

---

## Goals

- Increase immersion and danger in the world.
- Encourage defensive building strategies.
- Create varied and escalating challenges tied to in-game time.
- Expand creature and combat mechanics while maintaining Satisfactory's core factory gameplay loop.
- Support multiplayer sessions with dynamic scaling of enemy wave size, density, and behavior based on active player count.
- Introduce support for multiple player-built sub-bases, including various HUB types with distinct roles (e.g., command, defense, logistics).

---

## Project Approach & Philosophy

*The Wilds: Satisfactory* is a public mod project led by **Evil Genius Games**, developed with a commitment to transparency, collaboration, and community learning. The mod will be **open source**, allowing anyone to study, contribute to, and learn from the project. However, it will be licensed to **prevent commercial exploitation** by other entities or companies.

Evil Genius Games brings over **35 years of software development experience** to this project. While the core development will be driven in-house, we welcome collaboration from **artists, musicians, level designers**, and other interested community members. Recruitment for assistance with coding, testing, balancing, and creative content will be ongoing through open channels.

Graphics assets will utilize a mix of **licensed content** and **placeholder visuals** where necessary, particularly where original art is required. Sound effects and music may initially use temporary assets with the intent to replace them as quality resources become available.

Funding will be supported through **Patreon** and **Ko-fi** to help offset ongoing development costs. Until community support reaches a sustainable level, Evil Genius Games will cover all required expenses to keep development moving forward.

This project is being built for the enjoyment of the community, not for profit. We are committed to creating a challenging, high-quality modding experience that expands the boundaries of what Satisfactory can offer.

---

## Key Features

### 1. **Creature Expansion**
- [x] Increased spawn rates
- [x] Larger and more diverse enemy types
- [ ] Replacement or augmentation of existing Satisfactory creatures with enhanced models and AI
- [ ] Improved creature intelligence: dynamic pathing, coordinated attacks, threat prioritization
- [ ] Smart respawn system based on player expansion and wave cycle logic
- [ ] Biome-specific variants of creatures (desert, forest, swamp, etc.)
- [ ] Nest mechanics with boss-tier enemies originating from central map regions
- [ ] Patrols, ambushes, and reactive behaviors around resource-rich areas
- [ ] Water Creatures: aggressive aquatic threats in lakes/rivers
- [ ] Semi-Aquatic Creatures: mobile in both land and swampy terrain
- [ ] Flying Creatures: air-based threats targeting power poles, conveyors, and lookout towers
- [ ] Day-night behavior shifts (e.g., nocturnal aggression, diurnal migration)
- [ ] Sound design enhancements: territorial calls, alert phases, incoming wave cues

### 2. **Factory Damage System**
- [ ] Enable AI to identify, target, and damage player-built structures based on threat priority (e.g., power, production, logistics).
- [ ] Implement damage visual effects (smoke, sparks, scorched textures) to indicate critical infrastructure under attack.
- [ ] Introduce damage states for buildings (minor, major, critical) with corresponding performance degradation.
- [ ] Add a manual and automated repair system using repair drones or consumable kits.
- [ ] Ensure damage impacts power grid stability (e.g., generators offline, power spikes), encouraging the strategic use of batteries and segmented power grids to maintain critical systems and weapons during attacks.
- [ ] Interrupt production lines by disabling smelters, assemblers, or conveyors when damaged.
- [ ] Allow creatures to temporarily disable or destroy transportation infrastructure (belts, pipes, trains).
- [ ] Create a repair priority system for automated fixes based on building type and severity.
- [ ] Provide UI alerts and map overlays for damage reports and repair requirements.
- [ ] Add multiple repair methods:
  - **Repair Tool**: handheld device used by the player to manually fix damaged structures.
  - **Repair Drones**: autonomous units that patrol and repair damaged buildings within range.
  - **Repair Stations**: deployable structures that passively restore nearby infrastructure over time.
  - **Maintenance Bots**: factory-built units assigned to repair roles with limited resource inventories.
  - **Repair Grenade**: throwable nobelisk-style device that triggers an instant area repair effect upon detonation.

### 3. **Day-Night Wave Attacks**
- [ ] Define day-night detection system (how to hook)
- [ ] Central Nest coordinates and radius
- [ ] AI pathfinding to factory components
- [ ] Wave scaling (time-based or trigger-based)
- [ ] Boss bases/nests: high-threat zones hidden in the world that periodically generate elite waves. Players must explore, locate, and destroy these nests to reduce or stop wave spawns.

### 4. **Player Defenses**
- [ ] Placeable defensive structures (e.g., turrets, walls)
- [ ] Turret types: projectile, energy, AoE, etc.
- [ ] Power consumption and targeting behavior
- [ ] All defensive systems consume power and must be either directly wired or within proximity of a powered node to function, encouraging thoughtful base layout and power network segmentation
- [ ] Unlocks via MAM or HUB milestones?
- [ ] Visual UI for wave countdown, turret health, etc.
- [ ] Gun Turrets: fixed-installation weapons with upgradeable range, damage, and targeting logic
- [ ] Defensive Drone: new drone type that flies a configurable patrol route and engages hostile creatures during waves or proximity breaches
- [ ] Train Turret Car: mobile rail-based turret platform for perimeter defense or route protection
- [ ] Defensive Vehicles: mobile, ground-based turret platforms that patrol set paths or react to threats dynamically
- [ ] Turrets require ammunition produced by the player/factory and delivered via standard conveyor logistics
  - Ammo types could include ballistic rounds, energy cells, explosive shells, etc.
  - Encourages integration of turret supply into factory design and power balance
  - Running out of ammo during an attack creates natural pressure and urgency

---

## Dependencies

- [ ] Satisfactory Mod Loader (SML)  
- [ ] Satisfactory SDK (UE 5.3.x fork)  
- [ ] FicsItNetwork (Optional for AI/logic extensions)

---

## Game Systems Affected

- AI Behavior Trees
- Building Health and Placement
- World Grid / NavMesh
- Time of Day System
- Factory Production Chains
- Inventory / Milestone Unlocks

---

## Art & Assets

- [ ] Creature Models and Animations (Boss variants)
- [ ] New particle FX (explosions, damage states)
- [ ] Turret and wall models
- [ ] Sound design (alarms, attacks, turret fire)
- [ ] UI components for wave alerts, turret status

---

## Technical Challenges (To Research)

- [ ] How to attach waves to time of day system
- [ ] Hooking into or overriding AI navigation and targeting
- [ ] How to register and damage factory buildings without having to rebuild all existing assets; can we subclass a damage state to all existing objects
- [ ] Persistent base state and enemy aggression
- [ ] Multiplayer sync for attack waves and damage
- [ ] How to persist mod-specific data (e.g., nest state, damage states, wave timers) using the existing Satisfactory save system
- [ ] Multiplayer state management for wave logic, enemy spawns, AI targeting, and synchronized damage events to ensure consistent behavior across all clients

---

## Milestones / Phases

### Phase 1: Foundation
- [ ] Establish mod project with SDK/SML
- [ ] Add creature spawns and test density
- [ ] Set up basic nest system

### Phase 2: Structure Damage
- [ ] Implement structure health and repair
- [ ] Allow hostile AI to damage buildings

### Phase 3: Wave System
- [ ] Day-night trigger logic
- [ ] Spawn scaling and boss logic
- [ ] AI pathing and targeting

### Phase 4: Base Defenses
- [ ] Design turret behavior and UI
- [ ] Add wall segments and power cost
- [ ] Polish placement mechanics

### Phase 5: Tuning & Balance
- [ ] Creature difficulty scaling
- [ ] Damage vs repair pacing
- [ ] Wave frequency

---

## Notes

- Multiplayer compatibility is a stretch goal.
- Base destruction should not be total; balance is key.
- Turrets must feel satisfying but limited (power cost, range).
- Inspiration drawn from Tower Defense and RTS base attacks.
- The player is king

> **Note:** This design document represents a first-pass outline of the core vision for *The Wilds: Satisfactory*. It is intended to be a living document that will evolve over time. As new systems are explored and implementation details are uncovered during development, additional sections and refinements will be added to support ongoing discovery and design clarity. Other supporting documents will be created as needed to capture system-specific designs, technical specifications, and implementation notes.

---

## References

- [Satisfactory Modding Docs](https://docs.ficsit.app/satisfactory-modding/latest/)
- [Satisfactory Modding Discord](https://discord.com/invite/xkVJ73E)
- [Unreal Engine 5.3 Documentation](https://docs.unrealengine.com/5.3/en-US/)
