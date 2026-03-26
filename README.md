# 🌿 Lily Pad Update – Complete Detailed Design Document

## Document Overview
This document provides a comprehensive technical and gameplay specification for the Lily Update add-on for Minecraft Bedrock Edition.

---

## 📋 Table of Contents
1. [Core Concept](#1-core-concept)
2. [Block Registry](#2-block-registry)
3. [Item Registry](#3-item-registry)
4. [Entity Registry](#4-entity-registry)
5. [Mechanics & Systems](#5-mechanics--systems)
6. [World Generation](#6-world-generation)
7. [Villager Integration](#7-villager-integration)
8. [Piglin Bartering](#8-piglin-bartering)
9. [Crafting Recipes](#9-crafting-recipes)
10. [Brewing Recipes](#10-brewing-recipes)
11. [Suspicious Stew Effects](#11-suspicious-stew-effects)
12. [Particle Effects](#12-particle-effects)
13. [Achievements](#13-achievements)
14. [Technical Implementation](#14-technical-implementation)
15. [Balance & Balancing](#15-balance--balancing)

---

## 1. Core Concept

The Lily Pad Update introduces seven new lily pad variants across water and lava biomes, creating a complete ecosystem with propagation mechanics, mob spawning, a new lava frog, flower systems, bee integration, villager trades, piglin bartering and more.

### New lily pad variants:
- 4 new water variants (spreading lily pads) with flowers (white, pink, yellow, purple) that generate naturally in water in the Overworld.
- 1 new craftable water variant (spreading lily pad) with golden flower that can only be crafted.
- 2 new lava variants (1 plain lily pad and 1 spreading lily pad with black flower) that generate naturally in lava in the Nether.

### New Propagation Mechanics:
- All spreading lily pad variations can propagate.
- Density limits for propagation.
- Propagation only happens at night.
- Full moon increases propagation.
- Inheritance where spreading water lily pads have 95% chance to spawn vanilla lily pads, 5% chance to spread similar spreading lily pad on water source.
- Inheritance where crafted water lily pads have 100% chance to spawn a vanilla lily pad on water source.
- Inheritance where spreading lava lily pads have 95% chance to spawn lava lily pads, 5% chance to spread similar spreading lily pad on lava source.

### New Mob Spawning Mechanic:
- All spreading lily pads can spawn mobs (cod, salmon, tropical fish, squid, glow squid, dolphins and small magma cubes).
- Special conditions for mob spawning.

### New Lava Frog Added:
- Naturally spawns on lava.
- Eggs get laid on lava.
- Tadpoles swim in lava.
- Walks on lava source blocks.
- Breeds with fire charges.
- Eats smallest size magma cubes to drop lava froglight.
- Eats smallest size slime cubes to drop fire charge.
- Drops nothing when killed.
- Can be collected with a bucket.
- Can use a lead on the lava frog.

### Lily Flowers Added (White, Pink, Yellow, Purple, Black and Golden):
- Can be sheared from spreading lily pads.
- Will grow back on spreading lily pads (not the golden variant).
- Can be placed on vanilla lily pads or lava lily pads for cosmetic use only.
- Flower generates firefly effect on any lily pad.
- Golden lily flower can be crafted.
- Flowers can be crafted into dye.
- Flowers can be used to craft potions.

### Bee Integration:
- All flowers attract bees.
- All flowers give pollen to bees.
- Flowers can be used to breed bees (black flowers kill bees when used for breeding).

### Villager Trades:
- Fisherman and Wandering Trader.

### Piglin Bartering:
- Golden items have 5% chance to yield black lily pads.
- Golden spreading lily pads and golden lily flowers can be used to barter with piglins.

### Instant Death Arrows Added.

### Fishing loot

### Chest loot

### New potions



---

### 1.1 Spreading Lily Pad Variants

#### Water Variants (Overworld)
| Variant | Type | Flower Color | Generation | World | Lily pad name |
|---------------------------|-----------|--------|--------------------|---------|--------------------------------|
| White Spreading Lily Pad | Spreading | White | Natural (45%) | Overworld | lilypad_update:white_lily_pad |
| Pink Spreading Lily Pad | Spreading | Pink | Natural (30%) | Overworld | lilypad_update:pink_lily_pad |
| Yellow Spreading Lily Pad | Spreading | Yellow | Natural (15%) | Overworld | lilypad_update:yellow_lily_pad |
| Blue Spreading Lily Pad | Spreading | Blue | Natural (10%) | Overworld | lilypad_update:blue_lily_pad |
| Black Spreading Lily Pad | Spreading | Black | Natural (rare) | End Dimention | lilypad_update:black_lily_pad |
| Purple Spreading Lily Pad | Spreading | Purple | Natural (10%) | Overworld | lilypad_update:purple_lily_pad |
| Golden Spreading Lily Pad | Spreading | Golden | Craft only | | lilypad_update:golden_lily_pad |

#### Lava Variants (Nether)
| Variant | Type | Flower | Generation |
|---------|------|--------|------------|
| Lava Lily Pad | Plain | None | Natural |

---

### 1.2 Propagation Mechanics

All spreading lily pad variants can propagate with the following rules:

| Rule | Description |
|------|-------------|
| **Density Limit** | Propagation only occurs when less than 75% of blocks in a 9×9 area are occupied |
| **Night Only** | Propagation only happens at night |
| **Full Moon Bonus** | Full moon increases propagation rate |
| **Water Inheritance** | Spreading water lily pads: 95% vanilla lily pad, 5% same color spreading pad |
| **Golden Inheritance** | Golden lily pads: 100% vanilla lily pad |
| **Lava Inheritance** | Spreading lava lily pads: 95% lava lily pad, 5% black spreading pad |

---

### 1.3 Mob Spawning Mechanics

All spreading lily pads can spawn mobs under specific conditions:

| Pad Type | Flower Color | Spawn | Special Conditions |
|----------|--------------|-------|-------------------|
| Water Spreading | White | Cod | Player-placed, surrounded by 8 water, 3+ depth, 20% chance |
| Water Spreading | Pink | Salmon | Player-placed, surrounded by 8 water, 3+ depth, 20% chance |
| Water Spreading | Yellow | Tropical Fish | Player-placed, surrounded by 8 water, 3+ depth, 20% chance |
| Water Spreading | Purple | Squid / Glow Squid | Player-placed, surrounded by 8 water, 3+ depth, 20% chance (squid above Y=30, glow squid below Y=30) |
| Golden Pad | Golden | Dolphins | Player-placed, surrounded by 8 water, 3+ depth, 5% chance |
| Black Pad | Black | Small Magma Cubes | Player-placed, surrounded by 8 lava, 3+ depth, 10% chance |

---

### 1.4 Lava Frog

A new mob that lives in lava and follows vanilla frog mechanics adapted for the Nether:

| Aspect | Description |
|--------|-------------|
| **Spawning** | Naturally spawns on lava in the Nether |
| **Eggs** | Laid on lava source blocks |
| **Tadpoles** | Swim in lava |
| **Adult** | Walks on lava source blocks |
| **Breeding** | Uses fire charges |
| **Diet** | Eats smallest magma cubes → drops **Lava Froglight** |
| **Diet** | Eats smallest slime cubes → drops **Fire Charge** |
| **Death Drop** | Nothing |
| **Collection** | Can be collected with a bucket |
| **Leash** | Can be attached with a lead |

---

### 1.5 Lily Flowers

Six flower types that can be sheared from spreading lily pads:

| Flower | Source | Regrowth | Uses |
|--------|--------|----------|------|
| White | White Lily Pad | ✅ Yes (25% night, 100% full moon) | Dye, potions |
| Pink | Pink Lily Pad | ✅ Yes | Dye, potions |
| Yellow | Yellow Lily Pad | ✅ Yes | Dye, potions |
| Purple | Purple Lily Pad | ✅ Yes | Dye, potions |
| Black | Black Lily Pad | ✅ Yes | Dye, potions, instant death arrows |
| Golden | Golden Lily Pad | ❌ No | Dye, potions (crafted) |

**Flower Mechanics:**
- Can be sheared from spreading lily pads
- Regrow naturally on spreading pads (golden pads do not regrow)
- Can be placed on vanilla lily pads or lava lily pads for cosmetic use only
- Generate firefly effects at night on any lily pad
- Can be crafted into dye
- Can be used to craft potions

---

### 1.6 Bee Integration

| Flower | Attraction | Pollen Collection | Breeding Result |
|--------|------------|-------------------|-----------------|
| White/Pink/Yellow/Purple/Golden | ✅ Yes | ✅ Yes | ✅ Breed successfully |
| Black | ✅ Yes | ✅ Yes | ❌ Instantly kills bee |

---

### 1.7 Villager Trades

| Trader | Buys | Sells |
|--------|------|-------|
| **Fisherman** | Vanilla lily pads, colored flowers, spreading lily pads | Golden lily flower (Master level) |
| **Wandering Trader** | Emeralds | All lily pads, all flowers, suspicious stews, repellent potions, potion of instant death |

---

### 1.8 Piglin Bartering

| Item Given | Result |
|------------|--------|
| Golden Lily Pad | Standard gold ingot loot table + **5% chance for Black Lily Pad** |
| Golden Lily Flower | Standard gold ingot loot table + **5% chance for Black Lily Pad** |

Golden spreading lily pads and golden lily flowers can be used to barter with piglins.

---

### 1.9 Instant Death Arrows

| Item | Effect |
|------|--------|
| Potion of Instant Death | Crafted with black flower |
| Arrow of Instant Death | Crafted with potion + arrows |
| **Player** | 5% instant death / 95% large damage |
| **Regular Mobs** | 50% instant death / 50% large damage |
| **Immune Mobs** (Dragon, Wither, Warden) | 100% large damage |

---

### 1.10 Unified Block Properties

All lily pads share a unified property system for consistent behavior:

| Property | Values | Description |
|----------|--------|-------------|
| `has_flower` | true / false | Whether the pad currently has a flower |
| `is_cosmetic` | true / false | Non-propagating variant (decorative only) |
| `is_natural` | true / false | World-generated or player-placed |

---

## 2. Block Registry

### 2.1 Water Lily Pads (5 Variants)

| Block ID | Display Name | Flower Color | Rarity | Hardness | Blast Resistance | Light Emission | Break Time (Hand) |
|----------|--------------|--------------|--------|----------|------------------|----------------|------------------|
| `lily_update:white_lily_pad` | White Lily Pad | White | Common (45%) | 0.1 | 0 | 7 (with flower) | 0.2 sec |
| `lily_update:pink_lily_pad` | Pink Lily Pad | Pink | Common (30%) | 0.1 | 0 | 7 (with flower) | 0.2 sec |
| `lily_update:yellow_lily_pad` | Yellow Lily Pad | Yellow | Uncommon (15%) | 0.1 | 0 | 7 (with flower) | 0.2 sec |
| `lily_update:purple_lily_pad` | Purple Lily Pad | Purple | Rare (10%) | 0.1 | 0 | 7 (with flower) | 0.2 sec |
| `lily_update:golden_lily_pad` | Golden Lily Pad | Golden | N/A | 0.1 | 0 | 7 (with flower) | 0.2 sec |

**Unified Block Properties (All Water Lily Pads):**
| Property | Values | Description |
|----------|--------|-------------|
| `has_flower` | `true`, `false` | Whether pad has a flower |
| `is_cosmetic` | `true`, `false` | Non-propagating variant |
| `is_natural` | `true`, `false` | World-generated or player-placed |

**Placement:** On water source blocks only

**Collision Box:** 16×16×1 (same as vanilla lily pad)

---

### 2.2 Lava Lily Pads (2 Variants)

| Block ID | Display Name | Flower Color | Rarity | Hardness | Blast Resistance | Light Emission | Break Time (Hand) |
|----------|--------------|--------------|--------|----------|------------------|----------------|------------------|
| `lily_update:lava_lily_pad` | Lava Lily Pad | None | Common | 0.1 | 0 | 0 | 0.2 sec |
| `lily_update:black_lily_pad` | Black Lily Pad | Black | Rare | 0.1 | 0 | 0 | 0.2 sec |

**Unified Block Properties (All Lava Lily Pads):**
| Property | Values | Description |
|----------|--------|-------------|
| `has_flower` | `true`, `false` | Whether pad has a flower (lava pad always false, black pad can be true) |
| `is_cosmetic` | `true`, `false` | Non-propagating variant |
| `is_natural` | `true`, `false` | World-generated or player-placed |

**Placement:** On lava source blocks only

**Collision Box:** 16×16×1 (same as vanilla lily pad)

**Lava Lily Pad:**
- `has_flower` is always `false`
- Non-spreading, decorative only
- Can be made cosmetic via `is_cosmetic: true`

**Black Lily Pad:**
- Can have black flower (`has_flower: true/false`)
- Spreading variant when `is_cosmetic: false`
- Natural flower regrowth (25% night, 100% full moon)
- Drops black flower when sheared
- Player-placed variants generate magma cubes (10% chance every 60 seconds when has flower)
- Can be made cosmetic via `is_cosmetic: true` (stops propagation, keeps flower)

---

## 3. Item Registry

### 3.1 Flowers (6 Types)

| Item ID | Display Name | Dye Output | Suspicious Stew Effect | Effect Duration |
|---------|--------------|------------|------------------------|-----------------|
| `lily_update:white_flower` | White Lily Flower | White Dye | Strength | 8 seconds |
| `lily_update:pink_flower` | Pink Lily Flower | Pink Dye | Absorption | 12 seconds |
| `lily_update:yellow_flower` | Yellow Lily Flower | Yellow Dye | Speed | 10 seconds |
| `lily_update:purple_flower` | Purple Lily Flower | Purple Dye | Water Breathing | 8 seconds |
| `lily_update:golden_flower` | Golden Lily Flower | Yellow Dye | Invisibility | 15 seconds |
| `lily_update:black_flower` | Black Lily Flower | Black Dye | Instant Death | Instant |

**Properties:**
- Stack size: 64
- Can be placed in flower pots
- Used for bee breeding (except black flower kills bee)
- Used for suspicious stew crafting
- Used for dye crafting

---

### 3.2 Lily Pad Items (7 Types)

| Item ID | Display Name | Obtained From |
|---------|--------------|---------------|
| `lily_update:white_lily_pad` | White Lily Pad | Breaking white pad (any method), shearing natural white pad |
| `lily_update:pink_lily_pad` | Pink Lily Pad | Breaking pink pad (any method), shearing natural pink pad |
| `lily_update:yellow_lily_pad` | Yellow Lily Pad | Breaking yellow pad (any method), shearing natural yellow pad |
| `lily_update:purple_lily_pad` | Purple Lily Pad | Breaking purple pad (any method), shearing natural purple pad |
| `lily_update:golden_lily_pad` | Golden Lily Pad | Crafting (colored pad + 8 gold nuggets) |
| `lily_update:lava_lily_pad` | Lava Lily Pad | Breaking lava lily pad (any method), wandering trader |
| `lily_update:black_lily_pad` | Black Lily Pad | Breaking black pad (any method), shearing black pad, piglin bartering |

---

### 3.3 Potion Items (4 Types)

| Item ID | Display Name | Effect | Duration | Crafting |
|---------|--------------|--------|----------|----------|
| `lily_update:repellent_potion_i` | Repellent Potion I | Phantom prevention | 5 minutes | Awkward Potion + Any Lily Flower |
| `lily_update:repellent_potion_ii` | Repellent Potion II | Phantom prevention | 15 minutes | Repellent Potion I + Redstone |
| `lily_update:instant_death_potion` | Potion of Instant Death | 5% kill / 95% damage | Instant | Awkward Potion + Black Flower |
| `lily_update:instant_death_arrow` | Arrow of Instant Death | 5% kill / 95% damage | Instant | Potion + 8 Arrows |

---

### 3.4 Lava Frog Items (4 Types)

| Item ID | Display Name | Description |
|---------|--------------|-------------|
| `lily_update:lava_froglight` | Lava Froglight | Light block (level 15), red/orange color |
| `lily_update:lava_frogspawn` | Lava Frogspawn | Egg block placed on lava |
| `lily_update:lava_tadpole_spawn_egg` | Lava Tadpole Spawn Egg | Spawns lava tadpole |
| `lily_update:lava_frog_spawn_egg` | Lava Frog Spawn Egg | Spawns adult lava frog |

---

## 4. Entity Registry

### 4.1 Lava Frog

| Attribute | Value |
|-----------|-------|
| Entity ID | `lily_update:lava_frog` |
| Spawn Location | Nether, on lava near lava lily pads |
| Health | 10 hearts (20 HP) |
| Size | Same as vanilla frog |
| Behavior | Walks on lava without damage |
| Breeding Item | Fire Charge |
| Diet | Small magma cubes |
| Drop on Death | None |
| Drop on Eating Magma Cube | 1 Lava Froglight |

**Lifecycle:**
1. **Lava Frogspawn:** Placed on lava, hatches after 5 minutes (6000 ticks)
2. **Lava Tadpole:** Swims in lava, grows after 20 minutes (24000 ticks)
3. **Adult Lava Frog:** Walks on lava and land, eats magma cubes, breeds with fire charges

**AI Behaviors:**
- Seek and eat small magma cubes
- Follow player holding fire charge
- Breed when fed fire charge (both frogs enter love mode)
- Lay lava frogspawn on nearby lava source blocks after breeding

---

## 5. Mechanics & Systems

### 5.1 Breaking Mechanics

All lily pads can be broken by multiple methods, matching and extending vanilla behavior:

| Break Method | Water Lily Pads | Lava Lily Pads |
|--------------|-----------------|----------------|
| Hand | ✅ Breaks, drops item | ✅ Breaks, drops item |
| Any Tool | ✅ Breaks, drops item | ✅ Breaks, drops item |
| Boat Collision | ✅ Breaks, drops item | ✅ Breaks, drops item, boat takes fire damage |
| Water Flow | ✅ Breaks, drops item | N/A |
| Water Placed On | ✅ Breaks, drops item | N/A |
| Lava Flow | N/A | ✅ Breaks, drops item |
| Lava Placed On | N/A | ✅ Breaks, drops item |
| Explosion | ✅ Breaks, drops item | ✅ Breaks, drops item |
| Shears | Collects flower, pad remains | Collects flower, pad remains |

**Water Break Conditions (Water Lily Pads):**
| Condition | Result |
|-----------|--------|
| Water flows onto pad from adjacent block | Pad breaks, drops item |
| Water flows over pad from above | Pad breaks, drops item |
| Player places water bucket on pad | Pad breaks first, then water occupies block |

**Lava Break Conditions (Lava Lily Pads):**
| Condition | Result |
|-----------|--------|
| Lava flows onto pad from adjacent block | Pad breaks, drops item |
| Lava flows over pad from above | Pad breaks, drops item |
| Player places lava bucket on pad | Pad breaks first, then lava occupies block |

**Boat Collision:**
| Pad Type | Result |
|----------|--------|
| Water Lily Pad | Pad breaks, drops item, boat continues |
| Lava Lily Pad | Pad breaks, drops item, boat takes fire damage |

---

### 5.2 Drop Rules

| Condition | Drop |
|-----------|------|
| Spreading water pad with flower | Same colored lily pad item |
| Spreading water pad without flower | Vanilla lily pad |
| Cosmetic water pad with flower | Same colored lily pad item (preserves cosmetic) |
| Cosmetic water pad without flower | Same colored lily pad item (preserves cosmetic) |
| Golden pad with flower | Golden lily pad item |
| Golden pad without flower | Vanilla lily pad |
| Black pad with flower | Black lily pad item |
| Black pad without flower | Vanilla lily pad |
| Lava pad (any) | Lava lily pad item |

---

### 5.3 Propagation Mechanics

**Water Lily Pads:**
| Parent Type | `is_cosmetic` | Propagates | Offspring Distribution |
|-------------|---------------|------------|------------------------|
| White/Pink/Yellow/Purple | `false` | ✅ Yes | 95% Vanilla / 5% Same Color |
| White/Pink/Yellow/Purple | `true` | ❌ No | None |
| Golden | `false` | ✅ Yes | 100% Vanilla |
| Golden | `true` | ❌ No | None |

**Lava Lily Pads:**
| Parent Type | `is_cosmetic` | Propagates | Offspring Distribution |
|-------------|---------------|------------|------------------------|
| Black Lily Pad | `false` | ✅ Yes | 95% Lava Lily Pad / 5% Black Lily Pad |
| Black Lily Pad | `true` | ❌ No | None |
| Lava Lily Pad | Any | ❌ No | None |

**Density Limit:**
- Maximum occupancy: 75%
- Area: 9×9 square (4-block radius)
- Counts: Any lily pad + non-water/non-lava blocks
- No propagation when occupancy ≥ 75%

**Nighttime Propagation:**
- **Normal nights:** 25% chance per eligible block
- **Full moon nights:** 1-3 new pads per parent
- **Rare spawn:** 1-2% chance for new pads to have flower

---

### 5.4 Flower Growth & Regrowth

| Pad Type | `is_cosmetic` | Natural Regrowth (Normal Night) | Natural Regrowth (Full Moon) | Bone Meal |
|----------|---------------|-------------------------------|------------------------------|-----------|
| Colored Water Pad | `false` | 25% | 100% | 25% |
| Colored Water Pad | `true` | 0% | 0% | 0% |
| Black Lily Pad | `false` | 25% | 100% | 25% |
| Black Lily Pad | `true` | 0% | 0% | 0% |
| Golden Pad | Any | 0% | 0% | 0% |
| Lava Lily Pad | Any | N/A | N/A | N/A |

---

### 5.5 Shearing Mechanics

| Pad Type | With Flower | Without Flower |
|----------|-------------|----------------|
| Colored Water Pad | Drops colored flower, `has_flower` becomes `false` | Nothing |
| Golden Pad | Drops golden flower, becomes vanilla lily pad | Nothing |
| Black Lily Pad | Drops black flower, `has_flower` becomes `false` | Nothing |
| Lava Lily Pad | Never has flower | Nothing |

---

### 5.6 Flower Placement Rules

| Pad Type | `is_cosmetic` | Can Place Flower | Allowed Flowers | Result |
|----------|---------------|------------------|-----------------|--------|
| Vanilla Lily Pad | N/A | ✅ Yes | White, Pink, Yellow, Purple, Golden | Creates spreading colored pad (`is_cosmetic: false`) |
| Lava Lily Pad | Any | ✅ Yes | Black only | Adds flower (`has_flower: true`), preserves `is_cosmetic` |
| Any Colored Pad | Any | ❌ No | None | - |
| Golden Pad | Any | ❌ No | None | - |
| Black Lily Pad | Any | ❌ No | None | Flowers grow naturally |

---

### 5.7 Cosmetic Conversion

Players can convert any spreading lily pad to a cosmetic version using a tool or command to toggle the `is_cosmetic` property. Cosmetic pads:
- Do NOT propagate
- Keep their flower if they had one
- Drop the same colored lily pad item when broken (preserves cosmetic state)
- Still display fireflies at night
- Still attract bees (if has flower)

---

### 5.8 Fish Spawning (Water Pads)

**Conditions:**
- Player-placed colored pad (`is_natural: false`)
- Has flower
- Surrounded by water on all 8 sides
- Water depth ≥ 3 blocks below pad
- 20% chance every 60 seconds

**Fish Types by Flower Color:**
| Flower Color | Fish Spawned |
|--------------|--------------|
| White | Cod |
| Pink | Salmon |
| Yellow | Tropical Fish (yellow pattern) |
| Purple | Squid (above Y=30) / Glow Squid (below Y=30) |

---

### 5.9 Dolphin Spawning (Golden Water Pads)

**Conditions:**
- Golden lily pad
- Has golden flower
- Surrounded by water on all 8 sides
- Water depth ≥ 3 blocks below pad
- 5% chance every 60 seconds
- Any biome

---

### 5.10 Magma Cube Spawning (Black Lily Pads)

**Conditions:**
- Player-placed black lily pad (`is_natural: false`)
- `is_cosmetic: false`
- Has black flower
- 10% chance every 60 seconds
- Spawns 1-3 small magma cubes

---

### 5.11 Bee Interaction

| Flower | Attraction | Pollen Collection | Breeding Result |
|--------|------------|-------------------|-----------------|
| White/Pink/Yellow/Purple/Golden | ✅ Yes | ✅ Yes | ✅ Breed successfully |
| Black | ✅ Yes | ✅ Yes | ❌ Instantly kills bee |

---

### 5.12 Instant Death Effect

**Potion & Arrow Effect Table:**

| Target | Instant Death Chance | Instant Damage Chance | Notes |
|--------|---------------------|----------------------|-------|
| Player | 5% | 95% | Instant Damage = large damage |
| Regular Mobs | 50% | 50% | Instant Damage = large damage |
| Ender Dragon | 0% | 100% | Immune to instant death |
| Wither | 0% | 100% | Immune to instant death |
| Warden | 0% | 100% | Immune to instant death |

**Instant Damage:** Large amount of damage (similar to harming potion II)

---

### 5.13 Firefly System

| Occupancy | Firefly Density | Visual Effect |
|-----------|-----------------|---------------|
| Below 25% | Sparse | Occasional fireflies |
| 25-50% | Light | Regular fireflies |
| 50-75% | Moderate | Frequent fireflies |
| 75-100% | Dense | Very frequent, magical glow |

**Firefly Colors:**
- Colored water pads = matching color
- Golden pads = gold
- Vanilla pads = white
- Black lava pads = bright red
- Cosmetic pads = same as non-cosmetic (based on pad color)

**Firefly Density Calculation:**
```
Spawn Chance = Base Chance × Occupancy Multiplier

Base Chance: 0.02 (2% per tick)
Occupancy Multiplier: min(Occupancy Rate × 2, 2.0)

At 25%: 1% chance
At 50%: 2% chance
At 75%: 3% chance
At 100%: 4% chance
```

---

## 6. World Generation

### 6.1 Water Lily Pad Generation

| Parameter | Value |
|-----------|-------|
| Generation Chance | 5% of lily pads become colored pads |
| White | 45% |
| Pink | 30% |
| Yellow | 15% |
| Purple | 10% |
| `has_flower` | Always true |
| `is_natural` | Always `true` |
| `is_cosmetic` | Always `false` |
| Biomes | Swamp, River, Beach, Jungle (water sources) |

---

### 6.2 Lava Lily Pad Generation

**Lava Lily Pad:**
| Parameter | Value |
|-----------|-------|
| Rarity | Common |
| Spawn Condition | Surrounded by 8 lava source blocks |
| `has_flower` | Always `false` |
| `is_natural` | Always `true` |
| `is_cosmetic` | Always `false` |
| Biomes | Nether Wastes, Crimson Forest, Warped Forest, Soul Sand Valley, Basalt Deltas |

**Black Lily Pad:**
| Parameter | Value |
|-----------|-------|
| Rarity | Rare (similar to purple water pads) |
| Spawn Condition | Surrounded by 8 lava source blocks |
| `has_flower` | `true` (50% of generated black pads have flower) |
| `is_natural` | Always `true` |
| `is_cosmetic` | Always `false` |
| Biomes | Nether Wastes, Crimson Forest, Warped Forest, Soul Sand Valley, Basalt Deltas |

---

## 7. Villager Integration

### 7.1 Fisherman Trades

| Level | Trade (Buys) | Quantity | Payment | Trade (Sells) | Price | Max Uses |
|-------|--------------|----------|---------|---------------|-------|----------|
| Novice | No trades | - | - | - | - | - |
| Apprentice | Vanilla Lily Pad | 5 | 1 Emerald | - | - | 8 |
| Journeyman | Lily Flowers (white, pink, yellow, purple) | 2 | 1 Emerald | - | - | 8 |
| Expert | Spreading Lily Pads (white, pink, yellow, purple) | 1 | 1 Emerald | - | - | 8 |
| Master | - | - | - | Golden Lily Flower | 2 Emeralds | 4 |

---

### 7.2 Wandering Trader Trades

| Trade | Buys | Price | Sells | Price | Max Uses |
|-------|------|-------|-------|-------|----------|
| Lily Pads | Emerald | 1 | White/Pink/Yellow/Purple Pad | 2 | 4 |
| | Emerald | 5 | Golden Lily Pad | 1 | 2 |
| | Emerald | 2 | Lava Lily Pad | 2 | 4 |
| | Emerald | 4 | Black Lily Pad | 2 | 2 |
| Flowers | Emerald | 1 | White/Pink/Yellow Flower | 1 | 6 |
| | Emerald | 2 | Purple Flower | 1 | 4 |
| | Emerald | 4 | Golden Flower | 1 | 2 |
| | Emerald | 3 | Black Flower | 1 | 2 |
| Suspicious Stews | Emerald | 2 | Colored Stews | 1 | 4 |
| | Emerald | 3 | Golden Stew | 1 | 2 |
| | Emerald | 4 | Black Stew | 1 | 2 |
| Potions | Emerald | 2 | Repellent Potion I | 1 | 4 |
| | Emerald | 4 | Repellent Potion II | 1 | 2 |
| | Emerald | 5 | Potion of Instant Death | 1 | 2 |

---

## 8. Piglin Bartering

| Item Given | Standard Rewards | Bonus (5% Chance) |
|------------|------------------|-------------------|
| Golden Lily Pad | Same as gold ingot loot table | Black Lily Pad |
| Golden Lily Flower | Same as gold ingot loot table | Black Lily Pad |

**Bartering Mechanics:**
- Piglins pick up dropped golden items
- Examine item for 2-3 seconds
- Drop 1-5 items from gold ingot loot table
- Additional 5% chance to drop a Black Lily Pad

---

## 9. Crafting Recipes

### 9.1 Golden Crafting (Shaped)

**Golden Lily Pad:**
```
[G][G][G]
[G][L][G]
[G][G][G]

G = Gold Nugget
L = Any Colored Lily Pad (white, pink, yellow, purple)
```

**Golden Lily Flower:**
```
[G][G][G]
[G][F][G]
[G][G][G]

G = Gold Nugget
F = Any Colored Lily Flower (white, pink, yellow, purple)
```

---

### 9.2 Suspicious Stews (Shapeless)

**Colored Stews:**
| Ingredients | Output |
|-------------|--------|
| Red Mushroom + Brown Mushroom + Bowl + Any Colored Flower | Suspicious Stew (colored effect) |

**Floral Medley Stew:**
| Ingredients | Output |
|-------------|--------|
| Red Mushroom + Brown Mushroom + Bowl + White Flower + Pink Flower + Yellow Flower + Purple Flower | Suspicious Stew (all four effects, 15 seconds) |

---

### 9.3 Dye Crafting (Shapeless)

| Input | Output |
|-------|--------|
| White Lily Flower | White Dye |
| Pink Lily Flower | Pink Dye |
| Yellow Lily Flower | Yellow Dye |
| Purple Lily Flower | Purple Dye |
| Golden Lily Flower | Yellow Dye |
| Black Lily Flower | Black Dye |

---

### 9.4 Arrow Crafting

| Input | Output |
|-------|--------|
| Potion of Instant Death + 8 Arrows | 8 Arrows of Instant Death |

---

## 10. Brewing Recipes

### 10.1 Repellent Potions

| Base | Ingredient | Result | Duration |
|------|------------|--------|----------|
| Awkward Potion | Any Lily Flower | Repellent Potion I | 5 minutes |
| Repellent Potion I | Redstone Dust | Repellent Potion II | 15 minutes |

### 10.2 Instant Death Potion

| Base | Ingredient | Result |
|------|------------|--------|
| Awkward Potion | Black Flower | Potion of Instant Death |

lingering varient?
---

## 11. Suspicious Stew Effects

### 11.1 Colored Flower Stews

| Flower | Effect | Duration | Description |
|--------|--------|----------|-------------|
| **White Lily Flower** | Strength | 8 seconds | Increases melee damage |
| **Pink Lily Flower** | Absorption | 12 seconds | Adds 2 temporary hearts |
| **Yellow Lily Flower** | Speed | 10 seconds | Increases movement speed |
| **Purple Lily Flower** | Water Breathing | 8 seconds | Allows breathing underwater |
| **Golden Lily Flower** | Invisibility | 15 seconds | Makes player invisible to mobs |
| **Black Lily Flower** | Instant Death | Instant | 5% chance to kill instantly, 95% chance for large damage |

---

### 11.2 Special Stews

| Stew | Ingredients | Effect | Duration |
|------|-------------|--------|----------|
| **Floral Medley Stew** | White + Pink + Yellow + Purple Flowers + Bowl + Red Mushroom + Brown Mushroom | Strength + Absorption + Speed + Water Breathing | 15 seconds (all effects) |

---

### 11.3 Effect Details

| Effect | Vanilla Equivalent | Notes |
|--------|-------------------|-------|
| Strength | Potion of Strength | +3 melee damage |
| Absorption | Golden Apple | +2 temporary hearts |
| Speed | Potion of Swiftness | +20% movement speed |
| Water Breathing | Potion of Water Breathing | No drowning damage |
| Invisibility | Potion of Invisibility | Mobs don't see player |
| Instant Death | Custom Effect | 5% kill / 95% large damage (players), 50% kill / 50% large damage (mobs), 100% large damage (immune mobs) |

---

### 11.4 Crafting Method (Shapeless)

All suspicious stews are crafted using the same shapeless recipe pattern:

| Slot | Item |
|------|------|
| Any | Red Mushroom |
| Any | Brown Mushroom |
| Any | Bowl |
| Any | Lily Flower (any type) |

**Result:** 1 Suspicious Stew with effect matching the flower used

**Floral Medley Stew Recipe:**
| Slot | Item |
|------|------|
| Any | Red Mushroom |
| Any | Brown Mushroom |
| Any | Bowl |
| Any | White Lily Flower |
| Any | Pink Lily Flower |
| Any | Yellow Lily Flower |
| Any | Purple Lily Flower |

**Result:** 1 Suspicious Stew with all four effects for 15 seconds

---

### 11.5 Instant Death Effect Details

| Target | Instant Death Chance | Instant Damage Chance |
|--------|---------------------|----------------------|
| Player | 5% | 95% |
| Regular Mobs | 50% | 50% |
| Ender Dragon | 0% | 100% |
| Wither | 0% | 100% |
| Warden | 0% | 100% |

**Instant Damage:** Large amount of damage (similar to harming potion II)

---

## 12. Particle Effects

### 12.1 Particle Types

| Particle ID | Description | Color | Spawn Conditions |
|-------------|-------------|-------|------------------|
| `lily_update:green_upward` | Flower regrowth | Green | Natural regrowth, bone meal success |
| `lily_update:firefly` | Firefly | Varies by pad | Nighttime on pads (density-based) |
| `lily_update:brown_particle` | Bone meal failure | Brown | Bone meal failure |
| `lily_update:transformation` | Pad transformation | Gold | Golden pad shearing |
| `lily_update:splash_particle` | Boat/water break | White | Boat collision, water flow break |
| `lily_update:lava_splash` | Lava break | Orange/Red | Boat on lava, lava flow break |
| `lily_update:magma_spawn` | Magma cube spawn | Orange | Black pad magma generation |

---

## 13. Achievements (50 Total)

| ID | Name | Description | Requirement |
|----|------|-------------|-------------|
| `floral_diversity` | Floral Diversity | Collect all 4 colored water flowers | Have white, pink, yellow, purple flowers in inventory |
| `rare_bloom` | Rare Bloom | Find your first purple flower | Obtain purple lily flower |
| `floral_collector` | Floral Collector | Collect 10 of each colored water flower | Have 10 of each white, pink, yellow, purple flowers |
| `master_gardener` | Master Gardener | Propagate a purple water pad | Purple pad spawns another purple pad |
| `full_moon_bloom` | Full Moon Bloom | Witness a full moon with 5+ spreading pads | Be present during full moon with 5+ pads |
| `garden_designer` | Garden Designer | Maintain optimal density for 5 days | Keep 40-60% occupancy for 5 days |
| `cosmetic_florist` | Cosmetic Florist | Create cosmetic pads in all 4 colors | Create white, pink, yellow, purple cosmetic pads |
| `firefly_haven` | Firefly Haven | Achieve dense firefly density | Reach 75%+ occupancy in 9×9 area |
| `deep_sea_gardener` | Deep Sea Gardener | Attract glow squid with purple pad | Place purple pad below Y=30, spawn glow squid |
| `open_water_gardener` | Open Water Gardener | Place pad that spawns fish | Pad surrounded by 8 water, 3 deep, spawns fish |
| `master_chef` | Master Chef | Craft all 4 colored suspicious stews | Craft white, pink, yellow, purple stews |
| `gilded_gardener` | Gilded Gardener | Craft a golden lily pad | Craft golden lily pad |
| `dolphin_friend` | Dolphin Friend | Spawn dolphins from golden pad | Golden pad spawns dolphins |
| `invisible_chef` | Invisible Chef | Craft golden suspicious stew | Craft golden stew |
| `alchemist` | Alchemist | Smelt golden item back to gold nugget | Smelt golden pad or flower |
| `golden_harvest` | Golden Harvest | Shear golden pad to collect flower | Shear golden pad with flower |
| `vanilla_spreader` | Vanilla Spreader | Propagate golden pad to produce vanilla | Golden pad spawns vanilla lily pad |
| `lucky_fisherman` | Lucky Fisherman | Spawn fish from colored pad | 20% chance success |
| `rare_sight` | Rare Sight | Spawn dolphins from golden pad | 5% chance success |
| `master_trader` | Master Trader | Purchase golden lily flower | Buy from Master Fisherman |
| `green_thumb` | Green Thumb | Regrow flower with bone meal | 25% chance success |
| `boat_buster` | Boat Buster | Break pad with boat | Hit spreading pad with boat |
| `hand_breaker` | Hand Breaker | Break a lily pad by hand | Break any lily pad without tools |
| `water_flow_breaker` | Water Flow Breaker | Break a water lily pad with flowing water | Water flows over water lily pad |
| `lava_flow_breaker` | Lava Flow Breaker | Break a lava lily pad with flowing lava | Lava flows over lava lily pad |
| `piglin_trader` | Piglin Trader | Barter with Piglin using golden item | Give golden item to Piglin |
| `lucky_propagation` | Lucky Propagation | Get spreading pad from colored pad | 5% chance success |
| `phantom_repellent` | Phantom Repellent | Brew Repellent Potion I | Craft repellent potion |
| `extended_protection` | Extended Protection | Brew Repellent Potion II | Upgrade with redstone |
| `wandering_customer` | Wandering Customer | Buy from Wandering Trader | Purchase any lily item |
| `night_glow` | Night Glow | See flowering pad emit light | Witness light level 7 emission |
| `water_flow` | Water Flow | Break pad with flowing water | Water flows over pad |
| `into_the_nether` | Into the Nether | Find lava lily pad in Nether | Locate natural lava lily pad |
| `black_bloom` | Black Bloom | Find black lily pad with flower | Locate natural black pad with flower |
| `instant_death` | Instant Death | Brew Potion of Instant Death | Craft with black flower |
| `forbidden_stew` | Forbidden Stew | Craft black suspicious stew | Craft with black flower |
| `lava_frog_friend` | Lava Frog Friend | Find lava frog in Nether | Locate lava frog |
| `tadpole_in_lava` | Tadpole in Lava | Watch tadpole grow into adult | Witness lava tadpole maturation |
| `lava_froglight` | Lava Froglight | Obtain lava froglight | Frog eats magma cube |
| `magma_farmer` | Magma Farmer | Spawn magma cubes from black pad | Player-placed pad spawns magma |
| `nether_gardener` | Nether Gardener | Propagate black lily pad | Black pad spawns new pad |
| `pottery_collection` | Pottery Collection | Place all flowers in pots | All 6 flowers in flower pots |
| `bee_killer` | Bee Killer | Kill bee with black flower | Attempt breeding with black flower |
| `death_from_above` | Death from Above | Kill mob with instant death arrow | Arrow kills mob |
| `lava_walker` | Lava Walker | Walk on lava using lava lily pad | Stand on lava lily pad |
| `golden_barter` | Golden Barter | Obtain black lily pad from bartering | 5% chance success |
| `lava_spreader` | Lava Spreader | Black pad produces lava lily pad | 95% chance success |
| `cosmetic_toggle` | Cosmetic Toggle | Create a cosmetic lily pad | Toggle `is_cosmetic` property on any pad |
| `fire_charge_breeder` | Fire Charge Breeder | Breed lava frogs | Use fire charges |
| `lava_surround` | Lava Surround | Find pad surrounded by 8 lava | Natural spawn condition |
| `rare_nether_bloom` | Rare Nether Bloom | Find natural black pad | Rare Nether generation |

---

## 14. Technical Implementation

### 14.1 Unified Block Definition Template

```json
{
  "format_version": "1.20.0",
  "minecraft:block": {
    "description": {
      "identifier": "lily_update:white_lily_pad",
      "properties": {
        "lily_update:has_flower": [true, false],
        "lily_update:is_cosmetic": [true, false],
        "lily_update:is_natural": [true, false]
      }
    },
    "components": {
      "minecraft:collision_box": {
        "origin": [-8, 0, -8],
        "size": [16, 1, 16]
      },
      "minecraft:selection_box": {
        "origin": [-8, 0, -8],
        "size": [16, 1, 16]
      },
      "minecraft:flammable": false,
      "minecraft:destructible_by_mining": {
        "seconds_to_destroy": 0.2
      },
      "minecraft:destructible_by_explosion": {
        "explosion_resistance": 0
      },
      "minecraft:light_emission": {
        "condition": "query.block_property('lily_update:has_flower') == true && query.block_property('lily_update:is_cosmetic') == false",
        "value": 7
      },
      "minecraft:placement_filter": {
        "conditions": [
          {
            "block_filter": ["minecraft:water"],
            "allowed_faces": ["up"]
          }
        ]
      },
      "minecraft:on_interact": {
        "condition": "query.get_equipped_item_name == 'minecraft:shears' && query.block_property('lily_update:has_flower') == true",
        "event": "shear_flower"
      }
    },
    "events": {
      "shear_flower": {
        "run_command": {
          "command": [
            "playsound random.sheep @a ~ ~ ~",
            "particle lily_update:green_upward ~ ~0.5 ~ 0 0 0 0.5 10",
            "give @p lily_update:white_flower",
            "setblock ~ ~ ~ lily_update:white_lily_pad[\"lily_update:has_flower\"=false,\"lily_update:is_cosmetic\"=query.block_property('lily_update:is_cosmetic'),\"lily_update:is_natural\"=query.block_property('lily_update:is_natural')]"
          ]
        }
      }
    }
  }
}
```

---

### 14.2 Lava Block Placement Filter

```json
{
  "minecraft:placement_filter": {
    "conditions": [
      {
        "block_filter": ["minecraft:lava"],
        "allowed_faces": ["up"]
      }
    ]
  }
}
```

---

### 14.3 Water Flow Break Logic

```javascript
function onWaterFlow(padLocation, dimension) {
    const pad = dimension.getBlock(padLocation);
    const padType = pad.typeId;
    
    Check if pad is a water lily pad (not lava)
    if (padType === "lily_update:lava_lily_pad" || padType === "lily_update:black_lily_pad") {
        return; Lava pads don't break from water
    }
    
    Drop appropriate item
    dropLilyPadItem(pad, padLocation, dimension);
    
    Remove pad
    dimension.runCommand(`setblock ${padLocation.x} ${padLocation.y} ${padLocation.z} air destroy`);
    
    Spawn particles
    dimension.spawnParticle("lily_update:splash_particle", padLocation);
}
```

---

### 14.4 Lava Flow Break Logic

```javascript
function onLavaFlow(padLocation, dimension) {
    const pad = dimension.getBlock(padLocation);
    const padType = pad.typeId;
    
    Check if pad is a lava lily pad
    if (padType !== "lily_update:lava_lily_pad" && padType !== "lily_update:black_lily_pad") {
        return; Water pads don't break from lava
    }
    
    Drop appropriate item
    dropLilyPadItem(pad, padLocation, dimension);
    
    Remove pad
    dimension.runCommand(`setblock ${padLocation.x} ${padLocation.y} ${padLocation.z} air destroy`);
    
    Spawn particles
    dimension.spawnParticle("lily_update:lava_splash", padLocation);
}
```

---

### 14.5 Propagation Logic

```javascript
function canPropagate(parentPad, location, dimension) {
    Check if pad can propagate
    if (parentPad.permutation.getState("lily_update:is_cosmetic")) return false;
    
    Check density limit
    const radius = 4;
    let totalBlocks = 0;
    let occupiedBlocks = 0;
    
    for (let x = -radius; x <= radius; x++) {
        for (let z = -radius; z <= radius; z++) {
            totalBlocks++;
            const blockPos = {x: location.x + x, y: location.y, z: location.z + z};
            const block = dimension.getBlock(blockPos);
            
            if (!block || (block.typeId !== "minecraft:water" && block.typeId !== "minecraft:lava")) {
                occupiedBlocks++;
            } else {
                const aboveBlock = dimension.getBlock({...blockPos, y: blockPos.y + 1});
                if (aboveBlock && aboveBlock.typeId.includes("lily_update") || aboveBlock.typeId === "minecraft:lily_pad") {
                    occupiedBlocks++;
                }
            }
        }
    }
    
    return (occupiedBlocks / totalBlocks) < 0.75;
}

function getOffspringType(parentPad) {
    const parentType = parentPad.typeId;
    const isCosmetic = parentPad.permutation.getState("lily_update:is_cosmetic");
    
    Cosmetic pads don't propagate
    if (isCosmetic) return null;
    
    if (parentType === "lily_update:golden_lily_pad") {
        return "minecraft:lily_pad";
    }
    
    if (parentType.includes("_lily_pad") && 
        parentType !== "lily_update:lava_lily_pad" && 
        parentType !== "lily_update:black_lily_pad") {
        const rand = Math.random() * 100;
        if (rand < 95) {
            return "minecraft:lily_pad";
        } else {
            return parentType;
        }
    }
    
    if (parentType === "lily_update:black_lily_pad") {
        const rand = Math.random() * 100;
        if (rand < 95) {
            return "lily_update:lava_lily_pad";
        } else {
            return "lily_update:black_lily_pad";
        }
    }
    
    return null;
}
```

---

### 14.6 Instant Death Effect Logic

```javascript
function applyInstantDeathEffect(target, isPotion) {
    Check immunities
    if (target.typeId === "minecraft:ender_dragon" ||
        target.typeId === "minecraft:wither" ||
        target.typeId === "minecraft:warden") {
        target.applyDamage(12); Instant damage
        return;
    }
    
    Check if player
    if (target.typeId === "minecraft:player") {
        const rand = Math.random() * 100;
        if (rand < 5) {
            target.kill(); Instant death
        } else {
            target.applyDamage(12); Instant damage
        }
        return;
    }
    
    Regular mobs
    const rand = Math.random() * 100;
    if (rand < 50) {
        target.kill(); Instant death
    } else {
        target.applyDamage(12); Instant damage
    }
}
```

---

### 14.7 Lava Frog Logic

```javascript
function onLavaFrogEatMagmaCube(frog, magmaCube) {
    Kill magma cube
    magmaCube.kill();
    
    Spawn lava froglight
    frog.dimension.spawnItem("lily_update:lava_froglight", frog.location);
    
    Play sound
    frog.dimension.playSound("entity.frog.eat", frog.location);
}

function onLavaFrogBreed(frog1, frog2) {
    if (frog1.getComponent("minecraft:breedable").canBreed &&
        frog2.getComponent("minecraft:breedable").canBreed) {
        
        Find lava source nearby
        const lavaBlock = findLavaSource(frog1.location, 5);
        if (lavaBlock) {
            Place lava frogspawn
            frog1.dimension.spawnEntity("lily_update:lava_frogspawn", lavaBlock.location);
        }
    }
}
```

---

### 14.8 Magma Cube Spawn Logic

```javascript
function trySpawnMagmaCube(padLocation, pad, dimension) {
    Only player-placed black pads
    if (pad.typeId !== "lily_update:black_lily_pad") return false;
    if (pad.permutation.getState("lily_update:is_natural")) return false;
    if (pad.permutation.getState("lily_update:is_cosmetic")) return false;
    if (!pad.permutation.getState("lily_update:has_flower")) return false;
    
    10% chance every 60 seconds
    if (Math.random() < 0.10) {
        const count = Math.floor(Math.random() * 3) + 1; 1-3
        for (let i = 0; i < count; i++) {
            Spawn small magma cube nearby
            dimension.spawnEntity("minecraft:magma_cube", {
                x: padLocation.x + (Math.random() - 0.5) * 2,
                y: padLocation.y + 1,
                z: padLocation.z + (Math.random() - 0.5) * 2
            });
        }
        dimension.spawnParticle("lily_update:magma_spawn", padLocation);
        return true;
    }
    return false;
}
```

---

## 15. Balance & Balancing

### 15.1 Rarity Distribution

| Item | Rarity | Spawn Chance |
|------|--------|--------------|
| White Flower | Common | 45% |
| Pink Flower | Common | 30% |
| Yellow Flower | Uncommon | 15% |
| Purple Flower | Rare | 10% |
| Black Flower | Rare | 10% (Nether only) |
| Golden Flower | N/A | Craft only |

---

### 15.2 Economic Values

| Item | Fisherman Buy Price | Fisherman Sell Price | Wandering Trader Price |
|------|---------------------|----------------------|------------------------|
| White Flower | 2 for 1 Emerald | - | 1 Emerald each |
| Pink Flower | 2 for 1 Emerald | - | 1 Emerald each |
| Yellow Flower | 2 for 1 Emerald | - | 1 Emerald each |
| Purple Flower | 2 for 1 Emerald | - | 2 Emeralds each |
| Golden Flower | - | 2 Emeralds | 4 Emeralds each |
| Black Flower | - | - | 3 Emeralds each |
| Vanilla Lily Pad | 5 for 1 Emerald | - | - |
| White Lily Pad | - | - | 2 Emeralds |
| Pink Lily Pad | - | - | 2 Emeralds |
| Yellow Lily Pad | - | - | 2 Emeralds |
| Purple Lily Pad | - | - | 2 Emeralds |
| Golden Lily Pad | - | - | 5 Emeralds |
| Lava Lily Pad | - | - | 2 Emeralds |
| Black Lily Pad | - | - | 4 Emeralds |

---

### 15.3 Spawn Chances Summary

| Spawn Type | Chance | Quantity | Frequency |
|------------|--------|----------|-----------|
| Fish (water pads) | 20% | 2-3 fish | Every 60 seconds |
| Dolphins (golden pads) | 5% | 1-2 dolphins | Every 60 seconds |
| Magma Cubes (black pads) | 10% | 1-3 magma cubes | Every 60 seconds |
| Flower Regrowth (normal night) | 25% | 1 flower | Per pad per night |
| Flower Regrowth (full moon) | 100% | 1 flower | Per pad per night |
| Bone Meal Regrowth | 25% | 1 flower | Per use |
| Golden Crafting | 100% | 1 golden item | Per craft |
| Piglin Barter Bonus | 5% | 1 black lily pad | Per barter |

---

### 15.4 Propagation Rates

| Pad Type | Normal Night | Full Moon |
|----------|--------------|-----------|
| Colored Water Pad | 25% per eligible block | 1-3 new pads |
| Golden Water Pad | 25% per eligible block | 1-3 new pads |
| Black Lava Pad | 25% per eligible block | 1-3 new pads |

**Offspring Distribution:**
| Parent | Offspring |
|--------|-----------|
| Colored Water Pad | 95% Vanilla / 5% Same Color |
| Golden Water Pad | 100% Vanilla |
| Black Lava Pad | 95% Lava Lily Pad / 5% Black Lily Pad |

---

### 15.5 Light Levels

| Block | Light Level |
|-------|-------------|
| Flowering Water Pad | 7 |
| Flowering Golden Pad | 7 |
| Lava Froglight | 15 |
| All Other Lily Pads | 0 |

---

### 15.6 Damage Values

| Damage Source | Amount | Notes |
|---------------|--------|-------|
| Instant Damage (Potion/Arrow) | 12 damage (6 hearts) | Large damage |
| Instant Death (Player) | Instant kill | 5% chance |
| Instant Death (Regular Mob) | Instant kill | 50% chance |
| Instant Death (Immune Mob) | 12 damage | 100% chance |

---

## 16. Summary Table

| Category | Variants | Key Features |
|----------|----------|--------------|
| **Water Lily Pads** | 5 (White, Pink, Yellow, Purple, Golden) | Propagation, fish spawning, dolphin spawning, light emission, fireflies |
| **Lava Lily Pads** | 2 (Lava, Black) | Lava placement, propagation (black only), magma cube generation, red fireflies, immune to fire |
| **Flowers** | 6 (White, Pink, Yellow, Purple, Golden, Black) | Dyes, suspicious stews, potions, flower pots, bee interactions |
| **Potions** | 4 | Repellent I (5 min), Repellent II (15 min), Instant Death, Arrow (5% player kill) |
| **Suspicious Stews** | 6 | Strength, Absorption, Speed, Water Breathing, Invisibility, Instant Death |
| **Lava Frog** | 1 | Lava lifecycle, breeds with fire charges, lava froglight drop |
| **Piglin Bartering** | 5% chance | Black Lily Pad from golden items |
| **Spawn Conditions** | 8 lava source blocks | Lava and black lily pads require full lava surround to spawn naturally |
| **Golden Crafting** | Water only | Black variants cannot be crafted into golden variants |
| **Achievements** | 50 | All progression milestones |

---